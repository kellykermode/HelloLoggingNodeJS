## Generate load to your app
Once you have deployed your app to App Engine, you can look at the logs using generated traffic. 

To generate load to your App Engine NodeJS app, use the following commands:
1. Grab the URL for your app:

``` bash
gcloud app browse 
```
2. Copy the URL 

``` bash
URL=[url_you_copied_here]
```
``` bash
echo $URL
```
Make sure you get your correct URL with the echo command. If not, you may need to recreate the variable. 

3. Generate load with different results: 

#### General Load with Expected Results - Quick Traffic
``` bash
while true; \
do curl -s $URL \
-w '\n' ;sleep .1s;done
```
#### General Load with Expected Results - 1-second Traffic
``` bash
while true; \
do curl -s $URL \
-w '\n' ;sleep 1s;done
```

#### General Load with Random Error Results 
``` bash
while true; \
do curl -s $URL/random-error \
-w '\n' ;sleep .1s;done
```

#### General Load with Random Score Results
``` bash
while true; \
do curl -s $URL/score \
-w '\n' ;sleep .1s;done
```
## Head Back to the Console 
View the logs and metrics in [Logging](https://console.cloud.google.com/logs) and [Monitoring](https://console.cloud.google.com/monitoring). 
