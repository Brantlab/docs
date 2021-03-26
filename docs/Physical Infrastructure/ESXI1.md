# ESXI Host 1

## Why do I run this
This was one of my first "current" gen lab hosts. It has served me well for the last 5 years being an absolute unit of a machine. It has ran flawlessly during this time and continues to do so. I came from a blade system which just seemed to slurp the power down. This r710 drinks small little drinks and costs less than a dollar a day to run with its current work load. 

## Specs 

```
Manufacturer	Dell Inc.
Model	PowerEdge R710
CPU	
Logical processors	16
Processor type	Intel(R) Xeon(R) CPU E5640 @ 2.67GHz
Sockets	2
Cores per socket	4
Hyperthreading	Yes, enabled
Memory	127.99 GB
```

Local storage for the most part  
```
| Name              | Drive Type | Capacity  | Provisioned | Free      | Type  | Thin provisioning | Access |
|-------------------|------------|-----------|-------------|-----------|-------|-------------------|--------|
| FAST!             | SSD        | 931.25 GB | 394.16 GB   | 537.09 GB | VMFS6 | Supported         | Single |
| Slave 1 - Backups | Non-SSD    | 1.36 TB   | 23.75 GB    | 1.34 TB   | VMFS6 | Supported         | Single |
| Slave 1 - Drive 1 | Non-SSD    | 1.82 TB   | 1.06 TB     | 779 GB    | VMFS6 | Supported         | Single |
| Slave 1 - Drive 2 | Non-SSD    | 1.82 TB   | 232.76 GB   | 1.59 TB   | VMFS5 | Supported         | Single |
```