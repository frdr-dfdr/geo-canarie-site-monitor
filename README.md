# HealthCheck for WSO2 - Monitoring Script:

## Monitoring categories 

This is a cron job with bash, wget and curl commands to monitor following:

1. Sites :  Monitors carbon consoles or any other http/https sites, checking for “200” status returned  
2. Services :  Monitors Admin service for WSO2 server status, checking for RUNNING return code in xml response  


## Here is a basic feature list:  
Monitors any HTTP or HTTPS URL, checking for “200” status returned  
Monitors Admin service for WSO2 server status, checking for RUNNING return code in xml response  
Can be applied to multiple WSO2 Product  
Checks request fulfillment time for slow responses, not just UP/DOWN  
Sends email notification on state change (UP, SLOW, or DOWN)  
Customizable To/From notification settings  
Customizable SLOW latency threshold  
Tracks previous state change and last update to avoid multiple notifications  
Uses single text file for data storage, no DB necessary (configurable to have separate status files for Services and Sites)  


## Sample Email Response (for status changes)  

Time: 2018-06-28 00:07:56  
Site: https://localhost:9543/console/  
Status: DOWN  
Latency: 0 sec  
Previous status: UP  
Previous change: 2018-06-28 00:06:01  

Time: 2018-06-28 00:07:56  
Service: https://localhost:9543/services/ServerAdmin  
Status: DOWN  
Latency: 0 sec  
Previous status: UP  
Previous change: 2018-06-28 00:06:02  


## Sample Cronjob Definition  
*/5 * * * * root /home/username/HealthCheck.sh  
