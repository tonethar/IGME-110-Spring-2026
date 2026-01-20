# Creating a GitHub Pages Site

---

[**I. Recap**](#i-recap)

[**II. Markdown vs. HTML/CSS/JS**](#ii-markdown-vs-htmlcssjs)

[**III. HTML "Throw you in the deep end"!**](#iii-html-throw-you-in-the-deep-end)

[**IV. Sample HTML Pages**](#iv-sample-html-pages)

[**V. Posting an HTML page to GitHub**](#v-posting-an-html-page-to-github)

[**VI. Homework**](#vi-homework)

---

## I. Recap
- Last time ([GitHub Intro](github-intro.md)) we learned:
  - how to create a new GitHub repository named ***yourGithubId*/IGME-110-Repo**
  - how to create new documents in the respository
  - how to use basic markdown to format text content (headers, bold and italic text, and horizontal rules)
  - how to display display images
  - create hypertext links to web pages

### Demo
- Review of basic markdown covered last time
- How to create folders on a repo and upload files
  - go ahead and grab this ZIP of images -> [images.zip](../_files/images.zip)
  - and we will show you to upload them GitHub, and then link to them/display them from **README.md**

---

## II. Markdown vs. HTML/CSS/JS

- While markdown is a great way to simply and quickly format documents and to add simple interactivity (hypertext links) to them, web pages created with it are lacking many features that are taken for granted on the web today, including:
  - content rich web sites that use visually interesting fonts and animation - check out RIT's home page as an example - https://www.rit.edu/
  - web sites that gather information from users by utilizing forms (e-commerce sites etc)
  - web sites (like Google Docs) that are full blown apps that can replace desktop applications such as Word and Excel
  - web sites that can run games and interactive experiences - here is an IGME-330 project writen in JavaScript that is running on GitHub Pages: https://tonethar.github.io/projects/procedural-flowers/latest/index.html
 
###  HTML/CSS/JS
- To build pages and web sites that go beyond what markdown can do, you need 3 new languages: 
  - HyperText Markup Language (HTML) - a way to add *structure* to a page (this is heading, this is a paragraph, this is a list etc)
  - Cacading Style Sheets (CSS) -  changes the *presentation* (appearance) of a web page
  - JavaScript (JS) - adds *interactivity* to a page
- We're going to cover some of the basics in this course (to help you with your projects), and you'll go much deeper in future courses!
 
### IGM Core Web Classes
- IGME-235 "Intro to Web Tech" - Build web pages, web sites, learn advanced CSS layouts, build a web app, build a web game
  - https://github.com/rit-igm-web/igme-235-shared/blob/main/exercises/projects.md
- IGME-330 "Rich Media I" - Advanced interactivity and procedural drawing (the procedural flower app above is from this course)
- IGME-430 "Rich Media II" (required for New Media Interactive Dev, optional for GDD) - build "full stack" web apps and custom servers

---

## III. HTML "Throw you in the deep end"!

- See Slides in myCourses content section
- We'll quickly review the most important concepts!

---

## IV. Sample HTML Pages
- Go ahead and copy the HTML and create these files on your computer
  - there's also a zip of these files here --> [first-html-pages.zip](../_files/first-html-pages.zip)
- You can then open them in Chrome to see how the HTML is rendered
- You can edit their contents in text editors that handle plain text such as VSCode or Notepad++ (but NOT MS Word)
- We will start off by looking at **minimal.html** in the web browser, and then discussing how HTML *tags* work
- ... once we've done that together ...
- ***YOU DO:***
  - launch Visual Studio Code (if you don't have it on your computer, [download it here](https://code.visualstudio.com/))
  - choose File > Open Folder... and choose the **first-html-pages** folder
  - make some changes to **minimal.html** ...
  - change the title to `My GitHub Pages Site`
  - change the level-1 heading to `My schedule for Fall 2025`
  - change the list of colors to a list of the courses you are taking this semester
  - change the list of courses from an ordered list to an *unordered list* (i.e. a bulleted list)

---

**minimal.html**

```html
<html>
  <head>
    <!-- This shows up in the window title bar -->
    <title>My minimal Color page</title>
  </head>
  <body>
    <!-- Everything "inside" the body tag shows up in the browser window -->
    <h1>My Fav Colors!</h1>
    <ol>
      <li>Red</li>
      <li>Green</li>
      <li>Blue</li>
    </ol>
  </body>
</html>
```

---

**links.html**
- This page adds some information that browsers like (e.g. the character set and language) as well as information used by HTML validators (e.g. `<!DOCTYPE html>`
- Also note how we can write a bulleted list in HTML
- And how we create Hypertext links in HTML to both local files, and also remote files that are stored outside of our local files system
- ***YOU DO:***
  - modify the first two `<a>` tags so that the links open in a new browser window (or tab) when clicked on

  
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Links Page</title>
</head>
<body>
  <h1>Some Links (out on the Internet)</h1>
  <ul>
    <li><a href="https://en.wikipedia.org/wiki/Taco">Tacos</a></li>
    <li><a href="https://en.wikipedia.org/wiki/Hummus">Hummus</a></li>
  </ul>
  <h2>My Other Pages (these are "local" files)</h2>
  <p><a href="minimal.html">My Minimal Color Page</a></p>
  <p><a href="tacos.html">Taco Tuesday's Restaurant</a></p>
  <p><a href="dice-roller.html">Dice Roller</a></p>
</body>
</html>
```

---

**tacos.html**

- This page adds a more content and the beginning of a page layout
- It also adds an image (which you'll have to download yourself - [taco.jpeg](../_files/taco.jpeg))
- Most importantly, we now have CSS styling:
  - here the styling directives are located in the `<style>` tag
  - *CSS selectors* tell the browser which HTML element to apply the style rules to (e.g. `body`, `h1`, `h2` are all CSS "type" selectors)
- ***YOU DO:***
  - change the background color of the page to one of the CSS keyword colors listed here --> https://www.w3schools.com/cssref/css_colors.php --> and be sure to use the keyword in your CSS, not the hexadecimal value
  - using CSS, change the color of all text located inside of `<p></p>` tags to one of the CSS keyword colors listed above
  - wrap the `<h1></h1>` tag inside of a `<header></header>` tag and then style the header in some way (background-color, spacing etc)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      background-color: #faf2e4;
      margin: 0 10%;
      font-family: sans-serif;
    }

    h1 {  
      text-align: center;
      font-family: serif;
      font-weight: normal;
      text-transform: uppercase;
      border-bottom: 1px solid #57b1dc;
      margin-top: 30px;}
      
    h2 {  
      color: #d1633c;  
      font-size: 1em;
    }
  </style>
  <title>Taco Tuesday's Restaurant</title>
</head>
<body>
  <h1><img src="images/taco.jpeg" alt="taco" width="175"><br>Taco Tuesday's Restaurant</h1>

<h2>The Restaurant</h2>
<p>The Taco Tuesday Restaurant offers casual breakfast, lunch, dinner and late-night fare in a relaxed atmosphere. The menu features our curated selection of only the finest local tacos.</p>

<h2>The Staff</h2>
<p>Passionate about Food. <em>Dedicated.</em> <b>They love working here 7 days a week!</b> <small>(Apply now! We're always hiring!)</small></p>

<h2>Location and Hours</h2>
<p>West Naragonkshutt, NY;<br>Monday through Sunday 5am to Midnight</p>
</body>
</html>
```

---

**dice-roller.html**

- Finally, here we are using JavaScript to create a simple "Dice Roller" app
- You can see that we are giving some of our HTML elements unique `id` values so that we can reference them in our code
- You can also see some nice button styling
- and CSS *id selectors*
- and a *pseudo-class selector* that adds a rollover effect
- BTW - as HTML files get larger, we generally start to split them up by moving the JavaScript and CSS to separate files (in this class you won't have to to worry about doing this, unless you really want to)
- ***YOU DO:***
  - in order to be ready for your next TTRPG session, add D4, D8, D12 and D100  "dice" to the app and get them functioning
  - give each button a unique background color
  - optional: can you get the app to display a history of the numbers that were rolled, one on each line? With the most recent roll at the "top"? Make it so!
    - hint: the `.innerHTML` property of HTML elements will be helpful!
    - more optional: add a "Clear History" button that will clear out that history

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dice Roller</title>
  <style>
    h1{
      font-family: sans-serif;
    }
    /* https://www.w3schools.com/csS/css3_buttons.asp */
    button {
      background-color: #04AA6D;
      border: none;
      color: white;
      padding: 15px 32px;
      text-align: center;
      text-decoration: none;
      display: inline-block;
      font-size: 16px;
    }

    #btn10{
      background-color: #008CBA;
    }
    
    #btn20{
      background-color: #f44336;
    }

    button:hover {
      opacity: 0.8;
    }
  </style>
</head>
<body>
  <h1>Dice Roller!</h1>
  <div>
    <button id="btn6">D6</button>
    <button id="btn10">D10</button>
    <button id="btn20">D20</button>
  </div>

  <hr>

  <div>The roll is: <span id="numberSpan">???</span></div>
  <script>
    // We are putting the <script> tag at the bottom to make sure that 
    // the HTML page has loaded before we start trying to hook up button events
    
    // The following code is loaded in once, when the HTML page first loads
    
    function showRandomInt(min, max) {
      min = Math.ceil(min);
      max = Math.floor(max);
      let number = Math.floor(Math.random() * (max - min + 1)) + min;
      numberSpan.innerHTML = number;
    }

    btn6.onclick = function(){
      showRandomInt(1, 6);
    };

    btn10.onclick = function(){
      showRandomInt(1, 10);
    };

    btn20.onclick = function(){
      showRandomInt(1, 20);
    };
  </script>
</body>
</html>
```

---

## V. Posting an HTML page to GitHub
- First, you need an **index.html** page to post online -  this will be your GitHub pages "home page":
  - make a copy of **minimal.html** file and name it **index.html**
- Here are the instructions: https://pages.github.com/ - but here's a simplified version:

---

1) Create a New Repository named ***yourGitHubId.github.io***

![screenshot](_images/github-intro-1.png)

![screenshot](_images/github-intro-2.png)

- Give it a name of "yourGitHubId.github.io"
- Make it "Public"
- Check the box so we get a README.md file
- Click "Create repository"
  - for example, my GitHub pages repo is here - note the name - https://github.com/tonethar/tonethar.github.io - and note that it contains an **index.html** file

---

2) Check the settings (*kind of optional, you might not have to do this*)

- Head to Settings, "Code and automation" and click "Pages"
- Under "Build and deployment", under "Source", select "Deploy from a branch"
- Use the branch dropdown menu and be sure that the repo is deploying from the main branch

---

3) Upload **index.html** to this repo


---

4) Did it work? (it might take a minute or 2)
- Finally, head to `https://yourGitHubId.github.io/` to see your page
 - for example, my GitHub pages site is at: https://tonethar.github.io/
- BTW - whenever you update your **index.html** page or other files that are going to be part of your GitHub pages home page, it takes a minute or so for the changes to be visible on `https://yourGitHubId.github.io/`
   
---

## VI. Homework
- Update **index.html** that is visible on GitHub to also display the links (link code written in HTML, NOT markdown!) from your "listicle" (at least 5 of them)
- Head to the myCourses Assignments tab and post the link there in the applicable dropbox - be sure to give me the  `https://yourGitHubId.github.io/` "web page" version
- If you have some time look over the HTML PDFs that are posted to myCourses
- ZIP and attach the updated **first-html-pages** folder (with all of the ***YOU DO*** changes made) 
