# 8base Beginner Walkthrough

## Prerequisite
* <a href="https://nodejs.org/en/">Node.js</a>
* <a href="https://yarnpkg.com/lang/en/docs/install/">yarn</a>
* Yarn: `yarn global add cross-env`
* Install 8base CLI: `yarn global add 8base`

## Data Model
1. Login to https://app.8base.com
2. Create `Properties` table with fields `Title`, `Description`, `Pictures`, `Bedrooms`, `Sq Footage`, `Bathrooms`, `Garage`, `Pool`.

## Client Side

1. Clone repo: `git clone https://github.com/8base/uhack.git`
2. Go to the client directory `cd client`;
3. Edit `src/routes/properties/PropertiesTable.js` to add 
* Install dependencies `yarn`;
* Get 8base API endpoint for your account;
* Start app via `cross-env REACT_APP_8BASE_API_ENDPOINT=%YOUR_ENDPOINT% npm start`;
* Login to the app with your 8base credentials;
* Explore it.

## Server Logic

* Sign up 8base account;
* Install 8base CLI `npm install -g 8base`;
* Login using CLI `8base login`;
* Go to the server directory `cd server`;
* Install dependencies `npm install`;
* Deploy custom functions `8base deploy`;
* Import schema and data via `8base import -f=DEMO.JSON`;
