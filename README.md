DBT for Transforming the Data.

### Installation Process

On the new machine or environment, clone the repo as usual.
Set Up a Virtual Environment

Navigate to the cloned repo directory. Create a new virtual environment:

    $ python -m venv venv_name

Activate the virtual environment:

On MacOS and Linux:

    $ . venv_name/bin/activate

On Windows: 

    .\venv_name\Scripts\activate

Install Dependencies from requirements.txt

With the virtual environment activated, run:

    pip install -r requirements.txt

> Initialize the Python Bridge (If Applicable)

Upgrade both dbt and the Snowflake adapter to their latest versions, or ensure they are at versions known to be compatible.

    pip install dbt --upgrade
    pip install dbt-snowflake --upgrade

Initialize dbt Project:

Sometimes, re-initializing the dbt project can help resolve issues. **Navigate to your project directory and run**:

    dbt deps



> If your dbt project or any other tool you're using requires a Python bridge or some specific initialization, ensure you perform that step.

### DBT Power User(Used for better experience and executing Queries)

- Update the **vscode-dbt-power-user** extension to the latest version, if available. The issue might have been identified and fixed in a newer release.

### Using the starter project

Try running the following commands:

    dbt run
    dbt test


### Creating Models

Under Models folder:
- dim: represents that tables/models that will be published to the snowflake.
- src: represents a source table which acts as intermediatory tables to dim folder tables

### 


### Resources:
- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
- Check out [Discourse](https://discourse.getdbt.com/) for commonly asked questions and answers
- Join the [chat](https://community.getdbt.com/) on Slack for live discussions and support
- Find [dbt events](https://events.getdbt.com) near you
- Check out [the blog](https://blog.getdbt.com/) for the latest news on dbt's development and best practices
