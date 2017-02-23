# oao-docker
Simple repository to test oao with docker (link to guigrpa/oao#15)

With docker, oao command failed if not well formated in scripts :

If there are more than one lib, in main package.json :
```
"scripts": {
    //this will fail
    "_docker": "...&& oao bootstrap -s ./packages/*/"

    //this will fail
    "_docker": "...&& oao bootstrap -s ./packages/*"

    //this will success
    "_docker": "...&& oao bootstrap"

    //this will success
    "_docker": "...&& oao \"bootstrap -s ./packages/*\""
  }
```
