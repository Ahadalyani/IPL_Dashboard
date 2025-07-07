# 🏏 IPL Data Analysis & Interactive Power BI Dashboard (2008–2022)

This repository presents a detailed **interactive IPL dashboard** built using match and ball-by-ball data from 2008 to 2022. The project uses **PostgreSQL** for backend data handling and **Power BI** for frontend visualization. Key insights include top players, match outcomes, venue stats, and team performance.

![IPL Dashboard](./68903bbb-b8e6-4f95-be03-bb352410ba47.png)

---

## 📁 Project Structure

├── ipl_matches_2008_2022.csv # Match-level data
├── ipl_ball_by_ball_2008_2022.csv # Ball-by-ball data
├── SQL QUERIES FOR IPL DATA.docx # SQL queries for table creation and data loading
├── 68903bbb-b8e6-4f95-be03-bb352410ba47.png # Dashboard screenshot
└── README.md # Project documentation


---

## 🎯 Key Features of Dashboard

### 🎖️ Title Winner
- Displays the IPL champion of the selected season.

### 🧢 Player Awards
- **Orange Cap** – Highest run scorer (e.g., MEK Hussey – 733 Runs)
- **Purple Cap** – Highest wicket taker (e.g., DJ Bravo – 32 Wickets)

### 🏏 Player Stats
#### Batting (Example: RG Sharma)
- Total Runs: 538  
- 6s: 28  
- 4s: 35  
- Strike Rate: 129.64  

#### Bowling (Example: KA Pollard)
- Wickets: 10  
- Economy: 8.89  
- Average: 29.20  
- Bowling Strike Rate: 19.70  

### 📊 Season Summary
- Total Sixes: 680  
- Total Fours: 2053  

### 📍 Venue Stats
- Match win distribution by venue
- Win result type (Runs, Wickets, Super Over)

### 🧮 Team Performance
- Total wins by each team for a selected season

---

## 🛠️ Tools & Technologies Used

| Tool           | Purpose                        |
|----------------|-------------------------------|
| Power BI       | Data visualization & dashboard |
| PostgreSQL     | Backend database               |
| SQL            | Data querying & transformation |
| Excel/CSV      | Raw dataset format             |

---

## 📂 Datasets

### `ipl_matches_2008_2022.csv`
Includes:
- Match ID, City, Date
- Teams, Toss result
- Winning team, Player of the match
- Match method, Margin, Umpires

### `ipl_ball_by_ball_2008_2022.csv`
Includes:
- Match ID, Inning, Over, Ball
- Batter, Bowler, Non-striker
- Runs (batsman + extras), Wicket type, Fielders involved

---

## 🧾 SQL Queries Summary

### 1. Table Creation

```sql
CREATE TABLE ipl_matches_2008_2022 (
    id int8 PRIMARY KEY,
    city varchar(50),
    match_date date,
    season varchar(50),
    match_number varchar(50),
    team1 varchar(50),
    team2 varchar(50),
    venue varchar(100),
    toss_winner varchar(50),
    toss_decision varchar(50),
    superover varchar(50),
    winning_team varchar(50),
    won_by varchar(50),
    margin varchar(50),
    method varchar(50),
    player_of_match varchar(50),
    umpire1 varchar(50),
    umpire2 varchar(50)
);

COPY ipl_matches_2008_2022 
FROM 'D:/ipl_matches_2008_2022.csv' 
DELIMITER ',' CSV HEADER;


### 2. Ball-by-Ball Table Creation

```sql
CREATE TABLE ipl_ball_by_ball_2008_2022 (
    id int8 NOT NULL,
    innings int8,
    overs int8,
    ball_number int8,
    batter varchar(50),
    bowler varchar(50),
    non_striker varchar(50),
    extra_type varchar(50),
    batsman_run int8,
    extras_run int8,
    total_run int8,
    non_boundry int8,
    iswicket_delivery int8,
    player_out varchar(50),
    dismisal_kind varchar(50),
    fielders_involved varchar(50),
    batting_team varchar(50)
);

COPY ipl_ball_by_ball_2008_2022 
FROM 'D:/ipl_ball_by_ball_2008_2022.csv' 
DELIMITER ',' CSV HEADER;

### 2. Ball-by-Ball Table Creation

```sql
CREATE TABLE ipl_ball_by_ball_2008_2022 (
    id int8 NOT NULL,
    innings int8,
    overs int8,
    ball_number int8,
    batter varchar(50),
    bowler varchar(50),
    non_striker varchar(50),
    extra_type varchar(50),
    batsman_run int8,
    extras_run int8,
    total_run int8,
    non_boundry int8,
    iswicket_delivery int8,
    player_out varchar(50),
    dismisal_kind varchar(50),
    fielders_involved varchar(50),
    batting_team varchar(50)
);

COPY ipl_ball_by_ball_2008_2022 
FROM 'D:/ipl_ball_by_ball_2008_2022.csv' 
DELIMITER ',' CSV HEADER;
```

---

## 🚀 How to Use

1. Clone this repository.
2. Create the tables in PostgreSQL using the provided SQL queries.
3. Import the CSV files into the corresponding tables.
4. Connect Power BI to your PostgreSQL database.
5. Build the visuals as shown in the provided dashboard screenshot.
6. Add slicers and interactivity for Season, Player, and Team selection.

---

## 📌 Insights You Can Discover

- Player of the season (runs/wickets)
- Winning patterns by toss decision
- Most successful venues and teams
- How matches are won (by runs, wickets, or super overs)
- Trends in batting and bowling performances

---

## 🙌 Credits

- IPL data sourced from public cricket datasets.
- SQL design and transformations by [Your Name].
- Dashboard designed and developed using Power BI.

---

## 📬 Contact

**Ahad Alyani**  
📧 Email: [ahadalyani09@example.com]  
🔗 LinkedIn: [linkedin.com/in/ahad-alyani09]
