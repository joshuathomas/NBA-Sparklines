# index_json_data.md

The following is an explanation of the files in this folder, pointers to the downloads, and some accompanying documentation.

## Images

This node package documentation provided me with the location of the team logo images:  
https://www.npmjs.com/package/nba-api-client

They are all in this format, with the variable being the 3 letter team code:  
https://stats.nba.com/media/img/teams/logos/CHI_logo.svg

Now, they all live in the fllowing location for the purposes of this project (don't tell the NBA, we're doing this without their permisssion):  
../nba_logo_team_svg/

![Chicago Bulls Logo](../nba_logo_team_svg/CHI_logo.svg)

## Team Data

I was searching for the team logos and needed the following list to grab them.

Docs  
http://nbasense.com/nba-api/Data/Prod/Teams/Teams#request-example

>http://data.nba.net/prod/v1/2019/teams.json



## Game Data!

https://stats.nba.com/scores/01/31/2020

### I'm building this example assuming you would be querying all the games for a given date. My example is using 1/31/20.

Friday, the 31st was an exciting night in the NBA.

It was the first match up of Zion Williamson (NOP) and Ja Morant (MEM), last year's number 1 and 2 draft picks. Kyrie dropped a season high 54 as the Nets triumphed over the Bulls. Denver beat the current Eastern Conference leader, the Bucks - in Milwaukee, 127 to 115.

Additionally, the Lakers, Portland game was the 2nd highest rated, regular season game ever, on ESPN.

https://awfulannouncing.com/nba/trailblazers-lakers-viewers-second-largest-espn-nba-regular-season-audience-ever.html?utm_source=dlvr.it&utm_medium=twitter

### Games by date

Docs  
http://nbasense.com/nba-api/Data/Prod/General/Today#request-example

>http://data.nba.net/prod/v2/20200131/scoreboard.json

Returns the following 'gameId' attributes.

>0021900720  
0021900721  
0021900722  
0021900723  
0021900724  
0021900725  
0021900726  


### Each game's box score

Docs  
http://nbasense.com/nba-api/Data/Prod/Game/Boxscore#request-example

>http://data.nba.net/prod/v1/20200131/0021900720_boxscore.json
http://data.nba.net/prod/v1/20200131/0021900721_boxscore.json
http://data.nba.net/prod/v1/20200131/0021900722_boxscore.json
http://data.nba.net/prod/v1/20200131/0021900723_boxscore.json
http://data.nba.net/prod/v1/20200131/0021900724_boxscore.json
http://data.nba.net/prod/v1/20200131/0021900725_boxscore.json
http://data.nba.net/prod/v1/20200131/0021900726_boxscore.json

### Each game's score by quarter

This would obviously be part of some kind of call or local database. Once the game is over - it's set. It doesn't need to be called multiple times - that's just wasteful!

Hey, thinking about it - we're living on the 'edge' here. (Sounds like an 80's hair metal ballad song title.) Anyhow, ideally, I might build this out with my own web service to consume the feed - then pass a file off daily to the local machine so, there's only one call (or a minimum number of calls) each day. There are a mind numbingly high number of ways to architect an applicaiton like this with Intuiface and the web services that are available today. Tableau, Azure, AWS, Dash, etc., etc..

I mean, everyone can write their own reusable library like jQuery in a week, right?

I believe, now that I'm thinking about it, that I had to dig around on the "Advanced Stats" https://stats.nba.com/ page to find these calls. 

 >http://data.nba.net/prod/v1/20200131/0021900720_lead_tracker_1.json
http://data.nba.net/prod/v1/20200131/0021900720_lead_tracker_2.json
http://data.nba.net/prod/v1/20200131/0021900720_lead_tracker_3.json
http://data.nba.net/prod/v1/20200131/0021900720_lead_tracker_4.json
>
>http://data.nba.net/prod/v1/20200131/0021900721_lead_tracker_1.json
http://data.nba.net/prod/v1/20200131/0021900721_lead_tracker_2.json
http://data.nba.net/prod/v1/20200131/0021900721_lead_tracker_3.json
http://data.nba.net/prod/v1/20200131/0021900721_lead_tracker_4.json
>
>http://data.nba.net/prod/v1/20200131/0021900722_lead_tracker_1.json
http://data.nba.net/prod/v1/20200131/0021900722_lead_tracker_2.json
http://data.nba.net/prod/v1/20200131/0021900722_lead_tracker_3.json
http://data.nba.net/prod/v1/20200131/0021900722_lead_tracker_4.json
>
>http://data.nba.net/prod/v1/20200131/0021900723_lead_tracker_1.json
http://data.nba.net/prod/v1/20200131/0021900723_lead_tracker_2.json
http://data.nba.net/prod/v1/20200131/0021900723_lead_tracker_3.json
http://data.nba.net/prod/v1/20200131/0021900723_lead_tracker_4.json
>
>http://data.nba.net/prod/v1/20200131/0021900724_lead_tracker_1.json
http://data.nba.net/prod/v1/20200131/0021900724_lead_tracker_2.json
http://data.nba.net/prod/v1/20200131/0021900724_lead_tracker_3.json
http://data.nba.net/prod/v1/20200131/0021900724_lead_tracker_4.json
>
>http://data.nba.net/prod/v1/20200131/0021900725_lead_tracker_1.json
http://data.nba.net/prod/v1/20200131/0021900725_lead_tracker_2.json
http://data.nba.net/prod/v1/20200131/0021900725_lead_tracker_3.json
http://data.nba.net/prod/v1/20200131/0021900725_lead_tracker_4.json
>
>http://data.nba.net/prod/v1/20200131/0021900726_lead_tracker_1.json
http://data.nba.net/prod/v1/20200131/0021900726_lead_tracker_2.json
http://data.nba.net/prod/v1/20200131/0021900726_lead_tracker_3.json
http://data.nba.net/prod/v1/20200131/0021900726_lead_tracker_4.json


## Eratta (yes, I'm not using this term correctly - thanks)

### GIT stuff

https://egghead.io/lessons/git-git-ignore-a-file-that-has-already-been-committed-and-pushed

remove all of our files from our git cache with:

``` git rm -r --cached . ```

and then add back all the files we want with:

``` git add -A ```

The above sure didn't work on GitHub.

This did:

https://stackoverflow.com/a/1274447

```git rm -cached <file name> ```

```git commit -m "Your funny comment." ```

Well, the command line said it was gone but, apperantly, it lied. Time to move on and make this a to do.

Well, after giving it a few minutes it seems to have actually worked so, check - task complete!

# HOLY COW!!! IIS!!! 

IIS - the "IUSR" and the "IIS_IUSRS" have to be added to the symlink or virtual directory folder TARGET directory!!!

https://dotnet-revanth.blogspot.com/2016/01/iis-permissions-for-virtual-directory.html

Here's how you make a symlink - make sure you're running as administrator 
mklink /J Link Target
