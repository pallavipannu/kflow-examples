# Chapter-4 Pipelines 
## How to run Pipelines in DKube
1. Add the code repo in DKube https://github.com/pallavi-pannu-oc/kflow-examples/tree/main/pipelines
2. Create a IDE in DKube, select the code created in step 1.
3. Replace the client code with the below code in your notebooks.
   ```
   import os
   existing_token = os.getenv("DKUBE_USER_ACCESS_TOKEN")
   client = kfp.Client(existing_token=existing_token)
   ```
   
4. Run all the cells in the notebook.
5. It will automatically create a pipeline run in DKube, can be viewed from Experiments section by clicking on Pipelines in DKube.
