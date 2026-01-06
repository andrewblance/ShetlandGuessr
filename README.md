<!-- markdownlint-disable-next-line -->
<p align="center">
  <a href="https://www.geohub.gg"><img src="public/og-image.png" alt="GeoHub logo"></a>
</p>


## Andrew's Edits:

i need to:

* [DONE] fix leaderboards??
* [DONE] make daily challenges work
* make it so you can actually see viewpoints when you are creating your own map
* change theme to make it more fun 
* new font?
* new logo
* new art for backgrounds
* new emojis for sidebar

then , bigger jobs:

* host it online
* get the daily games cron job running all the time


ShetlandGuessr is a free and open source geography guessing game inspired by GeoHub, which in turn was inspired by Geoguessr.

For those unfamilar with Geoguessr, it uses Google Streetview to place you in a random location and you have to guess where you think you are in the world. You can move around and use clues around you such as Language, Architecture, Road Signs, etc... to make your guess. The objective is clear, the closer you are to the correct location, the more points you get.


## 🎉 How do I play?

Go to the [website](https://www.geohub.gg) and create an account, it is free and takes 15 seconds. 

<br />

Once you have an account, you are ready to play! You can click play on any of the offical maps on the home page such as:

- [World](https://www.geohub.gg/map/6185df7a7b54baf63473a53e)
- [Famous Landmarks](https://www.geohub.gg/map/6185dfd47b54baf63473a540)
- [Canada](https://www.geohub.gg/map/6185dff27b54baf63473a541)
- [United States](https://www.geohub.gg/map/6185e0077b54baf63473a542)

Or you can click on the `Find Maps` link on the sidebar to navigate between all the different supported country maps and community favorites!

<br />

If you get bored of playing the standard gamemodes, you can try out the other gamemode available:

- [The Daily Challenge](https://www.geohub.gg/daily-challenge)

<br />

Want to play with friends? Create a challenge link by following the steps below:

1. Choose a map you want to play
2. Click `Play Now` to open up the settings view
3. Instead of `Single Player` select `Challenge`
4. Choose the game play settings you want to enforce for the challenge
5. Click start and copy the challenge link
6. Share this link with friends and see how you compare

<br />

Tired of having the locations picked for you? Create your own map by following the steps below:

1. Click on the `My Maps` link on the sidebar
2. Click the `Create New Map` button
3. Choose a name for your map, and optionally a description and map avatar
4. Click `Next` to setup your custom map
5. Once on the map editor page, you can start adding locations to your map
6. Click anywhere on the map to preview the streetview location
7. Once you have added all the locations you want, click on the `Save Map` button which will let you save and optionally publish your map

## ❓ FAQ

#### Why are the colors inverted on google maps?

- This means the daily quota for the google maps API has been reached since the game is currently running on the Google Maps free tier. The daily quota resets at midnight Pacific Time (PT). If you want to play unlimited games without hitting the daily quota, see below for how to add/create your own Google Maps API key.

#### How do I add my own Google Maps API key?

- Go to your profile page and click on the settings button on the far right (alternatively you can go to this URL: [Settings](https://www.geohub.gg/user/settings)).
- You then simply paste your key into the `Custom API Key` field and click `Save Changes`. Now all you have to do is refresh the page and enojoy playing as much as you want!

#### How do I create my own Google Maps API key?

- Follow the steps outlined in this [PDF](https://www.geohub.gg/custom-key-instructions.pdf)

#### Will it cost me money to create my own Google Maps API key?

- Short answer: No, it is nearly impossible to exceed the $200 USD credit per month on your own. To put it into perspective, you would have to play atleast 100 games every day of the month to even come close to exceeding the free tier.
- If you are still concerned about getting billed, you can monitor your current billing period usage at any time by going to the Billing page on your Google Cloud account.

## 💻 Steps to run locally

1. Clone this repository
2. Create a Google Maps billing account and save the API key
3. Create a MongoDB database and save the connection string and name of the database you create
4. Create random secrets for NextAuth & Cryptr. On Linux/Windows run the following command in a terminal `openssl rand -base64 32`
5. In the root of the app, create a .env file and add the values below (replacing with your created credentials)

```
NEXT_PUBLIC_GOOGLE_API_KEY="your-google-maps-key"
MONGO_URI="your-mongodb-connection-string"
DB_NAME="your-mongodb-database-name"
NEXTAUTH_SECRET="any-random-string"
CRYPTR_SECRET="any-random-string"
NEXTAUTH_URL="http://localhost:3000"

other two keys you actually need too
```

Next, you can install the required dependencies and start the local dev server:

```
yarn
yarn dev
```

Now, you should be able to see the site running locally at [http://localhost:3000](http://localhost:3000)

## 🐳 Docker

something new about my compose file for mongo

