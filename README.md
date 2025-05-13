# cs4843-assignment-2-hadoop-cluster-setup-and-mapreduce-programming-solved
**TO GET THIS SOLUTION VISIT:** [CS4843  Assignment 2-Hadoop Cluster Setup and MapReduce Programming Solved](https://www.ankitcodinghub.com/product/cs4843-assignment-2-hadoop-cluster-setup-and-mapreduce-programming-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;92312&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS4843&nbsp; Assignment 2-Hadoop Cluster Setup and MapReduce Programming Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
<div class="page" title="Page 1">
<div class="layoutArea">
<div class="column">
&nbsp;

<ol>
<li>Install and Setup Hadoop on your existing VMs as described in the lecture notes.</li>
<li>Download the New York City Crime Data from 2016.
<pre>    wget http://cs.utsa.edu/~plama/CS4843/NYPD_Complaint_Data_Current_YTD.csv
</pre>
The file contains 361,740 rows and 25 columns, total size 89.48 MB. The columns relevant to this assignment are shown below:
</li>
<li>Create an input directory in HDFS, and copy the downloaded New York City Crime data file to HDFS as follows:
cd $HADOOP_PREFIX

bin/hadoop fs -mkdir /hw2-input

bin/hadoop fs -put ~/NYPD_Complaint_Data_Current_YTD.csv /hw2-input/
</li>
<li>Write a MapReduce program (in Python) that will answer the following ..

(based on New York City Crime Data 2016). Run the program with only one reduce task.

Where is most of the crime happening in New York?

What is the total number of crimes reported in that location ?

What types of crime are happening in that location (show unique crime types) ?
</li>
</ol>
Reading CSV file:

The NYPD police report is a CSV file. Please note that some of the comma separated values in this file have commas embedded inside double quotes. Therefore, a simple split(“,”) function will incorrectly split those special values. In order to avoid this issue, you need to import and use Python’s CSV module as follows:

</div>
</div>
</div>
<div class="page" title="Page 2">
<div class="layoutArea">
<div class="column">
#!/usr/bin/env python2.7 from csv import reader import sys

# skip first line (the header) next(sys.stdin)

for line in reader(sys.stdin):

boro, crime = (line[13].strip(), line[7].strip()) if not boro or not crime:

<pre>       continue
     # rest of the code
</pre>
Program Execution:

(a) Test your python programs locally on your master VM before running it in the Hadoop cluster.

To use Python2.7

cat NYPD_Complaint_Data_Current_YTD.csv | python2.7 hw2-mapper.py | sort | python2.7 hw2-reducer.py

To use Python3

cat NYPD_Complaint_Data_Current_YTD.csv | python hw2-mapper.py | sort | python hw2-reducer.py

(b) After uploading the crime data to HDFS, run your program in Hadoop cluster as follows:

To use Python2.7 (assuming that you have #!/usr/bin/env python2.7 in the first line of your mapper and reducer programs).

$HADOOP_PREFIX/bin/hadoop jar $HADOOP_PREFIX/contrib/streaming/hadoop-streaming-*.jar \ -input /hw2-input \

-output /hw2-output \

-file /home/cc/hw2-mapper.py \

-mapper /home/cc/hw2-mapper.py \ -file /home/cc/hw2-reducer.py \ -reducer /home/cc/hw2-reducer.py

To use Python3 (assuming that you have #!/usr/bin/env python in the first line of your mapper and reducer programs).

$HADOOP_PREFIX/bin/hadoop jar $HADOOP_PREFIX/contrib/streaming/hadoop-streaming-*.jar \ -input /hw2-input \

-output /hw2-output \

-file /home/cc/hw2-mapper.py \

-mapper /home/cc/hw2-mapper.py \ -file /home/cc/hw2-reducer.py \ -reducer /home/cc/hw2-reducer.py \ -cmdenv LC_CTYPE=en_GB.UTF-8

</div>
</div>
</div>
<div class="page" title="Page 3">
<div class="layoutArea">
<div class="column">
Troubleshooting Tips:

</div>
</div>
<div class="layoutArea">
<div class="column">
(c) If a job is long-running, and you want to free the shell for other activities, you can let the job run in the background by using:

Ctrl-C

(d) If a job hangs (making no progress), you can fetch the job id and kill the job as follows:

<pre>   bin/hadoop job –list
</pre>
<pre>   bin/hadoop job –kill job_2014----
</pre>
(e) To troubleshoot the task that took too long or failed, take the following steps:

– Check which tasks have failed on which worker nodes by using the following command bin/hadoop job –history &lt;output-directory&gt;

for example:

– Login to one of the worker nodes where task(s) have failed and check the corresponding “stderr” file under the directory,

<pre>   /usr/local/hadoop-1.2.1/logs/userlogs
</pre>
Submission Policy and Deliverables

Only one submission per group is required. Submission must include:

<ol>
<li>MapReduce programs (python files)</li>
<li>The resulting output files of your MapReduce programs should be downloaded from HDFS and submitted as a deliverable.</li>
<li>A PDF report that includes:
<ol>
<li>Representative Screenshots of the console output when you execute your programs.</li>
<li>Describe how the work was divided among your group members.</li>
</ol>
</li>
</ol>
</div>
</div>
</div>
