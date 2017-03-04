# kaws-etcd-ebs-backup

**kaws-etcd-ebs-backup** is a program for creating snapshots of EBS volumes used to back etcd in Kubernetes clusters created by [kaws](https://github.com/InQuicker/kaws).

## Usage

Create a Kubernetes cron job to run this program on a schedule you prefer.
When run, the program will create an EBS snapshot for the volume mounted at /dev/xvdf on the instances specified by the `INSTANCE_NAMES` environment variable.
It will then delete snapshots of these volumes that are more than 7 days old.

## Configuration

Environment variables:

* `INSTANCE_NAMES` (required): a common separated list of values to be used to filter EC2 instances by their "Name" tag.

## Legal

kaws-etcd-ebs-backup is released under the MIT license.
See LICENSE for details.
