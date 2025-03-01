# AWS Cloud Cost Optimization - Identifying Stale Resources

## Identifying Stale EBS Snapshots

In this example, we'll create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

### Description:

The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

### Deletion of Unused Resources:
The Lambda function was designed to delete unused EC2 instances, volumes, and snapshots. This ensured that resources were not left idle and incurring costs without providing any value.

### Increasing Timeout Session for Lambda Execution:
To ensure that the Lambda function had enough time to execute its tasks, I increased the timeout session. This allowed the function to complete its operations without timing out prematurely.
