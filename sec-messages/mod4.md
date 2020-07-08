# Mod 4

## Week 1 Day 1

### morning
@here
One important thing as we move into React is to make sure you have the right version of Node. If you type node -v into your terminal, the version number should be greater than 12. If not, you must update your version of Node. The recommended way to do this is using NVM, a Node version manager, which allows you to have multiple versions of node and switch between them. The Installing Node section of the manual setup (link below) explains how to install this and update your Node version.
Once your Node version is up to date, please run npm i -g create-react-app if you have not already. If you had to update Node, you will need to do this again.
https://github.com/learn-co-curriculum/environment-mac-os-catalina-setup

### morning again
:sparkles: :sparkles: :sparkles: :sparkles: :sparkles: :sparkles: :sparkles:
@here welcome to MOD4. From now on, the staff will be putting a lot of emphasis on promoting Personal Empowerment Protocol to make sure that you’ll enter MOD6 with a blast. These are the steps you should take before asking us for help:
1. Read the error or use console.log/debugger to identify WHAT and WHY this is not working
2. Google the problem (you should spend 30-45 minutes)
3. Ask a classmate (x2 15 minutes each)
4. If it is a question that is not pertaining to the labs but e.g. your side project, ask all-about-code, stackOverflow or Twitter (for real, get comfortable with that!)
5. Only then, ask an instructor or a coach
If you do come up to us, we expect you to tell us the following: “This is the component tree (have it drawn). This is the error I am having. I have googled this and that, console.logged/used debugger here and here, and tried to solve it with this and that person. What am I missing?“.

### React newsletter
Also, subscribe to this newsletter:
https://reactdigest.net/digests/251

### No render in functional comp:
:question: why is there no `render` in functional component?
Functional component itself is the `render` method (with an argument of props) under the hood as it is all nicely wrapped in `ReactDOM.render()` :
```js
ReactDOM.render(
  <div>
    <StatelessComponent title="Function" />
    <StatefulComponent title="Class" />
  </div>,
  document.getElementById("root")
);
```
Because of the fact that in the Class Components there’s usually more stuff than just the JSX, it is crucial that you specify what exactly needs to be rendered. But after we’ve specified what you want to be rendered, what is returned from these two components is identical —it’s a dom element:
```js
function StatelessComponent(props) {
  return <h1> {props.title} </h1>;
}
class StatefulComponent extends React.Component {
  state = {}
  render() {
    return <h1> {this.props.title} </h1>;
  }
}
```

### React props
https://reactjs.org/docs/faq-state.html#what-is-the-difference-between-state-and-props
Love the React Docs :heart:

### State vs props
If you’re still trying solidify basics like state vs. props I think this is awesome. It’s a presentation from the women of React conf that happened last month, given by Maggie Appleton who’s been working with Dan Abramov on a bunch of stuff (like his JS book). It’s ~16 min so it’s a quick one! https://www.youtube.com/watch?v=K8MF3aDg-bM&feature=youtu.be&t=13845

---
## Week 1 Day 2

### morning
TALK TO YOUR LEAD ABOUT SHARING A SIMILAR DOCUMENT
https://docs.google.com/document/d/1LCo4ZWskjTI2AVHdiN3LSbzj-iCmYppvbPaQEBkchLU/edit?usp=sharing

### keys in react
@here
:key: WHY DO I NEED THE KEY? :key:
tl;dr: Keys help React identify which items have changed, are added, or are removed. Use unique and constant keys when rendering dynamic children, or expect strange things to happen.
:old_key: https://reactjs.org/docs/lists-and-keys.html
:old_key: https://www.geeksforgeeks.org/reactjs-keys/

### react - fast
@here
Why is react so fast?
-> it doesn’t use actual DOM but the virtual one, which is fast to change
-> React uses observer design pattern, which basically tracks  changes in all children and reacts on spot
-> read about React’s diffing algo: https://reactjs.org/docs/reconciliation.html

---
## Week 1 Day 5

### around Hogwarts review
@here’s a process I always take when doing a React code challenge or a new app:
1. Draw the component hierarchy + wireframe
2. Build A Static Version in React (just a mockup — hardcode all the data just to see how everything connects)
3. Decide where the state lives
4.  If you need to pass the state down, write the state handler functions, pass it at props, console log everywhere to see if it connects
5.  Do other deliverables
Here are Thinking in React docs: https://reactjs.org/docs/thinking-in-react.html

### Eric's message
Ya already know what time it is:
It’s Friday afternoon of Week 1, which means that practice labs are deployed for you to practice over the weekend and solidify the concepts as well as some of the labs that cover some of the advanced parts of React.
Here’s my thoughts on some of the labs:
Pokemon Searcher is a classic React application. This requires you to toggle a component’s state to conditionally render some information (similar to the way it was in Hogs). If you have time to complete only one of these new lab, you can’t go wrong with this one.
React Stocks is fairly difficult to wrap your head around when it comes to state. You will be expected to manage multiple arrays in state as well as reuse components that have different functionalities. When you’re working with reusable components, it is the responsibility of the parent to decide what the keys of the props are going to be.
React Pizza gives to more practice with controlled forms, and displaying that data to the DOM. When working on this lab, be mindful that you’re not modifying state. This lab is a bit tricky and radio buttons may cause you some trouble, but don’t let it stop you from looking at this lab.
Westworld Command Center has a lot of deliverables. I’d say tackle the above labs :this: prior to tackling this one, but don’t let it stop you for checking this one out if you are curious. :robot_face: :cow-blob:
There is an additional lab that has an interesting twist, buried in the Practice Challenges -> Bonus: Debugging tab.
The Binge Finder Debugging Lab is a lab that is completely built out, but it is broken. I recommend making room for this lab over the weekend; it will give you experience and practice running into React bugs, and being able to figure out where the errors are.
In addition to the practice labs, please don’t be scared to create-react-app over the weekend and apply the ideas that we learned to build a small project of your own!

### follow up
controversial opinion:
:bangbang: Instead doing Westworld Command Center now, just build your own portfolio (you’ll need it in mod6!) :bangbang:
———-
it is a cool lab but it’s really huge and I am not sure if the juice is worth the squeeze now (you’ll spend a lot of time figuring out how everything relates to each other instead of coding)

### portfolio idea
If I wanted to create a portfolio AND still practice for the CC, I’d:
- implement a structure of e.g. Header - MainContainer(with children: Projects, About, …) - Footer
- have a dark mode done with a button in the header (which would require passing/handling state)
- save text in “About” or e.g. “Education” as objects and/or arrays in variables in another file so you’d need to import it and map through it
- leave CSS for when I no longer worry about React

### same page, different frameworks
This is a really cool site that lays out a huge number of the MVC frameworks. It (the react example, anyway) was written by the lead dev of ClojureScript and there are some nifty things in here. Seems to be using Localstorage but for the life of me I can’t figure out how/where. There’s a ‘store’ function in the utils.js file.  Very cool!
React part of the site: http://todomvc.com/examples/react/
Code: https://github.com/tastejs/todomvc/tree/master/examples/react/js
<<<WARNING>>> Do not check out this code if you’re allergic to reading old React syntax. It was written not long after React was open sourced.
If you’re interested in diving into the deep end of learning the React ecosystem (or if you want to at some point, but are underwater right now, maybe just throw a bookmark), this guide was written by Pete Hunt, who was one of the main guys at Facebook responsible for building and open sourcing React. It’s a little dated and I haven’t gone too deep yet, but it seems really great.
https://github.com/petehunt/react-howto (edited) 

___
## Week 2 Day 1

### Correct syntax reminder
Also, just a reminder to be consistent and correct with your syntax!
This was true in the previous mods, but it’s especially relevant when you’re working in React where symbols like  {}, (), =, : are used for many different reasons. For example, setState is a function invocation while the way we set our initial state is with state={} .
It’s very easy to mix things up, so please make sure you have a tight feedback loop and you’re checking your browser with every chunk of code that you write. Also, the spelling of keywords matters!

---
## Week 2 Day 2

### radio buttons
————- :radio: :radio_button: ———————
Here are two great articles on making radio buttons accessible by Haydon Pickering:
https://www.sitepoint.com/replacing-radio-buttons-without-replacing-radio-buttons/
https://www.smashingmagazine.com/2017/09/building-inclusive-toggle-buttons/

### Eric's reviews
Videos/Code of Reviews:
Pokemon Review Code: https://github.com/learn-co-students/nyc-dumbo-web-111819/tree/master/44-react-pokemon
Pokemon Review Vid 1: https://youtu.be/jaykQ_565IU
Pokemon Review Vid 2: https://youtu.be/ifBVKXEZ3iE
Stocks Review Video: https://youtu.be/eSnDmTkxdnM
Stocks Review Code: https://github.com/HyeokJungKim/React-Stocks-dumbo-web-career-031119
Dog API Practice Video: https://youtu.be/ujegsCu1PFQ
Sushi Code: https://github.com/HyeokJungKim/React-Practice-Code-Challenge-dumbo-web-071618/tree/review_solution

---
## Week 2 Day 3

### Additional lifecycle methods lecture
@channel as you are all waiting for the results, remember to take a moment to breath AND you may wanna watch this lecture I gave (or just do the repo) on Lifecycle Methods. This lecture goes DEEP into those more advanced lifecycle methods that we don’t usually cover in our curriculum. I set it up as a set of hurdles so you can just do the hurdles without the lecture.
code: https://github.com/sylwiavargas/lifecycle-methods-workshop
video: https://www.youtube.com/watch?v=lvIAWB2krKY&feature=youtu.be

### prevState
————————— prevState ————————————
Now that you have all passed and can enjoy coding, I would like to urge you to setState  using prevState , here’s why:
> React may batch multiple setState() calls into a single update for performance. Because this.props and this.state may be updated asynchronously, you should not rely on their values for calculating the next state.
More on the subject:
https://teamtreehouse.com/community/react-docs-now-recommends-using-function-with-prevstate-inside-of-setstate

### Eric's message
@here
Auth and Routing labs are out!
Definitely take some time to congratulate yourselves on a job well done and celebrate the fact that there are no more formal code challenges for the remainder of your time at Flatiron!
But please please please do not get complacent. You still have three of the biggest topics that get in the way of most, if not all, Mod 5 students ahead of you - Routing, Auth and Redux.
Senioritis is definitely real and while it is good to take a break and celebrate a little, I want you all to be aware that you still have 4 weeks ahead of you, 3 of which will be used to build your portfolio’s centerpiece.
So, continue working on the labs for the remainder of the day today and come well-prepared and well-rested for tomorrow!

---
## Week 2 Day 4

### Project week announcement
Hey @channel:
And lo, and behold! Project week begins!
Until the end of the day, please present to us:
:sparkles: in google doc: project pitch template (make a copy!);
:sparkles: in figma/adobe xd/sketch: component hierarchy (think what can be reusable + which should be functional components) + wireframes;
:sparkles: if working with a partner: filled out contract (make a copy!);
Then, share it with Eric, Randy and myself :heart:
We will not approve any project that will not have ALL OF THE ABOVE :slightly_smiling_face:
If you’d like to pair up, you see in the polls who’d be up for that — go ahead and arrange it :heart:
Enjoy!

### Follow up on ^

@channel Answers to common questions about mod4 project :heart:
- In this mod, we want you to prioritize stuff that you know you would be using in mod5 as much as possible — while you may have no idea what you want to do for your capstone project, you will most probably use stuff like: auth, router, css, well-developed backend, etc.;  for this reason (read next point)…
- …we are okay with you having fewer models in the backend; however, we do think that becoming really comfortable with serializing data in the backend is gonna help you a great deal and frankly, is very crucial in the professional world (my mod4 project had 5 models, and mod 5 one had 28, which was possible because I was very comfortable with non-standard serialization from the mod before);
- also, think about that if you want to pursue a front-end career, perhaps it’s good to use some css library, ideally some specific to React, like Tailwind, Emotion and/or Styled Components; IT IS PERFECTLY OKAY TO USE PURE CSS or other stuff you are comfortable with; I just personally just wish I had known about these when I was in mod 5;
- Do take time to learn about lifecycle methods (I shared a link to my repo/lecture yesterday if that works for you) — they are lifesaving in some cases!
- And remember, have FULL crud!!!!
However, remember that your first priority is to MASTER what you already know about React. Do not jump into extra stuff if you e.g. do not know controlled forms well or feel icky about state. First, learn React, then do fancy stuff.
Questions? Ask in comments :heart:

___
## Week 3 Day 3

### Intro to Redux
@channel
Hey y’alll! Starting tomorrow, we will be working on Redux.
To prepare for Redux:
Before our lectures tomorrow, please read the following pages in the official documentation:
- https://redux.js.org/introduction/motivation
- https://redux.js.org/faq/general#general-when-to-learn
- https://redux.js.org/faq/organizingstate#organizing-state-only-redux-state
- Just the first one about state.
Then:
We are releasing most of the Redux labs. You should start with Why Redux, Redux Flow, Redux Reducer, and Redux Dispatch in the Building Redux section.
The rest of the section is building out your own version of the rest of the Redux library. This is not essential, but does show how the functions we use from the Redux library work. After those, I would read the READMEs in the Redux Library section.
Additional Resources:
If you’re itching to get started, you can follow the tutorial series by the one and only, Dan Abramov, linked in the Learning Resources section of the docs:
- Getting Started with Redux - Video Series: https://egghead.io/series/getting-started-with-redux
- Course Notes - https://github.com/tayiorbeii/egghead.io_redux_course_notes
Also, here are some other tutorials. For looking at code, you might want to check out the Examples and Miscellaneous page:
- https://redux.js.org/introduction/examples
- https://redux.js.org/faq/miscellaneous#miscellaneous-real-projects
For some history on Redux:
- Original Redux intro video by Dan Abramov  - https://www.youtube.com/watch?v=xsSnOQynTHs
What should I focus on?
If you are curious as to what to focus on between your Mod 4 Projects or Redux, I would focus on your projects now. It is a hassle and a half to switch from a pure React application to a React-Redux application, so for most of you, if not all, there will probably not be enough time for you to implement Redux into your projects before our presentation on Friday. You’ll have the time over the weekend to practice and work with Redux! Keep in mind that Redux is not a mandatory part of Mod 5, but it is heavily heavily encouraged as it will make your life easier in the later parts of your project. 

### follow up
:bangbang: :bangbang: :bangbang:  PLEASE do yourself a favor and PRIORITIZE REDUX THIS WEEKEND :bangbang: :bangbang: :bangbang:
This is of an absolute priority. I am not joking. You will not have enough time in Mod5 to just start learning it then.
Improving Mod 4 project after Friday < Learning Redux
THIS IS SERIOUS.

### EOD Eric's message
Oh and something I think worth mentioning:
I like project week of every Mod. I think it’s a great way for every student to have fun and add a bit of their own personality to something that they create from scratch. Project demos are always a fun time, but unfortunately, week 3 is not supposed to be a break from the learning. I know lectures during Week 3 are annoying, but they’re all designed to help you along in the next mod. (ex: OOJS lecture in week 3 of Mod 3)
The reason I’m telling you all this is because tomorrow’s afternoon lecture has historically been a fire hose of a lecture. You all know me enough by now; I try and be as transparent as possible. So tomorrow,  please don’t be working on your projects during the lecture. There’s no way I’ll know at the time if you are, but would love it if all your focus was all on Redux during our lecture time so that you are able to use it in Mod 5 and get a strong centerpiece for your portfolio. There will be time tomorrow for you to work on your projects, so if y’all can give me your attention for 2 1.5 hour sections, it would be greatly appreciated. :super-excited-eric: