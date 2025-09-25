## TASK 3
1. 36860 lines, 4 columns
> wc -l clean_dialog.csv
2. 
    "title": title of the episode  
    "writer": writer of the episode  
    "pony": speaker (pony who is saying the line)  
    "dialog": content of the line/speech
> head clean_dialog.csv
3. 196 episodes
> awk -F, '{print $1}' clean_dialog.csv | sort | uniq | wc -l
(did -1 since b/c it included the header in the count)
4. sometimes multiple speakers (ex: "Narrator and Twilight Sparkle)
> less clean_dialog.csv

## TASK 4
Twilight Sparkle: 4770 (12.94%)  
Rarity: 2682 (7.27%)  
Pinkie Pie: 2880 (7.81%)  
Rainbow Dash: 3154 (8.56%)  
Fluttershy: 2116 (5.74%)
> awk 'BEGIN {FPAT = "([^,]*)|(\"[^\"]+\")"} $3 ~ /[pony name]/ {count++} END {print count}' clean_dialog.csv