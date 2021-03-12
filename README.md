# Chapter-4 Pipelines 

## How to run Pipelines in DKube
1. Add the code repo in DKube https://github.com/intro-to-ml-with-kubeflow/intro-to-ml-with-kubeflow-examples/tree/master/ch04/code
2. Create a IDE in DKube, select the code created in step 1.

## How to run ControlStructures.ipynb

3. Replace the entire content of cell 4 in ControlStructures.ipynb with the below client code.
   
   ```
   import os
   existing_token = os.getenv("DKUBE_USER_ACCESS_TOKEN")
   client = kfp.Client(existing_token=existing_token)
   client.create_run_from_pipeline_func(conditional_pipeline, arguments={})
   ```
   
## How to run Lightweight Pipeline.ipynb 

4. Replace the line `client = kfp.Client()` in cell 4 of Lightweight Pipeline.ipynb with the below client code.
   
   ```
   import os
   existing_token = os.getenv("DKUBE_USER_ACCESS_TOKEN")
   client = kfp.Client(existing_token=existing_token)
   ```
   
5. Run all the cells in the notebook.
6. It will automatically create a pipeline run in DKube, can be viewed from Experiments section by clicking on Pipelines in DKube.

## Chapter- Data Preparation

1. Add the code repo in DKube https://github.com/intro-to-ml-with-kubeflow/intro-to-ml-with-kubeflow-examples/tree/master/data-extraction
2. Create a IDE in DKube, select the code created in step 1.
3. Go to python-notebook and follow the following steps to run MailingListDataPrep.ipynb
   - Create the pv volumes if not already existing in your cluster.
   - Create 2 pv volumes say (mailing-storage1 & simple1) with sizes "5Gi" and other with "100Mi".
   - Add the parameter volume_name in dsl.VolumeOp in cell 20
     ```
     dvop = dsl.VolumeOp(
        name="create_pvc",
        resource_name="my-pvc-2",
        size="5Gi",
        modes=dsl.VOLUME_MODE_RWO,volume_name = 'mailing-storage1')
     tldvop = dsl.VolumeOp(
        name="create_pvc",
        resource_name="tld-volume-2",
        size="100Mi",
        modes=dsl.VOLUME_MODE_RWO,volume_name = 'simple1')
       ```
4. Replace the client code with the below code :
   ```
   import os
   existing_token = os.getenv("DKUBE_USER_ACCESS_TOKEN")
   client = kfp.Client(existing_token=existing_token)

5. Run all the cells of MailingListDataPrep.ipynb and it will create a Data-Prep pipeline in DKube.

# Chapter-8 Model Inference

Adding kubeflow sample models into Dkube

## Adding tensorflow model
1. From repo create a new model repo.
2. Give a name, eg: tensorflow-kf-eg
3. Choose Model Source: GCS
4. Bucket: kfserving-samples
5. Prefix: models/tensorflow/flowers
6. Click Add Model

## Adding pytorch model
1. From repo create a new model repo.
2. Give a name, eg: pytorch-kf-eg
3. Choose Model Source: GCS
4. Bucket: kfserving-samples
5. Prefix: models/pytorch/cifar10
6. Click Add Model

## Adding sklearn model
1. From repo create a new model repo.
2. Give a name, eg: sklearn-kf-eg
3. Choose Model Source: GCS
4. Bucket: kfserving-samples
5. Prefix: models/sklearn/iris
6. Click Add Model

## Model Publish
1. From any of the model above choose a model
2. Give a name.
2. Serving images can be choose according to the framework,

## Serving images
1. Tensorflow: `ocdr/tensorflowserver:1.14`
2. PyTorch: `ocdr/pytorchserver:1.6`
3. SKlearn: `ocdr/sklearnserver:0.23.2`
