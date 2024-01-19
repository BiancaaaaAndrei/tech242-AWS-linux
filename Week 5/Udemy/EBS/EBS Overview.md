# Understanding EBS Volumes in AWS

## EBS Volume Overview

- **EBS** (Elastic Block Store)
- A network drive attachable to running instances.
- Persists data even after instance termination.
- Can only be mounted to one instance at a time.
- Bound to a specific availability zone (AZ).
- Think of it as a network USB stick.

## Key Characteristics

- Network drive, not a physical drive.
- Network communication between instance and volume.
- Can be detached and attached quickly.
- Provision capacity in advance.
- Billed for provisioned capacity.
- Capacity and IOPS can be increased over time.

## Diagram Overview
![ebs volume example](<../../../readme-images/EBS/ebs volume example.png>)

- **Attachment to Instances:**
  - Each EC2 instance can have its own EBS Volume.
  - EBS Volumes cannot be attached to multiple instances simultaneously at CCP level.

- **Availability Zone Binding:**
  - EBS Volumes are linked to a specific availability zone.
  - Instances and volumes should be in the same availability zone.

- **Unattached EBS Volumes:**
  - EBS Volumes can be created and left unattached.
  - Can be attached on demand, providing flexibility.

## Delete on Termination Attribute

![EBS Delete on termination attribute](<../../../readme-images/EBS/ebs delete.png>)

- By default, as we can see, the root EBS Volume is deleted alongside the instance being terminated- so it's enabled.

- By default, any other attached EBS Volume is not deleted because it's disabled by default.

- But obviously as we can see in this UI, we can control if you want to enable or disable delete on termination.

