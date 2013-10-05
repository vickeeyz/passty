## PassTy: web application to keep your passwords in one place behind firewall install  running on nginx and unicorn

- - -

All credit goes to Dmitriy Zaporozhets : randx
> https://github.com/randx

Passty original code

```
git clone https://github.com/randx/passty.git
```

- - -


### Requirements:

* ruby 1.9+
* mysql db

### Setup:


1. Get code

        git clone https://github.com/randx/passty.git
        cd passty


2. Copy database.yml and edit mysql user/password


        cp config/database.yml.example config/database.yml
        vim config/database.yml


3. Setup libs, migrations etc

        bundle install --deployment --without development test
        bundle exec rake db:create RAILS_ENV=production
        bundle exec rake db:setup RAILS_ENV=production
        bundle exec rake assets:precompile RAILS_ENV=production 

4. For unicorn proxy with nginx and unicorn init script

https://github.com/vickeeyz/scripts/tree/master/nginx#unicorn-proxy-with-nginx

5. Get the nginx and unicorn configurations from my repo scripts

```
git clone https://github.com/vickeeyz/scripts.git
```
