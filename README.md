# Knex Migrations and Seeds Demo

## Setup

Clone repo:
```
git clone https://github.com/jamiesonbates/knex-migrations-seeds-demo.git
npm init -y
```

Setup DB:
```
createdb states_dev
```

## Configure knexfile && knex commands
Utilize article to:
* Configure knexfile.js so that you can connect to your database.
* Add a knex command to "scripts" within package.json

## Create a Migration
Create a migration file for a table named "cities."
```
npm run knex migrate:make states
```

You should see something like this:
![](https://students-gschool-production.s3.amazonaws.com/uploads/asset/file/615/1._fish__-Users-jamiesonbates-Projects-g56-lectures-knex-migrations-seeds-demo__fish__iTerm2__Today_at_8.00.24_AM.png)

The cities table should have the following columns:
* id
* name
* state
* population
* timestamps

When you have created a migration file, use the following command to check your work:
```
npm run knex migrate:latest
```

If successful, you should see something like this:
![](https://students-gschool-production.s3.amazonaws.com/uploads/asset/file/616/1._fish__-Users-jamiesonbates-Projects-g56-lectures-knex-migrations-seeds-demo__fish__iTerm2__Today_at_8.05.16_AM.png)

Also run this command to view information about the created table:
```
psql states_dev -c '\d states'
```
This command should result in something like this:
![](https://students-gschool-production.s3.amazonaws.com/uploads/asset/file/617/1._fish__-Users-jamiesonbates-Projects-g56-lectures-knex-migrations-seeds-demo__fish__iTerm2__Today_at_8.00.24_AM.png)

## Create a Seeds
Use the following data to create a seed for the table named "cities."

Create the seed file:
```
npm run knex seed:make 1_states
```

Next, utilize the following data to build out your seed file:
```javascript
const cities = [
  {
    name: 'Seattle',
    state: 'Washington',
    population: 704352
  },
  {
    name: 'Tacoma',
    state: 'Washington',
    population: 211277
  },
  {
    name: 'Bellingham',
    state: 'Washington'.
    population: 87574
  }
]
```

When you're read to seed your database, run the following command:
```
npm run knex seed:run
```

You should see something like this:


Also, run the following command to see the contents of your database:
```
psql states_dev -c 'SELECT * FROM cities';
```
