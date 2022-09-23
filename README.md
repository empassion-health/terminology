[![Apache License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) ![dbt logo and version](https://img.shields.io/static/v1?logo=dbt&label=dbt-version&message=1.x&color=orange)

# Terminology

This is the Tuva Project's Terminology Repository, a single source of truth for all terminology datasets used and maintained by the Tuva Project.  For more detailed information and a summary of all terminology datasets that ship with the Tuva Project, check out our [Terminlogy Docs site](https://thetuvaproject.com/docs/terminology).


Knowledge Base:
- Check out the [catalog](https://thetuvaproject.com/docs/terminology) of all terminology sets included in this repository

## Getting Started
Complete the following steps to configure the package to run in your environment.

1. [Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) this repo to your local machine or environment
2. Create a database to load terminology to, if it does not already exist.
3. Optional: Custom database/schema targets can be configured in the [dbt_project.yml](./dbt_project.yml) file
    - Fill in vars (variables):
        - **output_database** - database where terminology data set will be loaded.  default: `tuva`
        - **output_schema** - database where terminology data set will be loaded.  default: `terminology`
    - Alternatively, custom variables can be passed at the command line. See step 5 for more detail
4. Optional: Individual seed files can be disabled 
    - Add `enabled: false` to the `config:` section of any unwanted terminology set in [properties.yml](./terminology/properties.yml).
    - See the [dbt documentation](https://docs.getdbt.com/reference/seed-configs) for more detail and other configuration options.
5. Execute `dbt seed` to load all terminology files
    - To load a single seed file, use syntax like `dbt seed --select gender.csv`
    - To overwrite the database or schema configurations in [dbt_project.yml](./dbt_project.yml), use syntax like `dbt seed --vars '{output_database: tuva_test, output_schema: terminology_test}'`
    - See the [dbt documentation](https://docs.getdbt.com/reference/global-configs#command-line-flags) for more detail

