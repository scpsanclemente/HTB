
---
fileClass: Machine
---

<p align="center"> <img src= "https://www.hackthebox.com//storage/avatars/9d232b1558b7543c7cb85f2774687363.png"> </p>

#machine

## Operation system - Windows
<img style = "max-width:70px" src = "app://local//home/kali/HTNotes/HTB/.res/Windows.png">

## Metadata

|                       |   |
| ----------------      | - |
| ID                    |634 |
| Name                  |Administrator |
| Active                |✅  |
| User Flag             |❌ |
| Root Flag             |❌|
| Difficulty Text       |Medium  |
| Stars                 |⭐️ 4.7 |
| Created Note          |12/17/24 |
| Published             |11/09/24 |
| tags                  | |

<p style = "display:none">
id:: 634
active:: True
name:: Administrator
os::Windows
user_flag:: False
root_flag:: False
difficulty_text:: Medium
stars:: 4.7
created:: 12/17/2024
published:: 11/09/24
avatar:: /storage/avatars/9d232b1558b7543c7cb85f2774687363.png
tags:: 
</p>

## Statistics


```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: Radar

#-----------------#
#- chart data    -#
#-----------------#
data:
  - item: "ENUM"
    user: "user"
    score: 7.7
  - item: "REAL"
    user: "user"
    score: 7.1
  - item: "CVE"
    user: "user"
    score: 6.3
  - item: "CUSTOM"
    user: "user"
    score: 3.7
  - item: "CTF"
    user: "user"
    score: 2.9
  - item: "ENUM"
    user: "author"
    score: 0
  - item: "REAL"
    user: "author"
    score: 0
  - item: "CVE"
    user: "author"
    score: 0
  - item: "CUSTOM"
    user: "author"
    score: 0
  - item: "CTF"
    user: "author"
    score: 0

#-----------------#
#- chart options -#
#-----------------#
options:
  xField: "item"
  yField: "score"
  seriesField: "user"
  meta:
    score:
      alias: "Score"
      min: 0
      nice: true
  xAxis:
    line: null
    tickLine: null
  yAxis:
    label: false
    grid:
      alternateColor: "rgba(0, 0, 0, 0.04)"
  point: []
  area: []
```



### User rating


```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: Column

#-----------------#
#- chart data    -#
#-----------------#
data:
    - folder: "PIECE OF CAKE"
      count: 304
     
    - folder: "VERY EASY"
      count: 256

    - folder: "EASY"
      count: 1186
      
    - folder: "NOT TO EASY"
      count: 755
      
    - folder: "MEDIUM"
      count: 626
     
    - folder: "A BIT HARD"
      count: 170
      
    - folder: "HARD"
      count: 77
      
    - folder: "EXTREMELY HARD"
      count: 16
      
    - folder: "INSANE"
      count: 4
      
    - folder: "BRAINFUCK"
      count: 21

    

#-----------------#
#- chart options -#
#-----------------#
options:
  xField: "folder"
  yField: "count"
  padding: auto
  label:
    position: "middle"
    style:
      opacity: 0.6
      fontSize: 12
  columnStyle:
    fillOpacity: 0.5
    lineWidth: 1
    strokeOpacity: 0.7
    shadowColor: "grey"
    shadowBlur: 10
    shadowOffsetX: 5
    shadowOffsetY: 5
  xAxis:
    label:
      autoHide: false
      autoRotate: true
  meta:
    count:
      alias: "Votes"
```



```button
name Update this Machine info
type link
action obsidian://shell-commands/?vault=HTB&execute=g7sm2q030y
templater true
```

