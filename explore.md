# TASK 3
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