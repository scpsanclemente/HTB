
---
fileClass: Machine
---

<p align="center"> <img src= "https://www.hackthebox.com//storage/avatars/f96160a20e9cf0138885238444b47404.png"> </p>

#machine

## Operation system - Linux
<img style = "max-width:70px" src = "app://local//home/kali/HTNotes/HTB/Machines/Sightless/../../.res/Linux.png">

## Metadata

|                       |   |
| ----------------      | - |
| ID                    |624 |
| Name                  |Sightless |
| Active                |✅  |
| User Flag             |❌ |
| Root Flag             |❌|
| Difficulty Text       |Easy  |
| Stars                 |⭐️ 3.4 |
| Created Note          |11/19/24 |
| Published             |09/07/24 |
| tags                  | |

<p style = "display:none">
id:: 624
active:: True
name:: Sightless
os::Linux
user_flag:: False
root_flag:: False
difficulty_text:: Easy
stars:: 3.4
created:: 11/19/2024
published:: 09/07/24
avatar:: /storage/avatars/f96160a20e9cf0138885238444b47404.png
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
    score: 6.4
  - item: "REAL"
    user: "user"
    score: 5.3
  - item: "CVE"
    user: "user"
    score: 5.3
  - item: "CUSTOM"
    user: "user"
    score: 4.7
  - item: "CTF"
    user: "user"
    score: 4.7
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
      count: 679
     
    - folder: "VERY EASY"
      count: 999

    - folder: "EASY"
      count: 3111
      
    - folder: "NOT TO EASY"
      count: 1868
      
    - folder: "MEDIUM"
      count: 1182
     
    - folder: "A BIT HARD"
      count: 666
      
    - folder: "HARD"
      count: 444
      
    - folder: "EXTREMELY HARD"
      count: 135
      
    - folder: "INSANE"
      count: 38
      
    - folder: "BRAINFUCK"
      count: 120

    

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

