![Build Status](https://github.com/stasSajin/dbt-example/workflows/Build%20Status/badge.svg)
[![Netlify Status](https://api.netlify.com/api/v1/badges/7092003d-6c54-49e7-9a8c-a8235617cf1b/deploy-status)](https://app.netlify.com/sites/dbtexample/deploys)

# Purpose

The purpose of this repo is to showcase and explain the following:

* How to structure a DBT project.
* How to set up a CI/CD pipeline for DBT.
* How to share the DBT documentation for your project.

## Description of example

For the purposes of testing the project, I set up a micro PostgresSQL instance on AWS. Ideally, you would have your own instance.

## Pipeline Steps:

![](images/pipeline_steps.png)


### On Pull Requests
* First, the CI environment sets up all the dependencies.
* Run `dbt test` against your `sources` only. Note that we run tests for sources only because it allows us to verify the data integrity before we generate new models. In this context, a source is a table or collection of tables that get dumped into by the DB by some outside ETL system (e.g., Airflow, Dagster, Snowpipe, DMS, etc).
* Run `dbt run --target ci`. Ideally, the CI/CD environment will only run models that have been modified. DBT currently does not have this built out of the box. Note that this will not affect the production schema and the output of all the models will be available only to people who have access to dveelopment schema
* Run




## More information
What is dbt?
Read the dbt viewpoint
Installation
Join the chat on Slack for live questions and support.
