# Data-Base

## User Stories

* I would like to be able to see how much HP my hero has.
* I would like to be able to how much HP my enemies have.
* I would like to be able to see my heroes level.
* I would like to be able to see my enemies level.
* I would like to be able to see what skills my hero has.
* I would like to be able to see the race of my heroes.
* I would like to be able to see the race of the enemies.
* I would like to be able to see how much damage a skill does.
* I would like to be able to see how much healing a skill does.
* I would like to be able to see the type of skill that my hero has.
* I would like to be able to see the type of skill that my enemies have



## ERD
#### Below you can see the ERD which is a quick overview how the database will look, function and what it will contain. Under each of the database titles there are multiple Skills, ID, HP, Damage and many others. 

#### As you can see on the ERD some of the tables are linked to one another for example the ‘Heroes’ table is linked to the ‘Heroes Talents’. This means that information can link between them. At the bottom you can see ‘Skills’ which all of the tables link to this table will contain the damage the skills do and the name of then the range of them and if they can heal then how much it will heal. 

#### Overall the ERD is a template of what the data base that will be created will look like, contain and the purpose of it. 

![erd diagram for game](https://user-images.githubusercontent.com/31927415/38622242-a1f7e08c-3d9a-11e8-9d23-e5fc65e0bbb2.png)


## Data Dictionary
#### Below you can see a Data Dictionary for the database that I am creating. These dictionaries are to help the viewer understand. What type of input the table area will have, for example certain areas will have "float". This is to indicate whether there would be numbers or letters within the field of input. Data dictionaries are important as they can keep the database consistent from the start by giving it a set point as it allows viewers to look onto a clear view of what the database is going to be like and can always be referred to when putting the database together.

#### This data dictionary shows how my database will be made and what the value type they are. I will be able to use this dictionary as a fixed layout of the database when creating the final piece. I know what I must add and I know it’s everything I need all I should do is put it into a database. The dictionary helps keep me on track    
![capturej](https://user-images.githubusercontent.com/31927415/38619040-2b3d5f64-3d93-11e8-86ab-8a4a1660edae.JPG)


## SQL Code:

```
CREATE TABLE ENEMIES(
     ID INT NOT NULL PRIMARY KEY,
     LEVEL INT NOT NULL,
     NAME VARCHAR(50) NOT NULL,
     DAMAGE FLOAT NOT NULL,
     HP FLOAT NOT NULL
);

CREATE TABLE HERO(
     ID INT NOT NULL PRIMARY KEY,
     LEVEL INT NOT NULL,
     CLASS VARCHAR(50) NOT NULL,
     HP FLOAT NOT NULL,
     STATUS VARCHAR(50)
);

CREATE TABLE ENEMY_SKILLS(
     ENEMY_ID INT NOT NULL,
     SPELL_ID INT NOT NULL,
     LEVEL INT NOT NULL,
     PRIMARY KEY (ENEMY_ID, SPELL_ID),
     FOREIGN KEY (ENEMY_ID) REFERENCES ENEMIES(ID),
     FOREIGN KEY (SPELL_ID) REFERENCES SPELLS(ID)
);

CREATE TABLE HERO_SKILLS(
     HERO_ID INT NOT NULL,
     SPELL_ID INT NOT NULL,
     LEVEL INT NOT NULL,
     PRIMARY KEY (HERO_ID, SKILL_ID),
     FOREIGN KEY (HERO_ID) REFERENCES HERO(ID),
     FOREIGN KEY (SKILL_ID) REFERENCES SPELLS(ID)
);

CREATE TABLE SPELLS(
     ID INT PRIMARY KEY,
     DAMAGE FLOAT NOT NULL,
     RANGE FLOAT NOT NULL,
     NAME VARCHAR(50) NOT NULL
);


INSERT INTO ENEMIES VALUES(
1, 'DRAGON', 100.98, 9.9
);

DELETE FROM ENEMIES WHERE ID-2;
LEVEL > 2 AND NAME='DRAGON';

UPDATE HEROES
SET LEVEL - 4 HP = 100
WHERE NAME LIKE 'Adam%';

SELECT LEVEL, NAME FROM HEROES
WHERE NAME LIKE '%A%';

SELECT H.NAME, H.LEVEL, S.NAME, HS.LEVEL 

FROM HEROES H, SKILLS S, HEROES_SKILLS HS

WHERE HERO_ID = H.ID AND SKILL_ID = S.ID AND H.NAME LIKE '%A%';

SELECT COUNT (*) FROM HEROES;

SELECT MAX(H.LEVEL), MIN(H.LEVEL) FROM HEROES H; 

__________________________________________    Inserts To Heroes    _________________________________________


INSERT INTO Heroes VALUES(
1, 'Aragorn', Men, Captain, 116, 4000, 4000
);

INSERT INTO Heroes VALUES(
2, 'Legolas', Elf, Hunter, 116, 3500, 4500
);

INSERT INTO Heroes VALUES(
3, 'Gimli', Dwarf, Guardian, 116, 5000, 3000
);

INSERT INTO Heroes VALUES(
4, 'Gandalf', Maiar, Wizard, 116, 3500, 6000
);

INSERT INTO Heroes VALUES(
5, 'Frodo Baggins', Hobbit, Burglar, 116, 2000, 500
);

INSERT INTO Heroes VALUES(
6, 'Thorin', Dwarf, Champion, 116, 4000, 1500
);

INSERT INTO Heroes VALUES(
7, 'Elrond', Elf, Captain, 116, 3500, 3000
);

INSERT INTO Heroes VALUES(
8, 'Erinstel', High Elf, Hunter, 115, 9999, 9999
);

__________________________________________    Inserts To Enemies    _________________________________________


INSERT INTO Enemies VALUES(
1, 'Sauron', 9000, 9000,
);

INSERT INTO Enemies VALUES(
2, 'Witch-King', 7500, 4000,
);

INSERT INTO Enemies VALUES(
3, 'Nazgûl', 5000, 2000,
);

INSERT INTO Enemies VALUES(
4, 'Mûmakil', 8000, 3000,
);

INSERT INTO Enemies VALUES(
5, 'Gothmog', 3000, 500,
);

INSERT INTO Enemies VALUES(
6, 'Balrog', 8000, 4000,
);

INSERT INTO Enemies VALUES(
7, 'Azog', 4000, 1000,
);

INSERT INTO Enemies VALUES(
8, 'Smaug', 8000, 6000,
);

__________________________________________    Inserts To Hero_Skills    _________________________________________


INSERT INTO Hero_Skills VALUES(
1, 1, 116,
);

INSERT INTO Hero_Skills VALUES(
1, 2, 116,
);

INSERT INTO Hero_Skills VALUES(
1, 3, 116,
);

INSERT INTO Hero_Skills VALUES(
2, 4, 116,
);

INSERT INTO Hero_Skills VALUES(
2, 5, 116,
);

INSERT INTO Hero_Skills VALUES(
2, 6, 116,
);

INSERT INTO Hero_Skills VALUES(
3, 7, 116,
);



__________________________________________    Inserts To Enemy_Skills    _________________________________________

INSERT INTO Enemy_Skills VALUES(
1, 25, 116,
);

INSERT INTO Enemy_Skills VALUES(
1, 26, 116,
);

INSERT INTO Enemy_Skills VALUES(
1, 27, 116,
);

INSERT INTO Enemy_Skills VALUES(
2, 28, 116,
);

INSERT INTO Enemy_Skills VALUES(
2, 29, 116,
);

INSERT INTO Enemy_Skills VALUES(
2, 30, 116,
);

INSERT INTO Enemy_Skills VALUES(
3, 31, 116,
);




__________________________________________    Inserts To Skills    _________________________________________

INSERT INTO Skills VALUES(
1, Sword, High Cut, Melee, 
);

INSERT INTO Skills VALUES(
2, Sword, Low Cut, Melee, 
);

INSERT INTO Skills VALUES(
3, Sword, Double Strike, Melee, 
);

INSERT INTO Skills VALUES(
4, Bow, Quick Shot, Ranged, 
);

INSERT INTO Skills VALUES(
5, Bow, Heart Seeker, Ranged, 
);

INSERT INTO Skills VALUES(
6, Bow, Blind Side, Melee / Ranged, 
);

INSERT INTO Skills VALUES(
7, Hammer, Sweeping Cut, Melee, 
);

__________________________________________    All Of My Deletes    _________________________________________

DELETE FROM ENEMIES WHERE ID-2;
LEVEL > 120 AND NAME='Witch-King';


DELETE FROM Heroes WHERE ID-4;
LEVEL > 120 AND NAME='Gandalf';


DELETE FROM ENEMIES WHERE ID-20;
NAME='Rend';

DELETE FROM ENEMIES WHERE ID-4;
NAME='Quick Shot';


DELETE FROM ENEMIES WHERE ID-40;
NAME='Long Strike';


DELETE FROM ENEMIES WHERE ID-7;
LEVEL > 120 AND NAME='Elrond';


DELETE FROM ENEMIES WHERE ID-5;
LEVEL > 120 AND NAME='Gothmog';

__________________________________________    All Of My Updates    _________________________________________


UPDATE HEROES
SET LEVEL - 116, HP = 4000
WHERE NAME LIKE 'Aragorn%';

UPDATE HEROES
SET LEVEL - 116, HP = 2000
WHERE NAME LIKE 'Frodo Baggins%';

UPDATE Enemies
HP = 8000
WHERE NAME LIKE 'Balrog%';

UPDATE HEROES
SET LEVEL - 116, Damage = 3000
WHERE NAME LIKE 'Gimli%';

UPDATE Enemies
SET LEVEL - 116, Damage = 4000
WHERE NAME LIKE 'Witch-King%';

UPDATE HEROES
SET LEVEL - 115,
WHERE NAME LIKE 'Erinstel%';

UPDATE HEROES
SET HP = 4000, Damage = 4000
WHERE NAME LIKE 'Aragorn%';

__________________________________________    All Of My Selects    _________________________________________

SELECT LEVEL, NAME FROM HEROES
WHERE NAME LIKE '%A%';

SELECT LEVEL, NAME FROM Enemies
WHERE NAME LIKE '%T%';

SELECT LEVEL FROM HEROES
WHERE NAME LIKE '%E%';

SELECT NAME, Damage FROM HEROES
WHERE NAME LIKE '%A%';

SELECT LEVEL, NAME , Damage FROM HEROES
WHERE NAME LIKE '%E%';

SELECT HP, Damgage FROM Enemies
WHERE NAME LIKE '%G%';

SELECT TYPE, RANGE FROM Skills
WHERE NAME LIKE '%A%';
``` 


## Forms
The form you can see below is able to insert data into my Hero tab in the database you are able to add in every attribute as well. 

![forms](https://user-images.githubusercontent.com/31927415/39126810-43f6c13c-46fb-11e8-80fd-443af4b9f8f2.PNG)

## Validation
Here are some of the Validation Rules i have used thoughout my Database:

The first validation i used was >=0 which means the number that you enter must be higher than Zero
![valudatuib](https://user-images.githubusercontent.com/31927415/39234342-dabc8afa-486a-11e8-8f30-e42e60337bbc.PNG)

The Second Validation i used was <> 0 Which means the user must enter a nonzero number
![valudation 2](https://user-images.githubusercontent.com/31927415/39234919-75cbec88-486c-11e8-85fa-7988bad1ac1a.PNG)

The Third Validation i used was 0 or >100 which means the user must enter 0 or a number greater than 100
![valudation 3](https://user-images.githubusercontent.com/31927415/39235052-cb188c3c-486c-11e8-9564-8c8f48341d55.PNG)


## Reports
The screen shot below is of the report created about my Hero table. It contains all of their skills, levels, damage, name and many more things. The report has all of the things that are spread over different databases in one place to make it easy to see and read 

![reports](https://user-images.githubusercontent.com/31927415/39126938-830185d8-46fb-11e8-8c69-346cda1a888e.PNG)


## Test Plan
![test plan](https://user-images.githubusercontent.com/31927415/39513951-c8795bba-4ded-11e8-94ad-9874bd60a877.PNG)
