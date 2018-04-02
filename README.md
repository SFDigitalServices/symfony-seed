
The purpose of this project is to speed up the bootstrapping of symfony projects.

1. git clone git@github.com:SFDigitalServices/symfony-seed.git new-proj-name
2. Create repo for new project and point git it  
    `git remote set-url origin git@github.com:User/UserRepo.git`
3. git push

# Installation
* ### Install homebrew
[https://brew.sh]

* ### Install PHP 7
brew install php71 --with-postgresql

* ### Install composer
`brew install composer`

* ### Install npm
`brew install npm`

* ### Install docker
[https://docs.docker.com/docker-for-mac/install/]
or  
`brew cask install docker`

* ### Download dependencies
`npm dependencies` will run `npm install` and `composer install`

* ### Bring up the dev environment
`npm start` will run `./node_modules/.bin/encore dev --watch` and `docker-compose up`

* ### Stop the dev environmnet
`npm stop`

# Migrations
generate migrations `php bin/console doctrine:migrations:diff`
apply migrations to db `php bin/console doctrine:migrations:migrate`

# Production deployment
### Compile, minify, & optimize assets  
`./node_modules/.bin/encore production`

# Misc Notes
run `docker-compose ps` to find out what port

symfonyseed_database_1   docker-entrypoint.sh postgres   Up      0.0.0.0:32772->5432/tcp              
symfonyseed_web_1        /entrypoint supervisord         Up      443/tcp, 0.0.0.0:32773->80/tcp, 9000/tcp

in this case, the web server can be accessed at port 32773.
load the webapp at 127.0.0.1:32773

# Documentation
[symfony documentation](https://symfony.com/doc/current/index.html)  
[doctrine orm guide](https://symfony.com/doc/current/doctrine.html)
