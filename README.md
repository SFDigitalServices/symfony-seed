Install homebrew
Install composer
Install npm
Install docker

npm install
docker-compose up

# compile assets once
 ./node_modules/.bin/encore dev

# recompile assets automatically when files changes
 ./node_modules/.bin/encore dev --watch

# compile assets, but also minify & optimize them
 ./node_modules/.bin/encore production

run docker-compose ps to find out what port

Name                       Command              State                    Ports                  
---------------------------------------------------------------------------------------------------------
symfonyseed_database_1   docker-entrypoint.sh postgres   Up      0.0.0.0:32772->5432/tcp                 
symfonyseed_web_1        /entrypoint supervisord         Up      443/tcp, 0.0.0.0:32773->80/tcp, 9000/tcp

in this case, the web server can be accessed at port 32773.
load the webapp at 127.0.0.1:32773
