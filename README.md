# 🎧 **Spotify Wrapped 2025 — Power BI Dashboard**

This project is a Power BI dashboard that replicates the style and insights of Spotify Wrapped, but with the flexibility to view listening behavior **monthly and yearly**.
The dataset used in this project was AI-generated to mimic a full year of streaming activity, including:

* Songs
* Artists
* Albums
* Genres
* Minutes listened
* Dates
* Mood
* Streams



##  Project Overview

The goal of this dashboard was to create a personalized analytics experience that shows:

* Monthly listening behavior
* Top songs, artists, genres, and albums
* Minutes streamed across different categories
* Dynamic visuals that change based on the date slicer
* An auto changing artist image using Image URL fields
* Views that closely resemble Spotify’s design style



## Dashboard Features

### 1. Monthly Navigation Panel

A custom side panel displaying all 12 months.
When a month is selected, every visual updates, revealing your listening habits for that month.

### 2. KPI Summary Cards

At the top of the report, the dashboard displays:

* Total Songs Played
* Total Albums
* Total Genres
* Total Minutes
* Total Artists

These KPIs change dynamically with the selected month.



### 3. Top Song Section

Shows:

* The top streamed song for the month
* The number of streams
* Styled in a card format with Spotifythemed typography



### 4. Top Artist Section (with Dynamic Image)

Displays:

* The top artist of the month
* Total minutes spent listening
* The artist image, which changes automatically based on the selected date

This was achieved using:

```
TOP ARTIST IMAGE =
 VAR artistimage = [top artist]
  RETURN LOOKUPVALUE(music_listening_dataset_2024[image url],
  music_listening_dataset_2024[artist],artistimage
)
```

Then displayed using the Image Viewer visual in Power BI.



### 5. Top Album Section

Shows the most played album and total minutes spent listening.



### 6. Genre Breakdown

A visual listing all genres listened to in the selected period.



### 7. Top 5 Tables

The dashboard includes three dynamic tables:

* Top 5 Songs
* Top 5 Albums
* Top 5 Artists

Each table displays Minutes Spent and Streams where applicable.

---

## Technical Highlights

###  Image URL Integration

Artist's images were inserted via an *ImageURL* column and rendered with the Simple Image visual.

---

###  DAX Measures Used

Examples include:

**Top Song Card**

```DAX
Top Song  =
[Top Song] & UNICHAR(10) &
FORMAT([Top Song Streams], "0") & " Streams"
```

**Top Artist Minutes**

```DAX
Top Artist Minutes = 
CALCULATE(SUM(music_listening_dataset_2024[Minutes_Listened]),
 music_listening_dataset_2024[Artist] = [Top Artist])
```

**Top Song Streams**

```DAX
top song streams =
 VAR songname = [top song]
  RETURN CALCULATE(SUM(music_listening_dataset_2024[streams]), 
  music_listening_dataset_2024[song] = songname)
```

---

## Design Theme

The dashboard uses:

* A dark green, neon, and black color palette similar to Spotify
* Rounded cards
* Custom background design
* Clean typography
* Centered circular artist image for aesthetic emphasis


--

Image of the dashboard

<img width="994" height="557" alt="Image" src="https://github.com/user-attachments/assets/4173cc47-2788-4a91-9ed7-759f6c8fc02f" />
---

#### Interact with the dashboard here 👇

    

https://tinyurl.com/2n55mtsn



---
linkedln - Sandra Amalu

Email - chinnysandra77@gmail.com

