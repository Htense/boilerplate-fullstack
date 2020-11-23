# Notes from Hortense - Using Git in a Team!
# Clone & Make a branch
## 1. Clone
```
cd workspace
git clone + https link
cd myRepo
```
## 2. Make a branch using the name of the feature your are working on
```
git checkout -b myFeature  
code .  
```
## 3. Instal modules & reset the database
```
npm i
npm run knex migrate:latest
npm run knex seed:run
```

## 4. Commit & Push your branch
```
git status 
git add .  
git commit -m “commit message”  
git push origin myBranch  
```
# MERGE TIME!! 
### Feature is done, ready to merge? 

## 1. Commit your branch as above

```
git add .  
git commit -m “readyToMerge”   
```

## 2. Pull master into your branch, open VScode & deal with the conflicts there.

```
git pull origin master
code .
```
## 3. Any conflicts or changes need to be saved, added, & committed again
```
git add .
git commit -m “mergeTime”
git push origin myBranch
```
## 4. Github - create pull request

* Create pull request from mybranch to master (on github)
* Tell the git keeper, they will merge the pull request and there should be 0 conflicts as you have allready resolved these in your branch.

## 5. GitKeeper - merge the reauest

* Merge the pull request only if there are 0 conflicts

## 6. Everyone else now needs to pull from master & update their modules
```
npm i
```
* Reset database
```
rm server/db/dev.sqlite3
npm run knex migrate:latest
npm run knex seed:run

```


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
