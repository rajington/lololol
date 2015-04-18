# P.E.T.S.
## People for the Ethical Treatment of Summoners

We are not your "Minions", we are not your "Monsters". We are living breathing sentients that to live with you in harmony. Rito promised that summoners would FINALLY be NURFed, but it was all a cruel joke!

What the site basically does is expose the champions, items, and regions/tiers, that are the most CRUEL to sentients and the ones that are the NICEST to sentients. Behind the scenes, there's a lot more stats you can sort on though thanks to the API's wealth of data. We processed every bit of non-timeline information that made sense, like which champion dealt the most crowd control or who counter-jungled the most.

In general we chose free-tier eligible platforms for hosting, so we were somewhat limited in computational power and capabilities, so pardon things like non-cached data or slower response times.

## Features

### Background Jobs
Background jobs were used to process the data as it came in, and update the database with the moving averages.

### Responsive Web Design
Our splash page is extremely responsive and is browsable on smartphones.

### Merging Data
We merge metadata from Parse, statistical data from Parse (and potentially CouchDB), and static data from the Riot API on the fly to build our views.

### Advanced Tables
By integrating our data with datatables on the frontend, we did a lot of setup but only barely scratched the surface of what's possible with their API.

## Incomplete Features
Unfortunately URF ended too soon, and the timing made it tough for us to spend the time this project deserved.

### Map Reduce
As we started exploring the database more we wanted to perform analysis that wasn't capable with a simple relational database let alone moving averages. We uploaded all 13GB of our persisted matches data to IBM's Cloudant to start using a MapReduce view, and were even taking advantage of the Chained MapReduce features of Cloudant!

### Leaderboards
Our original plan was to do a leaderboard based on match data beyond what other services do with just your ladder ranking. Leaderboards really lend themselves to using Redis as a backend (because of ZSCORE), but the free tier options on most Redis hosts didn't cut it and there wasn't enough and migrating to a free tier PaaS with Redis support like Heroku or Beanstalk.
