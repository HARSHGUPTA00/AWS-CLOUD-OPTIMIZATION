# AWS Cloud Cost Optimization - Identifying Stale Resources

# Identifying Stale EBS Snapshots
In this project, we'll create a Lambda function that identifies EBS snapshots no longer associated with any active EC2 instance and deletes them to save on storage costs.

Description:
The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

# Create a Stale Resources 

- First Create an Ec2 Iantance with a volume
- Then Create an EBS snapshot of the volume
 
# Create a Lambda Function and  IAM permission

- Create a Lambda>function>createFunction
- Provide a name and the Runtime python3.10 and create
- Add the Python code into the lambda function then deploy and test but it fails
- Because the default lambda function execution time is 3 seconds we will increase it 10 seconds
- go to the configuration tab and edit execution time to 10 seconds
- add roles and attach the permission go to configuration>>Permissions>>Attach custom policy
- Create a custom policy and add service EC2 and actions snapshot described, snapshot delete.
- Create one more custom policy and add service EC2. Action will provide a description of EC2 and the described volume.
- Then delete the EC2 instance and default EBSvolume Then you will notice that the snapshot is there.
- Then run the lambda function Then you will notice your snapshot will be deleted.
- successfully identified stale resources and deleted them Automatically.
  


  





