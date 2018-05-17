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
  
  
