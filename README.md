# oao-docker
Simple repository to test oao with docker (link to guigrpa/oao#15)

### Getting started

```
$ docker-compose run js-build
```

With docker, oao command failed if :
* there are more than one lib
* if the script called by docker in main package.json :

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

