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


## Forms
The form you can see below is able to insert data into my Hero tab in the database you are able to add in every attribute as well. 

![forms](https://user-images.githubusercontent.com/31927415/39126810-43f6c13c-46fb-11e8-80fd-443af4b9f8f2.PNG)

## Validation
Here are some of the Validation Rules i have used thoughout my Database

The first validation i used was >=0 which means the number that you enter must be higher than Zero
![valudatuib](https://user-images.githubusercontent.com/31927415/39234342-dabc8afa-486a-11e8-8f30-e42e60337bbc.PNG)

## Reports
The screen shot below is of the report created about my Hero table. It contains all of their skills, levels, damage, name and many more things. The report has all of the things that are spread over different databases in one place to make it easy to see and read 

![reports](https://user-images.githubusercontent.com/31927415/39126938-830185d8-46fb-11e8-8c69-346cda1a888e.PNG)
