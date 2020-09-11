# Frequently Asked Questions

## General

1. **My labs don’t mark green - why?**
Learn outage, wait up to 24h.
2. **How do I prioritize what to learn?**
That's a great question to ask and I appreciate how proactive you are about managing your learning and possible future fatigue. I'd say, follow lead instructor's recommendation as to which are the priority labs. However, in the perfect-world scenario, you'd be able to do all the labs or at least read/skim the readmes before the lectures so you'd be able to at least be kinda familiar with the the new terminology and maybe even have some questions prepared.
3. **How do I enhance my online presence?**
I'd say, write tech blogs and then post about them on LinkedIn and Twitter using web dev hashtags.
4. **How can I avoid burnout?**
Here are a few survival tips:
:sparkles:take frequent breaks
**action step:** schedule your breaks or use pomodoro technique to force yourself away from keyboard!
:sparkles:find a way to connect to each other beyond talking code* — having a community based on honest relationships is really important in battling burnout or impostor syndrome
**action step:** take no-code breaks with different people each day;
:sparkles:find a way to be excited about tech/js/react beyond doing labs — when you are really sick and tired of that all the time new material coming your way, it is easily to slip into stagnation and procrastination;
**action step:** I used to listen to podcasts about radical tech, attend meetups on civic tech and just read about amazing tech solutions to social problems;
:sparkles:be really aware of what you don’t understand and what confuses you and address it with fellow Pry Babies or staff — don’t allow yourself to waste time being confused!
**action step:** note down all the questions as they arise; ask them after the discussion questions, the lecture or towards the end of the day (give us the opportunity to answer them first in the lectures or other labs!)
**REMEMBER** Your brain is a muscle and as such it needs time to rest. Take breaks. Engage in empathy. Talk to people :heart:
5. **I don't have any idea for an app**
Check this blog post, maybe something here will inspire you: https://dev.to/sylwiavargas/33-app-ideas-for-bootcamp-students-code-newbies-3n28

---
## Mod 1
tba
3. **What the hell are ternaries?**

___
## Mod 2
tba
3. **What the hell are ternaries?**
This is how ternaries work:


___
## Mod 3

1. **How do I take out the data from Promise?**
You don't. If you have a function like this:
```
let fetchedData = fetch('https://url.com').then(res => res.JSON()).then(data => data)
```
and you call on `fetchedData`, you will get a Promise. The easiest way (within the scope of our curriculum) is to invoke another function in the last then:
```
let fetchedData = fetch('https://url.com').then(res => res.JSON()).then(data => doSomething(data))
```
In this case, the `doSomething` function will receive the data that comes from the resolved Promise.

1. **What is the difference between map() and forEach()?**
map() creates a new array with the results of calling a provided function on every element in the calling array [hint: sounds a lot like Ruby, huh?]. In addition, `map()` allocates memory and stores return values. `forEach()` throws away return values and always returns `undefined` .
2. **Can we shovel (<< ) into an array?**
NO. That's Ruby. Use `.push` instead.
3. **How to create an Array from HTML collection?**
`Array.from(xyz)`
4. **Why does this element not react to event listener?**
Did you check if the event listener is added to the right element?
5. **Dodger lab: why is the dodger not moving to the right?**
It can only have one reference point (left or right), if both: it will confuse the css
6. **What exactly am I supposed to update a page?**
Check this blog: https://medium.com/better-programming/build-a-crud-js-app-with-fetches-f82143a48b6d
7. **How do I construct an arrow function?** 
Check this blog for a walkthrough: https://dev.to/sylwiavargas/arrow-functions-a-walkthrough-and-gotchas-4p4p
3. **What the hell are ternaries?**
This is how ternaries work:
{Question ?} {if true} {: if false}
areYouFeelingSick ? stayHome() : goHangOutWithYourLovelyFriends()

---
## Mod4
1. **I don't understand the difference between state and props**
One of my friends once used this analogy:
Imagine you're in your room — that's our component.
The room has a closet (state) where you can put whatever you want, e.g. some jumper or blanket (objects), some money (other data types like integer), but there's also a switch that switches on and off the light in your room (boolean).
Now, imagine that you take the blanket out of the closet and bring it to the sofa — you have just passed the props! The blanket is the prop from your room to its child, the sofa.
Let me know whether this analogy works for you!
2. **Can I deconstruct props in constructor?**
NO. Constructor gets called in too late. 
https://stackoverflow.com/questions/38104346/correctly-destructuring-this-props-for-the-whole-component
3. **What the hell are ternaries?**
This is how ternaries work:
{Question ?} {if true} {: if false}
areYouFeelingSick ? stayHome() : goHangOutWithYourLovelyFriends()
