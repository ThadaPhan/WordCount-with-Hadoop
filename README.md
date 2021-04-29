# ***MAPREDUCE DEMO IN HADOOP: WORKCOUNT PROJECT***

## ***INTRODUCTION***
* This project include:
    * 3 java file in PackageDemo package:
    <table>

    <tr>
        <td>Class</td>
        <td>Extends</td>
        <td>Implements</td>
    </tr>
    <tr>
        <td>map</td>
        <td>MapReduceBase</td>
        <td>Mapper</td>
    </tr>
    <tr>
        <td>reduce</td>
        <td>MapReduceBase</td>
        <td>Reducer</td>
    </tr>
    <tr>
        <td>runner</td>
        <td>None</td>
        <td>None</td>
    </tr>
   </table>
   
    * Note: runner class not extends or implements any class and interface, but in runner class must have a main static class*
  
 * data.txt: list of students receiving encourage learning scholarships in HCMUTE from 2018 to 2020.


## ***INSTALLATION***

* You can install this project in [WordCount with Hadoop](https://github.com/ThadaPhan/WordCount-with-Hadoop.git)

## ***BUILD***

* Step 1: Create a operation direction:
  * *mkdir operation*
* Step 2: Compiling the program in particular folder named as operation/:
  * *javac -cp $HADOOP_HOME/share/hadoop/common/hadoop-common-2.7.7.jar:$HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-client-core-2.7.7.jar:operation/:. -d operation map.java*
  * *javac -cp $HADOOP_HOME/share/hadoop/common/hadoop-common-2.7.7.jar:$HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-client-core-2.7.7.jar:operation/:. -d operation reduce.java*
  * *javac -cp $HADOOP_HOME/share/hadoop/common/hadoop-common-2.7.7.jar:$HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-client-core-2.7.7.jar:operation/:. -d operation runner.java*
* Step 3: Create WordCount.jar file:
  * *jar -cvf WordCount.jar -C operation/ .*

  Now, you have a WordCount jar file with name *WordCount.jar*

## ***DEMO***

* Step by step:
  * Step 1: Create input direction in HDFS:
    * *hdfs dfs -mkdir -p input*
  * Step 2: Put data.txt file into input in HDFS:
    * *hdfs dfs -put data.txt input*
  * Step 3: Demo WordCount
    * *hadoop jar WordCount.jar PackageDemo.runner input output*
  * Step 4: Show result
    * *hdfs dfs -cat output/part-00000*
* Instructional video: [Demo WordCount with Hadoop](youtu.be/dN8gNwBmy34)

