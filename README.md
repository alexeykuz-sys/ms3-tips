# MS3: Tips.

[View the live project here.](https://adamdelancey.github.io/ms3-tips/)

As my submission for the Code Institute Milestone Project 3, this Tips website is a site where users can create, read, update and delete suggestion of things to do in Stockholm,
for example where to eat and drink, in order to create a database of ideas that locals and tourists can use to maximise their experience in the city.It is designed to be 
responsive and accessible on a range of devices, making it interactive and easy to navigate for potential users.

<p align="center">
    <img src="documentation/screenshots/responsive.jpg">

# Access

View the project live: [here](https://ms3-tips.herokuapp.com/)

View the Github repo: [here](https://github.com/adamdelancey/ms3-tips)

## Contents

- [UX](#ux)
    - [Strategy](#strategy)
        - [Business Objectives](#business-objectives)
        - [User Stories](#user-stories)
            - [First Time Visitor Goals](#first-time-visitor-goals)
            - [Frequent User  Goals](#frequent-user-goals)
    - [Scope](#scope)
        - [Current Features](#current-features)
            - [Navbar](#navbar)
            - [Back to top Button](#back-to-top-button)
            - [Home Page](#home-page)
            - [Property Landing Page](#property-landing-page)
            - [Property Listing Page](#property-listing-page)
            - [Contact Page](#contact-page)
        - [Long-term goals](#long-term-goals)
    - [Structure](#structure)
    - [Skeleton](#skeleton)
        - [Wireframes](#wireframes)
    - [Surface](#surface)
        - [Design](#design)
            - [Colour Scheme](#colour-scheme)
            - [Typography](#typography)
            - [Imagery](#imagery)
            - [Icons](#icons)
- [Accessibility](#accessibility)
    - [Alt Tags](#alt-tags)
    - [Forms](#forms)
- [Technologies used](#technologies-used)
    - [Languages Used](#languages-used)
    - [Frameworks, Libraries & Programs Used](#frameworks-libraries-&-programs-used)
- [Testing](#testing)
    - [Validation](#validation)
    - [Autoprefixer CSS Online](#autoprefixer-css-online)
    - [Lighthouse](#lighthouse)
    - [EmailJS API](#emailjs-api)
    - [Testing User Stories from User Experience Section](#testing-user-stories-from-user-experience-section)
    - [Fixed Bugs](#fixed-bugs)
    - [Known Outstanding Bugs](#known-outstanding-bugs)
    - [Further Testing](#further-testing)
- [Deployment](#deployment)
- [Credits](#credits)
- [Acknowledgements](#acknowledgements)


# UX

## Strategy

### Business Objectives

1. To create a space where all users, first-time or frequent, can find exciting and new things to do in Stockholm.
2. To create a site where users can add suggestions to the community and find others' suggestions to improve their experience.
3. To create a site that is used by locals and tourists alike to share ideas.
4. To create an exciting database that can be used for further research into life in Stockholm.

### User stories

-   #### First Time Visitor Goals

    As a First Time Visitor, I want to:

    1. Quickly understand the service being provided by Tips and how I can interact with the service.
    2. Be able to easily browse the various 'tips' in Stockholm and find something that interests me.
    3. Be able to register to the website and add my own 'tips'.
    4. Be able to comfortably navigate throughout the site between my own tips and other users'.
    5. Get an instant first-impression that this is a professional, modern and up-to-date site with good UX.

-   #### Frequent User Goals

    As a Frequent User, I want to:
    1. Easily be able to check if any new tips have been added that may interest me.
    2. Login to the account that I had previously set up and see my own submissions.
    3. Add more tips to the website that I may not have done already.
    4. Edit my own tips.
    5. Delete any tips that are no longer relevant.

-   #### Admin Goals

    As Admin, I want to:
    1. Be able to create, read, update and delete all tips on the site.

## Scope

### Current features

* Opening Page
    - Video background showing off Stockholm, using free video footage from [Pexels](https://www.pexels.com/video/timelapse-of-stockholm-at-night-852395/).
    I believe this gives a modern and professional first impression on the user.
    - Fading in text and buttons to enter the site. Acting in sync with the video mentioned above, this adds to the modern
    first impression and should make users excited to see more of the site.
    - This page hides the navbar and footer in order to keep the page to fit to the total size of the viewing window.

* Base HTML - on all pages
    - Navbar (Desktop) - an easy to use, modern design and minimal options to help the user navigate throughout the site 
    at all time. Using an if statement, the navbar changes whether the user is logged in or out, or is an admin.
    - Navbar (Mobile) - using Materialize, the mobile navbar is a slide option that is triggered by the hamburger icon 
    in the fixed navbar. This adds to the user experience and allows for easier navigation on mobile.
    - Flash messages - using the imported 'flash' feature from Flask, there are flash messages that appear on each page each 
    time the user interacts with the site by logging in or registering, logging out, adding a tip, editing a tip, and deleting a tip.
    - Footer - Simple social media icons to learn more about the company. As this is a fictional site and there are no actual 
    social media accounts, to the links simply go to the homepages on an external link in order for the user to still 
    stay in the Tips site.  

* Landing Page
    - Filter icons to see the different categories of Tips that are on offer - Eat, Drink, In, Out, Stay, and then an option 
    for All to see all options. These are labelled with a large icon to continue with the modern style and the filters allow 
    the user to see only the tips that they want to see.
    - Search bar - similarly, in order to improve user experience, there is a search bar that searches for either the name or 
    description of the Tip, in order for the user to find the desired Tip sooner. There is also then the option to 
    'reset' the page for if the user wants to return to seeing all the options.
    - Cards - by using the jinja templated for loop, each individual Tip is displayed within a Materialize card 
    feature, making it easy to see the image, category, name and short description. The picture can then be clicked on as 
    a link to find out more information about the Tip. Additionally, using the sort method in Python, the most recent 
    and therefore most likely relevant Tip is displayed first.


* Tip Page
    - A simple layout featuring a large image of the Tip, the category name, tip name, long description and the details of the 
    user that added or edited the tip. In addition there is a 'return to home' button which acts as an additional navigation 
    option for ease of use.     

* Login/Register Page 
    - A simple card design for each, with a form to add in the desired username and password. The username and password must be 
    alphanumerical and be of a length between 5 and 15 characters.

* Profile Page
    - Instead of a flash message, the user is welcomed by a message which includes their username over the background of an image 
    of Stockholm.
    - A button to 'Add a Tip' allowing quick user access to add an additional Tip of their choice.
    - Features the Tips that the user has already added. For these cards, in contrast to the cards on the landing page, the user 
    is able to read, update and delete the tip if they choose.
    - As part of defensive programming, the delete button is followed by a modal which asks the user if they are sure that they 
    want to delete the tip, in order to avoid any accidental deletions. 

* Add/Edit Tip Page
    - These both have a similar design in order to create a new tip or update an existing tip. Each entry into the form uses the 
    required attribute, and some have min and max values to ensure that the layout remains consistent. As well as text 
    entries, there is a date selection function to choose the date that the tip has been added, and extra JQuery has been added to ensure 
    that the category name is not left blank.

* Manage All Page
    - For the Admin user only, there is a Manage All button in the Navbar where the user is able to read, update and delete all Tips 
    added by any user
  

### Long-term goals

Future improvements to the website may include:

* Be able to add reviews to other user's tips and then allow the website to order user suggestions from best to worst.
* Expanding the website to be used across more cities around the world.
* Include a paid service so that hotels or experiences companies can advertise their business on the site.
* Pagination could be included to the Tips page in the case of many users adding their Tips to the site.


## Structure

* I made the decision to have the site split into clear sections rather than one page. For all users, different pages for the home, 
tips, login and register page. For a logged in user, the Profile and Edit tip page, and for the Admin, additionally the Manage All 
page. Each page has the same navbar and the adjusting Navbar to ensure consistency and ease of use across the site.


## Skeleton

### Wireframes

Desktop View
<p><img src="documentation/screenshots/home-desktop.jpg">
    <img src="documentation/screenshots/browse-desktop.jpg">    
    <img src="documentation/screenshots/tip-view-desktop.jpg">
    <img src="documentation/screenshots/login-view-desktop.jpg">
    <img src="documentation/screenshots/register-desktop.jpg"></p>
    <img src="documentation/screenshots/profile-desktop.jpg"></p>
    <img src="documentation/screenshots/submit-desktop.jpg"></p>
    <img src="documentation/screenshots/edit-desktop.jpg"></p>

Mobile & Tablet Pages
<p><img src="documentation/screenshots/home-tablet-mobile.jpg">
    <img src="documentation/screenshots/browse-tablet-mobile.jpg">    
    <img src="documentation/screenshots/tip-view-tablet-mobile.jpg">
    <img src="documentation/screenshots/login-view-tablet-mobile.jpg">
    <img src="documentation/screenshots/register-tablet-mobile.jpg"></p>
    <img src="documentation/screenshots/profile-tablet-mobile.jpg"></p>
    <img src="documentation/screenshots/submit-tablet-mobile.jpg"></p>
    <img src="documentation/screenshots/edit-tablet-mobile.jpg"></p>

Full wireframes can be accessed here:

-   Desktop Wireframes - [View](documentation/wireframes/tips-desktop.pdf)

-   Mobile & Tablet Wireframes - [View](documentation/wireframes/tips-tablet-mobile.pdf)    


## Surface
   
### Design
-   #### Colour Scheme
    <p><img src="documentation/screenshots/colors.jpg"></p>
    -   I have used a simple, clean and chromatic design for the colours used in the project. The black is mainly used for 
    the text, while the dark-grey colour (as featured in Materialize) is used for the navbar, buttons and footer. In contract, the 
    off-white "cultured" colour is used for the background on all pages in order for the photos and cards to be lifted forward. Due to the 
    images from the tips being colourful, I believe this simple design compliments this well.

-   #### Typography
    -   The Sarala font is the main font used throughout the whole website with Sans Serif as the fallback font in case 
    for any reason the font isn't being imported into the site correctly. I chose this as I believe it has a modern feel and 
    reflects the style of the remainder of the site. 

-   #### Imagery
    - The hero images and background images were all taken from [Pexels](https://www.pexels.com/). The images for the tips 
    are added via a link by the user. 
    - All photos were put through [Tiny PNG](https://tinypng.com/) to reduce the file size and improve loading time.

-   #### Icons
    -   The icons used throughout the site are taken from [Font Awesome](https://fontawesome.com/).

# Information Architecture

MongoDB Atlas is used for storing data for this web site.

Current schema:
A txt version can be viewed [here](documentation/data/data.txt)

<p><img src="documentation/screenshots/data.jpg"></p>


For the needs of this website I did need to use other data types in MongoDB.

# Accessibility

## Alt Tags

In order to ensure that all images are accessible for those using a screen reader, I have ensured that all images used throughout the site include alt tags.

# Technologies used

## Languages Used

-   HTML5
-   CSS3
-   JavaScript
-   Python

## Frameworks, Libraries & Programs Used


1. [MongoDB](https://www.mongodb.com/1)
    - MongoDB was used to host the data used on the site and was chosen due to the non-relational nature of the data.
1. [Flask](https://flask.palletsprojects.com/en/1.1.x/)
    - The Flask framework was used to import the Flask, flash, render_template, redirect, request, session, and url_for 
    functions that are used throughout the site.
1. [BSon](http://bsonspec.org/)
    - This was imported in order to access the data used across the site.
1. [Werkzeug](https://werkzeug.palletsprojects.com/en/1.0.x/)
    - This was imported in order for the password control to enhance security on the site.
1. [Jinja Templating](https://jinja.palletsprojects.com/en/2.11.x/templates/)   
    - This was used predominantly for the with, for loops and if statements in order to display all of the relevant data.
1. [JQuery](https://jquery.com/)
    - I have used JQuery predominantly to initialise the components used in the Materialize framework. In addition, I used 
    code taken from the Data Centric Development Module with the Code Institute in order to ensure that the category names are 
    a required attribute.
1. [Materialize 1.0.0](https://materializecss.com/)
    - Materialize was used to assist with the responsiveness and styling of the website, such as the navbars for desktop and 
    mobile, buttons, forms, cards and colours.
1. [Google Fonts](https://fonts.google.com/)
    - Google fonts were used to import the 'Sarala' font which is used on all pages throughout the project.
1. [Font Awesome](https://fontawesome.com/)
    - Font Awesome was used on all pages throughout the website to add icons for aesthetic and UX purposes. 
1. [Git](https://git-scm.com/)
    - Git was used for version control by utilising the Gitpod terminal to commit to Git and Push to GitHub.
1. [GitHub](https://github.com/)
    - GitHub is used to store the projects code after being pushed from Git.
1. [Heroku](https://dashboard.heroku.com/apps)
    - Heroku is used for the hosting of the site and is deployed through here.
1. [Balsamic](https://balsamiq.com/)
    - Balsamiq was used to create the wireframes during the design process.

# Testing

## Validation

The W3C Markup and CSS Validator Services, JSHint and Python Validator were used to validate every page of the project 
to ensure there were no syntax errors in the project.

-   [W3C Markup Validator](https://validator.w3.org/) - [Results](https://validator.w3.org/nu/?doc=https%3A%2F%2Fms3-tips.herokuapp.com%2F)
    This same result appears across every page of the site.
    <p> <img src="documentation/screenshots/html-checks.jpg">  </p> 
-   [W3C CSS Validator](https://jigsaw.w3.org/css-validator/) - [Results](https://jigsaw.w3.org/css-validator/validator?uri=https%3A%2F%2Fms3-tips.herokuapp.com%2F&profile=css3svg&usermedium=all&warning=1&vextwarning=&lang=en) -  
    There is 1 property issue found when checking the site. However, these are being validated from the Materialize 
    link and therefore out of my control.
    <p> <img src="documentation/screenshots/css-validator.jpg">  </p> 
-   [JSHint](https://jshint.com/) - 
    No issues were found on this check.
    <p> <img src="documentation/screenshots/jshint.jpg"></p>      
-   [Python Validator](http://pep8online.com/)
    No issues were found on this check.
    <p> <img src="documentation/screenshots/pep8.jpg"></p>   
    

## Autoprefixer CSS Online

This was used to parse CSS and add vendor prefixes in order to ensure that the CSS styling works properly across all 
browsers. I have added the below header to my CSS styles sheet in order to show this:
<p> <img src="documentation/screenshots/css-prefix.jpg">  </p>

## Lighthouse

<p >Desktop<img src="documentation/screenshots/lighthouse.jpg">
Mobile<img src="documentation/screenshots/lighthouse-mobile.jpg"></p>

From Chrome Developer Tools, this Lighthouse score is based on the homepage while being viewed on desktop and mobile. I worked hard on
ensuring high scores across the site in particular by putting every image through [Tiny PNG](https://tinypng.com/), and improving 
SEO scores by adding a meta description to each page. The lower 'Best Practices' score is primarily due to the JavaScript
libraries being used for the site, specifically JQuery.

## EmailJS API

I have tested this manually on every page to ensure that the contact form is being sent through successfully. You can see this 
here:

<p> <img src="documentation/screenshots/emailjs.jpg">  </p>


## Testing User Stories from User Experience Section

-   #### First Time Visitor Goals - I want to:

    1. Quickly understand the service being provided by Tips and how I can interact with the service.
        - *XXXX*
    2. Be able to easily browse the various 'tips' in Stockholm and find something that interests me.
        - *XXXX*
    3. Be able to register to the website and add my own 'tips'.
        - *XXXX*
    4. Be able to comfortably navigate throughout the site between my own tips and other users'.
        - *XXXX*
    5. Get an instant first-impression that this is a professional, modern and up-to-date site with good UX.
        - *XXXX*


-   #### Frequent User Goals - I want to:

    1. Easily be able to check if any new tips have been added that may interest me.
        - *XXXX*
    2. Login to the account that I had previously set up and see my own submissions.
        - *XXXX*
    3. Add more tips to the website that I may not have done already.
        - *XXXX*
    4. Edit my own tips.
        - *XXXX*
    5. Delete any tips that are no longer relevant.
        - *XXXX*

## Fixed Bugs
After deployment, I found multiple bugs that needed addressing:

1. Bug 1
    - *Solution 1*
2.  Bug 2
    - *Solution 2*  
3.  Bug 3
    - *Solution 3*

## Known Outstanding Bugs

1. Bug 1
    - *Solution 1*
2.  Bug 2
    - *Solution 2*  

 
## Further Testing

- Throughout the development process, I used the Chrome Developer Tools, specifically for using the console.log function to test 
JavaScript code and also for the various CSS designs, particularly around responsiveness. On especially narrow devices < 300px, some images were 
larger than the width, however I felt this had no effect on UX.
- The website has been tested on various desktop browsers such as Google Chrome, Firefox, Safari and Edge, as mentioned above, I used 
the CSS tool Autoprefixer Online to help with this. 
- Each link has been tested across the site to ensure everything was linked correctly.
- Friends and family were also asked for advice particularly on layout and in order to ensure that the site was being tested across 
various devices. 


# Deployment

The site was published in GitPages using the following steps:
1. First, all code was written on the IDE Gitpod and was then pushed to GitHub using the 'git push' entry in the terminal, where it is now stored in [my repository](https://github.com/adamdelancey/ms2-ashtreeestates).
2. To push the site live, under the Settings section of the repository I selected, I scrolled down to where it says 'GitHub Pages'.
3. I then selected 'Master Branch' under Source and then the page automatically refreshed.
4. This created the URL which can be viewed [here](https://adamdelancey.github.io/ms2-ashtreeestates/index.html).
5. The site was then found by scrolling back to the "GitHub Pages" section where you can see the following:
<p><img src="documentation/screenshots/githubpages.jpg"></p>



To access the code, it can be run locally through a download or cloned.

Initially, I used "git commit" and "git push" for every major change, then at later stages used these functions when de-bugging or making minor editing changes to ensure the live version was the most recent version, as well as to avoid losing any work.

# Credits

- All professional images have been sourced from a combination of [Unsplash](https://unsplash.com/s/photos/bristol) and [Pixabay](https://pixabay.com/).
- All photos related to the properties have been sourced from Ash Tree Estates.
- The Navbar, Forms, Carousels and Cards have been chosen from Bootstrap templates and adapted using CSS.
- Initial instructions for setting up the Google Maps API were taken from the relevant lesson from the [Code Institute](https://codeinstitute.net/).
- Similarly, setting up the EmailJS API was also taken from the relevant lesson from the [Code Institute](https://codeinstitute.net/).
- Instructions for setting up the getNearbyPlaces function was taken from the [Google Codelabs Developer lessons](https://codelabs.developers.google.com/codelabs/google-maps-nearby-search-js#1)
- [Stack Overflow](https://stackoverflow.com/) and [W3C Schools](https://www.w3schools.com/) were used for occasional debugging or issues where I could not initially work out the solution myself.
- Fonts are from [Google Fonts](https://fonts.google.com/) and icons from [Font Awesome](https://fontawesome.com/).


# Acknowledgements

- My mentor, Aaron Sinnott, for his support and mentorship during the project.
- The peer-code-review channel on Slack and their trusty channel leads for both code and design tips.
- Friends and family for testing the site on their various devices.
