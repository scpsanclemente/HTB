
---
fileClass: Machine
---

<p align="center"> <img src= "https://www.hackthebox.com//storage/avatars/6f4647030d6aadc676b8d8a459de344f.png"> </p>

#machine

## Operation system - Linux
<img style = "max-width:70px" src = "app://local//home/kali/HTNotes/HTB/.res/Linux.png">

## Metadata

|                       |   |
| ----------------      | - |
| ID                    |636 |
| Name                  |Alert |
| Active                |✅  |
| User Flag             |❌ |
| Root Flag             |❌|
| Difficulty Text       |Easy  |
| Stars                 |⭐️ 4.5 |
| Created Note          |11/26/24 |
| Published             |11/23/24 |
| tags                  | |

<p style = "display:none">
id:: 636
active:: True
name:: Alert
os::Linux
user_flag:: False
root_flag:: False
difficulty_text:: Easy
stars:: 4.5
created:: 11/26/2024
published:: 11/23/24
avatar:: /storage/avatars/6f4647030d6aadc676b8d8a459de344f.png
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
    score: 7
  - item: "REAL"
    user: "user"
    score: 5.4
  - item: "CVE"
    user: "user"
    score: 6.4
  - item: "CUSTOM"
    user: "user"
    score: 3.6
  - item: "CTF"
    user: "user"
    score: 4.6
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
      count: 148
     
    - folder: "VERY EASY"
      count: 130

    - folder: "EASY"
      count: 340
      
    - folder: "NOT TO EASY"
      count: 246
      
    - folder: "MEDIUM"
      count: 141
     
    - folder: "A BIT HARD"
      count: 53
      
    - folder: "HARD"
      count: 45
      
    - folder: "EXTREMELY HARD"
      count: 14
      
    - folder: "INSANE"
      count: 2
      
    - folder: "BRAINFUCK"
      count: 5

    

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

