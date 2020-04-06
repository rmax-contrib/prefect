---
sidebarDepth: 2
editLink: false
---
# Azure ML Service Tasks
---
This module contains a collection of tasks for interacting with Azure Machine Learning Service resources.
 ## DatasetCreateFromDelimitedFiles
 <div class='class-sig' id='prefect-tasks-azureml-dataset-datasetcreatefromdelimitedfiles'><p class="prefect-sig">class </p><p class="prefect-class">prefect.tasks.azureml.dataset.DatasetCreateFromDelimitedFiles</p>(dataset_name=None, datastore=None, path=None, dataset_description="", dataset_tags={}, include_path=False, infer_column_types=True, set_column_types=None, fine_grain_timestamp=None, coarse_grain_timestamp=None, separator=",", header=PromoteHeadersBehavior.ALL_FILES_HAVE_SAME_HEADERS, partition_format=None, create_new_version=False, **kwargs)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/azureml/dataset.py#L12">[source]</a></span></div>

Task for creating a TabularDataset from delimited files for use in a Azure Machine Learning service Workspace. The files should exist in a Datastore. Note that all initialization arguments can optionally be provided or overwritten at runtime.

**Args**:     <ul class="args"><li class="args">`dataset_name (str, optional)`: The name of the Dataset in the Workspace     </li><li class="args">`datastore (azureml.core.datastore.Datastore, optional)`: The Datastore which holds the files.     </li><li class="args">`path (Union[str, List[str]], optional)`: The path to the delimited files in the Datastore.     </li><li class="args">`dataset_description (str, optional)`: Description of the Dataset.     </li><li class="args">`dataset_tags (str, optional)`: Tags to associate with the Dataset.     </li><li class="args">`include_path (bool, optional)`: Boolean to keep path information as column in the dataset.     </li><li class="args">`infer_column_types (bool, optional)`: Boolean to infer column data types.     </li><li class="args">`set_column_types (Dict[str, azureml.data.DataType], optional)`: A dictionary to set column data type, where key is column name and value is a `azureml.data.DataType`.     </li><li class="args">`fine_grain_timestamp (str, optional)`: The name of column as fine grain timestamp.     </li><li class="args">`coarse_grain_timestamp (str, optional)`: The name of column coarse grain timestamp.     </li><li class="args">`separator (str, optional)`: The separator used to split columns.     </li><li class="args">`header (azureml.data.dataset_type_definitions.PromoteHeadersBehavior, optional)`: Controls how column headers are promoted when reading from files. Defaults to assume that all files have the same header.     </li><li class="args">`partition_format (str, optional)`: Specify the partition format of path. Defaults to None. The partition information of each path will be extracted into columns based on the specified format. Format part `{column_name}` creates string column, and `{column_name:yyyy/MM/dd/HH/mm/ss}` creates datetime column, where `yyyy`, `MM`, `dd`, `HH`, `mm` and `ss` are used to extrat year, month, day, hour, minute and second for the datetime type. The format should start from the position of first partition key until the end of file path. For example, given the path `../Germany/2019/01/01/data.csv` where the partition is by country and time, `partition_format="/{Country}/{PartitionDate:yyyy/MM/dd}/data.csv"` creates string column `Country` with value `Germany` and datetime column `PartitionDate` with value `2019-01-01`.     </li><li class="args">`create_new_version (bool, optional)`: Boolean to register the dataset as a new version under the specified name.     </li><li class="args">`**kwargs (dict, optional)`: additional keyword arguments to pass to the Task constructor</li></ul>

|methods: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:----|
 | <div class='method-sig' id='prefect-tasks-azureml-dataset-datasetcreatefromdelimitedfiles-run'><p class="prefect-class">prefect.tasks.azureml.dataset.DatasetCreateFromDelimitedFiles.run</p>(dataset_name=None, datastore=None, path=None, dataset_description="", dataset_tags={}, include_path=False, infer_column_types=True, set_column_types=None, fine_grain_timestamp=None, coarse_grain_timestamp=None, separator=",", header=PromoteHeadersBehavior.ALL_FILES_HAVE_SAME_HEADERS, partition_format=None, create_new_version=False)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/azureml/dataset.py#L70">[source]</a></span></div>
<p class="methods">Task run method.<br><br>**Args**:     <ul class="args"><li class="args">`dataset_name (str, optional)`: The name of the Dataset in the Workspace     </li><li class="args">`datastore (azureml.core.datastore.Datastore, optional)`: The Datastore which holds the files.     </li><li class="args">`path (Union[str, List[str]], optional)`: The path to the delimited files in the Datastore.     </li><li class="args">`dataset_description (str, optional)`: Description of the Dataset.     </li><li class="args">`dataset_tags (str, optional)`: Tags to associate with the Dataset.     </li><li class="args">`include_path (bool, optional)`: Boolean to keep path information as column in the dataset.     </li><li class="args">`infer_column_types (bool, optional)`: Boolean to infer column data types.     </li><li class="args">`set_column_types (Dict[str, azureml.data.DataType], optional)`: A dictionary to set column data type, where key is column name and value is a `azureml.data.DataType`.     </li><li class="args">`fine_grain_timestamp (str, optional)`: The name of column as fine grain timestamp.     </li><li class="args">`coarse_grain_timestamp (str, optional)`: The name of column coarse grain timestamp.     </li><li class="args">`separator (str, optional)`: The separator used to split columns.     </li><li class="args">`header (azureml.data.dataset_type_definitions.PromoteHeadersBehavior, optional)`: Controls how column headers are promoted when reading from files. Defaults to assume that all files have the same header.     </li><li class="args">`partition_format (str, optional)`: Specify the partition format of path.     </li><li class="args">`create_new_version (bool, optional)`: Boolean to register the dataset as a new version under the specified name.</li></ul>**Returns**:     <ul class="args"><li class="args">`azureml.data.TabularDataset`: the created TabularDataset</li></ul></p>|

---
<br>

 ## DatasetCreateFromParquetFiles
 <div class='class-sig' id='prefect-tasks-azureml-dataset-datasetcreatefromparquetfiles'><p class="prefect-sig">class </p><p class="prefect-class">prefect.tasks.azureml.dataset.DatasetCreateFromParquetFiles</p>(dataset_name=None, datastore=None, path=None, dataset_description="", dataset_tags={}, include_path=False, set_column_types=None, fine_grain_timestamp=None, coarse_grain_timestamp=None, partition_format=None, create_new_version=False, **kwargs)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/azureml/dataset.py#L165">[source]</a></span></div>

Task for creating a TabularDataset from Parquet files for use in a Azure Machine Learning service Workspace. The files should exist in a Datastore. Note that all initialization arguments can optionally be provided or overwritten at runtime.

**Args**:     <ul class="args"><li class="args">`dataset_name (str, optional)`: The name of the Dataset in the Workspace     </li><li class="args">`datastore (azureml.core.datastore.Datastore, optional)`: The Datastore which holds the files.     </li><li class="args">`path (Union[str, List[str]], optional)`: The path to the delimited files in the Datastore.     </li><li class="args">`dataset_description (str, optional)`: Description of the Dataset.     </li><li class="args">`dataset_tags (str, optional)`: Tags to associate with the Dataset.     </li><li class="args">`include_path (bool, optional)`: Boolean to keep path information as column in the dataset.     </li><li class="args">`set_column_types (Dict[str, azureml.data.DataType], optional)`: A dictionary to set column data type, where key is column name and value is a `azureml.data.DataType`.     </li><li class="args">`fine_grain_timestamp (str, optional)`: The name of column as fine grain timestamp.     </li><li class="args">`coarse_grain_timestamp (str, optional)`: The name of column coarse grain timestamp.     </li><li class="args">`partition_format (str, optional)`: Specify the partition format of path. Defaults to None. The partition information of each path will be extracted into columns based on the specified format. Format part `{column_name}` creates string column, and `{column_name:yyyy/MM/dd/HH/mm/ss}` creates datetime column, where `yyyy`, `MM`, `dd`, `HH`, `mm` and `ss` are used to extrat year, month, day, hour, minute and second for the datetime type. The format should start from the position of first partition key until the end of file path. For example, given the path `../Germany/2019/01/01/data.csv` where the partition is by country and time, `partition_format="/{Country}/{PartitionDate:yyyy/MM/dd}/data.csv"` creates string column `Country` with value `Germany` and datetime column `PartitionDate` with value `2019-01-01`.     </li><li class="args">`create_new_version (bool, optional)`: Boolean to register the dataset as a new version under the specified name.     </li><li class="args">`**kwargs (dict, optional)`: additional keyword arguments to pass to the         Task constructor</li></ul>

|methods: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:----|
 | <div class='method-sig' id='prefect-tasks-azureml-dataset-datasetcreatefromparquetfiles-run'><p class="prefect-class">prefect.tasks.azureml.dataset.DatasetCreateFromParquetFiles.run</p>(dataset_name=None, datastore=None, path=None, dataset_description="", dataset_tags={}, include_path=False, set_column_types=None, fine_grain_timestamp=None, coarse_grain_timestamp=None, partition_format=None, create_new_version=None)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/azureml/dataset.py#L215">[source]</a></span></div>
<p class="methods">Task run method.<br><br>**Args**:     <ul class="args"><li class="args">`dataset_name (str, optional)`: The name of the Dataset in the Workspace     </li><li class="args">`datastore (azureml.core.datastore.Datastore, optional)`: The Datastore which holds the files.     </li><li class="args">`path (Union[str, List[str]], optional)`: The path to the delimited files in the Datastore.     </li><li class="args">`dataset_description (str, optional)`: Description of the Dataset.     </li><li class="args">`dataset_tags (str, optional)`: Tags to associate with the Dataset.     </li><li class="args">`include_path (bool, optional)`: Boolean to keep path information as column in the dataset.     </li><li class="args">`set_column_types (Dict[str, azureml.data.DataType], optional)`: A dictionary to set column data type, where key is column name and value is a `azureml.data.DataType`.     </li><li class="args">`fine_grain_timestamp (str, optional)`: The name of column as fine grain timestamp.     </li><li class="args">`coarse_grain_timestamp (str, optional)`: The name of column coarse grain timestamp.     </li><li class="args">`partition_format (str, optional)`: Specify the partition format of path.     </li><li class="args">`create_new_version (bool, optional)`: Boolean to register the dataset as a new version under the specified name.</li></ul>**Returns**:     <ul class="args"><li class="args">`azureml.data.TabularDataset`: the created TabularDataset.</li></ul></p>|

---
<br>

 ## DatasetCreateFromFiles
 <div class='class-sig' id='prefect-tasks-azureml-dataset-datasetcreatefromfiles'><p class="prefect-sig">class </p><p class="prefect-class">prefect.tasks.azureml.dataset.DatasetCreateFromFiles</p>(dataset_name=None, datastore=None, path=None, dataset_description="", dataset_tags={}, create_new_version=False, **kwargs)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/azureml/dataset.py#L297">[source]</a></span></div>

Task for creating a FileDataset from files for use in a Azure Machine Learning service Workspace. The files should exist in a Datastore. Note that all initialization arguments can optionally be provided or overwritten at runtime.

**Args**:     <ul class="args"><li class="args">`dataset_name (str, optional)`: The name of the Dataset in the Workspace     </li><li class="args">`datastore (azureml.core.datastore.Datastore, optional)`: The Datastore which holds the files.     </li><li class="args">`path (Union[str, List[str]], optional)`: The path to the delimited files in the Datastore.     </li><li class="args">`dataset_description (str, optional)`: Description of the Dataset.     </li><li class="args">`dataset_tags (str, optional)`: Tags to associate with the Dataset.     </li><li class="args">`create_new_version (bool, optional)`: Boolean to register the dataset as a new version under the specified name.     </li><li class="args">`**kwargs (dict, optional)`: additional keyword arguments to pass to the         Task constructor</li></ul>

|methods: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:----|
 | <div class='method-sig' id='prefect-tasks-azureml-dataset-datasetcreatefromfiles-run'><p class="prefect-class">prefect.tasks.azureml.dataset.DatasetCreateFromFiles.run</p>(dataset_name=None, datastore=None, path=None, dataset_description="", dataset_tags={}, create_new_version=False)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/azureml/dataset.py#L332">[source]</a></span></div>
<p class="methods">Task run method.<br><br>**Args**:     <ul class="args"><li class="args">`dataset_name (str, optional)`: The name of the Dataset in the Workspace     </li><li class="args">`datastore (azureml.core.datastore.Datastore, optional)`: The Datastore which holds the files.     </li><li class="args">`path (Union[str, List[str]], optional)`: The path to the delimited files in the Datastore.     </li><li class="args">`dataset_description (str, optional)`: Description of the Dataset.     </li><li class="args">`dataset_tags (str, optional)`: Tags to associate with the Dataset.     </li><li class="args">`create_new_version (bool, optional)`: Boolean to register the dataset as a new version under the specified name.</li></ul>**Returns**:     <ul class="args"><li class="args">`azureml.data.FileDataset`: the created FileDataset</li></ul></p>|

---
<br>

 ## DatastoreRegisterBlobContainer
 <div class='class-sig' id='prefect-tasks-azureml-datastore-datastoreregisterblobcontainer'><p class="prefect-sig">class </p><p class="prefect-class">prefect.tasks.azureml.datastore.DatastoreRegisterBlobContainer</p>(workspace, container_name=None, datastore_name=None, create_container_if_not_exists=False, overwrite_existing_datastore=False, azure_credentials_secret="AZ_CREDENTIALS", set_as_default=False, **kwargs)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/azureml/datastore.py#L17">[source]</a></span></div>

Task for registering Azure Blob Storage container as a Datastore in a Azure ML service Workspace. 

**Args**:     <ul class="args"><li class="args">`workspace (azureml.core.workspace.Workspace)`: The Workspace to which the Datastore is to be registered.     </li><li class="args">`container_name (str, optional)`: The name of the container.     </li><li class="args">`datastore_name (str, optional)`: The name of the datastore. If not defined, the container name will be used.     </li><li class="args">`create_container_if_not_exists (bool, optional)`: Create a container, if one does not exist with the given name.      </li><li class="args">`overwrite_existing_datastore (bool, optional)`: Overwrite an existing datastore. If the datastore does not exist, it will be created.     </li><li class="args">`azure_credentials_secret (str, optinonal)`: The name of the Prefect Secret that stores your Azure credentials; this Secret must be a JSON string with two keys: `ACCOUNT_NAME` and either `ACCOUNT_KEY` or `SAS_TOKEN` (if both are defined then`ACCOUNT_KEY` is used).      </li><li class="args">`set_as_default (bool optional)`: Set the created Datastore as the default datastore for the Workspace.     </li><li class="args">`**kwargs (dict, optional)`: additional keyword arguments to pass to the Task constructor</li></ul>

|methods: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:----|
 | <div class='method-sig' id='prefect-tasks-azureml-datastore-datastoreregisterblobcontainer-run'><p class="prefect-class">prefect.tasks.azureml.datastore.DatastoreRegisterBlobContainer.run</p>(container_name=None, datastore_name=None, create_container_if_not_exists=False, overwrite_existing_datastore=False, azure_credentials_secret="AZ_CREDENTIALS", set_as_default=False)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/azureml/datastore.py#L53">[source]</a></span></div>
<p class="methods">Task run method.<br><br>**Args**:     <ul class="args"><li class="args">`container_name (str, optional)`: The name of the container.     </li><li class="args">`datastore_name (str, optional)`: The name of the datastore. If not defined, the container name will be used.     </li><li class="args">`create_container_if_not_exists (bool, optional)`: Create a container, if one does not exist with the given name.      </li><li class="args">`overwrite_existing_datastore (bool, optional)`: Overwrite an existing datastore. If the datastore does not exist, it will be created.     </li><li class="args">`azure_credentials_secret (str, optinonal)`: The name of the Prefect Secret that stores your Azure credentials; this Secret must be a JSON string with two keys: `ACCOUNT_NAME` and either `ACCOUNT_KEY` or `SAS_TOKEN` (if both are defined then`ACCOUNT_KEY` is used)     </li><li class="args">`set_as_default (bool optional)`: Set the created Datastore as the default datastore for the Workspace.</li></ul>Return:     - (azureml.data.azure_storage_datastore.AzureBlobDatastore): The registered Datastore.</p>|

---
<br>

 ## DatastoreList
 <div class='class-sig' id='prefect-tasks-azureml-datastore-datastorelist'><p class="prefect-sig">class </p><p class="prefect-class">prefect.tasks.azureml.datastore.DatastoreList</p>(workspace, **kwargs)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/azureml/datastore.py#L114">[source]</a></span></div>

Task for listing the Datastores in a Workspace.

**Args**:     <ul class="args"><li class="args">`workspace (azureml.core.workspace.Workspace)`: The Workspace which Datastores are to be listed.      </li><li class="args">`**kwargs (dict, optional)`: additional keyword arguments to pass to the Task constructor</li></ul>

|methods: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:----|
 | <div class='method-sig' id='prefect-tasks-azureml-datastore-datastorelist-run'><p class="prefect-class">prefect.tasks.azureml.datastore.DatastoreList.run</p>()<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/azureml/datastore.py#L128">[source]</a></span></div>
<p class="methods">Task run method.<br><br>**Returns**:     <ul class="args"><li class="args">`(Dict[str, Datastore])`: a dictionary with the datastore names as keys and Datastore objects as items. </li></ul></p>|

---
<br>

 ## DatastoreGet
 <div class='class-sig' id='prefect-tasks-azureml-datastore-datastoreget'><p class="prefect-sig">class </p><p class="prefect-class">prefect.tasks.azureml.datastore.DatastoreGet</p>(workspace, datastore_name=None, **kwargs)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/azureml/datastore.py#L139">[source]</a></span></div>

Task for getting a Datastore registered to a given Workspace.

**Args**:     <ul class="args"><li class="args">`workspace (azureml.core.workspace.Workspace)`: The Workspace which Datastore is retrieved.      </li><li class="args">`datastore_name (str, optional)`: The name of the Datastore. If `None`, then the default Datastore of the Workspace is returned.      </li><li class="args">`**kwargs (dict, optional)`: additional keyword arguments to pass to the Task constructor</li></ul>

|methods: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:----|
 | <div class='method-sig' id='prefect-tasks-azureml-datastore-datastoreget-run'><p class="prefect-class">prefect.tasks.azureml.datastore.DatastoreGet.run</p>(datastore_name=None)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/azureml/datastore.py#L157">[source]</a></span></div>
<p class="methods">Task run method. <br><br>**Args**:     <ul class="args"><li class="args">`datastore_name (str, optional)`: The name of the Datastore. If `None`, then the default Datastore of the Workspace is returned. </li></ul>**Returns**:     <ul class="args"><li class="args">`(azureml.core.datastore.Datastore)`: The Datastore. </li></ul></p>|

---
<br>

 ## DatastoreUpload
 <div class='class-sig' id='prefect-tasks-azureml-datastore-datastoreupload'><p class="prefect-sig">class </p><p class="prefect-class">prefect.tasks.azureml.datastore.DatastoreUpload</p>(datastore=None, relative_root=None, path=None, target_path=None, overwrite=False, **kwargs)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/azureml/datastore.py#L176">[source]</a></span></div>

Task for uploading local files to a Datastore.

**Args**:     <ul class="args"><li class="args">`datastore (azureml.data.azure_storage_datastore.AbstractAzureStorageDatastore, optional)`: The datastore to upload the files to.      </li><li class="args">`relative_root (str, optional)`: The root from which is used to determine the path of the files in the blob. For example, if we upload /path/to/file.txt, and we define base path to be /path, when file.txt is uploaded to the blob storage, it will have the path of /to/file.txt.     </li><li class="args">`path (Union[str, List[str]], optional)`: The path to a single file, single directory, or a list of path to files to eb uploaded.      </li><li class="args">`target_path (str, optional)`: The location in the blob container to upload to. If None, then upload to root.     </li><li class="args">`overwrite (bool, optional)`: Overwrite existing file(s).     </li><li class="args">`**kwargs (dict, optional)`: additional keyword arguments to pass to the Task constructor</li></ul>

|methods: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:----|
 | <div class='method-sig' id='prefect-tasks-azureml-datastore-datastoreupload-run'><p class="prefect-class">prefect.tasks.azureml.datastore.DatastoreUpload.run</p>(datastore=None, path=None, relative_root=None, target_path=None, overwrite=False)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/azureml/datastore.py#L207">[source]</a></span></div>
<p class="methods">Task run method.<br><br>**Args**:     <ul class="args"><li class="args">`datastore (azureml.data.azure_storage_datastore.AbstractAzureStorageDatastore, optional)`: The datastore to upload the files to.      </li><li class="args">`relative_root (str, optional)`: The root from which is used to determine the path of the files in the blob. For example, if we upload `/path/to/file.txt`, and we define base path to be `/path`, when `file.txt` is uploaded to the blob storage, it will have the path of `/to/file.txt`.     </li><li class="args">`path (Union[str, List[str]], optional)`: The path to a single file, single directory, or a list of path to files to eb uploaded.      </li><li class="args">`target_path (str, optional)`: The location in the blob container to upload to. If None, then upload to root.     </li><li class="args">`overwrite (bool, optional)`: Overwrite existing file(s).</li></ul>**Returns**:     <ul class="args"><li class="args">`(azureml.data.data_reference.DataReference)`: The DataReference instance for the target path uploaded</li></ul></p>|

---
<br>


<p class="auto-gen">This documentation was auto-generated from commit <a href='https://github.com/PrefectHQ/prefect/commit/n/a'>n/a</a> </br>on March 30, 2020 at 17:55 UTC</p>