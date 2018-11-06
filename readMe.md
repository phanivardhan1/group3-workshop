**Prerequisites**
cloudera quickstart running in the machine
the following services should be running
Hue
HDFS
YARN
Spark

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

**step6**: To see the collection that we created live_logs click on it.

![image1](https://paste.pics/b562862c7a86b3d6e02e2a39f8d6abfc)

**step7**: Starting  Log Generator
**start_logs**

**step8**: You can verify that the log generator has started by running 
**tail_logs**

**step9**: to stop the log generator you can: 
**stop_logs**

![image2](https://paste.pics/9cb1bbc3799d0b6df9e2ae8e9dec062e)

**step10**: Flume and morphlines to load the index with the real-time log data
       **flume-ng agent \
                        --conf /opt/examples/flume/conf \
                        --conf-file /opt/examples/flume/conf/flume.conf \
                        --name agent1 \
                        -Dflume.root.logger=DEBUG,INFO,console**

![image3](https://paste.pics/cf4a8492686d951c04e4e3ee60a3823d)

![image4](https://paste.pics/a198e1b09ca5b13c6f71096047993fdd)
                
