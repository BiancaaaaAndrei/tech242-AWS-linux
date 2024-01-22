# EBS Snapshots and Management

## Creating a Snapshot

1. **Creating a Snapshot from a GP2 EBS Volume:**
   - Navigate to the EC2 console.
   - Locate the desired EBS volume under "Volumes."
   - Select the volume and click on "Actions."
   - Choose "Create snapshot."
![Create snapshot](<../../../readme-images/EBS/Create snapshot.png>)
   - Provide a description (e.g., DemoSnapshots).
   - Click "Create snapshot."

## Managing Snapshots

1. **Viewing Snapshots:**
   - In the EC2 console, navigate to "Snapshots."
   - View a list of all snapshots, including details like completion status and availability.

2. **Copying Snapshots to Another Region:**
   - Right-click on a snapshot and choose "Copy Snapshots."
   - Select the destination region for the snapshot copy.
   - Useful for implementing a Disaster Recovery Strategy or backing up data in another region.

3. **Restoring a Volume from a Snapshot:**
   - Right-click on a snapshot and choose "Create volume from snapshots."
   - Specify volume details (e.g., size, volume type, AZ).
   - Optionally encrypt the volume and add tags.
   - Click "Create volume."

4. **Recycle Bin for Snapshots:**
   - Protects snapshots from accidental deletion.
   - Create a Retention Rule (e.g., DemoRetentionRule):
     - Select "EBS Snapshots."
     - Apply to all resources and set retention duration (e.g., one day).
     - Choose Rule Lock Setting (e.g., unlocked).
     - Click "Create Retention Rule."
   - View resources in the Recycle Bin.

## Storage Tiers and Archiving Snapshots

1. **Archiving Snapshots:**
   - Change the storage tier by archiving a snapshot.
   - Move the snapshot to a different pricing level.
   - Archiving snapshots comes with a 24 to 72 hours restoration period.

2. **Deleting Snapshots and Recycle Bin:**
   - Delete snapshots, and they move to the Recycle Bin.
   - Prior, snapshots were permanently deleted.
   - View deleted snapshots in the Recycle Bin.
   - Recover deleted snapshots from the Recycle Bin.

## Considerations and Practical Use Cases

- Snapshots allow efficient backup and recovery.
- Copying snapshots between regions supports data transfer and global infrastructure utilization.
- The Recycle Bin prevents accidental snapshot deletions.
- Archiving snapshots provides cost optimization with a trade-off of longer restoration times.

## Notes

- Stress the importance of using EBS snapshots for data protection.
- Demonstrate the versatility of snapshots in supporting disaster recovery strategies and cross-region data transfers.
- Highlight the Recycle Bin as a valuable safety net for managing snapshots.
- Discuss the storage tier options and trade-offs, emphasizing the benefits of archiving for cost-saving.
