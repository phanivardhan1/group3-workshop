**Prerequisites**
cloudera quickstart running in the machine
the following services should be running <br/>
spark <br/> 
Hue <br/>
HDFS <br/>
Spark <br/>
flume <br/>

**Introduction**

**step1**:creating an empty configuration
**The command is solrctl --zk quickstart:2181/solr instancedir --generate solr_configs**

 
**step2**:editing the schema

 **step3**:uploading the configuration
  **cd /opt/examples/flume**
 **solrctl --zk quickstart:2181/solr instancedir --create live_logs ./solr_configs **

**step4**: creating your collection
 **solrctl --zk quickstart:2181/solr collection --create live_logs -s 1 **
 
  **step5**: Verify  collection in Solr by going to Hue and click Indexes

![screenshot 216](https://user-images.githubusercontent.com/31742627/48086158-c54e9780-e1c1-11e8-9ba3-7ec7e0e1e24d.png)

**step6**: To see the collection that we created live_logs click on it.

**step7**: Starting  Log Generator
**start_logs**

**step8**: You can verify that the log generator has started by running 
**tail_logs**

**step9**: to stop the log generator you can: 
**stop_logs**

![screenshot 192](https://user-images.githubusercontent.com/31742627/48085738-bca99180-e1c0-11e8-83eb-6907cf9e104d.png)


**step10**: Flume and morphlines to load the index with the real-time log data
       **flume-ng agent \
                        --conf /opt/examples/flume/conf \
                        --conf-file /opt/examples/flume/conf/flume.conf \
                        --name agent1 \
                        -Dflume.root.logger=DEBUG,INFO,console**

![screenshot 193](https://user-images.githubusercontent.com/31742627/48085997-612bd380-e1c1-11e8-812f-0f67bd262319.png)

![screenshot 194](https://user-images.githubusercontent.com/31742627/48086073-920c0880-e1c1-11e8-9614-06135f1c412f.png)


                
