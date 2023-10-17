# AUTOMATION-AND-OPTIMIZATION-WITH-S3
Open the  Amazon S3 console .
Choose Create Bucket.
Choose a  DNS-compliant name  for your new bucket (bucket1).
Click the created bucket and Upload a new file (welcome.txt)
Choose Create Bucket.
 Choose a  DNS-compliant name  for your new bucket (bucket2).
 Click and check that the bucket is empty (no objects are there).
 Open the command prompt and configure aws
 Create a directory (folder) named ‘sample1’ and create any file inside the directory.
 
 AWS Sync command usage:

1. syncs the bucket to the local current directory
aws s3 sync . s3://bucket1

2. syncs bucket1 to bucket2. 
aws s3 sync s3://mybucket s3://mybucket2

3. syncs the current local directory to the bucket.
aws s3 sync s3://mybucket .

------------------------------------------------------------------------WE CAN USE LAMBDA FUNCTION TO TRIGGER ----------------------------------------

Bucket Creation:
1. Open the  Amazon S3 console .
2. Choose Create two Bucket.
3.  Choose a  DNS-compliant name  for your new bucket (bucket-src).
4.  Click the created bucket and Upload a new file (welcome.txt)
5. Choose Create Bucket.
6.  Choose a  DNS-compliant name  for your new bucket (bucket-dest). Click and
check that the bucket is empty (no objects are there).

7. Make sure you select a correct region. It is best not to enable public access without
the need to ‘Block all public access’. 
Lambda Function Creation:
8. Open the IAM console.

9. Create a new IAM role for the lambda function. Select ‘Author from Scratch’.
Function name is given as ‘allfile-copy’. Select ‘Python’.

10. Expand ‘Change default execution role’. Select ‘Use an existing role’. Select
‘LabRole’ from the list of roles.

11. Click ‘Create Function’.
12.  USE The python code which i mentioned in this repo.
  


14. Once you have made sure that everything is working correctly, then you can add
the automation. In ‘Function overview‘, you click Add trigger:

15. Select S3 from the list and the name of your source bucket, that is where you will
be adding files.
16. You set the event type to PUT because you only want the function to be triggered
when objects are added.
17. Click Add
18. You can test the function by adding files to S3 via the UI, or using CLI. Whenever
an object is created in source bucket, it get automatically copied to destination bucket.
