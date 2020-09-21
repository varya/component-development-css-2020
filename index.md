---

layout: ig

style: |

    #Cover h2 {
        margin:30px 0 0;
        color:#FFF;
        text-align:center;
        font-size:70px;
        }
    #Cover p {
        margin:10px 0 0;
        text-align:center;
        font-size:20px;
        }
    #Picture h2 {
        color:#FFF;
        }
    #SeeMore h2 {
        font-size:100px
        }
    #SeeMore img {
        width:0.72em;
        height:0.72em;
        }


    .slide--center {
      text-align: center;
    }
    .slide--center .slide__content {
      text-align: justify;
    }
    .no-title h2 {
      display: none;
    }

    .slide .relevant-link {
      font-size: 0.5em;
      position: absolute;
      bottom: 25px;
      margin-bottom: 0.25em;
    }

    .slide .quadruple {
      column-count: 4;
    }

    .code--size--m {
      font-size: 0.8em;
    }
---

# <span class="dev">Component development</span> <span class="css">with CSS</span> <span class="year">in 2020</span> {#Cover}

<b>Varya Stepanova</b>, Design Systems Architect / [varya.me](http://varya.me)
{: .author }

<style>

#Cover {
  padding-left: 60px;
  padding-right: 60px;
}

#Cover,
#Cover h2,
#Cover p
 {
  color: black;
}

#Cover h2 {
  font-size: 55px;
  margin-top: 0.25em;
  line-height: 1em;
  text-transform: capitalize;
}

#Cover h2 .dev {
  display: block;
  color: #38bcc2;
}

#Cover h2 .css {
  font-size: 100px;
  font-family: "Graphik Light";
  display: block;
  text-transform: uppercase;
  margin-top: 0.5em;
  margin-bottom: 0.25em;
}

#Cover h2 .year {
  color: #ca4e1f;
}

#Cover .author {
  margin-top: 252px;
  text-align: right;
}

#Cover .event {
  font-size: 0.5em;
  text-align: right;
  margin-top: 0;
}

</style>


## Me
{: .no-title .about-me }

![](pictures/me.jpg){: .photo }

### Varya Stepanova
<b>Design Systems Architect</b><br/>

* Design systems
* UI libraries
* Frontend development
{: .above }

- Design operations
- Research-driven project vision and strategy
- Cultivating a thriving design & development community
- Facilitating collaboration between teams
- Setting up effective processes and practices
- Coaching and training
- Automating the routines
{: .below }


[@varya_en](https://twitter.com/varya_en){: .twitter } /
[varya.me](http://varya.me) /
[mail@varya.me](mailto:mail@varya.me)
{: .contacts }

<style>
.about-me p,
.about-me .above,
.about-me .below {
  font-size: 70%;
}

.about-me .above li,
.about-me .below li {
  padding-top: 0.15em;
  padding-bottom: 0.15em;
}

.about-me .above li:before,
.about-me .below li:before {
  left: 250px;
  line-height: 1.75em;
}

.about-me .iceberg {
  float: left;
  width: 300px;
  margin-top: 115px;
  margin-bottom: 6em;
  margin-right: 2em;
}

.about-me h4 {
  color: #ca4e1f;
  font: 1em/1 'FF Meta Serif',sans-serif;
  margin-bottom: .5em;
}
.about-me b {
  font-size: 1.25em;
}

.about-me .contacts {
  line-height: 1;
  font-size: 0.75em;
  margin-top: 35px;
}

.about-me .twitter
{
  text-decoration: none;
  color: currentColor;
  background: none;
  border-bottom: 0;
}
.about-me .twitter::before
{
  content: "";
  display: inline-block;
  width: 1.5em;
  height: 1.5em;
  background-image:url('pictures/twitter-logo.png');
  background-size: cover;
  margin-right: 0.5em;
  margin-bottom: -0.5em;
}
</style>

<!--
Before we start, I would like to introduce myself and explain why
this topic has been chosen.
-->

<style>
.about-me p {
  font-size: 80%;
}
.about-me .photo {
  float: left;
  width: 300px;
  margin-top: 1em;
  margin-bottom: 6em;
  margin-right: 2em;
  border-radius: 50%;
  margin-left: -3em;
}
</style>


## Spoiler

* Industry challenges when developing CSS
* Today's solutions for components on the web

<!--
This is what I'm going to show today
  https://www.styled-components.com/
  https://vuejs.org/v2/guide/single-file-components.html#For-Users-New-to-Module-Build-Systems-in-JavaScript
  CSS modules
  CSS-in-JS

  https://speakerdeck.com/okonet/modular-css-v2-css-in-js-edition
-->


## CSS

> *Cascading Style Sheets* (CSS) is a style sheet language used for describing the look and formatting of a document
> written in a markup language. <cite>[Wikipedia](https://en.wikipedia.org/wiki/Cascading_Style_Sheets)</cite>

First published in 1996
{: .note}

<!--
The meaty part of the lecture is about CSS.
Are you familiar with this technology?

CSS is used to style web documents. CSS rules can be matched to DOM nodes and bring them view which
is descriped with CSS properties.

This concept is pretty old. CSS was first introduced in 1996. And nothing conceptually has been changed since then.
However the web now is far more complex than in 1996, so in industry we are facing the chalelngies and need a way to
overcome.
-->


## Industry challenges
{: .no-title }

![](pictures/homepage.png)

<!--
In this picture you can see how the web pages used to look like. And from the architectural point of view they were
similar. The industry just did not have experience back then to provide recommendations how to build the web good.

Now things have already changed. Today, if you are developing not you cat's homepage but a serious website, it should
meet the requirements.
-->


## Bulletproof Web Desing
{: .bulletproof .no-title }

<!--
This problem was first spoken out loud by this gentelman. His name is Dan Cederholm and he is the author of the book
shown. The "Bulletproof Web Design" is a first place where the inductry needs were explained.
It was first published in 2005 and has 2 more editions since then. However this is quite mature book, I still recommend
it if you want to step in the industry level of creating web sites.
He first said that the HTML/CSS markup we produce should be stable. It should be maitainable meaning not very sensetive
to the providing changes.
So, it's not like single action - provide the code and forget about it. A developer will get back to their code to fix
something. Other developers will bring their changes into the code. And nothing should be broken in unexpected places.
-->

<style>
.shower.list .bulletproof,
.bulletproof {
  background-image:
    url('pictures/bulletproof.jpg'),
    url('pictures/dan-cederholm.jpg');
  background-position: top right, -120px 0;
  background-size: auto, 100%;
  background-repeat: no-repeat;
}
</style>


## Big CSS

* massive sites
* big teams of developers
* heavy UI
* long-running projects

<!--
massive sites: A lot of code, thousands of lines
big teams of developers: up to hundreds of ppl, teams can grow and change
heavy UI: each piece of interface has a lot of code and logic behind
long running project: need to be maintainable
-->


## Massive web sites

* Thousands of lines of code
* A lot of files
* Many pages
{: }

* A lot of websites with common codebase
* Common corporate style

<!--
You cannot check all the pages visially for every change, so your code should be written the way which
makes it possible to predict.

A lot of websites with common codebase: repeating would be too expensive.
-->


## Big teams

* Hundreds of developers
* Growing teams
* Changing the context

<!--
Hundreds of people.
Developers need common approaches.
Communication matters.
-->


## Heavy UI
{: .heavy-ui .no-title }

![](pictures/domik.png){: .cover }

<!--
This login form in the middle does not look as a massive component.
Just 2 inputs, checkbox, button.
Guess how much code is needed to represent it?
-->


## Heavy UI
{: .heavy-ui-code .no-title }

    <form class="b-mail-domik g-js" method="post" action="https://passport.yandex.com/passport?mode=auth&amp;from=mail&amp;origin=hostroot_com_nol_enter&amp;retpath=https%3A%2F%2Fmail.yandex.com">
      <i class="b-mail-domik__roof"></i>
      <table class="b-mail-domik__shadow">
        <tbody>
          <tr>
            <td class="b-mail-domik__shadow__lt">&nbsp;</td>
            <td class="b-mail-domik__shadow__t"></td>
            <td class="b-mail-domik__shadow__rt">&nbsp;</td>
          </tr>
          <tr>
            <td class="b-mail-domik__shadow__l">&nbsp;</td>
            <td class="b-mail-domik__shadow__m">
              <div class="b-mail-domik__form">
                <div class="b-mail-domik__username">
                  <label class="b-hint-input g-js" for="b-mail-domik-username11" style="display: block;">username</label>
                  <div class="b-input"><input tabindex="1" name="login" id="b-mail-domik-username11" class="b-input__text" autocapitalize="off" autocorrect="off" aria-label="username"></div>
                </div>
                <div class="b-mail-domik__password">
                  <label class="b-hint-input g-js" for="b-mail-domik-password11">password</label>
                  <div class="b-input"><input type="password" tabindex="2" name="passwd" id="b-mail-domik-password11" class="b-input__text" aria-label="password"></div>
                </div>
                <div class="b-mail-domik__permanent"><input type="hidden" name="twoweeks" value="yes"><input type="checkbox" tabindex="3" id="b-mail-domik-permament11" class="b-mail-domik__check">&nbsp;<label for="b-mail-domik-permament11">don't remember me</label></div>
                <div class="b-mail-domik__button b-mail-domik__button_qr"><span class="b-mail-button b-mail-button_default b-mail-button_button b-mail-button_grey-26px b-mail-button_26px b-mail-button_lead"><span class="b-mail-button__inner"><span class="b-mail-button__text">Log in</span></span><input type="submit" tabindex="4" class="b-mail-button__button" value="Log in"></span><a href="https://passport.yandex.com/auth/?mode=qr&amp;retpath=https%3A%2F%2Fmail.yandex.com" class="js-button-qr b-mail-button b-mail-button_default b-mail-button_button b-mail-button_grey-26px b-mail-button_26px b-mail-button_dependent"><span class="b-mail-button__inner"><span class="b-mail-button__ico b-mail-button__ico_qr"></span></span></a></div>
                <div class="b-mail-domik__remember"><a tabindex="5" class="b-mail-domik__remind js-count-click" href="https://passport.yandex.com/passport?mode=restore" data-metrika="Клики на 'Вспомнить пароль'" data-paranja="check">Forgot your password?</a></div>
                <div class="b-mail-domik__social"><a class="b-mail-domik__social-link js-social-link" data-provider="fb"><i class="b-mail-domik__social-icon b-mail-domik__social-icon_provider_fb"></i></a><a class="b-mail-domik__social-link js-social-link" data-provider="tw"><i class="b-mail-domik__social-icon b-mail-domik__social-icon_provider_tw"></i></a><a class="b-mail-domik__social-link js-social-link" data-provider="gg"><i class="b-mail-domik__social-icon b-mail-domik__social-icon_provider_gg"></i></a></div>
              </div>
            </td>
            <td class="b-mail-domik__shadow__r">&nbsp;</td>
          </tr>
          <tr>
            <td class="b-mail-domik__shadow__lb">&nbsp;</td>
            <td class="b-mail-domik__shadow__b"></td>
            <td class="b-mail-domik__shadow__rb">&nbsp;</td>
          </tr>
        </tbody>
      </table>
      <div class="antivirus js-antivirus">Yandex.Mail has <a href="http://www.drweb.com/" target="_blank"></a> virus protection</div>
    </form>

<!--
So, this is HTML.
And almost every node here needs CSS. Not one property but many.
-->

<style>
.heavy-ui-code pre code {
  font-size: 7px;
}
</style>


## Long running projects

* Code lives for years
* Continious development

<!--
In the web development you cannot create version 2, we provide changes little by little
So, the code should be maintainable for years
-->


## Where is CSS hard?
{: .slide--shout .slide--red }


## Building meme
{: .no-title .slide--full-image }

![](pictures/css1.jpg)


## Is this good?

```css
H1 { color: blue }
P EM { font-weight: bold }
A:link IMG { border: 2px solid blue }
A:visited IMG { border: 2px solid red }
A:active IMG { border: 2px solid lime }
```

<!--
Now look at this code. Do you see something strange? Any guess?
Who would write their CSS like this?

The problem is that CSS was created to make text bold and links underlined. It ideally suited
solving these problems. In many websites developers still use CSS like.

Actually this code from [CSS level 1 specification](http://www.w3.org/TR/CSS1/). It is
very simple, was recommended in 1996. Time passed and we met new chalenges.
-->


## What makes CSS hard?

* Vertical centering
* Equal height columns
* Browser inconsistencies
* Unobvious tricks
{: .next }

<!--
Before we decide what is wrong with that peice, let's guess what is hard in CSS.

When ppl are asked, the repson is usually
- vertical centing
- making columns of equial height
- browers render CSS differently, so it takes special knowledge and work to make the interface consistent
- many solutions are unobvious tricks which needed to be memorized

But this is not true, this is easy or at least clear how to manage. You can google for all this questions.
-->


## What <mark>really</mark> makes CSS hard?

* Scoping
* Specificity conflicts
* Non-deterministic matches
* Dependency management
* Removing unused code

<!--
The real hard problems of CSS are here:
- No scoping. Everything is CSS is global.
- Specificity conflicts. I'll explain in detal later.
- Non-deterministic matches which naturally result from declarativeness of CSS language
- Dependency management
- Removing unused code
-->


## CSS has no scoping

```css
a { /* Affects all the links */
  color: red;
}
ul li a { /* Affects all the links in lists */
  color: green;
}
```

<!--
This especially maters if you link third-party CSS.
A common problem for developing libraries or code which will be later delivered to another web site.
Everything in CSS is global, and writing good CSS is similar to writing a good program module if you only allowed to use
global variables.
This can be mixed with another CSS and applied to wrong nodes.
Writing good CSS means you has to predict the future.
-->


## Specificity

> Specificity is the means by which a browser decides which property values are the most relevant to an element and gets
> to be applied. Specificity is only based on the matching rules which are composed of selectors of different sorts.

<!--
Another problem is specificity.
Who remember what specificity is?
Ok, I will explain.
-->


## The most specific matters

```html
<div id="test">
  <span>Text</span>
</div>
```

```css
div#test span { color: green }
span { color: red }
div span { color: blue }
```

<!--
If a brower has 2, 3 or more rules which match the same DOM node, how it decides what are the properties to take into
work?
The order does not matter.
For every selector a browser calculates how important this set of rules is. The rule with the more specific selector
would be prioritized.
So, here we see...
-->


## How to overwrite?

    <div class="sidebar">Left floated sidebar</div>

<separator/>

    .sidebar { /* Does it redefine `div.sidebar`?! */
      float: right;
    }
{: .next }

<separator/>

    body .sidebar { /* Overwrites 'div.sidebar {}' */
      float: right;
    }
{: .next }

<!--
When it comes to developments, specificity matters when redefining pre-given
components.

To redefine the left-floated sidebar, we would overwrite the rule.
-->


## Specificity hell
{: .no-title }

```css
.navbar-inverse .navbar-nav>li>a {
  color: #999;
}

#home-menu-container #home-menu li a {
  color: red;
}

body #home-menu ul li a {
  color: blue !important;
}
```
{: .code--size--m }

<!--
People ask on Stackoverflow how to overwrite Bootsrtap
These things can be in different files
-->


## Family guy meme
{: .no-title .slide--full-image }

![](pictures/css2.gif)


## Non-deterministic matches

```css
#content div div {
  float: left;
}
```

<!-- This can be matched to anything -->
<!-- You cannot rely on the document structure, because it contantly changes while developing -->
<!-- в момент, когда ты пишешь, ты указываешь признаки нод, на которые сматчится правило, а не точный адрес. смотри:
можно писать адрес «Rettigweg 1, 13187 Berlin", а можно «около Wollankstrasse такая боковая улица с тремя домами, и
там есть такой желтый дом, и там на втором этаже ещё балконы металлические с узорами» -->


## Doctor meme
{: .no-title .slide--full-image }

![](pictures/css3.gif)


## Dependency management
{: .dependency-management }

### No dependencies, sorry

<div class="next" markdown="1">
### But what about?

    @import url('i-need-this.css');
</div>

### No, sorry again.
{: .next .sorry }

<!--
CSS was not developed as a programming language and now it still isn't. So, there is no way to declare that
one piece of CSS needs anotehr one.
OK, there is import. But this is not  aproduction solution. And assuming undeterministic matches we cannot rely on it.
-->

<style>
.dependency-management h3 {
  padding-top: 1em;
  margin-bottom: 0.5em;
}
.dependency-management .sorry
{
  color: green;
}
</style>


## Removing unused code

100 pages in projects

```css
.person div a {
  color: pink;
}
```

Can I remove it? Will it break something? Maybe it is for a third-party HTML code?

<!--
CSS is declarative, so you cannot say what are the nodes the rules will aply to.
If you have a lot of pages you cannot remove a piece of CSS and check visually if something is broken.
Even worse with  dynamic web sites.
-->


## Where CSS is hard?
{: .no-title .hard-css }

<table><thead>

<th markdown="1">

This is not hard in CSS

</th>

<th markdown="1">

This is!

</th>

</thead><tr>

<td markdown="1">

    #sidebar ul li a {
      <mark>color: red;</mark>
      <mark>display: block;</mark>
      <mark>padding: 1em;</mark>
    }
{: .css }

</td>

<td markdown="1">

    <mark>#sidebar ul li a</mark> {
      color: red;
      display: block;
      padding: 1em;
    }
{: .css }

</td>

</tr></table>

*How do we architect encapsulated components?*
{: .next }

<!--
Writing CSS is easy. It is very easy to read and it is very likely that you can
find the tricks you need at Stackoverflow. But architechting CSS is very difficult.

We need a way to architect independent encapsulated components.
Being put into any place on the page, the components should not break anything. Also, it should not be broken
itself.
-->

<style>
.hard-css em {
  font-size: 30px;
}
</style>


## Dealing with CSS
{: .slide--shout .slide--red }


## Ways out

* Standards
* Methodology
* Technology


## Standards
{: .slide--shout .slide--azure }

<!--
Here I introduce you a concept called Web Components. This is not the methodology but
a new technology, a new standard which will hopefully solve the problems we considered.
-->

## W3C
{: .no-title .w3c }

<style>

.shower.list .w3c,
.w3c {
  position: relative;
  background-image: url(pictures/w3c.png);
  background-size: auto 640px;
  background-position: 50% 50%;
  background-repeat: no-repeat;
}

</style>


## Web Components
{: .wc-behind }

<div class="wc-logo"></div>

* Shadow DOM
* Custom Elements
* HTML Templates
* <s>HTML Imports</s> (not supported any more)

<!--
Web Components is not another language but some additions into already existing standards.
So, the additionas are:
- shadow DOM
- Custom elements in HTML
- HTML templates
- HTML Imports

I will show you in code what it all means.
-->

<style>

.wc-behind .wc-logo {
  display: block;
  float: right;
  width: 200px;
  height: 200px;
  margin-right: 200px;
  background-image:url('pictures/webcomponents.png');
  background-size: contain;
  background-repeat: no-repeat;
  background-position: 50% 50%;
}

</style>

## Inspect shadow dom
{: .chrome-dev-tools }

![](pictures/chrome-shadow-dom.png)


<style>

.chrome-dev-tools img {
  width: 500px;
}

</style>

## Web Components

* [Native component](demo/video.html)
* [Custom web component](demo/custom-button.html)
* [Templates](demo/templates.html)
* <s>HTML imports</s> (not supported any more)

<!--
These are a few pages I prepared for the lecture which demonstrate the concept.
Let's take a look into them one by one.

1. Video page
Open code
Inspect element
Switch on Shadow DOM
Shadow DOM is DOM behind the component. Video is native component.

2. Custom web component
We can write our own components.
HTML is just <my-button>
In Shadow DOM we can see more compex structure.
This is because we can tech the browser to deal with our custom component. This teaching
goes with JavaScript.
Take into account that styles are encapsulated.

3. Templates
Easier than describe everything in JavaScript

4. HTML imports
Everything about one components can be detached into an HTML file and then linked to the page.

-->


## HTML import, library

```html
<!-- Import element -->
<link rel="import" href="my-lib/google-map.html">

<!-- Use element -->
<google-map lat="37.790" long="-122.390"></google-map>
```

<!--
With HTML imports you can create your own components and use them across different websites.
Or you can use someone else's components as a library.
-->


## [Can I use?](https://caniuse.com/?search=web%20components)
{: .slide--shout .slide--azure }


## Web Components Polyfills
{: .wc-polyfills }

* [WebComponents.org](http://webcomponents.org/)
* [X-Tag](http://www.x-tags.org/)

<!--
However we can live with Polyfills.
These are JavaScript additions which "teach" a browser to emulate the work of Web Components.
Add such a sript onto your page and you will be sure that the components work.
-->

<style>

.wc-polyfills ul li::before {
  content: '';
  width: 100px;
  height: 100px;
  margin-right: 1em;
  display: inline-block;
  background-size: contain;
  background-repeat: no-repeat;
  background-position: top left;
  background-position: 50% 50%;
  vertical-align: middle;
  position: relative;
}
.wc-polyfills ul li:first-child::before {
  background-image: url('pictures/webcomponents.png');
}
.wc-polyfills ul li:nth-child(0n + 2)::before {
  background-image: url('pictures/polymer.svg');
}

</style>


## Make it work

    <!-- Polyfill Web Components support for older browsers -->
    <mark><script src="webcomponents.min.js"></script></mark>

    <!-- Import element -->
    <link rel="import" href="google-map.html">

    <!-- Use element -->
    <google-map lat="37.790" long="-122.390"></google-map>
{: .html }


## Ready-made components

* [Polymer](https://www.polymer-project.org/)
* [Google Web Components](http://googlewebcomponents.github.io/)

<!--
You can search for ready-made components. There is not that many of them, but
you can have some.
-->


## Usage examples

* [Toolbar](demo/toolbar.html)
* [Google map](demo/google-map.html)

<!--
I created a couple of examples about how the components can be used.

1. Toolbar
With linking the components simple code turns into more complex. Each element has its styles.

2. Goole Map
The component encapsulates JavaScript logic

This is all about web components

-->


## Methodologies
{: .slide--shout .slide--azure }

<!--
As CSS does not provide us with the answer to the question how to do it, the developers should up
the methodologies.
The methodology does not give change into the technology. It suggest a developer how to use the
technology better.
-->


## OOCSS
{: .slide--shout }

<!--
The first methodology proposed was OOCSS, stands for Object Oriented CSS.
-->


## Nicole<br/>Sullivan
{: .nicole }

<!--
It was in 2007, this is Nicole Sullivan, who authored it.
She worked for Yahoo and by that time she was dealing with components for Yahoo UI and was trying to
give some order to all this mess. So, she proposed to use some principles from OOP to CSS. This was in 2007.
I will not explain the detailes because I belive that this era is passed by.
But I still think that I should mentione her as a pioneer. She was a first developer who was trying to
solve it.
-->

<style>

.shower.list .nicole,
.nicole {
  position: relative;
  background-size: auto 640px;
  background-position: 50% 50%;
  background-repeat: no-repeat;
  background-image: url('pictures/nicole-sullivan.jpg');
}

.nicole h2 {
  position: absolute;
  right: 60px;
  bottom: 320px;
  font-size: 60px;
  color: white;
  font-weight: bold;
  text-shadow: 5px 10px 15px rgba(0,0,0,1);
}

</style>


## SMACSS
{: .slide--shout }

<!--
Another milestone is SMACCS, which is Scalable and Modular Architecture for CSS.
This is a book, first published in 2009 but still available.
-->


## Jonathan<br/>Snook
{: .jonathan }

<!--
The author is this gentelman, Jonathan Snook. You can find his website if interested.
-->

<style>

.shower.list .jonathan,
.jonathan {
  position: relative;
  background-size: auto 640px;
  background-position: 50% 50%;
  background-repeat: no-repeat;
  background-image:url(pictures/jonathan-snook.jpg);
}

.jonathan h2 {
  position: absolute;
  right: 50px;
  bottom: 200px;
  font-size: 52px;
  font-weight: bold;
}

</style>


## BEM
{: .slide--shout }

<!--
And the last new thing appeared was BEM, stands for Block, Element Modifier.
It was created in 2009, then evoluated and had a long way to its popularity by now.
-->

## BEM creators

* ![](pictures/vitaly-harisov.jpg) Vitaly Harisov
* ![](pictures/veged.jpg) Sergey Berezhnoy
* and others
{: .harisov-veged }

<style>

.harisov-veged img {
  width: 150px;
  margin-bottom: 1em;
  vertical-align: middle;
}
.slide ul.harisov-veged li:before {
  top: 70px;
}
.slide ul.harisov-veged li:last-child:before {
  top: 0;
}
</style>

<!--
This is one of the main authors. Vitaly Harisov. He works for Yandex and heads the
frontend development there.

Another co-author is Sergey Berezhnoy, who also works for Yandex.
O was very lucky to work with them and be a member of the BEM team, so I can tell you
a little bit more about it today.
-->


## BEM eco-system

* <mark>CSS Methodology</mark>
* JavaScript framework
* Template engine
* Building system
* Supplementary tools

<!--
Actually behind BEM there is a massive amount for JavaScript libraries, own template engine, many supplimentary tools.
Mosty these things are very local, but the CSS Methodology is a popular thing and becoming a standard all over the
world. So, I'll explain it in details.
-->


## Harry & Nicolas
{: .no-title .harry-nicolas }

### Harry<br/>Roberts
{: .harry }

### Nicolas<br/>Gallagher
{: .nicolas }

<!--
These 2 gentelmen are also important persons in the BEM community.
These are Harry Roberts from Britan and Nicolas Gallaher from USA. They had have a great role in BEM to be wide-spreaded
and become a standard.
Both are very famous developers and Harry is also the most wanted speaker for frontend conferences now.
So, if you are interested in their motivation of taking this approach, you can google for their blogs and social
networks accounts.
-->

<style>

.shower.list .harry-nicolas,
.harry-nicolas {
  position: relative;
  background-size: auto 640px;
  background-position: 50% 50%;
  background-repeat: no-repeat;
  background-image: url(pictures/harry-nicolas.jpg);
}

.harry-nicolas .harry {
  color: #fff;
  font-size: 45px;
  position: absolute;
  bottom: 25px;
  left: 265px;
  line-height: 1.5em;
}

.harry-nicolas .nicolas {
  color: #fff;
  font-size: 45px;
  position: absolute;
  bottom: 25px;
  right: 25px;
  line-height: 1.5em;
}

</style>


## Technology
{: .slide--shout .slide--azure }


## Modular CSS

* CSS modules
* Styled Components
* and many more


## CSS modules
{: .slide--shout .slide--no-title }

![](pictures/css-modules-logo.png){: .css-modules-logo }

<style>
.css-modules-logo {
  width: 400px;
}
</style>


## Glen<br/><span class="surname">Maddern</span>
{: .maddern .slide--full-image }

![](pictures/glen-maddern.jpg)

<!--
-->

<style>

.maddern h2:not(.slide--shout) {
  display: block;
  position: absolute;
  right: 90px;
  top: 55px;
  font-size: 80px;
  font-weight: bold;
}

.maddern h2 .surname {
  color: white;
}

</style>


## Manual CSS

### page.html

```html
<h1 class="title">An example heading</h1>
```

### styles.css

```css
.title {
  background-color: red;
}
```


## CSS modules input

### page.js -> page.html

```js
import styles from "./styles.css";

element.innerHTML = 
  `<h1 class="${styles.title}">
     An example heading
  </h1>`;
```


## CSS modules output

### page.html

```html
<h1 class="<mark>_styles__title_309571057</mark>">
  An example heading
</h1>
```

### styles.css

    .<mark>_styles__title_309571057</mark> {
      background-color: red;
    }
{: .css }


## Automated BEM

<table><thead>

<th markdown="1">

BEM

</th>

<th markdown="1">

CSS modules

</th>

</thead><tr>

<td markdown="1">

```css
.button { ... }
.button--disabled { ... }
.button__label { ... }
```

</td>

<td markdown="1">

```css
.button { ... }
.disabled { ... }
.label { ... }
```

### ⬇

```js
styles: {
  button: 'button__abc5436',
  disabled: 'button__disabled__deff65',
  label: 'button__label__1638bcd'
}
```

</td>

</tr></table>

## CSS modules pros and cons

* Scoped & fast selectors (BEM for free)
* Code reuse
* Framework agnostic

<separator/>

* Non standard syntax
* Required building
* No dead code elimination


## Why to write classes?
{: .thinkful-cat }

![](pictures/thinkful-cat.svg)

<style>
.thinkful-cat p {
  text-align: center;
}

.thinkful-cat img {
  width: 500px;
}
</style>


## Styled components
{: .slide--shout }

![](pictures/styled-components.png){: .styled-components-logo }

<style>
.styled-components-logo {
  width: 400px;
}
</style>


## Styled crew

<div class="double" markdown="1">
* ![](pictures/glen.jpeg) Glen Maddern
* ![](pictures/max.jpeg) Max Stoiber
* ![](pictures/phil.png) Phil Plückthun
* and the others
{: .styled-components-crew }
</div>

<style>
.styled-components-crew img {
  width: 150px;
  margin-bottom: 1em;
  vertical-align: middle;
}
.styled-components-crew li:last-child {
  margin-top: 60px;
}
.slide ul.styled-components-crew li:before {
  top: 70px;
}
.slide ul.styled-components-crew li:last-child:before {
  top: 0;
}
</style>

## CSS-in-JS

> “CSS-in-JS” refers to a pattern where CSS is composed using JavaScript instead of defined in external files<br/>- [FAQ Styling](https://reactjs.org/docs/faq-styling.html)


## To style component

```js
const Title = styled.h1`
  font-size: 1.5em;
  text-align: center;
  color: green;`;

render(
  <Title>
    Hello, world!
  </Title>
)
```
{: .code--size--m }

## Reflect the state
{: .styled-components-example }

    const Button styled.button`
      background: <mark>${props => props.primary ? 'green' : 'white' }</mark>;
      color: <mark>${props => props.primary ? 'white' : 'green' }</mark>;
      font-size: 1em;`;

    render (
      <div>
        <Button>Normal</Button>
        <Button primary>Primary</Button>
      </div>
    );
{: .code--size--m .js }

<div class="example">
  <button>Normal</button>
  <button class="primary">Primary</button>
</div>

<style>
.styled-components-example .example {
  position: absolute;
  right: 40px;
  bottom: 80px;
}

.styled-components-example button {
  display: inline-block;
  appearance: none;
  box-shadow: none;
  font-size: 40px;
  padding: 0.25em;
  margin: 0 0.5em;
  background: white;
  color: green;
}
.styled-components-example button.primary {
  background: green;
  color: white;
}
</style>


## What does browser get?
{: .no-title }

### HTML

```html
<button class="sc-bxivhb clMJJc">Normal</button>
<button class="sc-bxivhb iJPdAn">Primary</button>
```
{: .code--size--m }

### CSS

    .clMJJc {
      /* ... other rules */
      background: white; color: green;
    }
    .iJPdAn {
      /* ... other rules */
      background: green; color: white;
    }
{: .code--size--m .css }


## Styled <mark>components</mark>

* No thinking up class names
* No manual class-component mapping
* Styles reflect the state of component


## Styled innovation
{: .slide--shout .slide--no-title }

> styled-components [...] remove the mapping between components and styles
> <figcaption><a href="https://www.styled-components.com/" target="_blank">www.styled-components.com</a></figcaption>


## More to study

### CSS-in-JS solutions

[http://michelebertoli.github.io/css-in-js/](http://michelebertoli.github.io/css-in-js/)


## Component development with CSS in 2020

* Big CSS
* Web Components
* Methodologies
* CSS modules
* styled-components


## Thank you
{: .thanks }

Varya Stepanova, independent consultant on design systems<br/>
[@varya_en](https://twitter.com/varya_en){: .twitter }; on the web: [varya.me](http://varya.me){: .web }

### Slides

#### [varya.me/component-development-css-2020](http://varya.me/component-development-css-2020/)

#### Credits
{: .credits-header}

Roman Komarov, [@kizmarh](https://twitter.com/kizmarh);
Andrey Okonetchnikov, [@okonetchnikov](https://twitter.com/okonetchnikov);
Vadim Makeev, [@pepelsbey_](https://twitter.com/pepelsbey_).
{: .credits}

<style>
.thanks h3 {
  font-size: 28px;
  margin-bottom: 0.5em;
  margin-top: 1em;
  line-height: 1.25em;
}
.thanks .twitter
{
  text-decoration: none;
  color: currentColor;
  background: none;
  border-bottom: 0;
}
.thanks .twitter::before
{
  content: "";
  display: inline-block;
  width: 1.5em;
  height: 1.5em;
  background-image:url('pictures/twitter-logo.png');
  background-size: cover;
  margin-right: 0.5em;
  margin-bottom: -0.5em;
}
.thanks .credits-header {
  margin-top: 1.5em;
}
.thanks .credits {
  font-size: 0.75em;
}
</style>
