

**DBT** ([Data Build Tool](https://www.getdbt.com/)) for Transforming the Data..

### Installation Process

- Clone the [Repository](https://github.com/getsurance/Mandrill)

On the new machine or environment.
Navigate to the cloned repo directory. Create a new virtual environment:

    $ python -m venv venv_name

Activate the virtual environment:

On MacOS and Linux:

    $ . venv_name/bin/activate

On Windows: 

    .\venv_name\Scripts\activate

Install Dependencies from **requirements.txt**

With the virtual environment activated, run:

    pip install -r requirements.txt

> Initialize the Python Bridge (If Applicable)

Upgrade both dbt and the Snowflake adapter to their latest versions, or ensure they are at versions known to be compatible.

    pip install dbt --upgrade
    pip install dbt-snowflake --upgrade

> We need to configure dbt(profiles.yml) in ~/.dbt/

- To create this 

Windows

    mkdir %USERPROFILE%\.dbt

Mac

    mkdir ~/.dbt/

To setup **profiles.yml** the connections and details exist in these file [refer here](https://docs.getdbt.com/docs/core/connect-data-platform/snowflake-setup)

    my-snowflake-db:
    target: dev
    outputs:
        dev:
            type: snowflake
            account: [account id]

            # User/password auth
            user: [username]
            password: [password]

            role: [user role]
            database: [database name]
            warehouse: [warehouse name]
            schema: [dbt schema]
            threads: [1 or more]
            client_session_keep_alive: False
            query_tag: [anything]

            # optional
            connect_retries: 0 # default 0
            connect_timeout: 10 # default: 10
            retry_on_database_errors: False # default: false
            retry_all: False  # default: false
            reuse_connections: False # default: false (available v1.4+)
        
To Check it whether if its configured or not by using these commands once you are in the project folder.
For more info [refer here](https://docs.getdbt.com/docs/core/connect-data-platform/connection-profilesl)

To check the connection between connector and dbt project

    $ dbt debug 
    $ dbt debug --config-dir
    
To view your profiles.yml file, run:

Windows

    start C:\Users\user_profile\.dbt  

Mac

    open /Users/user_profile/.dbt

Initialize dbt Project:

Sometimes, re-initializing the dbt project can help resolve issues. **Navigate to your project directory and run**:

    dbt deps

> If your dbt project or any other tool you're using requires a Python bridge or some specific initialization, ensure you perform that step.

### DBT Power User(Used for better experience and executing Queries)

- Update the **vscode-dbt-power-user** extension to the latest version, if available. The issue might have been identified and fixed in a newer release.
- Check the installation settings in the dbt power user and update **settings.json** in VS code
  (you need to do this in order to have query results in VS code for the respective model) 

### How we can start the project 

Try running the following commands: [For more commnads](https://docs.getdbt.com/docs/introduction)

    
    $ dbt run                              # to run all the models

    $ dbt run --select model_name          # to run a specific model 

    $ dbt test                             # Executes the tests you defined for your project


### Creating Models

Under Models folder:

- **dim**: represents that tables/models that will be published to the snowflake.
- **src**: represents a source table which acts as intermediatory tables to dim folder tables

### 


### Resources:
- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
- Check out [Discourse](https://discourse.getdbt.com/) for commonly asked questions and answers
- Join the [chat](https://community.getdbt.com/) on Slack for live discussions and support
- Find [dbt events](https://events.getdbt.com) near you
- Check out [the blog](https://blog.getdbt.com/) for the latest news on dbt's development and best practices