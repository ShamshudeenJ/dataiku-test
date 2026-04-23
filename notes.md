# Dataiku

## Introduction
* Projects can be import/exported


### Installation of Dataiku DSS on Docker
```shell
docker pull dataiku/dss
cd dir
docker run -p 10000:10000 -d dataiku/dss
```

Open http://localhost:10000


## Components
* Project
* Flow: Visual narrative of data journey
* Dataset: Piece of data in tabular format; Each column is of same storage type. Represented as square.
* Recipe - Has multiple Steps. Can be Visual, code and plugins. Represented as Circle. Has optional pre and post filter.
  * **Prepare** data has date conversion, formulas and Regex
  * **Joins**: Left, right, inner, outer, fuzzy, geo
  * **Group**: key and aggregators
  * **Window**: definition and aggregation
  * **Sort**
  * **Top N**
  * **Pivot**
  * **Filter**: condition or formaula or SQL expresion
  * **Sample**: first records or random or Column subset or Class rebalance
  * **Distinct**: remove duplicates(all) or distinct based on subset of columns
  * **Stack** (Append two or more data): Union or Intersection or Use schema or Use column order or Manual remap or Custom schema.
  * **Split**: Map values on single column or Random or Filters or Dispatch percentile
  * **Sync** (Copy a dataset): Free output schema or Maintain strict schema
* Connectors

## Dataiku Cloud
* **Launchpad** is the administrative hub
* Spaces
    - Nodes: Design, Automation, API and Govern nodes.


## Collaboration
* **Tags**: Universal property; can be added to all elements of the project
* **Discussions**: Integrated chat
* **Workspace** to organize and centralize shared resources
* **Libraries** : sharing code
* **Wikis**
* **Data catalog**: Look for existing works; share dataset.
* **Feature store**: Discover and re use features and curated dataset
* **Dashboards** : Publish elements(tables, chart) of a project 

## Data Connections
* Move data to SQL db through recipe: `Sync, Prepare and Python`
* For dataset / Charts: Execution engine = `In-database` is faster than `DSS engine`
* SQL notebooks to leverage SQL engine for in-database computations

## Variables
* Types
  - Instance level Global variables (DSS settings / variables)
  - Project level
  - Scenario level
* Used in Visual recipes, scenarios, code recipes and dataiku applications
* Defined as **JSON** object
* Used as `${var_name}` (use `''` for string variables)




### Check Dataiku version
```bash
[dataiku@caab3f984721 ~]$ ls
dataiku-dss-14.4.1  dss  run.sh
[dataiku@caab3f984721 ~]$ cd dss/
[dataiku@caab3f984721 dss]$ ls
R.lib          bin        config         databases         html-apps        instance-id.txt  lib               managed_folders          notebook_results  pyenv         timelines           uploads
ai-assistants  caches     cost-limiting  dss-version.json  install-support  jobs             local             model_evaluation_stores  plugins           run           tmp                 workload-folders
analysis-data  code-envs  data-catalog   exports           install.ini      jupyter-run      managed_datasets  most-used-datasets       privtmp           saved_models  unified-monitoring
[dataiku@caab3f984721 dss]$ cat dss-version.json
{
  "conf_version": "14400",
  "product_version": "14.4.1",
  "product_commitid": ""
}[dataiku@caab3f984721 dss]$
```
