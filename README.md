# SMPBR-database  
Docker composer configuration for SMPBR database stack based on TICK stack  
This stack contains services:  
- InfluxDB - Port 8086  
- Chronograf - Port 8888  
- Kapacitor - Port 9092  
- Avahi mDNS - http://smpbr_data  

Start by: `docker compose up`  

Telegraf instance on device should find running server in local network based on mDNS record.  
Telegraf must have configured same TOKEN as defined in composer file in `telegraf.d/database.conf`  


## InfluxDB
Database access  
User: reactor  
Password: growgrow  

## Chronograf
Chronograf must be configured in order to connect to InfluxDB.
Based on Influx db conf file.
- URL: http://localhost:8086
- Organization: trendbit
- Telegraf database name: telegraf
- InfluxDB v2 Auth: ON
- Token: my-super-secret-auth-token
