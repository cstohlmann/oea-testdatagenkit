# Base-Truth Table Generation Notebooks

There are two notebooks necessary for generating the overarching base-truth tables (see below). These base-truth tables are used to create the module-specific test data.

## [Base Truth Tables Generation Class](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_test_data_generation_kit/notebook/test_data_generation_py.ipynb)

The class notebook supports two main roles:
- defining the five base-truth tables to be created, and
- creating artificial students, schools, courses, sections, and enrollment within the scope of the respective base-truth tables. Generation is based on user-input of the number of students and schools, and education level desired to be reflected in the generated test data.

Class functionality and methods are clearly commented and outlined in the notebook.

## [Base-Truth Table Generation Demo](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_test_data_generation_kit/notebook/test_data_gen_demo.ipynb)

The demo generation notebook depends on the base truth tables generation class, and is responsible for executing the functions of the class notebook.

## Base-Truth Table Generation Instructions

1. Either create a new Spark pool and attach the [requirements_test_data_gen.txt file](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_test_data_generation_kit/notebook/requirements_test_data_gen.txt), or attach file to an existing Spark pool. For more guidance on how to do this, follow the instructions in the [Chronic Absenteeism package](https://github.com/microsoft/OpenEduAnalytics/tree/main/packages/package_catalog/Predicting_Chronic_Absenteeism/pipelines#creating-an-apache-spark-pool-with-package-requirements), except with the requirements specific to this test data generation kit.
2. Download and import both notebooks, and attach the demo notebook to the Spark pool with the proper requirements (from the step above). Then, execute this demo notebook to create the base-truth tables. These base-truth tables with be generated and landed in stage1, specifically:
    * ```stage1/Transactional/test_data/v0.1/base_students/snapshot_batch_data/rundate=.../*.csv```
    * ```stage1/Transactional/test_data/v0.1/base_schools/snapshot_batch_data/rundate=.../*.csv```
3. After successfully creating these tables, you can execute the desired module-specific test data generation notebook(s).
