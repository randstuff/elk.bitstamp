
ELK stack for bitstamp 
=======================

## What's this stuff ?

I wanna experiment ELK stack in docker and because I like to play with crypto currency I created this dashboard to monitor the bitstamp market using their public API.

Note you will need the vcure script to collect and archive the data retrieve from bitstamp. ([Available here](https://github.com/randstuff/vcure) 

You don't like ? Improve it.
I am not an ELK master. That's just a quick (and dirty) test I want share. 

## Quick help : 

First you need to run the ELK stack : 

```
  docker-compose up -d

  # show logs
  docker-compose logs -f
```

Then if your ELK stack is up and running, You can use the vcure.sh to collect and archive data from bitstamp : 

```
  ./vcure.sh -c 
```
Note that the vcure script is available here :
Finally, use filebeat to index the data (version 5.6.3) : 

```
  ./filebeat -e -c [path]/filebeat/virtcur.yaml
```

## Kibana dashboard : 

![Dashboard screenshot](/randstuff/elk.bitstamp/blob/master/screenshot.png?raw=true "Dashboard screenshot")


An export of my dashboard is available on ./kibana/dashboard/ including :

 - An index mapping export
 - A search export 
 - A visualization export :


## Note / reminder  

On ubuntu this could be usefull to start your the redis database : 

```
  sysctl -w vm.max_map_count=262144  

```


