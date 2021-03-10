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
