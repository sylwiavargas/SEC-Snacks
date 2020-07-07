# Mod1

## Week 1 Day 1

### After lecture
Congrats on your first lecture! A few lecture notes:
✨ when in pry:
- to leave the long return value: press `q`;
- to see next lines: press `enter`;
✨ hashes are unordered collections — you don’t need to know the index of the elements to access them;
✨`--f-f` stands for “fail fast”;
✨To transform a nested array into a flat one, you can run `.flatten()`
``` ruby
multidimensional_array = [["Alex", "is"], "so", "talented"].flatten
#=> ["Alex", "is", "so", "talented"] 
```
✨ transforming a string into an array:
- `.split()` just places the string in the array;
``` ruby
        "Vidhi is the lead instructor".split()
        #=> ["Vidhi", "is", "the", "lead", "instructor"] 
```
- `.split("")` splits it into an array of characters;
``` ruby
        "Vidhi is the lead instructor".split("")
        #=> ["V", "i", "d", "h", "i", " ", "i", "s", " ", "t", "h", "e", " ", "l", "e", "a", "d", " ", "i", "n", "s", "t", "r", "u", "c", "t", "o", "r"] 
```
- `.split(" ")` or `.split("a")` would split the string into elements whenever it encounters the character in the argument, cutting it out;
``` ruby
        "Vidhi is the lead instructor".split("i")
        #=> ["V", "dh", " ", "s the lead ", "nstructor"] 
```

### Opening Learn Lab on your laptop:
How to open a learn.co lab on your Laptop? https://www.youtube.com/watch?v=gHEQa-zfLYU&feature=youtu.be 

### EOD Messages
✨ Congratulations, everyone! You’ve made it through your first day! ✨
Thank you for all the questions and answers you all shared with each other — and for the kindness you showed to others during the group discussion. Flatiron School is all about community because programming is never a solo sport.

You should see an INTIMIDATINGLY HUGE number of new labs deployed on learn.co, **but fear not!**, almost all of them are from the pre-work, just added to your curriculum.

Things to keep in mind:
- take breaks away from your computer — even if it’s a quick stretch or a round to the kitchen;
- get proper sleep, even if you feel behind — you are doing yourself a disfavor if you’re working tired;
- **this is a marathon, not a sprint so prioritize your well-being!**
See you all at 9am EST tomorrow!
@here

---
##  Week 1 Day 2

### Discussion Questions Intro
Hi friends!
I've deployed your first DISCUSSION QUESTIONS!
Pretty much every day we'll start with a set of discussion questions, which will be available on Learn.co. At the beginning of each day, spend some time reading through it with your section of your table (or the whole table! YOU are in charge), and discussing your potential answers.

### After lecture
This is a guide I just found with google, there's an example of an initialize method using key value parameters a little less than halfway down the page: https://www.rubyguides.com/2018/06/rubys-method-arguments/

### SWAPI Pairing Lab
Hey y’all,  we are about to send out your groups for today’s pairing lab --  we will be working with the Star Wars API! As you are working, **please rotate every 20 minutes between the Driver and the Navigator**. You’ll hear us use these terms a lot. The Driver will be the one actually typing, and the Navigator will be the one guiding, catching typos, thinking of what to google, etc. Keep your code to one computer, but feel free to use a second to google stuff if you need.
Think of it like this...
> A good navigator never grabs the steering wheel, and a good driver never takes their eyes off the road to look at the map.
**PLEASE EMOJI THAT YOU HAVE READ THIS!**


### Email Parser Lab
Some of you have started working on the `Email Parser lab`. It’s a lab that can be solved in a few ways, some of which will require `regex`.
Regex stands for “Regular Expression” and it is a language-agnostic (meaning: you can use it with any programming language) tool to locate any character pattern or a single character in strings or numbers. While it’s very helpful to know it exists, I wouldn’t recommend frying your brain while trying to memorize i — there are better uses of your time.
In Ruby you have a few methods that are specificly for using regex, such as:
- `.match(/\s/)` - finds all instances of the pattern (now the example will find all the spaces;
- `.gsub(/hi/, "hello")`  - it takes two arguments: first, the regex expression and then the stuff to replace it with; in this example, it will look for a “hi” and replace it with “hello”
You can also use regex in e.g. `split()`. For instance, the regular `.split(“i”)` would cut the “i” out, right?
```ruby
str = "Vidhi is awesome"
str.split("i")
#=> ["V", "dh", " ", "s awesome"] 
```
However, you can use an expression that will find an “i” and save everything that comes before, for instance:
```ruby
str = "Vidhi is awesome"
str.split(/(?<=i)/)
#=> ["Vi", "dhi", " i", "s awesome"] 
```
Or even just split it only on the first “i”:
```ruby
str.split(/(?<=i)(.*)/)
#=> ["Vi", "dhi is awesome"] 
```
‼️ Here’s a bunch of resources that may help you with regex ‼️
1.  [a Regex console and cheatsheet](https://regexr.com/) that helps you locate specific patterns - you can paste your text and then use cheatsheet on the left to build your expression and see if what you’re trying to target is being targeted
2.  [a Regex practice tool](https://regexcrossword.com/) for those nights when you can’t sleep and need something to help you do that
Please don’t trouble yourself with learning Regex or even about Regex. You don’t need it currently, if ever. Just know that if you ever need to find a pattern, you can use Regex — and google your way through it ❤️

---
##  Week 1 Day 3

### After lecture
:ruby: Lecture chat notes :ruby:
✨ methods whose name starts with `self.`  are class methods, meaning, they are called on the class itself and so the self is the class;
✨ You’d use single quotes for strings that contain double quotes, e.g. 'My favorite doc is "Samsara"'
✨ `new` is a class method, which generally creates an instance of the class (this deals with the tricky stuff like allocating memory that Ruby shields you from so you don’t have to get too dirty). `new` calls on `initialize`
✨ `initialize`, an instance method, tells the object to set its internal state up according to the parameters requested
✨ ruby style guide: https://rubystyle.guide/ :bangbang::bangbang::bangbang:
✨ overview of Ruby variables through an analogy: https://medium.com/swlh/hitchhikers-guide-to-ruby-variables-1b4cf83d540c
✨ adding elements to an array is not changing its data type or memory path so you’re not mutating it
✨ when initialized, an array is given a memory path, no matter how many elements it has, even if it is empty; because of that, Ruby is not throwing errors when you’re adding elements to the array
@here 

### Method chaining
On the question of whether you can chain methods to the end of the ruby block, the Ruby style guide recommends against it and shows preference for the inline (or {...} ) syntax for chaining:
> Avoid do…​end when chaining.
```ruby
# bad
names.select do |name|
  name.start_with?('S')
end.map { |name| name.upcase }
# good
names.select { |name| name.start_with?('S') }.map(&:upcase)
```
More on this here:
https://rubystyle.guide/#single-line-blocks

### Before pair programming
- CASK feedback framework write-up: https://medium.com/unsupervised-learning/giving-actionable-specific-and-kind-feedback-6fc83eb04a65
- Recipe for a good pair-programming experience: https://docs.google.com/document/d/1x5UJk5FJ2MGNtkAR48-RdpQiUzoHARNbdfluWR8miIk/edit?usp=sharing

Contract for pair programming: https://docs.google.com/document/d/1ce3zFnY_z3VoVQNmpqQHt1Bm00l8HThioPubD80Haq4/edit?usp=sharing
Make a copy of this doc before filling out. One per team.

### After pair programming
 If your pair is done with lab. Here is the feedback form: LINK. Please take few mins to feel it out before you provide feedback to your partner.

### Getting Comfortable with Command Line
 Hey folks! Here's a video by one of our coaches that will help you get more comfortable with the command line. Check it out once you've finished those labs 
https://youtu.be/WH_Zp_aMKXU
Here's a mini challenge, after watching the video, try to create and organize your files for the program!
It should look something like this:
```
Flatiron/
   |
   |-- Mod1/
        |- Labs/
        |- DQs/
        |- Code-Challenge/
        |- Project/
   |-- Mod2/
        |- Labs/
     ...etc
```
---
##  Week 1 Day 4

### After lecture
✨ Ruby allows you to “extend” their classes — you can customize all the errors, all the classes, all the validations and methods (e.g. if you want a method to accept an additional argument for some reason or for a given error to catch also other, application-specific exceptions)
✨ relational databases expect to know exactly what columns a table will have when created; in the lecture example, you know that each Tweet will have a User but don’t know how many tweets a user will have; in our terminology, we say that Tweet `belongs_to` User, and User `has_many` Tweets; because of that, you will add a `user_id` column to the Tweet and not 10,000,000 `tweet_id` columns to the user;
✨ article on the difference between using an @class_var and self.class_var: https://medium.com/@sgg2123/vs-self-in-ruby-1d4d88170

### Require vs require_all question
✨ `require` vs `require_all`  vs `require_all` :  https://medium.com/@ellishim/understanding-require-vs-require-relative-vs-require-all-80e3b26d89e6
Though `require` can be used to both execute gems and external dependencies, the preferable method to load relative paths is `require_relative`. `require_relative` is a subset of `require` and is a convenient method to use when you are referring to a file that is relative to the current file you are working on (basically, within the same project directory).
So why would you want to use `require_relative` over `require`? While `require` relies on the directories loaded in root, the `require_all` gem allows you to execute code from other files without having to shovel in directories beforehand. The general rule of thumb is `require` should be used for external files, like gems, while `require_relative` should be used for referring to files within your directory. Though you can call on absolute paths using both methods, but `require_relative`’s scope is wider and is aware of the entire directory where the program resides.

### Getting lecture code
How to get lecture code?
✨`git clone` (do not fork) this repo: COHORT REPO
✨`cd` into the folder
How to get updated/new lecture code?
✨ `cd` to the lecture folder that you have cloned down (from step-1)
✨ run `git pull`; if you get an error about the uncommitted changes:
- the changes are important: `git add . & git commit -m "work in progress" & git pull`
- if the changes are not important: `git stash`
✨ if you have `git pull`ed but the code you see on github has not downloaded, you can run `git pull origin master` and see if that fixes the problem

### Asking good questions
Here are Stack Overflow guidelines on asking a good question, which became the industry standard
https://stackoverflow.com/help/how-to-ask

##  Week 1 Day 5

### EOD
What to do if you feel overwhelmed and behind in labs?
-> First and foremost: this is totally normal! You are enrolled at a top-tier "Software Engineering Immersive Bootcamp"; this is a normal way to feel the first week!
-> Each section has fundamental material, these are usually the topics that have a reading immediately followed by a lab. Usually at the end of each section there will be an 'Advanced Lab', these are still beneficial but of less utility to you than other fundamental topics from other sections you may have not gotten to yet. I would suggest doing 80% of each section and finishing everything rather than doing 100% of only 80% of the labs.  Keep in mind: the first week is the hardest and you've all made it this far  As we go froward you will get better with the tempo and pace of program and better develop strategies to excel as a result. Be patient yet persistent and keep asking as many questions as you may need, we here to get you there!
See you all Monday!

### Weekend message
@here Are you enjoying Ruby? Here are some newsletters that bring joy:
:ruby: general Ruby hot goss: https://rubyweekly.com/
:ruby: Sandi Metz’s newsletter: https://www.sandimetz.com/subscribe
:ruby: Advi Grimm’s newsletter https://www.rubytapas.com/category/brunch/
Here are great Ruby blogs:
:ruby: Sandi Metz’s blog: https://www.sandimetz.com/blog
:ruby: Thoughtbot’s blog (posts tagged Ruby):https://thoughtbot.com/blog/tags/ruby
:ruby: Ruby Reddit: https://www.reddit.com/r/ruby/
:heart: If you want to take a break but feel guilty about abandoning Ruby :heart:
Beth Haubert created a melody extrator in Ruby that turns any song into meowing
hear her talk: https://www.youtube.com/watch?v=W7KL1jl1bKM
read about it: https://thoughtbot.com/blog/meowifier-a-hiss-tory-lesson 

===
##  Week 2 Day 1

### If / else
Hey folks! Something I noticed many people do but is redundant is the following code:
```ruby
if courses.length > 2
  true
else
  false
end
```
 or, in ternary version:
`courses.length > 2 ? true : false`
This can be reduced to just: `courses.length > 2 `
because the condition itself already evaluates it to true or false.
✨ **tl;dr: skip conditionals if your “action” is “return true” or “return false”**  ✨ 

## Week 2 Day 3

### SQL
Don’t you love the all-caps SQL expressions? :smile: Here's a little trivia blog post about the syntax:
https://dev.to/sylwiavargas/cs-trivia-7-why-is-sql-shouting-at-me-5f8e
While at it, if you want to get REALLY good at SQL, here’s a set of exercises based on real-world data: https://dev.to/zchtodd/sql30-day-1-wildfires-2b02

##  Week 2 Day 4

### SQL Pokemon Lab
Hey folks! In order to get the lab rolling, you’d need to start with schema_migration.sql  file. You can figure out what the sql statement should contain by reading the specs.
However, since the readme kinda states that this file should already be given to you, I add the code snippet in the comment.
```sql
CREATE TABLE IF NOT EXISTS pokemon(id INTEGER PRIMARY KEY, name TEXT, type TEXT);
```

## Week 2 Day 5

### After lecture
@channel remember:
 :clap: never :clap: change :clap: your :clap: schema :clap: file

### ActiveRecord Hierarchy
Cheat Sheet for directory hierarchy etc.  https://dev.to/jbshipman/activerecord-rake-cheatsheet-21l6 

### Git methods walkthrough for the project week
If you've finished all the labs, you can watch this video tutorial that shows you all the git basics that you'll need for Project Week :github:
https://youtu.be/fmF19_TvplU

### Project guidelines announcement slackbot message
Here are the guidelines for the project: https://learn.co/tracks/module-1-web-development-immersive-3-0/ruby/module-1-projects/module-1-final-project-guidelines. 
Here is document for project pitch: https://docs.google.com/document/d/1GfTDCwFGCAnvEhxhzfwbd4OHJZCQgsii0PLX6x_QCMA/edit. Make copy of this document and send it us on Monday before your project approval.
Visit LINK to see your assigned groups.

### Module 1 sample projects
Module 1 sample projects: (GitHub repo | Video)
https://github.com/timothyalton/module-one-final-project-guidelines-houston-web-012720		 | https://youtu.be/QRCCYkc8oMU
https://github.com/Gavrilajava/Map-Scrapper-Placido-and-Georgii-mod1-project		 | https://youtu.be/pm74u-FsfX4
https://github.com/pahoffart25/module-one-final-project-guidelines-houston-web-012720		 | https://www.youtube.com/?v=PK-nLyU75aI&feature=youtu.be
https://github.com/DrVonDevious/PokeCli | https://youtu.be/-bgkli4to2Q
https://github.com/GianMoran/module-one-final-project-guidelines-houston-web-012720		 | https://www.youtube.com/watch?v=yZUel6mHJjY
https://github.com/SteRobWms/module-one-final-project-guidelines-houston-web-012720		 | https://youtu.be/_Bkc0ABOoy4

===
## Week 3 Day 1

### Morning message
@channel Good morning everybody! If you feel comfortable with labs, you can also use this time to ideate on the projects and/or send us your pitch. In preparing the docs for the pitch:
remember to make a copy of the form on the google docs;
enable commenting access on the doc;
send it in a message to INSTRUCTOR, COACH your partner and me :slightly_smiling_face:

### After lecture
:ruby: About ActiveRecord’s `pluralize` method and non-standard words from the English-centric perspective: :ruby:
if the word is of non-English and a relatively new addition to the language or if it’s an entirely made-up word, AR will just add “s” to the end:
- “Spaghetti” is already plural but `"Spaghetti".pluralize`  gives us "Spaghettis"
- “spaghetto” is singlular but `"spaghetti".pluralize` gives us "spaghettos"
- “pokemon” is uncountable but it’s gonna be “pokemons”
- “ąę” will be “ąęs”
and this is how pluralize deals with the right-to-left alphabets:
```ruby
"מה זה".pluralize
=> "מה זהs\n"
```
You can override the pluralization by extending the Inflector class:
- https://apidock.com/rails/ActiveSupport/Inflector
- https://flylib.com/books/en/2.44.1/understanding_pluralization_rules.html
- https://medium.com/@anna7/ruby-on-rails-pluralization-b3927de2ca8e
@here

## Week 3 

### Github and project week

:ruby: :ruby: :ruby: :ruby: :ruby: :ruby: :ruby: :ruby:  ALL ABOUT GIT :ruby: :ruby: :ruby: :ruby: :ruby: :ruby: :ruby: :ruby:
Routine my tech collective follows:
- everyone is added as a collaborator to the repo;
- clone the repo; in the repo, have two standard branches: `master` and `dev`;
- before coding (each time), first run `git pull origin master`, then `git checkout -b nameOfTheFeature-yourName`; every now and then, `push` the code to that new branch;
- once the feature is “done” and you checked whether it’s not bugging out, merge it to `dev`;
- once it’s on the `dev`, your partner checks your code and if it’s okay, they merges it to `master`;
**SO:**
- `master branch`: ONLY push to this branch if the feature is working + reviewed by both partners
- `dev branch`: code that works + is up for review (it’s like a pull request?)
- `feature branch`: code in progress
We use `git projects` (instead of trello or asana) and git issues. We do stand ups and stand downs every day, where we distribute tasks and give summaries of what has been done.
**SOME RESOURCES:**
- A blog post by my former student on streamlining git add/commit/push: https://medium.com/swlh/creating-new-bash-commands-and-aliases-c9272fd589c4
- A guide to good commit messages: https://www.freecodecamp.org/news/writing-good-commit-messages-a-practical-guide/
- A git cheat-sheet: https://education.github.com/git-cheat-sheet-education.pdf
:ruby: :ruby: :ruby: :ruby: :ruby: :ruby: :ruby: :ruby: CLI SNACKS :ruby: :ruby: :ruby: :ruby: :ruby: :ruby: :ruby: :ruby:
**SOME RESOURCES:**
- A cli starter repo, which basically gives you a basic file organization that I created to help students start somewhere :slightly_smiling_face: I also mention some helpful gems, APIs and trick in the README . Sharing in case it’s helpful: https://github.com/sylwiavargas/Ruby-CLI-Setup
- Adding animations to your CLI: https://medium.com/better-programming/add-an-animation-or-a-giph-to-your-ruby-cli-29952e8c46ea
@here 

### Daily checkins doc
(this is for the yale cohort, create a copy)
Daily checkin: https://docs.google.com/spreadsheets/d/1vdkwgz4z06BYKYmr13eLKtWDAyzsPAPKquIE6dSOX50/edit#gid=0

### Public APIs
Here's a list of free public apis that you can use to get all sorts of data!
https://github.com/public-apis/public-apis

### API Keys
One of the ways we can hide and using our api key:
- create a `.gitignore` file at the top level of the repo
`touch .gitignore`
- add `.env` to your gitignore file
- add and commit this change** so that git knows not to track this file sooner than later
`git add . && git commit -m "..."`
- create a `.env` file at the top level of your repository of the repo
`touch .env`
- add your API Key to your `.env` file
Example:
`GOOGLE_MAPS_API_KEY="thisisakey154321"`
Now it'll be hidden, then you can use it by:
- installing the `dotenv gem`
`gem install dotenv`
- in the files that need the env variable you can require it
`require dotenv`
- then you should be able to use it this way
`ENV['GOOGLE_MAPS_APY_KEY']`

### Getting started with CLI
Hey Folks! In case you feel like you don’t know where to start with the CLI or don’t want to pre-seed your database with an API response but make calls on the go instead, here’s a lecture I ran about half a year ago where we’re creating a dad jokes app. The first part is a walk-through on how to set up a CLI and the second is all about making requests to an external API —instead of seeding the database, it makes a request on the go (and saves them if you want) + there’s also some dose of regex and other snacks :heart: you can also just check the code instead (“done_kit” folder contains A LOT of comments so everyone can see what does what) or download it and play around.
:film_projector: video (pt 1): https://www.youtube.com/watch?v=Jhcjvt4fxpc
:film_projector: video (pt2): https://youtu.be/mwcRjASeUFI
:space_invader:code: https://github.com/learn-co-students/nyc-dumbo-web-111819/tree/master/10-hashes-and-the-internet
@here 

### Reseting the id incrementation
:ruby: problem: seeding causes incrementation of the id’s :ruby:
Have you noticed that when running `rake db:seed`, the ids keep incrementing even though you have the same number of entries and have `destroy_all` at the top? Well, that’s because of how relational databases work: even though something has been destroyed, its id is still “reserved” in case some code or other entities depend on it. However, it is annoying when you’re just developing your app. How to get around it?
add this to the gemfile:
`gem 'activerecord-reset-pk-sequence'`
  2.  run:
`bundle install`
  3. add this in the seeds:
`User.destroy_all`
`User.reset_pk_sequence`
@here

### Default values
Question: How can we provide default values to attributes using activeRecord?
Answer: You can provide default value in migration for any attribute/column. For example: t.integer :total, :default => 0

### Hiding terminal output
:ruby: Question: How do I turn off my SQL logger?
:ruby:  Answer:  ruby # in config/environment.rb add this line: ActiveRecord::Base.logger = nil
and if you don’t have environment.rb file, you can add it in the runner or just directly in the class

### SQL Injections
SQL injection and security: the site has a lot of interesting cybersecurity topics, and interactive tutorials https://www.hacksplaining.com/prevention/sql-injection