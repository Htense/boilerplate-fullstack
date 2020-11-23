# Notes from Hortense

Using Git in a Team!
Clone & Make a branch

(change directory) to where you want to keep your repo
```
cd workspace
git clone + https link
cd myRepo
npm i
```

This means node package manager - install
Run migrations to reset the database
```
npm run knex migrate:latest
npm run knex seed:run
```
Make a branch

Use the name of the feature your are working on
```
git checkout -b myFeature  
code .  
```
to open in VScode

Commit  & Push your branch
```
git status 
git add .  
git commit -m “commit message”  
git push origin myBranch  
```
Feature is done, ready to merge? 
Merge the Master into your branch, commit & push
In local,
Pull master into MyBranch. Deal with conflicts there. 
```
git add .
git commit -m “readyToMerge”
git pull origin master
```
Open VStudio
```
code .
```
Deal with your conflicts here, then save

Any conflicts or changes need to be saved, added, & committed again
```
git add .
git commit -m “mergeTime”
```
Github

Then create pull request from mybranch remote to master remote (on github)


Tell the git keeper, they will merge the pull request and there should be 0 conflicts as you have allready resolved these in your branch.

Everyone else now needs to pull from master, 
```
npm i

rm server/db/dev.sqlite3
npm run knex migrate:latest
npm run knex seed:run

```
If you want a fast way to add, commit and push to your branch use this command (enter your own commit message)
# Dev academy Readme

## Getting Started

### From the Github UI
See the instructions [here](https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template) to use Github's feature to create a new repo from a template.

### From the command line

```
git clone https://github.com/dev-academy-challenges/boilerplate-fullstack [your-project-name]
cd [your-project-name]
npm install # to install dependencies
npm run dev # to start the dev server
```

You can find the server running on [http://localhost:3000](http://localhost:3000).

## Details

This repo includes:

* a single, simple API endpoint (`/api/v1/fruits`)
* a single React component (`<App />`)
* an example database module (`server/db/fruits.js`)
* an API client module (`client/apis/fruits.js`)
* configuration for Jest and Enzyme (including JSDOM)
* configuration for server-side debugging in VS Code
* a single client-side test (`client/components/App.test.js`)
