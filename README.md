# Hadoop
Sample code for Hive, spark and sqoop
1. sqoop import \
  --connect jdbc:mysql://quickstart.cloudera:3306/retail_db \
  --connect jdbc:mysql://gateway/problem1
  --username=retail_dba \
  --password=cloudera \
  --table departments \
  --as-avrodatafile \
  --target-dir /user/cloudera/departments
  --columns "name,employee_id,jobtitle"
  --where "id > 400" 
  --where "start_date > '2010-01-01'"
  --compress \
  --compression-codec org.apache.hadoop.io.compress.SnappyCodec ( GzipCodec) \
  --fields-terminated-by '\t' 
  --lines-terminated-by '\n'

2. sqoop export
  --connect jdbc:mysql://quickstart.cloudera:3306/retail_db \
  --connect jdbc:mysql://gateway/problem1
  --username=retail_dba \
  --password=cloudera \
  --table departments \
  --export-dir /user/cloudera/departments  
  --input-fields-terminated-by '\t' 
  --input-lines-terminated-by '\n'
  
  pyspark 
--master yarn
--num-executor 6 \
--executor-cores 2 \ -- ( The num-executor * executor-memory (12) should not exceed the number of blocks )
--executor-memory 2G \
--conf spark.ui.port=12345

spark-submit \
--master yarn
--num-executor 6 \
--executor-cores 2 \ -- ( The num-executor * executor-memory (12) should not exceed the number of blocks )
--executor-memory 2G \
--conf spark.ui.port=1234
/home/cloudera/sample.py --(this is the python script to be executed as spark application with fully qualified path)
  
  
