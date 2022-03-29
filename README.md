# Day 2, Lab 4 - Batch inference

Batch Transform in Amazon SageMaker is used when you need any of the following: 
* Preprocess datasets to remove noise or bias that interferes with training or inference from your dataset.
* Get inferences from large datasets.
* Run inference when you don't need a persistent endpoint.
* Associate input records with inferences to assist the interpretation of results

When a batch transform job starts, SageMaker initializes compute instances and distributes the inference or preprocessing workload between them. Batch Transform partitions the Amazon S3 objects in the input by key and maps Amazon S3 objects to instances. When you have multiples files, one instance might process input1.csv, and another instance might process the file named input2.csv. If you have one input file but initialize multiple compute instances, only one instance processes the input file and the rest of the instances are idle.

### Choosing Your Deployment Option


|                     |       Scaling                     | Management  | Cost                                        | Latency                          |
| ------------------- | ----------------------------------| ----------- | ------------------------------------------- | -------------------------------- |
| Sagemaker endpoints | Autu-scaling enabled              | AWS-Managed | Higher - Cluster always on                  | Lowest(always on)                |
| Batch               | Configure size of cluster per run | AWS-managed | Lower - Cluster is decommissioned after use | 3-4 wait time (cluster creation) |


## Prepare environment for Lab

1. Download content from Github to Notebook. In the SageMaker notebook, click on the **Launch Terminal in current SageMaker Image** icon. The kernel must be fully started (the circle on the right next to the Share button must be empty) to be able to click on the icon.
![image](https://static.us-east-1.prod.workshops.aws/public/efba5343-6e05-478c-96d9-9f5a094e69a3/static/prerequisites/image36.png)


2. In the terminal, type the following command:
`git clone https://github.com/bizzelicious/sm-immersionday-InferencePipeline.git`


3. After completion of step 2 you will have **sm-immersionday-InferencePipeline** folder created in left panel of the studio. Start the lab by opening the folder and the file `linear_learner_multi_model_endpoint_inf_pipeline.ipynb`. Follow the lab instructions in the Notebook.

