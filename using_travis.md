Using Travis-CI
============

Basic steps on how to use Travis-CI



### Creating an Account ###
============

You're github account will be linked to Travis.

You have two options:

https://travis-ci.org/ - It's Free

https://travis-ci.org/ - 100 Free Builds then it's $129 per month



### Enabling the repo ###
============

Travis will scan your github account for all your repos and you can enable them individually.

https://travis-ci.org/profile 



### travis.yml ###

You'll need to include a file name '.travis.yml' in your enabled repo. This will used by Travis as a guide on building your app.

```
language: ruby
cache: bundler
rvm:
  - 2.1.0
before_script:
  - "rake db:create db:migrate test"
```


### Additional Configurations ###

You have three options on when Travis will build your app. These can be set per repo.
- Build only commits with '.travis.yml' file (This is disabled by default)
- Build on pushed 
- Build on pull requests



# Demo #
