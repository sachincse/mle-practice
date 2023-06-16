# Simpel Template
This repository contains the template for creating your own use case of simpel.  
The simpel template framework takes care of ETL, logging, monitoring, CI-CD etc. 
so the developer should focus on **creating functional data transformation logic.**

## Getting Started

### 1. Pre-Requisites
Before getting started, ensure you have the following software installed:

- Anaconda
- Java
- Git Bash
- Apache Spark
  
For detailed instructions on installation and setting up the environment variables, refer to the [installation guide](https://simpel-portal.azurewebsites.net/projects/documentation/installation.html) on the Simpel portal.

### 2. Cloning the repo
To start your work, clone the repository using the following link: :- 

https://dev.azure.com/marsanalytics/ODDA%20Central/_git/sds-simpel-template

```
C:\simpel_code>git clone https://marsanalytics@dev.azure.com/marsanalytics/ODDA%20Central/_git/sds-simpel-template
```


## Local Setup

To run a local version, follow these steps:
1. After cloning change the directory

```
C:\simpel_code>cd sds-simpel-template
```

2. Open the File Explorer and locate the 'HadoopInstallation_Script2.0.ps1' file in your cloned project. Right-click on the file and click on "Run with PowerShell". The file is located at:

```
C:\simpel_code\sds-simpel-template\docs\samples\example_data\HadoopInstallation_Script2.0.ps1
```

To validate the resources created by the PowerShell script, you can perform the following steps:

```
1. Git:
   - Check if Git is installed by running the command `git` in PowerShell.
   - Verify that the installation was successful by checking if Git commands are recognized and executed without errors.
   - Confirm that the Git executable path is added to the system's PATH variable.
   - Optionally, you can check the installed version of Git using the command `git --version`.

2. Anaconda3:
   - Check if Anaconda3 is installed by running the command `conda` in PowerShell.
   - Verify that the installation was successful by checking if Conda commands are recognized and executed without errors.
   - Confirm that the Anaconda3 installation path is added to the system's PATH variable.
   - Optionally, you can check the installed version of Anaconda3 using the command `conda --version`.

3. Java 8:
   - Check if Java 8 is installed by running the command `java -version` in PowerShell.
   - Verify that the installation was successful by checking if Java commands are recognized and executed without errors.
   - Optionally, you can check the installed version of Java using the command `java -version`.

4. Spark:
   - Check if Spark is installed by verifying the presence of the Spark installation directory specified in the script (`C:\Spark`).
   - Validate that the Spark binary archive was downloaded by checking if the file `spark-3.3.2-bin-hadoop3.tgz` exists.
   - Confirm that the Spark installation directory contains the necessary files and folders, such as `bin`, `conf`, etc.
   - Ensure that the Spark bin folder is added to the system's PATH variable.
   - Optionally, you can check the installed version of Spark by running the command `spark-submit --version`.

5. Hadoop:
   - Check if Hadoop is installed by verifying the presence of the Hadoop installation directory specified in the script (`C:\hadoop`).
   - Validate that the Hadoop files were downloaded from GitHub by checking if the `winutils` folder exists in the specified download path.
   - Confirm that the necessary files and folders are present in the Hadoop installation directory, such as `bin`, `etc`, etc.
   - Optionally, you can check the installed version of Hadoop by running the command `hadoop version`.

By performing these checks, you can ensure that each resource (Git, Anaconda3, Java 8, Spark, and Hadoop) is installed and configured correctly as intended by the script.
```

If the script is unable to download and install the required resources, you can manually download and configure them using the following methods:

```
1. Git:
   - Manually download the Git installer from the official Git website (https://git-scm.com/downloads).
   - Run the installer and follow the installation instructions.
   - Add the Git executable path to the system's PATH variable manually:
     - Open the Control Panel and navigate to System > Advanced system settings > Environment Variables.
     - Edit the "Path" variable under System variables and append the Git executable path (e.g., C:\Program Files\Git\cmd) to the list of existing paths.
     - Click OK to save the changes.

2. Anaconda3:
   - Manually download the Anaconda3 installer from the official Anaconda website (https://www.anaconda.com/products/individual).
   - Run the installer and follow the installation instructions.
   - During the installation, make sure to select the option to add Anaconda3 to the system's PATH variable.
   - If Anaconda3 was not added to the PATH during installation, you can manually add it:
     - Open the Control Panel and navigate to System > Advanced system settings > Environment Variables.
     - Edit the "Path" variable under System variables and append the Anaconda3 installation path (e.g., C:\ProgramData\Anaconda3) to the list of existing paths.
     - Click OK to save the changes.

3. Java 8:
   - Manually download the Java Development Kit (JDK) 8 installer from the Oracle website (https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html).
   - Run the installer and follow the installation instructions.
   - Set the JAVA_HOME environment variable manually:
     - Open the Control Panel and navigate to System > Advanced system settings > Environment Variables.
     - Click "New" under System variables and add a variable named JAVA_HOME with the value set to the JDK installation directory (e.g., C:\Program Files\Java\jdk1.8.0_xx).
     - Click OK to save the changes.
   - Add the JDK's "bin" directory to the system's PATH variable:
     - Edit the "Path" variable under System variables and append the JDK's "bin" directory (e.g., C:\Program Files\Java\jdk1.8.0_xx\bin) to the list of existing paths.
     - Click OK to save the changes.

4. Spark:
   - Manually download the Spark binary archive from the official Spark website (https://spark.apache.org/downloads.html).
   - Extract the contents of the downloaded archive to a desired location (e.g., C:\Spark).
   - Add the Spark bin folder to the system's PATH variable:
     - Open the Control Panel and navigate to System > Advanced system settings > Environment Variables.
     - Edit the "Path" variable under System variables and append the Spark bin directory (e.g., C:\Spark\bin) to the list of existing paths.
     - Click OK to save the changes.

5. Hadoop:
   - Manually download the Hadoop binary distribution from the official Hadoop website (https://hadoop.apache.org/releases.html).
   - Extract the contents of the downloaded archive to a desired location (e.g., C:\hadoop).
   - Configure the Hadoop installation manually:
     - Update the Hadoop configuration files located in the "etc" directory within the Hadoop installation.
     - Customize the configuration files based on your specific requirements and cluster setup.
     - Optionally, set the HADOOP_HOME environment variable to the Hadoop installation directory (e.g., C:\hadoop).

By following these manual download and configuration methods,
```


3. Create conda environment using the requirements.txt file which also contains the location of wheel for simpel library.

```
C:\simpel_code\sds-simpel-template>conda create --name simpel_project python==3.8
```

```
C:\simpel_code\sds-simpel-template>conda activate simpel_project
```

4. Download simpel and simpel-data-quality library wheel files from the below links and save them in your working directory.

- simpel 0.0.39: [simpel 0.0.39](https://dev.azure.com/marsanalytics/ODDA%20Central/_artifacts/feed/sds-simpel-library@Local/PyPI/simpel/overview/0.0.39)  
- simpel-data-quality 0.0.28: [simpel-data-quality 0.0.28](https://dev.azure.com/marsanalytics/ODDA%20Central/_artifacts/feed/sds-shared-utils@Local/PyPI/simpel-data-quality/overview/0.0.28) 

- simpel_logging 0.0.12: [simpel_logging 0.0.12](https://dev.azure.com/marsanalytics/ODDA%20Central/_artifacts/feed/sds-shared-utils@Local/PyPI/simpel-logging/overview/0.0.12)

Save to below path :-

- C:\simpel_code\sds-simpel-template\simpel_data_quality-0.0.28-py2.py3-none-any.whl

- C:\simpel_code\sds-simpel-template\simpel-0.0.39-py2.py3-none-any.whl

- C:\simpel_code\sds-simpel-template\simpel_logging-0.0.12-py2.py3-none-any.whl

5. Create a requirements.txt file with below updated library :-

```
numpy==1.24.2
pandas==1.5.3
py4j==0.10.9.5
pydeequ==1.0.1
pyodbc==4.0.35
pyspark==3.3.2
python-dateutil==2.8.2
pytz==2022.7.1
six==1.16.0
sparkmeasure==0.21.1
wincertstore==0.2
zipp==3.14.0
./simpel_data_quality-0.0.28-py2.py3-none-any.whl
./simpel-0.0.39-py2.py3-none-any.whl
./simpel_logging-0.0.12-py2.py3-none-any.whl
```

5. Run the requirements.txt

```
(simpel_project) C:\simpel_code\sds-simpel-template>pip install -r requirements.txt
```


6. Create simpel_template library.
- Reason: dags.json and will try to find src.simpel_template as a module.

7. To use simpel_template as a module you need to create a setup.py file. Here is an example of how the setup.py file can be structured:

- setup.py
```python
from setuptools import find_packages, setup

PROJECT_NAME = "simpel_template"
PROJECT_DESC = "Template project used to demonstrate how Simpel works"

# with open("README.md", "r") as fh:
#     long_description = fh.read()

setup(
    name=PROJECT_NAME,
    version="1.5.0",
    include_package_data=True,
    description=PROJECT_DESC,
    setup_requires=['wheel'],
    # long_description=long_description,
    long_description_content_type="text/markdown",
    scripts=['src/main/main.py'],
    packages=find_packages(),
    package_data={
        # If any package contains *.txt or *.rst files, include them:
        '': ['*.txt', '*.rst', '*.json', '*.csv', '*.cfg'],
        # And include any *.msg files found in the 'hello' package, too:

    },
    classifiers=[
        "Programming Language :: Python :: 3",
        "License :: OSI Approved :: MIT License",
        "Operating System :: OS Independent",
        "Development Status :: 3 - Alpha"
    ],
    python_requires='>=3.7'
)
```

8. Run the below command 

```
C:\simpel_code\sds-simpel-template>pip install -e .
```

9. Go to all example.json files present inside a_trusted_raw_zone, b_refined_zone, c_common_zone, and update the below parameters in LOCAL. 

```parameters
write_location
logging_location
spark_home
hadoop_home
```
example:-

```json
"LOCAL":{
          "environment":"LOCAL",
          "input":"src/simpel_template/a_trusted_raw_zone/settings/example/input.json",
          "output":"src/simpel_template/a_trusted_raw_zone/settings/example/output.json",
          "deequ":"src/simpel_template/a_trusted_raw_zone/settings/example/deequ.json",
          "dags":"src/simpel_template/a_trusted_raw_zone/settings/example/dags.json",
          "write_location":"C:/simpel_code/simpel_workflow_new/spark-warehouse/",
          "logging_location":"C:/simpel_code/simpel_workflow_new/spark-warehouse/governance/resource_governance/utils/",
          "project_mailing_list":"hardik.talati@effem.com,rich.nixon@effem.com",
          "data_catalog_config":"/data_catalog/example/data_catalog.yml",
          "spark_home": "C:/Spark/",
          "hadoop_home": "C:/hadoop/"
      },
```

```note
Notes: 
1. Make sure actual paths don't contains spaces.
2. Trailing slashes `/` are important 
```

10. Run the run_me.py present inside src\simpel_template\samples\example_data\run_me.py, on your virtual environment terminal, with below values defines on run_me.py file

```html
project_name = "example"
env = "LOCAL"
process_name = "EXAMPLE_PIPE_1"
database = "example"
data_layer = "a_TRUSTED_RAW_ZONE"
template = "simpel_template"

```

```commandline
C:\simpel_code\sds-simpel-template>python src\simpel_template\samples\example_data\run_me.py
```

It will create spark-warehouse folder in your current directory, which contains the partition data

```html
├── docs
├── |
├── |
├── spark-warehouse ---> newly created folder containing example data with partition with date.
├── |
├── |
```


11. Run the below command in terminal
```commandline
C:\simpel_code\sds-simpel-template>python src\main\main.py --project_name example --process_name EXAMPLE_PIPE_1 --write_database example --environment LOCAL --data_layer a_trusted_raw_zone
```

12. Check if example database is created on Local. If it is created you can start executing the other pipelines to check all the connectivity.

13. You can use scratch_me.py present in src\simpel_template\samples\example_data\scratch_me.py for better debugging purpose. 

```
Note: In scratch_me.py change the import from  `deequ_before_after` should be changed to `dq_before_after`
```

### 
---------------------------------------------------------------------------------------------

## DEV SETUP

To run a Dev version in databricks follow the following:

If you have Azure DevOps repository and pipelines access then you can follow offical methods :-

[Deploying Simpel to Databricks Workflows](https://mydrive.effem.com/personal/ewan_copsey_effem_com/_layouts/15/stream.aspx?id=%2Fpersonal%2Fewan%5Fcopsey%5Feffem%5Fcom%2FDocuments%2FRecordings%2FDeploying%20Simpel%20to%20Databricks%20Workflows%2Emp4&nav=eyJwbGF5YmFja09wdGlvbnMiOnsic3RhcnRUaW1lSW5TZWNvbmRzIjoxNzEuMTc4NjY2fX0%3D&referrer=StreamPlaylist&referrerScenario=PopOut%2Emis%2Ed39124bd%2Df684%2D41e4%2D9ee3%2D5b9b49b85522) 

1. If you don't have access follow the following:-

2. Update the `write_location` in example.json with the DBFS location. (Example: `"write_location": "dbfs:/FileStore/simpel_demo_data/demo1/",`)

3. Upload the example data from (src\simpel_template\samples\example_data\sample)in DBFS location (example:- dbfs:/FileStore/simpel_data_dev/). Update the `run_me_on_databricks.py` with the below, it is updated with example data parameters and update `SAMPLE_DATA_LOC` and `location` parameters according to your path where the data is uploaded and where you want to write:-

```
from simpel.common.common import get_configured_session

project_name = "example"
env = "DEV"
process_name = "EXAMPLE_PIPE_1"
database = "example"
data_layer = "a_TRUSTED_RAW_ZONE"
template = "simpel_template"
spark = get_configured_session(template, data_layer, project_name, env)


def load_me(files: list, date: str, loc: str):
    # from src.simpel_template.constants import SAMPLE_DATA_LOC
    SAMPLE_DATA_LOC = "dbfs:/FileStore/simpel_data_dev/"
    path = SAMPLE_DATA_LOC
    for i in files:
        f = (date).split("-")
        folder = f[0] + "/" + f[1] + "/" + f[2]
        if i in ("sales2", "sales3", "scd_sample2", "scd_sample3"):

            df = spark.read.format("csv").load(
                path + "/{0}.csv".format(i),
                header=True, inferSchema=True)
            df.show()
            a = i
            i = ''.join([i for i in a if not i.isdigit()])
            df.write.format("parquet").save("{2}/example/{0}/{1}".format(i, folder, loc))
        else:
            df = spark.read.format("csv").load(
                path + "/{0}.csv".format(i),
                header=True, inferSchema=True)
            df.write.option("header", "True").format("parquet").save(
                "{2}/example/{0}/{1}".format(i, folder, loc))
    return print("data loaded")


def run_me(loc: str):
    files = ["sales", "vendor", "item", "product", "scd_sample"]
    date = "2022-10-01"

    files2 = ["sales2", "vendor", "item", "product", "scd_sample2"]
    date2 = "2022-10-02"

    files3 = ["sales3", "vendor", "item", "product", "scd_sample3"]
    date3 = "2022-10-03"

    load_me(files, date, loc)
    load_me(files2, date2, loc)
    load_me(files3, date3, loc)
    return print("data loaded")

files = ["sales", "vendor", "item", "product","scd_sample"]
date = "2022-10-01"

files2 = ["sales2", "vendor", "item", "product","scd_sample2"]
date2 = "2022-10-02"

files3 = ["sales3", "vendor", "item", "product","scd_sample3"]
date3 = "2022-10-03"
location = "dbfs:/FileStore/simpel_demo_data/demo1/raw"

load_me(files, date, location)
load_me(files2, date2, location)
load_me(files3, date3, location)
```

4. Build the wheel file, using the below command.
```
C:\simpel_code\sds-simpel-template>python setup.py bdist_wheel
```

5. Upload the wheel file in DBFS.

```
To upload a wheel file to Databricks File System (DBFS), you can follow these steps:

- First, make sure you have the wheel file ready on your local machine.

- Open the Databricks workspace and navigate to the cluster where you want to upload the file.

- Click on the "Data" tab on the left-hand side menu.

- In the Data tab, click on the "Upload File" button.

- In the file upload dialog box, click on the "Drop your files here to upload" area or use the file explorer to locate and select the wheel file from your local machine.

- Once the file is selected, it will begin uploading to the DBFS.

- After the upload is complete, you will see the file listed in the data view with its path in DBFS.

Now you can use the uploaded wheel file in your Databricks notebooks or scripts. 
```

6. Upload the `main.py` script sepeartly to any accessible DBFS location. (Example:- dbfs:/FileStore/main.py)


6. Create the cluster with Databricks Runtime Version(10.4) and add all necessary library and dependent wheel files. 

```
To create a cluster and install all the necessary libraries and dependent wheel files, you can follow these steps:

- Open the Databricks workspace and navigate to the "Clusters" tab.

- Click on the "Create Cluster" button to start creating a new cluster.

- Provide a name for the cluster to identify it easily.

- Select the desired cluster mode and Databricks runtime version 10.4.

- In the "Libraries" section, click on the "+ Create" button to add libraries.

- Specify the library source. If you have wheel files to install, select "Upload Python Wheel" as the source.

- Upload the necessary library and dependent wheel files from your local machine. You can click on the "Upload" button to browse and select the files.

- Once the files are uploaded, Databricks will automatically install the libraries and their dependencies.

- Review the other cluster settings such as instance types, auto scaling, and permissions, and adjust them according to your requirements.

- Click on the "Create Cluster" button to create the cluster.
```

`Note:` `Databricks Runtime Version 10.4` is important because it upload the libraries folder in the path '/databricks/python3/lib/python3.8/site-packages' which is hard coded inside the simpel core library.

9. This step is one time activity to create partition data in DBFS for example data. Run the run_me_on_databricks.py code on the notebook environment using the same created cluster. Run the command in notebook cell.

```
python /databricks/python3/lib/python3.8/site-packages/src/simpel_template/samples/example_data/run_me_on_databricks.py
```

`Or` directly paste the `run_me_on_databricks.py` code on the notebook cell and run it. 


10. On the Workflows homepage, select Create Job. This will prompt you to configure your first task in the job.

Enter the following parameters:

- `Task Name` : <Pipeline Name From Simpel Dags Settings>
- `Type` : Python Script
- `Source` : DBFS
- `Path` : <Path to deployed main.py> (Example: /dbfs/scripts/main/main.py)
- `Cluster` : Attach your pre-prepared interactive cluster which contains dependent libraries. 

11. Finally, the parameters that are fed into the main.py script need to be defined. These should be taken from what is defined within your simpel project. Below is an example:
- `Parameters` = ["--project_name","example","--process_name","EXAMPLE_PIPE_1","--write_database","example", "--environment","DEV","--data_layer","a_trusted_raw_zone"]

12. Click Create to create the task.

13. The task created will run the specific simpel pipeline defined in the parameters. To stitch together a full pipeline, click the large blue plus icon and add a new `Python` Script task.

14. Repeat the above steps to configure new tasks.
- The parameters should be changed according to which simpel pipeline is being run.
- The cluster should be the same job cluster in each task.

15. The completed `Job` can be run by clicking `Run now` in the top-right corner.


### 
---------------------------------------------------------------------------------------------

## Adopting simpel to your project

1. Creating project folder in each layer by coping the example folder.

```html
├── a_trusted_raw_zone
│   ├── dags
│   │   ├── example
│   │   ├── <project_name> ---> do this for all folders
│   ├── ddls 
│   ├── |
├── 
```

2. Update the file name example.json to the <project_name>.json

3. Update all the json files in every zone present in setting folder:-

        1. <project_name>.json
        2. input.json
        3. output.json
        4. deequ.json 
        5. dags.json

Note: Make sure to update the right folder, files and imports details associated to your <project_name> and path does not contains spaces.

4. Write the table schema code inside ddls folder.

```
Note: 
1. Keep columns key_hash', 'data_hash', 'row_valid_to_ts', 'dw_update_ts', 'dw_insert_ts' in the schema as it required by template.
2. ddls required only when we have `type_of_write` as `delta_append`. In case of `delta_scd1` we must have ddls function empty
```
5. Test if all the json file configured properly with below command and check if input and output table created successfully. Refer scratch_me.py for more detailed code.

```python
from simpel.common.common import get_configured_session, create_database_if_not_exist, get_settings, get_data

project_name = "<project_name>"
env = "LOCAL"
process_name = "EXAMPLE_PIPE_1"
database = "<project_name>"
data_layer = "a_trusted_raw_zone"
template = "simpel_template"

spark = get_configured_session(template, data_layer, project_name, env)
create_database_if_not_exist(spark, database)
the_env, write_read_path, input_dict, output_dict, deequ_dict, ddl, transformer = get_settings(env, data_layer,
                                                                                               project_name,
                                                                                               process_name, template)
ddl(spark, write_read_path, database)
```

Note: Run the command in interactive mode, for debugging purpose.

6. Add the transformation logic to transformation folder script, Execute it in dags folder script i.e. dags/<project_name> folder.

7. Add DQ checks to deequ.json

        1. Before writing the dataframe
        2. After writing the dataframe
    
8. Test the code locally.

```
Note:
1. `output.json` `folder` needs to be similar as `.location()` mentioned ddls script, same goes with `output_name`.
2. `input.json` `dataframe_name` should be used in dags script while performing transformation
```

### 
---------------------------------------------------------------------------------------------


### Recommendation

- Use same name in `dataframe_name` and `input` for `input.json`
- use same name in `output_name` and `table_name` in `output.json`


### Some points to remember 

- If you are not getting data and you trying to change the schema, make sure to delete the example database before and also folders created related to databse in spark-warehouse folder.



### Simpel Training Documentation
Slides: [Simpel_Training](https://mydrive.effem.com/:p:/g/personal/ewan_copsey_effem_com/Efg5Hkbz6bBNjzCYua7kgO0B87EI-x3pzUYWezCXG5c1IQ?e=d9tyxZ)  
Videos: [Simpel_Learning_Videos](https://mydrive.effem.com/:l:/g/personal/ewan_copsey_effem_com/FP35Ve3UiJZFlWteKQvly7sBQiLL8uYx3HRZcxHoDjfbBQ?e=qDMm9E) 



