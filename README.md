# AWS Cloud Cost Optimization - Identifying Stale Resources

## Identifying Stale EBS Snapshots

In this example, we'll create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

### Description:

The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

### Deletion of Unused Resources:
The Lambda function was designed to delete unused EC2 instances, volumes, and snapshots. This ensured that resources were not left idle and incurring costs without providing any value.

### Increasing Timeout Session for Lambda Execution:
To ensure that the Lambda function had enough time to execute its tasks, I increased the timeout session. This allowed the function to complete its operations without timing out prematurely.

### Adding Permissions:
I added the necessary permissions to the Lambda function's IAM role to ensure it could perform the required operations on EC2 instances and EBS snapshots.

### Cost Efficiency:
By automating the deletion of unused resources, this project helps reduce AWS costs significantly. It ensures that resources are utilized efficiently and that unnecessary expenses are avoided.

### Conclusion
This project demonstrates how AWS Lambda can be used to optimize AWS costs by automating the management of EBS snapshots and EC2 instances. By implementing similar strategies, organizations can streamline their cloud operations and enhance cost efficiency.
