---
layout: post
title: "Create Me a Rails App"
date: 2011-09-26 20:18
comments: true
categories:
- technical
---

So, I'm sitting here at something called Ruby Racer - a Seattle thing.  Different from Ruby Brigade - it's something more for beginners, where nobody should be afraid of asking a question that might make them look bad (Of course, that never seems to stop me.)

I watched the latest Railscast episode this morning - on [spork](http://railscasts.com/episodes/285-spork) and I kind of thought I'd publish some kind of checklist of what I do to setup a Rails project.  Of the projects I'm working on, I wind up putting them all into a consistent environment, and I have a little checklist in Evernote that I figured would be good to stick on a blog.  So here it is:

- Create a git repository: Git is pretty awesome.  If you don't care who sees your app, you can stick it up on github for free!  There was someone from github at the Cascadia Ruby Conference, and he did note that they needed to change their pricing model, so who knows how long that will last...
    - Where to put it: I'm too cheap to use github - I do have a [Linode](http://linode.com) slice, and I just threw my own private git repository up there.  Now that git can host web sits (Jekyll) and now that I'm using heroku to host my apps, I'm thinking I don't need linode anymore (especially if just create a small account on github)
    - Run through git init for the app
    - Create a generic .gitignore file for the app.  Here's what's in one of mine: 
        - .bundle
        - db/\*.sqlite3
        - log/\*.log
        - tmp/restart.txt
        - tmp/\*
        - .DS\_Store # Damn that Apple DS\_Store file
        - public/system/documents\*
        - .sass-cache/\*
        - .powenv
- Use RVM: [RVM](http://beginrescueend.com) helps you manage multiple version of Rubies and related gem environments.  I try to use one rvm for all my "rails 3.1 apps that could end up on heroku"
    - Add an .rvmrc file to the root directory:  You should do this before you run "rails new" because you want to make sure you're using the version of ruby rails you want.  This means you should have a ruby and gemset created  already via rvm.
  Create the app: "rails new <app_name>" (You create so few apps, I always have to look this up)
  Add the gems you want to work with (above and beyond what's in the default gem file. I've always got a few I like to use


       pg - this is important because postgres is the default on heroku, where most of my apps end up.  On top of that, I like the pg admin tool on mac os. Much more pleasant that mysql or using sqllite.
       metric_fu - based on advice from railscats metrics, metrics, metrics - can't argue that.
       formtastic - if you have any forms
     For Testing 
   database-cleaner - help with faster tests
  rspec-rails - I like rspec
  cucumber-rails - I like cucumber
  capybara
  nokogiri - helpful with cucumber and capybara
  factory\_girl\_rails - test factories

For continuous testing

  spork
  guard-spork
  guard-rspec
  guard-cucumber
  rb-fsevent - a listener for guard

  Check it in… Check in early and often
  Change your spec\_helper.rb file and move functionality up into the Spork pre fork block.
  Change your environment.rb to allow for factory girl and cucumber integration (of lots of borrowable step definitions)
     require 'factory\_girl step\_definitions'
  Create a database:
     I use postgres for dev.  It's what heroku uses, and it's where most of my apps end up.
     I just use the pg admin tool
  Change your database.yml:
     adapter: postgresql
     database: accountingtrak
     username: postgres
     password: password
     pool: 5
     timeout: 5000
     host: localhost

  Install RSpec
     rails g rspec:install
  Install Cucumber
     rails g cucumber:install
  Add a model
  Migrate your database(s)
     rake:db:create (if the db isn't there)
     rake:db:migrate
     rake:db:test:prepare
  Make sure the site runs with one of your object controllers being the default home page configure everything for running tests quickly and automatically
     spork --bootstrap (add spork wrapper in spec\_helper.rb
     configure spec helper to use database cleaner
     guard init spork
     guard init rspec
     guard init cucumber     
     make sure spark block comes first
     make sure rspec and cucumber both startup (in guard) with the --drb option
     example: root :to 'contact#index"
  Add a project in pivotal tracker to manage your stories and velocity
     I'm partial to pivotal tracker, because it's a web app, and it's much faster than your typical kanban tools
  BDD TDD in your features








