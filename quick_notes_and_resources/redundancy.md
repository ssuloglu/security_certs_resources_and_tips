# Redundancy

| Entity | Solution | 
|------- | -------- |  
| Disk | RAID | 
| Server | Failover Cluster | 
| Power | UPS/Generators | 
| Site | hot/warm/cold | 


## Comparison of RAID Disks 

Note that +(plus) refers to "exists", and R is abbreviation of RAID.


|     | R0 | R1 | R5 | R6 | R1+0/R0+1/R10 | 
|---- | -- | -- | -- | -- | ------------- | 
|num of drivers | 2 | 2 or more | 3 or more | 4 or more | 4 or more |
|Stripping | + | | + | + | + |  
|Mirroring | | + |  |  | + | 
|Parity |  | | + | + |  |
|num of disks can be failed | 0 | 1 | 1 | 2 | 1 | 
|Fault Tolerance |  | + | + | + | + |


## Failover Cluster
* number of servers: 2 or more servers
* types: 
	* active/passive: when active server is down, inactive server takes over  
	* active/active
* load balancers (hw/sw) + Virtual IP

