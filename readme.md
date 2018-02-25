# Apps:
 ## Create:
    - dokku apps:create myAppName

 ## Delete:
    - dokku apps:destroy myAppName

 ## Deploy:
    - git remote add dokku dokku@markwilkinsapps.com:myAppName
    - git push dokku master

 ## get SSL:
    - (https://github.com/dokku/dokku-letsencrypt)
    - dokku config:set --no-restart myapp DOKKU_LETSENCRYPT_EMAIL=a@b.com (add email)
    - dokku letsencrypt myAppName (ssl app)
    - letsencrypt:auto-renew

# Mongo
    (https://github.com/dokku/dokku-mongo)
    ## Create:
    - mongo:create myMongoServiceName
    - mongo:link myMongoServiceName myAppName - links the app and DB service, exposing the env variable MONGO_URL (process.env.MONGO_URL)

    ## Destroy:
    - mongo:destroy myMongoServiceName


# DOCKER
    ## list all containers (dokku or otherwise)
    - docker ps
    
    ## stop container
    - docker stop $containerID
    
    ## destroy container
    - docker rm #containerID

# Admin 
    ## add ssh keys to dokku (so other people can deploy)
    - dokku ssh-keys:add nameOfUserHere path/to/sshkey/here
    - include admin in the name to give them admin powers
    
NOTES:
    -Pushing to Dokku may not delete docker container, but WILL delete the container from dokku. May be neccesary to manually kill the now out of date docker container.