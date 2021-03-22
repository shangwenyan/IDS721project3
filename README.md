# A Word Count Program using pyspark on AWS EMR

# How to use the code:

## 1. Clone the repository
- Clone this repo to your local machine.

## 2. Create cluster
- Log in to AWS EMR and create cluster using setting shown below

![img](http://imgur.com/Ed6DlBS.jpg)

## 3. Create private key for ssh access
- Click on "Learn how to create an EC2 key pair" to create and modify your EC2 key pair.

## 4. Upload input file on S3
- Go to S3 and create a bucket
- In the bucket, create a folder 
- Upload the input.txt file from this repo
- In permissions, tick the box for read everywhere. Nothing to do in properties
- Head forward and submit the file
- Click on the uploaded file and click the Make public button just to make sure

## 5. Create wordcount.py on the Master node
- Now on our created cluster page (Cluster list->our cluster)
- Near the "Master public DNS:" field click the SSH button
- Follow the instructions and SSH on the master node
- In /home/hadoop create wordcount.py (vi wordcount.py)
- Copy over the contents from wordcount.py in this repo
- In wordcount.py change the input file s3 url to point to input.txt in your bucket, created above

## 6. Execute wordcount.py
- Go through the code in wordcount.py and checkout what it does
- Execute the script using "spark-submit wordcount.py | tee output.txt"
- This will also generate output.txt with a copy of the logs
- You may have the output file copied to your s3 bucket by using the cmd "aws s3 cp output.txt s3://my_bucket/my_folder/"
- Out put should look like

And: 2<br>
on: 1<br>
then: 1<br>
Aberbrothok: 2<br>
bell: 1<br>
that: 1<br>
of: 2<br>
knew: 1<br>
Had: 1<br>
placed: 1<br>
Abbot: 2<br>
they: 1<br>
worthy: 1<br>
blest: 1<br>
Rock: 2<br>
Inchcape: 1<br>
the: 3<br>
The: 1<br>
perilous: 1<br>


#### Reference
- https://github.com/Aliga8or/csds-spark-emr
