# Comparison of RAID Disks 

Note that +(plus) refers to "exists", and R is abbreviation of RAID.


|     | R0 | R1 | R5 | R6 | R1+0/R0+1/R10 | 
|---- | -- | -- | -- | -- | ------------- | 
|num of drivers | 2 | 2 or more | 3 or more | 4 or more | 4 or more |
|Stripping | + | | + | + | + |  
|Mirroring | | + |  |  | + | 
|Parity |  | | + | + |  |
|num of disks can be failed | 0 | 1 | 1 | 2 | 1 | 
|Fault Tolerance |  | + | + | + | + |
