## **Relational Schema**

1. **NOCs Table**

```Scss
scss
Copy code
NOCs(noc_code, country, country_long)
PK: noc_code

```

1. **Athletes Table**

```Scss
scss
Copy code
Athletes(athlete_id, athlete_name, gender, country, country_code, coach_id)
PK: athlete_id
FK: country_code → NOCs(noc_code)
FK: coach_id → Coaches(coach_id)

```

1. **Athlete_Events Table**

```VB.Net
vbnet
Copy code
Athlete_Events(athlete_id, event)
PK: (athlete_id, event)
FK: athlete_id → Athletes(athlete_id)
FK: event → Events(event)

```

1. **Coaches Table**

```Scss
scss
Copy code
Coaches(coach_id, name, gender, country, disciplines)
PK: coach_id
FK: country → NOCs(country)

```

1. **Events Table**

```VB.Net
vbnet
Copy code
Events(event, sport, sport_code)
PK: event
UNIQUE: sport_code

```

1. **Medals Table**

```VB.Net
vbnet
Copy code
Medals(athlete_id, event, medal_type, country_code)
PK: (athlete_id, event)
FK: athlete_id → Athletes(athlete_id)
FK: event → Events(event)
FK: country_code → NOCs(noc_code)

```

1. **Medals_Total Table**

```Scss
scss
Copy code
Medals_Total(country_code, gold_medal, silver_medal, bronze_medal, total)
PK: country_code
FK: country_code → NOCs(noc_code)

```

1. **Schedules Table**

```VB.Net
vbnet
Copy code
Schedules(event, venue_id, start_date, end_date)
PK: (event, venue_id)
FK: event → Events(event)
FK: venue_id → Venues(venue_id)

```

1. **Teams Table**

```Scss
scss
Copy code
Teams(team_id, team, country_code, num_athletes)
PK: team_id
FK: country_code → NOCs(noc_code)

```

1. **Technical_Officials Table**

```Scss
scss
Copy code
Technical_Officials(official_id, name, gender, disciplines)
PK: official_id

```

1. **Venues Table**

```Scss
scss
Copy code
Venues(venue_id, venue, sports, date_start, date_end)
PK: venue_id

```

---

## **SQL Code to Create the Tables in MySQL**

```SQL
sql
Copy code
CREATE TABLE NOCs (
    noc_code CHAR(3) PRIMARY KEY,
    country VARCHAR(100) NOT NULL,
    country_long VARCHAR(100) UNIQUE
);

CREATE TABLE Athletes (
    athlete_id INT PRIMARY KEY,
    athlete_name VARCHAR(100) NOT NULL,
    gender VARCHAR(10) NOT NULL CHECK (gender IN ('Male', 'Female')),
    country VARCHAR(100) NOT NULL,
    country_code CHAR(3),
    coach_id INT,
    CONSTRAINT fk_noc FOREIGN KEY (country_code) REFERENCES NOCs(noc_code),
    CONSTRAINT fk_coach FOREIGN KEY (coach_id) REFERENCES Coaches(coach_id)
);

CREATE TABLE Athlete_Events (
    athlete_id INT NOT NULL,
    event VARCHAR(100) NOT NULL,
    CONSTRAINT fk_athlete FOREIGN KEY (athlete_id) REFERENCES Athletes(athlete_id),
    CONSTRAINT fk_event FOREIGN KEY (event) REFERENCES Events(event),
    PRIMARY KEY (athlete_id, event)
);

CREATE TABLE Coaches (
    coach_id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    gender VARCHAR(10) NOT NULL,
    country VARCHAR(100) NOT NULL,
    disciplines VARCHAR(100) DEFAULT 'General',
    CONSTRAINT fk_country FOREIGN KEY (country) REFERENCES NOCs(country)
);

CREATE TABLE Events (
    event VARCHAR(100) PRIMARY KEY,
    sport VARCHAR(100) NOT NULL,
    sport_code CHAR(3) UNIQUE
);

CREATE TABLE Medals (
    athlete_id INT NOT NULL,
    event VARCHAR(100) NOT NULL,
    medal_type VARCHAR(20) DEFAULT 'Participation',
    country_code CHAR(3),
    CONSTRAINT pk_medals PRIMARY KEY (athlete_id, event),
    CONSTRAINT fk_medal_athlete FOREIGN KEY (athlete_id) REFERENCES Athletes(athlete_id),
    CONSTRAINT fk_medal_event FOREIGN KEY (event) REFERENCES Events(event),
    CONSTRAINT fk_medal_country FOREIGN KEY (country_code) REFERENCES NOCs(noc_code)
);

CREATE TABLE Medals_Total (
    country_code CHAR(3) PRIMARY KEY,
    gold_medal INT DEFAULT 0,
    silver_medal INT DEFAULT 0,
    bronze_medal INT DEFAULT 0,
    total INT DEFAULT 0,
    CONSTRAINT fk_total_country FOREIGN KEY (country_code) REFERENCES NOCs(noc_code)
);

CREATE TABLE Schedules (
    event VARCHAR(100) NOT NULL,
    venue_id INT NOT NULL,
    start_date DATE NOT NULL,
    end_date DATE,
    CONSTRAINT pk_schedule PRIMARY KEY (event, venue_id),
    CONSTRAINT fk_schedule_event FOREIGN KEY (event) REFERENCES Events(event),
    CONSTRAINT fk_schedule_venue FOREIGN KEY (venue_id) REFERENCES Venues(venue_id)
);

CREATE TABLE Teams (
    team_id VARCHAR(50) PRIMARY KEY,
    team VARCHAR(100) NOT NULL,
    country_code CHAR(3) NOT NULL,
    num_athletes INT DEFAULT 0 CHECK (num_athletes >= 0),
    CONSTRAINT fk_team_country FOREIGN KEY (country_code) REFERENCES NOCs(noc_code)
);

CREATE TABLE Technical_Officials (
    official_id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    gender VARCHAR(10) NOT NULL,
    disciplines VARCHAR(100) DEFAULT 'General'
);

CREATE TABLE Venues (
    venue_id INT PRIMARY KEY,
    venue VARCHAR(100) NOT NULL,
    sports VARCHAR(100),
    date_start DATE NOT NULL,
    date_end DATE
);

```

---

### **How to Use This SQL Code in MySQL:**

1. Open your **MySQL client** or **MySQL Workbench**.
2. Create a new database:
    
    ```SQL
    sql
    Copy code
    CREATE DATABASE olympics;
    USE olympics;
    
    ```
    
3. Copy and paste the SQL code into your MySQL environment and execute it.

This code will create all the tables with the necessary **primary keys, foreign keys, unique constraints, not null constraints, and default values**.

Let me know if you need further assistance!