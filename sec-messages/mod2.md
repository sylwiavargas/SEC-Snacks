# Mod 2

## Week 1 Day 1

### ERB tags
 If you feel confused about ERB tags, here’s a very simplified cheat sheet that works 90% of the time:
https://medium.com/swlh/cheatsheet-which-erb-tag-should-i-use-4b3de261f15f

### Nokogiri
If Nokogiri takes some time, you can run:
`gem install nokogiri -- --use-system-libraries`
From this Github issue:
https://github.com/flavorjones/mini_portile/issues/31

### Capybara announcement
@here  CAPYBARA ANNOUNCEMENT in case someone drifted away:
We thought we’d spare you despair and give you a heads-up on that the tests for this module are written in Capybara. They are slightly different - Capybara tests are SUPER specific. If your wording/spacing/capitalization/spelling is not exact and precise, the test will not pass. It is more precise than the tests for the previous labs. If you solve the problem, and you get the output that the read me asks, but the tests do not pass, that is okay. These labs are going to test you behavior-driven development skills, unlike the other labs which were using test-driven development.
Also, some tests require you to finish ALL the app (even if the error mentions a status code or routing) to turn green so you may wanna move onto the next error before losing patience.
Please don’t feel discouraged if you did what has been asked from you and yet the tests are not passing. The real test of whether your code is working is how it looks in the browser.
However, if you are a person who cares about having the learn.co all adorned with green marks :green_light:, you can either spend more time comparing your code vs the tests, change the tests or simply check the solution branch on GitHub and see where the difference is.
:bangbang: BUT PLEASE DO REMEMBER THAT CAPYBARAS ARE AWSOME IN REALITY :bangbang:
Here’s a meme about capybaras bringing folks together:
https://files.slack.com/files-pri/T02MD9XTF-F015A6LL347/capy.jpeg

## Week 1

### Labels in HTML
:railsrailsrails: :railsrailsrails: :railsrailsrails: Labels in HTML :railsrailsrails: :railsrailsrails: :railsrailsrails:
:arrow_right:  What is it for: the `<label>` tag enhances user experience,  making it easy to make sure what you are expected to type in the field but also increasing its accessibility for screen users.
:arrow_right: In plain HTML, do we need to include the `id` ?
- YES, if you write your labels above the input (and you need the attribute “for”)
```html
<label for = "city"> City </label>
 <input type="text" name="City" id="city">
```
- NO, if you wrap the label around the input — this should be used as a last resort, e.g. when you are using third-party code and can’t know what the id generated:
```html
<label> City
 <input type="text" name="City" id="city">
</label>
```
:arrow_right: Sometimes folks don’t want to use a label because they know how to style it to look okay or think that without a label their page looks better and the placeholder text in the inputs already makes it clear what you are supposed to type in. This approach makes your page inaccessible because navigation through a form without labels is a real nightmare if you’re using a screen reader + placeholders can do only so much even for the sighted users. However, if you decide to not have labels on the page, do it properly:
:sparkles: **Approach 1:** keep the label but visually hide it with css:
```html
<label for="search" class="visuallyhidden">Search: </label>
<input type="text" name="search" id="search">
<button type="submit">Search</button>
```
:sparkles: **Approach 2:** Use an `aria-label`:
<input type="text" name="search" aria-label="Search">
<button type="submit">Search</button>
```
@here

### Deleting dependents
Problem: ActiveRecord doesn't delete dependent objects by using force: :cascade!
Solution:
In the model with association add: dependent: :destroy
For example,
```ruby
class Owner < ActiveRecord::Base
    has_many :dogs, dependent: :destroy
end
```
A foreign key with cascade delete means that if a record in the parent table is deleted, then the corresponding records in the child table will automatically be deleted. This is called a cascade delete in SQL Server.
[Good explanation of cascade (ON DELETE/UPDATE) behavior](https://dba.stackexchange.com/questions/44956/good-explanation-of-cascade-on-delete-update-behavior)

### Closing zombie ports
Hey if any of you are having port issues with shotgun, check out Sylwia’s blog that shows you how to kill a running process you can’t initially see:
https://dev.to/sylwiavargas/how-to-properly-close-a-port-2p36

### REST API and request-response cycle
An article about REST APIs and the request-response cycle that I found helpful:
https://www.smashingmagazine.com/2018/01/understanding-using-rest-api/

### HTTP Codes with Rihanna
:sparkles: HTTP codes with Rihanna: https://www.httriri.com/ :sparkles:
It’s a work in progress — Monica Powell has launched it just recently and you all can contribute the gifs there to the codes that are missing :heart: contribute here: https://github.com/M0nica/httriri
@here

### VS Code Extenstions
VS Code extensions for ERB, HTML and CSS:
:sparkles: Auto-closing tags: https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag
:sparkles: CSS color picker: https://marketplace.visualstudio.com/items?itemName=lihui.vs-color-picker
:sparkles: HTML CSS support: https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css#review-details
:sparkles: Prettier (code formatter — helps you with proper indentation): https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode
:sparkles: Rainbow brackets (so you know where your brackets are ending): https://marketplace.visualstudio.com/items?itemName=2gua.rainbow-brackets
:sparkles: Rainbow indentation: https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow
:sparkles: Simple Ruby ERB (Cycles through the tags <%= %>, <% %> and <%# %> ) :https://marketplace.visualstudio.com/items?itemName=vortizhe.simple-ruby-erb

___ 
## Week 2 

### Troubleshooting Rails app
Something is not working in your rails app? Follow these steps:
1) Check `config/routes`
2) Are your routes connected to an action in a controller?
3) Action in the controller —does it exist?
4) What are you sending over to the views?
5) What’s being rendered on the views?
@here

### Rails and forms
@here read more about form_for, form_tag, form_with:
:sparkles: docs: https://guides.rubyonrails.org/form_helpers.html
:sparkles: blog: https://m.patrikonrails.com/rails-5-1s-form-with-vs-old-form-helpers-3a5f72a8c78a

### Index action on Rails infographic by isabel
https://files.slack.com/files-pri/T02MD9XTF-F0117ULNNKB/rails_index_action.png

### Notes on action by Eric
https://flatiron-school.slack.com/files/U91CXSUN4/F011J44A8EL/rails__1_.pdf

### CRUDopus
https://flatiron-school.slack.com/files/U91CXSUN4/F011KH2KUM7/restful_diagram__1_.png

### Nice formatting of Rails
Problem: How to get nice formatting in the Rails console?
-------------------------------------------------------------------------
**Solution-1:** 
- add `gem "awesome_print"` to gem file
- In rails console: run commands starting with ap for example: `ap Dog.all`
-------------------------------------------------------------------------
**Solution-2:**
Add "awesome_print" gem by default with irb/rails/pry console:
`gem install awesome_print`
Add following lines to your `~/.irbrc`   file(usually find at `/Users/yourLaptopUsername/.irbrcat`):
```bash
require "awesome_print"
AwesomePrint.irb!
```

### Validations in Rails
@here Build your own custom validations in two ways:
https://dev.to/sylwiavargas/rails-custom-validations-58mo
For only changing error messages, :message  option can be used. Find more details here: https://guides.rubyonrails.org/active_record_validations.html#message

### Rails generators:
Rails generators syntax: https://medium.com/@kevinyckim33/rails-generators-cli-cheatsheet-711295e7a1ed

### Ruby on Rails Slack Community:
@here Here’s a Ruby on Rails slack community of ~15k devs who always are happy to help out and share awesome materials :heart:
https://www.rubyonrails.link/

### Before Code Challenge
@channel I remember that what helped me in my code challenge was developing a structure/habit in approaching a lab. I’d encourage you to develop one for yourself if you stress out or feel overwhelmed. Write a step-by-step instruction for yourself and do three labs following the steps.  For instance, here are the steps that helped me pass&finish fast:
1. `git clone, bundle install`
2. While your terminal is doing the job, read the instruction.
3. ON A WHITEBOARD: draw the models, draw the associations (does it need a join model?), write what each model needs (columns), mark validations and views
NOW only you’re starting to code. Create models (`rails g model`). I’d also copy/paste instructions for each model from the read me. If you feel like a task is super confusing, put it at the bottom of the list so that you get to it at the end (5/6 tasks done is better than being stuck for 40 minutes in panic)
4. Add association macros and validations in models
5. Create and run migrations: `rails db:create`, `rails db:migrate`
6. Write seed data just to check associations (I’d say, three instances of each class but only 2 for a joiner; in each of the classes, there should be one instance without connection)
7. `rails db:seed`
8. In `rails console`: try to access instances of different classes through associations:
- check whether your seeds exist (e.g. `User.all or User.all.first`)
- check whether associations work (e.g. `User.all.first.students` would check for all my students and `User.all.first.laptop` would check for the laptop of the first user and `User.all.first.laptop.gadgets.first`  would check the first gadget that belongs to the laptop)
- check validations: try to create a student with incomplete required stuff and then checks if it went to your database (e.g. `User.all.last`) — if it did, you check your validations
9. check which routes you’d need, go to `config/routes.rb`, write up the correct routes
10. create controllers (`rails g controller users`) and fill them up with the actions that are in accordance with the routes and the readme
11. create views that are required from you by the readme
12. fire up the server: `rails s`
13. go have fun with your page —try to break it!
AND OF COURSE YOU DON’T HAVE TO FOLLOW THIS! My point is only that for me it felt overwhelming and I developed a structure/habit that helped me not panic and not forget to e.g. test!

### Pulse Check Survey
@channel As the CODE CHALLENGE is approaching, we’d like to make sure you all are in great shape. Here’s a little pulse check — for you to tidy up all your learnings (yes, it is a word) and for us to see how to better assist you in the upcoming days. Here’s how it works:
1) You’ve got 5 hours (by 6pm today) to complete the survey;
2) Please google/use notes whenever necessary — this is an opportunity for you to learn more;
3) If you do google, could you please write [NI] for “no idea” and [NS] for “not sure” in your answer so we know how confident you were when you first saw the question? We are not judging you for not knowing, we genuinely want to help out!
Any questions? Ask us!
here’s the link: LINK

### For/in loop vs each
:ruby: :ruby: :ruby:  I heard a good question today: why is for/in loop a less optimal option than .each? :ruby: :ruby: :ruby:
So, `for/in loop` contains an elaborate `if/else` statement and also, syntactic sugar for each and as such:
- takes more computing time
- uses more memory because it has a wider lexical scope
- has a different return statement
- its variable (e.g. for element in array; the element is the variable) is returned
`.each` on the other hand works on a block of code, returns the same array and introduces new, temporary lexical scope and as such is just faster
Look here, element persists in the memory when using `for/in`:
```ruby
array = [1,2,3]
for element in array
     puts element
end
# => 1
# => 2
# => 3
# => [1, 2, 3] 
element
# => 3 
```
vs in `.each`:
```ruby
array = [1,2,3]
array.each{|el| puts el}
# => 1
# => 2
# => 3
# => [1, 2, 3] 
element
# => NameError (undefined local variable or method `el' for main:Object)
```
Read more: http://graysoftinc.com/early-steps/the-evils-of-the-for-loop

## Dark Mode with Cookies
:cookie:  :cookie:  :cookie:  :cookie:  :cookie:  :cookie:  :cookie:  :cookie:  :cookie:
@here’s a blog on dark/light modes with Rails: https://medium.com/@sylwiavargas/dark-mode-in-ruby-on-rails-with-cookies-c892ac52ebaa
:cookie:  :cookie:  :cookie:  :cookie:  :cookie:  :cookie:  :cookie:  :cookie:  :cookie:

___
## Project Week 

### Welcome
:sparkles:  :sparkles: WELCOME TO PROJECT WEEK! :sparkles: :sparkles:
Most importantly: congratulations to ALL OF YOU for passing the code challenge. You are such a wonderful community of folks who help each other succeed :meow_party:
We have deployed MOD2 project guidelines. Before you start coding, we want you to:
:sparkles: think through your app;
:sparkles: check next week’s schedule to be very much aware of the lectures that are coming your way so you plan accordingly;
:sparkles: copy this project pitch template into your own document and fill it out;
:sparkles: create a wireframe in figma, sketch, or adobe xd (all of them are free) and submit it together with the template;
:sparkles: once you’re done with it, send these documents in a message to Eric+Ian+Rei+me; if we have any further questions, we’ll send you a message or get on a call with you :heart: however, try to already think about what questions we will have and answer them in your template beforehand to continue having wonderful and frustration-free lives :heart:
You can start coding only once you’ve gotten our approval.
What questions do you have about this process?
@channel

### Postgresql
you should all consider creating your Rails app using Postgres instead of Sqlite to make it easy for yourself to deploy your website to the world.

The command for that is:

`rails new myapp --database=postgresql`

You’ll need to also have downloaded the app from https://postgresapp.com/ and have it running on your computer while working.
The only major difference is that before you run `rails db:migrate`, you’ll have to create your database by first running `rails db:create`

### Good pairing reminder
@channel I hope you guys are enjoying this beautiful weather and getting some rest before the project week!
Because I believe it’s great to enter a new week with strong motivation to show up and contribute, I am resharing the ideal-world scenario on collaboration. Please please please make sure you and your partner are on the same page with regards to the project idea, app functionality and code. It all has to be consensual — before the week begins, think about how you can make this week a wonderful experience for yourself and your partner. For instance:
- if your partner usually does not speak up, make sure to take a step back and let them speak!
- if you usually don’t express your thoughts, this is the time for you to train that skill!
- ask, and ask again, whether all is clear!
- and lastly, PLEASE AGREE ON GROUND RULES (how you’ll resolve misunderstandings and differences, how much you’ll work, etc.)
Here’s the doc I shared with you previously:
https://docs.google.com/document/u/4/d/1x5UJk5FJ2MGNtkAR48-RdpQiUzoHARNbdfluWR8miIk/edit?usp=sharing
tl;dr: here’s a pair-programming/project recipe you can follow:

### Challenging folks to be ambitions
:sparkles: :sparkles: :sparkles: :sparkles: :sparkles: :sparkles: :sparkles: :sparkles: :sparkles: :sparkles:
Hello Friends!
Since everyone passed the code challenge and everyone is working solo, we want to encourage you to:
- have a basic mvp and be done with it in two days,
- dream big about additional features (and implement them one by one).
We want you to take time to learn stuff that will benefit you in the next mods. Here’s a curated of ideas of stuff that can really make it easier for you in the next mods:
**RAILS:**
- custom validations;
- custom routes (e.g. when I click on the button, it sends a POST request, creates another instance of the join model and increases points in the database);
- custom error handling;
- auth;
- self-referential and polymorphic models (e.g. a user can follow another user on social media);
- guard clauses - instead of else/ifs;
- named scope — a way to make faster database queries (e.g. if you want a method that will always give you entries in a specific order);
request tests;
- using cookies for dark/light mode;
- nested forms (nested params) —a form that creates instances of a few models all at once;
**GEMS:**
- seeding data from an external API;
- ActiveMailer — sending email notifications;
- ActiveStorage — profile picture upload (if they have user model);
- Twillio API — sending sms (you can connect it to the dev hackaton; read more: https://dev.to/devteam/announcing-the-twilio-hackathon-on-dev-2lh8)
**CSS:** 
- use a styling library like bootstrap, semantic ui, bulma — really straightforward implementation, good docs, lots of blog posts; You’ll save so much time in the next mods;
@channel

### Rails project examples:
Additional examples with youtube videos:
https://github.com/anamsoomro/CaptionIt		https://youtu.be/qpiVlTYH9As
https://github.com/pahoffart25/project-2		https://www.youtube.com/watch?v=15LeO02_Ms0&feature=youtu.be
https://github.com/somaia-khalil/QuizMe1		https://www.youtube.com/watch?v=FTQ13u0bsoM&feature=youtu.be
https://github.com/SteRobWms/mod2-blackjack-project		https://youtu.be/A7KbyE3_uwA
https://github.com/timothyalton/flight-guru-app		

### I wish I had known about CSS
Here’s something I wish I had known before doing my MOD2 (that I cover in the lecture and in the repo):
:bangbang: 4 RULES OF CSS :bangbang:
- **Cascade:** CSS is a cascade (a type of algorithm). At a very low level, it means that that the order of CSS rules matter; meaning, if you define a background color of a div in two places, the color that comes last will be applied;
- **Specificity:** however, more important than the cascading character of css is the rule of specificity; CSS will take more seriously the requsts that are more specific; here’s the hierarchy of specificity (from the most to the least): element selector -> class selector -> id selector note: inline CSS is more specific than external file, which is why it’s easy to overwrite external libraries;
PS: Specificity is set up with point system -- each declaration is evaluated in points, then compared and the winners take it all! For instance, if you declare styling inline, this declaration gets 1000 points from the get-go (for real), as opposed to 0 when declared in an outside stylesheet;
- **Inheritance:** now, some elements inherit styling from their parents while others don’t; for instance, color and font will be inherited by children but width and height will not! You can play with inheritance by using an inherit attribute!
- **!important:** now, you can override all rules using the value of !important; however, beware: you will enter the long-term css debugging hell if you invite this value without an absolute desperate necessity;

### Friendly CSS libraries:
:sparkles: :sparkles: :sparkles:  Friendly CSS libraries  :sparkles: :sparkles: :sparkles:
Semantic UI (my fav): https://semantic-ui.com/
setting up with Rails: https://stackoverflow.com/questions/37283642/how-do-i-set-up-a-rails-application-with-semantic-ui
Materialize: https://materializecss.com/
Setting up with Rails: https://rubyinrails.com/2015/09/17/how-to-integrate-material-ui-with-rails/
Bootstrap: https://getbootstrap.com/
Setting up with Rails: https://github.com/twbs/bootstrap-rubygem (edited) 

### Make your page accessible
LAST BUT NOT LEAST, PLEASE READ ABOUT HOW TO MAKE YOUR PAGE ACCESSIBLE:
https://dev.to/sylwiavargas/checklist-web-accessibility-3abl

### Polymorhpic / Self-referential 
@here if anyone is thinking about building a social media platform, please be mindful of that you need to have so-called self-referential/polymorphic associations. For instance, in a standard social media site, you’d have a functionality of users following each other. That would mean that a User has_many Users (followers) and/or has_many Users (and those who they follow) but also belongs_to User. That’s messy unless you build it with self-referentials. Other examples of this include e.g. comments, liked posts, etc.
Please read this before you venture onto this quest :slightly_smiling_face:
- https://medium.com/@TheDickWard/self-referential-relationships-aka-self-joins-in-rails-64f8f36ac311
- https://flatiron-school.slack.com/archives/G0167UWPN2W/p1593444569002500
And watch this lecture by one of our instructors, Eric Kim on fancy Active Record including self-referentials:
Code: https://github.com/learn-co-students/dumbo-web-060319/tree/master/22-advanced-activerecord
Video: https://youtu.be/LDKZvG8NHto

### On designing your Domain Model:
Also, so I don’t need to say it in DMs:
If you are planning on filtering/sorting feature in your app based on an attribute, in 99% of cases, that is a hint for you to make this attribute a separate model. What do I mean by that? Imagine I’m building a database of all after-school activities run by teachers:
```
Activity -< ActivityTeacher >- Teacher
price                          name
subject
location
```
In this case, `subject` and `location` will be strings and `price` would be an int. In that case, it is possible that somewhere along the way you’d end up not only with spellings but also two different versions of e.g. the same subject (“Math” and “Mathematics”). Instead of thinking of 10,000 safeguards, you can just…
```
subject   
   |
   ^
Activity -< ActivityTeacher >- Teacher
   |
   ^                          
location
```
In this case, you pre-populate all the possible subjects and when someone wants to create a new entry, they just choose an already-existing one. It also helps with querying because instead of querying 10,000 activities to find the three that are connected to “curling”, you’d just find the Curling subject and get all `Activities` connected to it.
Moreover, `location` can also be further split into several models, e.g.: `city`, `zipcode`, `street`, etc. to make it easier to query.
@here

### Uploading files
If anyone is looking to upload files/pictures to their rails app:
- https://medium.com/@gabalexa/using-active-storage-to-handle-image-uploads-in-ruby-on-rails-b8df32be7d79
- https://medium.com/better-programming/how-to-upload-files-in-a-react-and-rails-app-69c31a9cf9b7
@here 

### Bootstrap and Rails
@here For all of you working with Bootstrap, please remember that it is an opinionated library and it needs you to follow closely best practices in the framework/library of your choosing, which means that e.g. instead of using `<button>` , it prefers you use `<%= button_to %>`  . In the same manner, there’s also a gem specifically for forms:
https://github.com/bootstrap-ruby/bootstrap_form
And a gem specifically for nav bars (I never worked with this one):
https://github.com/bootstrap-ruby/rails-bootstrap-navbar
Here’s one project from my previous student (Stephanie Zou) who used Bootstrap with Rails and shed many tears. If something is not working in your code, please check how she implemented it for reference:
https://github.com/stephaniezou1/Acorn-Search-Engine

### Community message
:sunny: :sunny: :sunny: :sunny: :sunny: :sunny: :sunny: :sunny:
Bold proposal: I know this program feels like SCHOOL but it doesn’t have to! Let’s think about this first and foremost as a community of folks who are doing this courageous thing with their lives. If you take such lense, it’s going to be easier not only to offer help (you all are great with this) but also to reach out to others. You are all sooo knowledgeable and resourceful — help each other share their skills and insights with you!
For instance, if you feel like you’re totally not great with design —make a post here and let others help you out! Or, if you feel like your method is clunky ask others to look at it. And if you’re asked to look at it, don’t just say “it’s good” —ask questions! Working together while working separately on different projects is SOOOO rewarding —and that’s gonna be your life as devs!
Good questions to ask in order to get informative feedback on your code:
- could you read this out loud to me and tell me what this code should be doing? (if they can’t, the reason might be how you wrote the code!)
- how do you think I could name this better?
- the problem I’m trying to solve is xyz — can you brainstorm with me ways I could achieve that?
Good questions to ask when you’re giving feedback:
- what feedback are you looking for?
- if you had to cut out two lines of code from your project/model/controller, which ones would you cut?
- which part did you struggle with understanding when you were initially writing it — where are the comments that explain what this code does?
- could you explain to me what this class/method/controller/route does?
- could you show me how one uses your app? What do ou think would make the experience easier? How do you think you can achieve that yourself or by reaching to others?
:sunny: :sunny: :sunny: :sunny: :sunny: :sunny: :sunny: :sunny: :sunny:

___
## Week 3 Day 5

### Before JS
@here if at any point today you fell done with the project and rails and want to have a pleasant read about JS, I’d recommend either of these two very friendly books:
- https://justjavascript.com/ - written by Dan Abramov (React core team, creator of Redux); it’s still free and comes in chapters to your email (so far only 8/10 mini-chapters are released)
- https://eloquentjavascript.net/ - a longer book that goes into details of how everything works in js; reading even one chapter can shed a lot of light on the language

### Sandi Metz's rules
Also, you could spend a second refactoring your project following Sandi Metz’s rules:
1. Classes can be no longer than one hundred lines of code.
2. Methods can be no longer than five lines of code.
3. Pass no more than four parameters into a method. Hash options are parameters.
4. Controllers can instantiate only one object. 
More on them here:
https://thoughtbot.com/blog/sandi-metz-rules-for-developers

### bye bye Rails
GREAT APPS, EVERYONE!! I really appreciate all the thought and work you put into the apps. You’ve worked very hard —and it shows. Congratulations! 🥳 🥳 🥳
A good way to close the Ruby chapter and enter JavaScript world is watching this video:
@here
https://files.slack.com/files-pri/T02MD9XTF-F01636RSAJ3/download/wat.mp4

### After project presentations
Resources I mentioned in the zoom chat:
 :star: Deploying Rails on Heroku:
https://medium.com/@kasiarosenb/deploying-your-rails-app-on-heroku-a2096dc40aac
:star: here’s a good starter for realtime messaging (without page refreshing):
 https://iridakos.com/programming/2019/04/04/creating-chat-application-rails-websockets
:star: here’s a good twilio walkthrough for sms messaging feature:
 https://www.twilio.com/blog/2017/12/send-sms-ruby-rails-5-coffee.html

 ### JS is powerful
 @here for all you Hamilton fans — an example of why JS is awesome and powerful:
https://pudding.cool/2017/03/hamilton/index.html

## JS Warmup
@here here’s the repo I created for today’s optional intro to js:
https://github.com/sylwiavargas/js-warmup
I thought today is going to be just an overview of js syntax, terminology and the differences that concern Rubyists. However, I am planning to give a few shorter “warm-ups” of this kind throughout mod3 to cover the stuff that’s good to know — sometimes it’s going to be a subject (e.g. practical difference between var , let  and const ) and sometimes it’s going to be one of the js gotchas that illustrate how the language works. You’re welcome to join, to fork the repo (so you can get updates even if you don’t participate) or not join and do your own thing :heart:

## DEPLOY
PLEASE DEPLOY!  
https://medium.com/@kasiarosenb/deploying-your-rails-app-on-heroku-a2096dc40aac
and write good readmes asap!
- brag about all the stuff you implemented and solutions (yes, auth, validations, nested routes, numerous user journeys, css library or pure css, external apis etc.)
- attach gifs that show your website
Here are two of my readmes to make your life easier:
- one that I’m more proud of: https://github.com/luanesouza/backend-lets-change-the-subject/blob/master/README.md
- one that is featuring the solutions (aimed at e.g. employees): https://github.com/sylwiavargas/Gentrification-Map-Frontend/blob/master/README.md

## Get excited about JS
:sparkles::sparkles: my personalized collection of :sparkles::sparkles:
:sparkles::sparkles::sparkles:JavaScript inspirations :sparkles::sparkles::sparkles:
beautiful pages, fun frameworks, amazing tools for this and next mods
for the moments when you hate JS to remind you of its beauty and power
first of all, SUBSCRIBE TO THIS EMAIL-BASED BOOK ASAP:
https://justjavascript.com/
-> it’s by Dan Abramov (an amazing dev on React core team), where he uses amazing analogies to explain how JS works and why
Warm-up:
http://eelslap.com/
https://theuselessweb.com/
Beautiful and fun stuff:
https://avseoul.net/particleEqualizer/ (!!!!!)
https://patatap.com/ (!!!)
https://codepen.io/TheCodeDepository/pen/jKBaoN?page=8
https://mattdesl.github.io/jsconfeu-generative-visuals/public/
http://www.fallingfalling.com/
https://bellwoods.xyz/
https://codepen.io/akm2/full/rHIsa
https://femurdesign.com/theremin/
Data viz:
https://pudding.cool/2017/03/hamilton/ (!!!!)
http://joshworth.com/dev/pixelspace/pixelspace_solarsystem.html (!!!)
Games:
Graham’s tetris: https://www.fuckyeahgtj.com/tetris/
Elizabeth Le and Woody Lucas: http://flatiron-ware-game.herokuapp.com/
Angelo Spaminato and Maximo Bautista: https://evolfo.github.io/tom-pilgrim-vs-the-universe/front-end/index.html
AR (Artificial Reality):
https://github.com/jeromeetienne/AR.js
https://stemkoski.github.io/AR-Examples/
Storytelling:
http://www.oatthegoat.co.nz/
http://i-remember.fr/en (!!!!)
Robots:
https://cylonjs.com/
ML (Machine Learning):
https://www.tensorflow.org/js/
Drawing:
https://trackingjs.com/
Lots of inspirations:
https://experiments.withgoogle.com/collection/chrome
Graham’s amazing page that involves scrolling:
http://www.fieldmuseum.org/discover/on-exhibit/specimens/
AI (Artificial Intelligence):
face recognition (good docs): https://github.com/justadudewhohacks/face-api.js/
real-time object detection (easy tutorial): https://developer.ibm.com/patterns/create-a-real-time-object-detection-app-using-watson-machine-learning/
Front-end fameworks I love dearly:
https://p5js.org/examples/
http://paperjs.org
https://two.js.org/examples/text.html
https://two.js.org/examples/rubber-ball.html
https://d3js.org/
:sparkles::sparkles::sparkles: Learn JavaScript :sparkles::sparkles::sparkles:
https://javascript30.com/ (once you feel comfortable with the basics)
https://eloquentjavascript.net/ (amazing textbook - but goes really into detail)
https://learnxinyminutes.com/docs/javascript/ (if you have questions like “but why” or “but how”)
https://github.com/getify/You-Dont-Know-JS (very much in-depth textbooks -- save it for mod6)
@channel