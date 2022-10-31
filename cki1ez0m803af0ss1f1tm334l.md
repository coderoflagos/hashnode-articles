# Introduction to dbt

[dbt](https://www.getdbt.com/) means Data Build Tool. It sounds simple, but it means a lot, especially to data scientists. It is a tool that is used by data scientists and data engineers to transform data in their warehouses by writing simple SQL select statements. You write a select statement or set of related select statements and dbt handles the work of building the tables and views from them.

## What do data scientists use dbt for?
Data scientists use dbt to transform data in their warehouses by writing SQL select statements and [Jinja](https://palletsprojects.com/p/jinja/). Jinja is a templating engine built for Python. In dbt, you combine your SQL with Jinja to add things like if-statements and for-loops to your SQL and to do more advanced things like build one query based-off the results of another.

## Why use dbt instead of your warehouse’s SQL editor?
dbt’s primary function is to take a model, compile it to SQL, and then run it against your data warehouse. You can do a lot of this in your data warehouse’s SQL editor too, but, with dbt, you don’t have to create any tables or views or worry about the order you run your SQL statements. dbt handles all of that.

## What’s in a dbt project?
*   **A project file:** A file named `dbt_project.yml`. It is your project configuration file. This file does a lot of things, including change your model materializations, build schemas, and apply tags.
*   **A model:** A model is a .sql file. Each model has a single select statement. Each project must have at least one model, but can have as many as you need. You create a dependent acyclical model (DAG) to determine the order that the models in a project are run.

### Materializations
Materializations are a way for building dbt models on a warehouse. There are four types of materializations built into dbt. They are:
*   **Table:** The model is rebuilt on your warehouse as a table each time it is run.
*   **View:** The model is rebuilt on your warehouse as a view each time it is run.
*   **Incremental:** The new records in the model are inserted or updated into a table in your warehouse each time it is run.
*   **Ephemeral:** These models are not directly built on your warehouse. They query and make available data that you only need for other models. dbt includes ephemeral models in the other models that depend on them.


To make full use of dbt, you need to know SQL. It may also be beneficial to know some programming basics, such as for-loops and if-statements, to use Jinja effectively in your models.

I learned a lot about dbt writing this, and if you want to learn about dbt too, go check out [getdbt.com](https://www.getdbt.com/), [dbt's Docs site](https://docs.getdbt.com/docs/introduction), and [dbt’s getting started guide](https://docs.getdbt.com/tutorial/setting-up/).

Thanks for taking out your time to read this short article.

## Here are the sources I used to write this:
*   [https://docs.getdbt.com/docs/introduction](https://docs.getdbt.com/docs/introduction)
*   [https://docs.getdbt.com/docs/building-a-dbt-project/jinja-macros](https://docs.getdbt.com/docs/building-a-dbt-project/jinja-macros)
*   [https://docs.getdbt.com/reference/dbt_project.yml](https://docs.getdbt.com/reference/dbt_project.yml)
*   [https://docs.getdbt.com/docs/building-a-dbt-project/projects/](https://docs.getdbt.com/docs/building-a-dbt-project/projects/)
*   [https://docs.getdbt.com/docs/building-a-dbt-project/building-models](https://docs.getdbt.com/docs/building-a-dbt-project/building-models)
*   [https://docs.getdbt.com/docs/building-a-dbt-project/building-models/materializations](https://docs.getdbt.com/docs/building-a-dbt-project/building-models/materializations)