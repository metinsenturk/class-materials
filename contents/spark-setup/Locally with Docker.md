# Docker

This tutorial shows how to install Apache Spark using Docker in the simplest way from pip. Since Apache Spark has a dependency to Java, we need to install that along with the pyspark.

Build image using the [Dockerfile](with_pip.dockerfile) from with below.

> docker build -f "contents/spark-setup/with_pip.dockerfile" -t pyspark-simple

Run a container from the image. Driver UI is available at http://localhost:4040/jobs/.

> docker run -d -p 4040:4040 pyspark-simple

Sample commands to run in the shell.

``` py
# get spark master setup
spark.conf.get('spark.master')
# get app name
spark.conf.get('spark.app.name')

# read a text file
text_file = spark.read.text('/usr/local/lib/python3.9/site-packages/README.txt')

# some actions
text_file.first()
text_file.count()    
text_file.show()    
```