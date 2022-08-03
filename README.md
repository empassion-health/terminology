[![Apache License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) ![dbt logo and version](https://img.shields.io/static/v1?logo=dbt&label=dbt-version&message=1.x&color=orange)

# Terminology

This repo is the source of truth for all terminology datasets maintained in the Tuva Project.  For a complete summary of all terminology datasets that ship with the Tuva Project, check out the Terminology Datasets tab in [Tuva Data Models](https://docs.google.com/spreadsheets/d/1NuMEhcx6D6MSyZEQ6yk0LWU0HLvaeVma8S-5zhOnbcE/edit?usp=sharing).

For more info about the Tuva Project check out our [docs](http://thetuvaproject.com/)

To see what we're building next, take a look at our [Virtual Roadmap](https://miro.com/app/board/uXjVOxvjM5o=/)

## Getting Started
Complete the following steps to configure the package to run in your environment.

1. [Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) this repo to your local machine or environment
2. Create a database called `tuva` in your data warehouse
    - Note: this is optional, the terminology dataset can be loaded into an existing database with any name.  See steps 3 and 5 for how to configure non-default database names
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

## Terminology Datasets

| Dataset                                                                                                    | Maintaining Organization           | Last Updated |
|------------------------------------------------------------------------------------------------------------|------------------------------------|--------------|
| [acute diagnosis ccs](.\terminology\acute_diagnosis_ccs.csv)                                               | QualityNet                         | 4/19/2022    | 
| [acute diagnosis icd 10 cm](.\terminology\acute_diagnosis_icd_10_cm.csv)                                   | QualityNet                         | 4/19/2022    | 
| [admit source](.\terminology\admit_source.csv)                                                             | National Uniform Billing Committee | 4/19/2022    | 
| [admit type](.\terminology\admit_type.csv)                                                                 | National Uniform Billing Committee | 4/19/2022    | 
| [always planned ccs diagnosis category](.\terminology\always_planned_ccs_diagnosis_category.csv)           | QualityNet                         | 4/19/2022    | 
| [always planned ccs procedure category](.\terminology\always_planned_ccs_procedure_category.csv)           | QualityNet                         | 4/19/2022    | 
| [chronic conditions](.\terminology\chronic_conditions.csv)                                                 | CMS                                | 6/22/2022    | 
| [code type](.\terminology\code_type.csv)                                                                   | Tuva                               | 4/19/2022    | 
| [discharge disposition](.\terminology\discharge_disposition.csv)                                           | National Uniform Billing Committee | 4/19/2022    | 
| [encounter type](.\terminology\encounter_type.csv)                                                         | Tuva                               | 6/17/2022    | 
| [exclusion ccs diagnosis category](.\terminology\exclusion_ccs_diagnosis_category.csv)                     | QualityNet                         | 4/19/2022    | 
| [gender](.\terminology\gender.csv)                                                                         | Tuva                               | 4/19/2022    | 
| [hcpcs level 2](.\terminology\hcpcs_level_2.csv)                                                           | CMS                                | 4/19/2022    | 
| [icd 10 cm](.\terminology\icd_10_cm.csv)                                                                   | CMS                                | 4/19/2022    | 
| [icd 10 cm to ccs](.\terminology\icd_10_cm_to_ccs.csv)                                                     | QualityNet                         | 4/19/2022    | 
| [icd 10 pcs](.\terminology\icd_10_pcs.csv)                                                                 | CMS                                | 4/19/2022    | 
| [icd 10 pcs to ccs](.\terminology\icd_10_pcs_to_ccs.csv)                                                   | QualityNet                         | 4/19/2022    | 
| [mdc](.\terminology\mdc.csv)                                                                               | CMS                                | 4/19/2022    | 
| [ms drg](.\terminology\ms_drg.csv)                                                                         | CMS                                | 4/19/2022    | 
| [payer type](.\terminology\payer_type.csv)                                                                 | Tuva                               | 4/19/2022    | 
| [place of service](.\terminology\place_of_service.csv)                                                     | National Uniform Billing Committee | 4/19/2022    | 
| [potentially planned ccs procedure category](.\terminology\potentially_planned_ccs_procedure_category.csv) | QualityNet                         | 4/19/2022    | 
| [potentially planned icd 10 pcs](.\terminology\potentially_planned_icd_10_pcs.csv)                         | QualityNet                         | 4/19/2022    | 
| [present on admission](.\terminology\present_on_admission.csv)                                             | CMS                                | 4/19/2022    | 
| [revenue center code](.\terminology\revenue_center_code.csv)                                               | National Uniform Billing Committee | 6/23/2022    | 
| [specialty cohort](.\terminology\specialty_cohort.csv)                                                     | QualityNet                         | 4/19/2022    | 
| [surgery gynecology cohort](.\terminology\surgery_gynecology_cohort.csv)                                   | QualityNet                         | 4/19/2022    |


