# cs764-Argo
Argo Json document store on Quickstep, Postgres, MongoDB [CS 764 Project Fall 2016]

**Python Files**

- driver.py - Main program that executes the experiment
- mongo_driver.py - Program that executes the MongoDB NoBench queries Query 1 - Query 12
- postgres_driver.py - Program that executes the PostgreSQL NoBench queries Query 1 - Query 12
- quickstep_driver.py- Program that executes the Quickstep NoBench queries Query 1 - Query 12
- Global.py - Configuration file for global variables [Eg. datasize, collection name]
- nobench_gendata.py - Genrerates json objects as per workload requirement of NoBench queries
- json2bulksql.py - Converts json objects resulting from NoBench data generation module and converts to 3 files in Argo format

**Library**

pyqs/pyqs.py for connecting to Quickstep via python

**Execution**
- python driver.py - Generates data, loads data into all 3 systems, executes 10 runs of NoBench queries on all 3 systems
- python driver.py --mongo --psql --qstep     - Same as 1
- python driver.py --gen --load --run --mongo - Same as 1 but only on MongoDB
- python driver.py --gen --load --run --mongo --noclean - Same as 1 but only on MongoDB and retains data in MongoDB after run
- python driver.py --gen --load --run --test - Same as 1 but populates test data [smaller data size] in test tables on all 3 sys

**Files generated by the program**
- nobench_data_argo - json objects output from data generation module
- nobench_data_argo_extra - extra json objects output from data generation module
- rec_strs - Query8 parameters output from data generation module

**nobench_data_argo is converted to the below 3 files inline with Argo3 format**
- nobench_data_argo_str.txt
- nobench_data_argo_num.txt
- nobench_data_argo_bool.txt

**nobench_data_argo_extra is converted to the below 3 files inline with Argo3 format**
- nobench_data_argo_extra_str.txt
- nobench_data_argo_extra_num.txt
- nobench_data_argo_extra_bool.txt

results\<datasize\>.csv [Eg. results16000000.csv] - Elapsed time for 10 runs of the 12 NoBench Queries on the systems






