# Hadoop Migration Analyzer
The hadoop analyzer is a homegrown tool which helps understand the number and complexity of:

* Pyspark scripts
* Scala spark scripts
* Shell scripts
* Oozie workflows
* Hive scripts
* Presto

The results of the analyzer help the hadoop migration scoping team to create a scoping estimate with ease. Any tools beyond this list need to be assessed manually through workshops with the customer to give a complete estimate.

Note : The hadoop analyzer is different from the Bladebridge Analyzer tool.


### Requirements
* OS: Windows, Linux, Mac OS
* Python 3.10+: https://www.python.org/downloads/
* Java 17+: https://www.oracle.com/ca-en/java/technologies/downloads/

## How to use it 
* Clone this repository: ```git clone https://github.com/databricks/hadoop-migration-analyzer.git``` (If the customer is going to run the analyzer, we need to share the code with the customer since this is a databricks private repo)

* Create a python virtual environment: ```python3 -m virtualenv venv```

* Enable the virtual enviroment: ```python3 -m virtualenv venv```

* Install the requirements: ```pip install -r requirements.txt```

* Create a folder named "output" under the cloned code folder. This is where the code analyzer output will be populated

* Download the code to be analyzed in a local folder on your laptop. The analyzer is capable of drilling down subfolders as well.

* Enter the hadoop migration analyzer folder and run: ```python3 hadoop_migration_analyzer.py -path path-to-the-main-code-folder-to-be-analyzed pyspark hive```


### Parameters
* modules: The list of modules that will be used to analyze the files(separated by space): pyspark hive scala_spark
* path: The path to where the files to be migrated are located, default is "samples" local folder with few samples

## Results 
The ouput of an analyzer run is stored at the output folder in the same directory as the analyzer and it includes the following files:
* estimates_output.xls: Spreadsheet template to build the final estimates containing the complexity of each of the assets
* hadoop_migration_analyzer.log: File that logs the executions of the script and also contain the metrics collected for each file
* File checksum: Checksum of the file analyzed during the execution
* metrics.json: All the metrics collected in a json format


## Estimates Example
![alt text](/images/estimates_example.png?raw=true)

##### Disclaimer
This tool is provided "as is", however, feedback can be submitted through the github issues page, the analyzer is meant to provide support on
hadoop migration assessments, use these metrics provided at your own discretion.

# hadoop-migration-analyzer
