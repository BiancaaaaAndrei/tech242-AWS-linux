# Exploring EBS Volumes in AWS Console

## Demonstration Steps on how to attach 2 EBS Volumes to one instance:

1. **Access Storage Tab:**
   - Navigate to EC2 instance.
   - Go to the Storage tab:
![Go to storage](<../../../readme-images/EBS/EBS HandsON/go to storage.png>)

2. **View Attached Volumes:**
   - Observe existing volumes.
   - Click on a volume to access the Volumes interface:
![Click on the Volume](<../../../readme-images/EBS/EBS HandsON/click on volume.png>)

3. **Create Additional Volume:**
   - Create a new volume (e.g., 2 GB, GP2 type).
   - Choose the same availability zone as the EC2 instance. To find your instance zone, go back to "Instances" > Click on your Instance > Go in the "Networking" section of your instance:
![availability zone](<../../../readme-images/EBS/EBS HandsON/availability zone.png>)

4. **Attach New Volume:**
   - After the Volume has been created, select the freshly created volume.
   - Go the "Actions" and use the "Attach Volume" action to attach it to the instance:
![Attach Volume](<../../../readme-images/EBS/EBS HandsON/Attach Volume.png>)

5. **Check Block Devices:**
   - Refresh the EC2 Storage tab of your instance.
   - Observe the new block device attached.

6. **Create Volume in a Different AZ:**
   - Create another volume in a different AZ.
   - Attempt to attach it to the same instance. What you will see is that our instance is not available because this EBS Volume is in a different availability zone.

7. **Terminate EC2 Instance:**
   - Terminate the EC2 instance.
   - Observe detachment and termination of volumes.

## Important Notes

- EBS Volumes are attached to instances and bound to specific AZs.
- Termination of EC2 instances can impact attached volumes.
- Delete on Termination attribute controls volume behavior.
- Understand how to manage volumes, detach, and delete them.
