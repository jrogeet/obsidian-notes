## Bubble sort
Arrange the following to ascending order( swapping technique)
![[Pasted image 20220913090728.png]]
`Compared the data adjacent to each other from left to right. Which is Lower? (swap if needed)`


| 16   | 17   | 7   | 9  | 6  |
| --- | --- | --- | --- | --- |
| 16   | 7   | 17   | 9   | 6   |
| 16   | 7   | 9   | 17   | 6   |
|  16   |  7    |  9   |   6  |  17   |

![[Pasted image 20220913092026.png]]

![[Pasted image 20221011091248.png]]
| Vortex | Shortest distance from A | Previous Vortex |
| ------ | ------------------------ | --------------- |
| `A`      | 0                        |                 |
| `B `     | 1                        | A               |
| `C`      | 7                        | B               |
| `D`      | 2                        | A               |
| `E`      | 6                        | B or D          |
| `F`      | 5                        | A               |
| `G`      | 7                        | F               |
| `H`       |    9                      |    E             |
