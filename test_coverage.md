Test Coverage and Code Quality
======

Travis-CI alone is only helpful IF you have tests. If you don't have tests then Travis-CI will always pass your build. 
Essentially we can always cheat ourselves into always having a passing build as long as we don't test.

The solution. Integrate it with Code Climate. 

Travis-CI already runs our tests and checks our coverage. We just a way to interpret that.




### Code Climate ###
Create an and link to your github account. 

Code Climate will automatically scan your github account for repos you want to include. 
*Note that you need to have admin or owner permission for this.



### Integrating Travis-CI ###
Add this gem to your app
```
gem "codeclimate-test-reporter", require: nil
```

Add this to the top of your spec_helper.rb or test_helper.rb
```
require "codeclimate-test-reporter"
CodeClimate::TestReporter.start
```

You'd also need to add a unique code climate token to your '.travis.yml' file. It should look similar to this.
```
language: ruby
cache: bundler
rvm:
  - 2.1.0
addons:
  code_climate:
    repo_token: c8......41657d97b
before_script:
  - "rake db:create db:migrate test"
```



# Demo #

