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
