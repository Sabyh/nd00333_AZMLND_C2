

# Operationalizing Machine Learning

In this project I have registered the dataset and then run autoML on that dataset after that I have deployed the best performing model. Then I have enabled insight logs against the endpoint and then try to consume that endpoint. I also performed some loaded testing and created a dashboard using swagger. 

## Architectural Diagram
![Design](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/check.svg)


## Key Steps
1. **Create an experiment using AutoML, register the dataset, configure a compute cluster, and use that cluster to run the experiment. On successfull completion best performing model will be returned.**

For registering dataset I have first go to dataset and click on create dataset from web.
![Registering Dataset step 1:](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/registered-dataset3.PNG)

Then I have pasted the url in the web url text box and typed a name for the dataset and hit next.
![Registering Dataset step 2:](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/registered-dataset4.PNG)

Then in column headers I changed the value to "Use headers from the first file".
![Registering Dataset step 3:](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/registered-dataset5.PNG)

Final result
![Final result](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/datasets.PNG)

After that I went to automl and selected the registered dataset and configured automl first create a compute for running automl run and then tell automl to use classification models, exit criteria to 1 and concurrent execution to 5.
![AutoML experiment](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/experiment-completed.PNG)


![Registered Dataset](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/2.PNG)
![Completed Experiment](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/3.PNG)
![Best Model Summary](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/4.PNG)
![Best Model Details](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/5.PNG)

2. **Then Deploy the best performing model.**

Then I deployed the best performing Model.


3. **Then Enable Log insights of the endpoint.**

I have enabled logs using logs.py script in which I have used "service.update(enable_app_insights=True)" to enable the logs in the deployed model endpoint.

This is the response I got after running logs.py
![log.py](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/logs-running.PNG)

This is the screen shot of my script
![log.py script](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/enable-log.PNG)


![Application Insights Enabled In Deployed Model](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/8.PNG)
![Logs In Bash](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/7.PNG)

4. **Make documentation of deployed endpoint using swagger.**
For setting up swagger I have first downloaded swagger.json file from deployed model endpoint and then I have pasted the swagger.json file in the folder where my script resides. 

Then I have run serve.py script which serves our json using python script. Below is the screen shot of serve.py result. 
![serve result](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/swagger-json.PNG)

Then I have pasted the url of json served using serve.py to swagger which is running on port 9000 and then I have checked the /score endpoint.
![Swagger API detail](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/swagger-info.PNG)

Below is the screen shot of scripts running to use swagger
![Swagger running](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/swagger-running.PNG)

![Swagger API Documentation](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/9.PNG)
![Swagger APIS json](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/10.PNG)

5. **Consume the model endpoints and show benchmarks for the endpoint.**

![Endpoing Output](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/11.PNG)
![Benchmarks 1](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/12.PNG)

6. **Use Jupyter Notebook to create, publish and consume a pipeline.**

![Dataset](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/2.PNG)
![Published Pipeline Overview](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/16.PNG)
![Run Details](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/15.PNG)
![Pipeline Created](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/20.PNG)
![Pipeline Endpoint](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/19.PNG)
![Scheduled Run](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/21.PNG)

## Screen Recording
[Link to screen recording](https://drive.google.com/file/d/10HCKoCkYEO-xW9_hR9LKix70nrdCHYZ-/view)

## Standout Suggestions
Maybe try deploying some other model. for the future I would also love to consume my endpoint using postman and will also love to do load testing from postman as there is a feature in postman for that. 
