# Mod 3

## Week 1 Day 1

### first message
Hi @channel, welcome to JavaScript! I wanted to share some thoughts about the upcoming mod:
Entering JavaScript can feel like entering a new universe. This mod will take everything you’ve learned up until today and flip it on its head, but armed with this new knowledge, you’ll be able to build radically more interactive experiences. It will be so so so so much fun (and work)!
Your default track in learn should now be `web-development-immersive-3-0-module-three` (refresh your page if that is not the case). The curriculum focuses on getting ‘just enough javascript’ to make things happen in Front End Web Programming. We’ll get deeper into the nuances of the language later next week.
In the meantime, please take the time this weekend to work through the newly released labs and gain some comfort in JavaScript!

### Callbacks
Before our lecture, in addition to doing the labs and eating breakfast, please watch this medium-sized videos on Javascript callbacks:
https://youtu.be/Nau-iEEgEoM
You don’t need to go past more than 7:27-ish in the video, but if you want to watch the whole thing, please feel free to do so!
As one of the Youtube comments read, this video is:
One if the best explanation on callbacks on YouTube.
And if that’s not good enough, I don’t know what is.

### Question about semicolons
@here here are the answers to all the semicolon questions you have and will have, including the Automatic Semicolon Insertion:
http://inimino.org/~inimino/blog/javascript_semicolons

### JS Styleguide
AirBnB has one of the best JS formatting style guides to the point that many companies now treat AirBnB as standard. Here’s what they say about if/else:
https://github.com/airbnb/javascript#16.2

### A quick overview of JS
A quick overview of JS:
https://learnxinyminutes.com/docs/javascript/

### More JS inspiration:
Very fun JS project: https://saurabhdaware.github.io/text-to-handwriting/

### EOD
:heart:  CONGRATULATIONS ON SURVIVING  — and enjoying — YOUR FIRST JS DAY :heart:
now, take a break

---
## Week 1 Day 2

### Morning
@channel IT’S MOD3!!! YAY! Are you excited? Of course you are. You are most probably also stressed, worried and confused — and that’s fine, everyone feels this way at this point. From now on more than ever you need to take care of yourself and your fellow students.
Here are a few survival tips: 
✨take frequent breaks
**action step:** schedule your breaks or use pomodoro technique to force yourself away from keyboard!
✨find a way to connect to each other beyond talking code* — having a community based on honest relationships is really important in battling burnout or impostor syndrome
**action step:** take lunch or breaks with one or maximum two people, different people each day;
✨find a way to be excited about tech/js/react beyond doing labs — when you are really sick and tired of that all the time new material coming your way, it is easily to slip into stagnation and procrastination;
**action step:** I used to listen to podcasts about radical tech, go to meetups on civic tech and just read about amazing tech solutions to social problems;
✨be really aware of what you don’t understand and what confuses you and address it with fellow pry’ers (quest’ers?) or staff — don’t allow yourself to waste time being confused!
**action step:** note down all the questions as they arise; ask them after the discussion questions, the lecture or towards the end of the day (give us the opportunity to answer them first in the lectures or other labs!)

**REMEMBER** Your brain is a muscle and as such it needs time to rest. Take breaks. Engage in empathy. Talk to people ❤️


### After lecture
TWO VERY IMPORTANT THINGS:
1) you can call methods on DOM nodes to find children by selector or class name! That’s right, DOM node objects have querySelector and querySelectorAll methods on them! Try it today.
2) There are like, literally 5 methods you can call to find DOM Nodes or array-like collections of nodes:
```md
| Selector | Return shape + type | Live? | Reference | can i call forEach? |
| -------- | ------------------- | ----- | --------- | ------------------- | 
| `document.getElementById()`| Element | N/A | https://goo.gl/8cHGoy | N/A |
| `element.getElementsByClassName()`| HTMLCollection | Yes | https://goo.gl/qcAhcp | No |
| `element.getElementsByTagName()` | HTMLCollection | Yes | https://goo.gl/QHozSh | No |
| `element.querySelector()` | Element | N/A | https://goo.gl/6Pqbcc | N/A |
| `element.querySelectorAll()` | NodeList | No | https://goo.gl/vTfXza | Yes |
```

---
## Week 1 Day 3

### A walkthrough
@here’s a blog post, in which I go step by step through different fetch requests, including pseudo-coding and `console.logs` so you know what to console.log and when (you’ll appreciate my UPDATE request —it’s very clean and spicy :heart: ) :
https://medium.com/better-programming/build-a-crud-js-app-with-fetches-f82143a48b6d

### Dog CEO review
If y’all want to see a review video of the Dog API Lab, here’s one Eric did a while back!
Video: https://youtu.be/ChGqLp7ngXs
Code: https://github.com/HyeokJungKim/fetch-intro-dog-ceo-challenge
---

## Week 1 Day 4

### Blogging ideas
@here  here’s a gift for you all inquisitive minds  
Blog ideas to write out of nowhere:
- debugging js
- closure vs delegation in fetching
- three ways to solve fizzbuzz
- why NaN is not equal to NaN?
- naming variables in js
Blog ideas that require you to research:
- what is closure?
- async / await
- control flow
- call stack
- execution context
- building something with recursion
- building your own forEach/map/select/…
- when is hoisting useful
- inheritance + prototype chain
- What are HOCs?
- JS prototypes for dummies
- OOP vs FP
- when not to use arrow functions
- passed by value vs passed by reference
- global scope / function scope / block scope
- what is `this` in js?

### Arrow functions
@here
If you’re curious about how you transform a function into an arrow function, here’s a walkthrough:
0. this is our function we want to transform:
```js
function sum(num1, num2){
    return num1 + num2
}
```
now, arrow functions are anonymous so in order to preserve the name, we need a variable:
```js
const sum
```
2. Now, put an = between the name  and the arguments, and a => between the arguments and {}
```js
const sum = (num1, num2) => {
  return num1 + num2
}
```
This already works! However,  since the body of the function has only line, we can write it like this:
```js
const sum = (num1, num2) => { return num1 + num2 }
```
And now, since this is only one line, we can simplify it:
```js
const sum = (num1, num2) => num1 + num2
```
WHAT?! NOW RETURN?! Yes. You need a `return` statement as soon as there are `{}` in the picture — and you need `{}` as soon as you have more than 1 line of function body

And if you have no arguments:
```js
function helloWorld(){
 console.log("Hi")
}
```
you can make it:
```js
const helloWorld = () => console.log("Hi") 
```
or:
```js
const helloWorld = _ => console.log("Hi")  
```
[the difference is that () says there might be some default argument and _ says there will for sure be no defaults —but it’s a niche thing and no one uses it even in obscure dev]

And one argument:
```js
function myName(name){
 console.log(`Hi, my name is ${name}`)
}
```
can be:
```js
const myName = name => console.log(`Hi, my name is ${name}`)
```
since it’s just one argument, it doesn’t need parenthesis 

### async js, async/await, promises:
More on async/await and asynchronous js:
- general intro: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Introducing
- why async works without await: https://medium.com/javascript-in-plain-english/async-await-javascript-5038668ec6eb
- an awesome short course on what promises are: https://www.udacity.com/course/javascript-promises--ud898

--- 
## Week 1 Day 5

### About practice labs
If you are unsure of which labs to prioritize, here are my recommendations/reviews/comments/thoughts:
- The DOM Challenge - A good lab to practice events and DOM manipulation. There’s no database associated with that lab, so you unfortunately won’t be able to practice fetch. If you want a good review of Events & DOM Manipulation, I would work on this.
- Github Search App - A good lab to practice all three pillars using an external API. This may require you to take a look at documentation for an external API. Also, be warned: Your requests are rate limited, which means that you can only make a limited number of requests in a time period.
- Monsters - A good lab to practice all three pillars using a json-server. However, it requires you to pass in query parameters in the URLs. It isn’t too bad, but if you are struggling with the three pillars and don’t want to deal with another layer of difficulty on top of everything else, I would save this lab for later.
- Woof Woof - A good lab to practice all three pillars using a json-server. There is a bonus that is particularly tricky, but if you can do the first four deliverables, I think you’ll be in good shape. Recommend doing this one to begin practicing the three pillars.
- Dog Show - A good lab to practice all three pillars using a json-server. It uses HTML tables in the code, but once you get over that small hurdle, you should be able to meet the deliverables using the three pillars.
- Book Liker - A good lab to practice all three pillars using a json-server. Although liking a book is tricky, I would give it a try regardless. Organize your thoughts and always keep the liking deliverable in the back of your mind as you plan/build your app.
- Calorie Counter- A good lab to practice all three pillars using a rails server. The server is all set up for you and to get it off the ground and running, you’ll have to read the README. This lab has a lot of in-depth deliverables, so make sure you plan your time accordingly.
Here is the order I would do the labs:
1) The DOM Challenge
2) Woof Woof
3) Dog Show
4) GitHub API
5) Monsters
6) Book Liker
7) Calorie Counter
Here’s also another practice lab Eric created:
https://github.com/HyeokJungKim/js_good_burger

### EOD
Hey Friends! The weekend hasn’t yet started and I already miss your jolly company.
I want to thank you all once again for how curious, driven and friendly you are. I really love sitting close to you all!
Otherwise — take a good rest and code. What to do if you feel overwhelmed and behind with material?
✨ find a moment to celebrate all the immense learning you did this and previous weeks; please give yourself a little reward for all this very long way you did already! Imagine, last week you were coding in Ruby! This week you are rocking the DOM! YOU REALLY ARE AWESOME!
✨ remind yourself that this is a top-tier bootcamp and that you are so successful in it!
✨ do your labs or re-do the ones we did in class — it will help you solidify the material;
✨ as you arrive at a point of confusion, try to verbalize what confuses you: is there something you don’t understand (a “why”)? Is there something you keep forgetting about? Is there something that does not flow right? To each of these worries there is an actionable solution — I am happy to help you find it!
✨ when I was in the bootcamp, I’d have code parties at my home; they weren’t really parties (you know me by now) but just come-together and code-together; sometimes we’d just review material, sometimes we’d build something and sometimes we’d watch the Office and feel happysad together; all these are valid points in the process!
✨ try to develop a process of tackling a lab; for me, it was more-or-less this:
1) read the readme; draw it out (what needs to be done? what do you fetch and from where? what functionality each element needs to have?)
2) read the html and css, spot what will be useful and what needs to be added — add it to your drawing;
3) make sure that js is connected to the html file;
4) copy the tasks from readme to js file;
5) save all the necessary querySelectors to variables at the very top;
6) if the app requires some toggling, create a let for it
7) write the first fetch method (url, then, then + slapItOnTheDom)
8) console.log to see how returned data looks;
9) write slapItOnTheDom method:
- create new elements
- give these elements datasets and innerHTML/innerText
- add eventListeners where they belong + remember to write a helper function
- appendChild
10) crash test it and debug;
11) Add other fetches (make sure of the headers and that body sends out the correct data)
12) make sure preventDefault is where you want it to be!
 write down the errors you’re getting and what they tell you
✨ AND MOST IMPORTANTLY, GET GOOD REST

___
## Week 2 Day 1

### saving obejct id 
A reminder on why we don’t wanna save an object id to an html attribute of an id:
DO NOT save the object id (the database id) to the html attribute of an id because what happens if you fetch 5,000 different element, say the fox objects, the city objects where they live and food objects they eat — among that group it likely may happen that the numbers will repeat (say, there will be a fox with an id of 1, city with the id of 1 and food with the id of 1); the implications for this may be dire! 
WHY DO WE SAVE IDs AT ALL? We save object ids to datasets because it will make it easy to later withdraw the id when you need to update the object or delete it (you need the id to append in the restful url)
SAVE THE OBJECT ID TO THE DATASET because: 1) that’s why we have datasets; 2) it makes your code more robust and maintainable: conventionally, that’s where others will look for that; 3) although you could interpolate the id of an object to e.g. class or the html attribute of an id but then in order to send a delete request, you’d need to split the string, most probably using regex so save yourself the trouble!


## Week 2 Day 2

### EOD (before Code Challenge)
@here PSA: every single one of you has worked REALLY hard this week.
DON’T stay up late trying to cram in that last little bit of practice, research, lab completion. Don’t do it. Go home, relax, eat some dinner, and SLEEP.

DO: be proud of the work you put in this last week-and-a-half, and acknowledge that even if you’re not done learning javascript, you’ve made a good start

the only thing that the outcome of the code challenge tomorrow can change is your schedule for next friday morning (and by that I mean: whether or not you do the retake)

it’s not a measure of whether you’re smart or not, whether you can be a good software developer or not, whether or not you are a good person, or anything other than whether or not you’re ready for mod 4 (to the best of our ability to measure it)

**OR: ALTERNATIVE MESSAGE**
I am very impressed by how hard you have worked this and past week. Please don’t think too much about tomorrow — its result is irrelevant in the grand scheme of things. No employer will ever ask you about it. Your children won’t ask you about it. You yourself won’t remember it soon.
Please approach it with a curious mind. The challenge is not a reflection of your aptitude, of your IQ, of your hard work. JavaScript is a tough friend to make and sometimes it takes a moment. Regardless of the results tomorrow, I can reassure you that you will get enough practice in js to really develop appreciation for it 
You are all amazing.
You’ve worked really hard.
Please take a moment to reflect on HOW MUCH you’ve done these past 10 days.
It really is awesome. You are writing JavaScript. You rock!

---
## Week 2 Day 3

### Project guidelines
We have deployed MOD3 project guidelines. You have the rest of today and tomorrow to work on your project ideation as well as doing your labs, so please be mindful of your time!
Before you start coding, we want you to:
- think through your app;
- check next week’s schedule to be very much aware of the lectures that are coming your way so you plan accordingly;
- copy this project pitch template into your own document and fill it out;
- create a wireframe in figma, sketch, or adobe xd (all of them are free) and submit it together with the template;
- once you’re done with it, send these documents in a message to Eric+Sylwia+me; if we have any further questions, we’ll send you a message or get on a call with you ……however, try to already think about what questions we will have and answer them in your template beforehand to continue having wonderful and frustration-free lives 
You can start coding only once you’ve gotten our approval.
Sound good?

---
## Week 2 Day 4

### serializers
Here’s an example of how the data from the Fast_JSONAPI is structured
If you want to take a deeper look, here is the documentation for it:
https://github.com/Netflix/fast_jsonapi#object-serialization
If you want to take a look at the documentation on the speed:
https://github.com/Netflix/fast_jsonapi/blob/master/performance_methodology.md
> Fast JSON API is not a replacement for AMS. AMS is a great gem, and it does many things and is very flexible. We still use it for non JSON:API serialization and deserialization.

### js fun
@here run this JS snippet in your console to see what we think about you :open_mouth:
```js
(+[![]]+[+(+!+[]+(!+[]+[])[!+[]+!+[]+!+[]]+(+!+[])+(+[])+(+[])+(+[]))])[+!+[]+[+[]]]+(({})+({}))[+!+[]]+([][[]]+[])[+[]]+(!+[]+[])[+!+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(+(+!+[]+[+!+[]]+(!![]+[])[!+[]+!+[]+!+[]]+[!+[]+!+[]]+[+[]])+[])[+!+[]]+(!+[]+[])[+!+[]]+(![]+[])[+!+[]]+([][[]]+[])[!+[]+!+[]]
```

IN COMMENTS: 
- it’s basically translating js into binary and that into ascii codes
- https://en.wikipedia.org/wiki/JSFuck

---
## Week 2 Day 5

### variables fun
@here I’ve prepared some js variable naming lols for you —try them out in the console:
```js
// JS doesn not like emojis:
const 🔲 = "square";
//=> Uncaught SyntaxError: Invalid or unexpected token
// but non-emoji unicode signs are fine:
const ᱹ = "square";
const ❤️ = "heart";
const ಠ_ಠ = "really?";
// it gets even more fun:
const 〱〱 = 8;
〱〱 << 〱〱
//also, declare these (the name of the first one and the value of the second are the same) and then call them one by one:
const \u006C\u006F\u006C\u0077\u0061\u0074 = 'gotcha';
const surprise = "\u006C\u006F\u006C\u0077\u0061\u0074"
//what the hell is this and why does it work
const Hͫ̆̒̐ͣ̊̄ͯ͗͏̵̗̻̰̠̬͝ͅE̴̷̬͎̱̘͇͍̾ͦ͊͒͊̓̓̐_̫̠̱̩̭̤͈̑̎̋ͮͩ̒͑̾͋͘Ç̳͕̯̭̱̲̣̠̜͋̍O̴̦̗̯̹̼ͭ̐ͨ̊̈͘͠M̶̝̠̭̭̤̻͓͑̓̊ͣͤ̎͟͠E̢̞̮̹͍̞̳̣ͣͪ͐̈T̡̯̳̭̜̠͕͌̈́̽̿ͤ̿̅̑Ḧ̱̱̺̰̳̹̘̰́̏ͪ̂̽͂̀͠ = 'Cthulhu';
```

___
## Week 3 Day 1

### After OOJS lecture
Highlights from OOJS:
- Functions defined in a class (without the function keyword) can be considered instance methods
- Class methods are defined with the static key word
- Prototypes are objects and every instance gets their shared functions from within the prototype object
- The value of this inside instance functions will hopefully be the instance (that’s why we should use arrow functions)
Highlights from this/bind/call/apply:
- Arrow functions and how they take on the value of this during the function definition
- Regular function determines the value of this at their function execution
- Bind is a function you can invoke on a function definition that returns a function definition with a specific this
- Call/apply is a function that you can invoke on a function definition that executes the function with a specific this'
- USE ARROW FUNCTIONS TO DEFINE INSTANCE METHODS IN REACT BECAUSE THEY IMPLICITLY BIND THE INSTANCE TO THE FUNCTION

### API keys
@here
If you are working with an external API that requires a key, consider using @Sylwia Vargas (she/her)’s blog to hide that API key:
https://medium.com/better-programming/how-to-hide-your-api-keys-c2b952bc07e6

---
## Week 3 Day 5

### Eric's notes
Highlights from OOJS:
- Functions defined in a class (without the function keyword) can be considered instance methods
- Class methods are defined with the static key word
- Prototypes are objects and every instance gets their shared functions from within the prototype object
- The value of this inside instance functions will hopefully be the instance (that’s why we should use arrow functions)
- USE ARROW FUNCTIONS TO DEFINE INSTANCE METHODS IN REACT BECAUSE THEY BIND THE INSTANCE TO THE FUNCTION
Highlights from this/bind/call/apply:
- Arrow functions and how they take on the value of this during the function definition
- Regular function determines the value of this at their function execution
- Bind is a function you can invoke on a function definition that returns a function definition with a specific this
- Call/apply is a function that you can invoke on a function definition that executes the function with a specific this
Highlights from Code Organization:
- Components are modular pieces of the HTML
- Components describe the structure of the HTML & what event listeners are available for that component
- Functions inside Adaptors return a promise, which can be chained on using .then
Highlights from the ES6 Lecture:
- Objects and arrays can be spread - they make a new object/array in memory with the same key-value pairs/elements
- Objects and arrays can be destructured to pull out variables from the keys of existing objects (Useful when it comes to functional components)
- The keys and values of objects can be created from variables (Useful when it comes to the body of fetch )
- Arrow functions have to meet certain conditions in order for there to be an implicit return
`   -map , filter and sort all take a callback and those callback functions must return a specific value
In terms of which lectures to review, the ES6 Lecture is probably the highest priority, especially the second half.
Then, Code Organization.
However, Code Organization is built on the ideas covered in the OOJS Lecture and the This Lecture, so if you are feeling lost about Code Organization, start from the beginning.
Recommended Steps:
- Watch ES6 Lecture
- Review Code Organization
- If you’re lost with Code Organization, watch OOJS and then, This.
- Get some React practice with labs, tutorials and videos.
- Get some React practice with labs, tutorials and videos.
- Get some React practice with labs, tutorials and videos.

### Sylwia's message
@channel In preparation for React:
There’s some homework this weekend so that you have a strong foundation for how the tools that we’ll use with React work under the hood, and so we can focus on the core React concepts starting on Monday.
Here is a really nice, short and smooth crash course to React that @Rei Reynoso (He/Him) recommended: https://www.youtube.com/watch?v=sBws8MSXN7A
You can also follow the official React tutorial https://reactjs.org/tutorial/tutorial.html. You’ll generally find that the React docs are excellent - I recommend scanning them now, reading them next week, and then referencing them forever.
Finally, there are new React labs on Learn. They start by reviewing some of the material mentioned above, then move into an overview of React and the building blocks of React apps: Components.
:sparkles: :sparkles: :sparkles: :sparkles: :sparkles: :sparkles: :sparkles:
If you want to understand React better, we’d propose that you  watch this webpack crash course video https://youtu.be/Teaw6HAoZyI. It covers some of the basics of webpack, a developer tool for bundling up different JavaScript files into a single that you can include on your page. It’s super useful both for splitting your code into different files and for including libraries in your JavaScript projects, both of which will be super useful in mod 4.
React depends on lots of modern web technologies. It’s a wide wide world out there. Different types of modern technologies include: package managers, JavaScript transpilers, bundlers, development servers, hot module replacement tools, code minifiers; all sorts of things! Check out this resource to read a high-level overview of different parts of the toolchain. Don’t try to follow along programming any of these things. This resource is actually outdated.  The commit history shows it was last updated at the end of 2017. Things change fast in web development. This guide still provides an excellent high-level overview of different pieces of technology, but it definitely uses old out-dated versions of these technologies simply because new versions have since come out. Read it to learn the concepts, do not read it as a tutorial to programming along with! https://github.com/verekia/js-stack-from-scratch

---

### forEach vs for loop

In general, when I don’t have to, I do not use loops, especially nested loops, and use forEach or map instead because (top three reasons):
forEach keeps the variable’s scope to the block, so if you’ve assigned a variable outside and re-use it within the forEach, the outside variable retains its value:
/////////////////////// FOREACH /////////////////////////
let num = 4;
let arr = [0, 1, 2];

arr.forEach(num => {
  console.log(num);
});

// Result:
// 0
// 1
// 2

console.log(num);
// Result:
// 4

/////////////////////// FOR / IN /////////////////////////
let num = 4;
let arr = [0, 1, 2];

for(num in arr){
 console.log(num)
}

// Result:
// 0
// 1
// 2

console.log(num);
// Result:
// 2
forEach is a method specific to arrays (or, Array object) and as such, it expects you to obey the laws of arrays —if you don’t, you’ll get better errors (or, errors at all instead of silence)
and of course, forEach is better for readability

I’d only choose loops when I want to be able to break from the iteration if some condition is not met. That’s not possible with forEach  and that leads to performance issues.