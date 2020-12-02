

# Operationalizing Machine Learning

In this project I have registered the dataset and then run autoML on that dataset after that I have deployed the best performing model. Then I have enabled insight logs against the endpoint and then try to consume that endpoint. I also performed some loaded testing and created a dashboard using swagger. 

## Architectural Diagram
![Design](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/check.svg)


## Key Steps
1. **Create an experiment using AutoML, register the dataset, configure a compute cluster, and use that cluster to run the experiment. On successfull completion best performing model will be returned.**

![Registered Dataset](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/2.PNG)
![Completed Experiment](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/3.PNG)
![Best Model Summary](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/4.PNG)
![Best Model Details](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/5.PNG)

2. **Then Deploy the best performing model.**

3. **Then Enable Log insights of the endpoint.**

![Application Insights Enabled In Deployed Model](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/8.PNG)
![Logs In Bash](https://github.com/Sabyh/nd00333_AZMLND_C2/blob/master/7.PNG)

4. **Make documentation of deployed endpoint using swagger.**

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
Maybe try deploying some other model.
