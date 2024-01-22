# EBS Snapshots in AWS

## Overview

- EBS Snapshots are backups capturing the state of EBS Volumes.
- Snapshots allow volume restoration, even after termination.
- Detaching volumes before snapshot creation is recommended for cleanliness.

## Use Cases

![Snapshots](<../../../readme-images/EBS/EBS Snapshots.jpeg>)

- **Backup and Restore:**
  - Snapshots serve as backups, restoring volumes as needed.

- **Cross-AZ or Cross-Region Transfer:**
  - Snapshots enable data transfer across availability zones or regions.

## Key Features

1. **EBS Snapshot Archive:**
   - Move snapshots to a cheaper archive tier.
   - Archive tier is 75% cheaper.
   - Takes 24 to 72 hours for restoration.

2. **Recycle Bin for EBS Snapshots:**
   - Set up a recycle bin for deleted snapshots.
   - Specify a retention period for snapshots in the bin (from 1 day to 1 year).

![Snapshots Feature 1 ](<../../../readme-images/EBS/Snapshots Feature 1.jpeg>)


## Best Practices

- **Detach Before Snapshot (Recommended):**
  - Detaching volumes before snapshot creation is recommended for cleanliness.

- **Cross-AZ Transfer:**
  - Use snapshots to move data across availability zones.
  
- **Cost Optimization:**
  - Utilize EBS Snapshot Archive for less critical data to save costs.
  - Set up the recycle bin for additional protection against accidental deletions.

## Conclusion

EBS Snapshots provide backup and transfer capabilities for EBS Volumes, with best practices enhancing data management and cost-effectiveness.
