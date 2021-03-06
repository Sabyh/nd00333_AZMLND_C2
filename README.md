

# Operationalizing Machine Learning

In this task I have enrolled the dataset and afterward run autoML on that dataset after that I have sent the best performing model. At that point I have empowered knowledge logs against the endpoint and afterward attempt to devour that endpoint. I likewise played out some stacked testing and made a dashboard utilizing strut. The dataset is about bank showcasing in which it contain a few subtleties of the clients like credit taken or not indicated as "advance" section and different subtleties like age, work title, conjugal status. The objective is to anticipate y section utilizing different highlights given in dataset we initially accomplish it utilizing autoML which do alot of preparing himself. This is essentially an order issue in which we need to foresee if a client will purchase an advancement offer.

## Architectural Diagram
![Design](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/Architecture-diagram.jpg)


## Key Steps
1. **Create an experiment using AutoML, register the dataset, configure a compute cluster, and use that cluster to run the experiment. On successfull completion best performing model will be returned.**

For registering dataset I have first go to dataset and click on create dataset from web.
![Registering Dataset step 1:](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/registered-dataset3.PNG)

Then I have pasted the url in the web url text box and typed a name for the dataset and hit next.
![Registering Dataset step 2:](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/registered-dataset4.PNG)

Then in column headers I changed the value to "Use headers from the first file".
![Registering Dataset step 3:](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/registered-dataset5.PNG)

Final result
![Final result Registered Dataset](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/datasets.PNG)

After that I went to automl and selected the registered dataset and configured automl first create a compute for running automl run and then tell automl to use classification models, exit criteria to 1 and concurrent execution to 5.
![AutoML experiment](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/experiment-completed.PNG)


![Best Model Summary](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/4.PNG)
![Best Model Details](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/5.PNG)

2. **Then Deploy the best performing model.**

Then I deployed the best performing Model. You can see in the screen shot that it is deployed.
![Best performing model Deployed](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/best-performing-model.PNG)

3. **Then Enable Log insights of the endpoint.**

I have enabled logs using logs.py script in which I have used "service.update(enable_app_insights=True)" to enable the logs in the deployed model endpoint.

This is the response I got after running logs.py
![log.py](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/logs-running.PNG)

This is the screen shot of my script
![log.py script](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/enable-log.PNG)

![Application Insights Enabled In Deployed Model](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/8.PNG)

4. **Make documentation of deployed endpoint using swagger.**
For setting up swagger I have first downloaded swagger.json file from deployed model endpoint and then I have pasted the swagger.json file in the folder where my script resides. 

Then I have run serve.py script which serves our json using python script. Below is the screen shot of serve.py result. 
![serve result](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/swagger-json.PNG)

Then I have pasted the url of json served using serve.py to swagger which is running on port 9000 and then I have checked the /score endpoint.
![Swagger API detail](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/swagger-info.PNG)

Below is the screen shot of scripts running to use swagger
![Swagger running](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/swagger-running.PNG)


5. **Consume the model endpoints and show benchmarks for the endpoint.**

For consuming the model I have pasted my score url and primary key in the endpoint.py file.
![Endpoint script](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/endpoint.PNG)

Then I have checked that whether I have az installed and then I have run endpoint.py in the command line which gave me the following result.
![Endpoint result](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/endpoint2.PNG)


![Benchmarks 1](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/12.PNG)

6. **Use Jupyter Notebook to create, publish and consume a pipeline.**

![Dataset](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/2.PNG)
![Published Pipeline Overview](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/pipeline-status3.PNG)
![Run Details](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/15.PNG)
![Pipeline Created](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/20.PNG)
![Pipeline Endpoint](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/19.PNG)
![Scheduled Run](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/21.PNG)
![RunDetails Widget](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/runDetail.PNG)

## Screen Recording
[Link to screen recording](https://drive.google.com/file/d/11XMsGRz7bdQnORH0zpfNJrMTUQ9BNXD8/view)

## Standout Suggestions

For future work, I would propose making further changes to the AutoML step of the pipeline. There are a ton of settings included and making changes to them could improve the hunt space and help locate a far better model arrangement. There are likewise extra advances that could be added to the pipeline, maybe doing some dataset cleanup or highlight designing before the AutoML step, or doing extra strides after the AutoML step has finished. I would recommend you all to search for some different arrangements for labs as opposed to utilizing RDP gateway as it is irritating and bridle your advancement. 

Finally, I would accept the enlisted model as an Artifact with, for instance, Azure DevOps, and make a Continuous Deployment pipeline to consistently have it prepared with the Endpoint everytime another model is logged. Furthermore, to go much further, it'd be ideal to have each git-commit order to trigger a Continuous Integration pipeline, that would then enroll the new form of the model, shutting the DevOps cycle. This would help us automating the whole process of deploying the model in a production environment. 


