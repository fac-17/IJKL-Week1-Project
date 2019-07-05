# IJKL Digital Agency: One-Page Portfolio Website

## Authors

- <a href="https://github.com/Albadylic">@Albadylic</a>
- <a href="https://github.com/Coletterbox">@Coletterbox</a>
- <a href="https://github.com/reubengt">@reubengt</a>
- <a href="https://github.com/xIrusux">@xlrusux</a>

## Contents

The site aims to have:

- a headline about the team
- a concise description of what we have to offer
- a navigation link for "About," "Team" and "Contact"
- a contact form

## Purpose

The site aims for:

- the ability to easily navigate to various areas of the site
- the ability to easily view the site when browsing on mobile, tablet or desktop
- the ability for the visually impaired to easily read and understand the text on the site
- the ability for blind clients to easily navigate using a screen reader
- the ability to visit the site with JavaScript turned off and get a similar experience

## Process

Our tasks include:

- write README.md
- create HTML skeleton
- create nav bar
- style page
- build scroll arrow
- create form
- write page content
- add page images
- check accessibility

Our stretch goals include:

- add a "thanks" screen for after the form has been submitted
- change the scroll arrow to be a "jump to top" arrow on the last screen

After completing the aforementioned goals, the updated list includes:

- update README.md with user stories
- check comments and increase readability
- reduce white space on "Team" page
- make "About" page more readable
- add one more line of text for Reuben
- correct the up arrow link
- thicken nav borders
- change arrow shape
- add message for after submitting form

<img alt="open pull requests" src="https://img.shields.io/github/issues-pr/fac-17/IJKL-Week1-Project.svg?style=popout"></img>
<img alt="closed pull requests" src="https://img.shields.io/github/issues-pr-closed/fac-17/IJKL-Week1-Project.svg?style=popout"></img>

<img alt="open issues" src="https://img.shields.io/github/issues/fac-17/IJKL-Week1-Project.svg?style=popout"></img>
<img alt="closed issues" src="https://img.shields.io/github/issues-closed/fac-17/IJKL-Week1-Project.svg?style=popout"></img>

## Problems

- following the workflow for git commit
- maintaining a serious demeanour
- not drinking too much coffee
- butt sweat

## Things We Learned

- we got more familiar with the git workflow
- Gregor learned grid
- Christine learned how to create a form
- we practised making pages that were automatically responsive by using vh and vw
- #### Accessibility Titles for screen readers
  we had our content inside a wrapper/container element inside of the actual sections of the website.
  this meant that while we had titles for each of our content boxes, the main sections in the html did not have titles, and the html outliner in chrome was showing them as "untitled section".the accessibility audit started whining about this so we had to fix it.
  we did some googling to fix this, and learnt that each of these needed an actual heading tag as a direct child to show up on the html outline correctly. The issue was that our titles were already present, but useless to the html outliner, and screenreaders, since they were nested inside wrappers(not direct children).
  so we added duplicate h1 tags just so that each of our main sections had a title showing up on the html outliner, and not just "untitled section".  
  **We had to hide these**. display: none, and visibility: hidden is how you usually hide stuff in css.  
  **But these hide content from the screenreader too**.
  some more googling led us to [this website](https://webaim.org/techniques/css/invisiblecontent/) which outlines ways to hide content in css without hiding it from the screen reader.
  **So we added a separate class to these duplicate headings, scr-rdr-only**  
  and gave it the following styles:  
  `position: absolute; left: -10000px; top: auto; width: 1px; height: 1px; overflow: hidden`  
  position absolute removes it from document flow and makes sure it doesnt occupy space, then we just made it really tiny and offset it a whole lotta pixels off the screen so nobody could find it.  
  **but screenreaders can still read it as its still in the html outline**
  **this is a minor issue but it helped our accessibility score**  
  It's worth noting that we only had to do this workaround because our headings were nested inside a wrapper which we needed for styling purposes.
  If your headings are directly inside your page sections, all this is unnecessary.  
  \*\*But if your html outline shows "Untitled Nav" or "Untitled Section", this is one way to fix it"
