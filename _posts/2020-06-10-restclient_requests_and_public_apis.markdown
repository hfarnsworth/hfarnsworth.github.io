---
layout: post
title:      "RESTClient requests and public APIs"
date:       2020-06-10 22:44:33 +0000
permalink:  restclient_requests_and_public_apis
---


<!-- wp:cover {"url":"https://smushcathome.files.wordpress.com/2019/12/coverphoto-1.jpeg","id":22,"hasParallax":true,"gradient":"cool-to-warm-spectrum","className":"alignfull is-style-default"} -->
<div class="wp-block-cover has-background-dim has-parallax has-background-gradient alignfull is-style-default" style="background-image:url(https://smushcathome.files.wordpress.com/2019/12/coverphoto-1.jpeg)"><span aria-hidden="true" class="wp-block-cover__gradient-background has-cool-to-warm-spectrum-gradient-background"></span><div class="wp-block-cover__inner-container"><!-- wp:paragraph {"align":"center","placeholder":"Write title…","fontSize":"large"} -->
<p class="has-text-align-center has-large-font-size">Creating the Marvel Mission Maker</p>
<!-- /wp:paragraph --></div></div>
<!-- /wp:cover -->

<!-- wp:paragraph -->
<p>At Flatiron we have a very specific path to becoming a full-stack web developer.  In module 2 we created our own web app to apply everything we learned about Rails up to that point in the program.  As such I took it upon myself to use the project as an opportunity to learn more about APIs and how to use them.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>My Project</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>My first project was a bit more than I could handle.  It was a "social app" where writers would pitch scripts by adding them to a database in which "producers" could buy them and move them into production.  As a result, I decided to do something relatively simple, but I always want to learn, so I decided to model a domain which would allow me to use some kind of API.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I decided to make a simple domain with some join classes.  I decided to use superheroes as there would certainly be some kind of public API for me to use.  Originally I was going to use <a href="https://superheroapi.com/">superheroapi</a>, but I ended up going directly to Marvel so that I could get some hands-on experience using a corporate, public API.  It was fairly straightforward but it was new territory for me.  First, I had to create a developer account at Marvel.com.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":82,"sizeSlug":"medium"} -->
<figure class="wp-block-image size-medium"><img src="https://smushcathome.files.wordpress.com/2020/01/screen-shot-2020-01-15-at-12.47.12-pm.png?w=300" alt="" class="wp-image-82"/><figcaption>This is a website</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>In my web app project, a user can login in order to create "missions" with which to send "teams" of "superheroes."  There's not much going on here, but it helped me get to grips with building a rails app from the ground up, and the biggest hurdle was learning how to use the official Marvel API to seed my data with accurate, official information.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>In order to use the Marvel API, I thought that all I had to do was send my developer API key with my get request.  However, I received an error, which told me they were expecting a hash, just an extra level of security.  The url format for the hash is like so.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>https://gateway.marvel.com/v1/public/characters?name="name"&amp;ts="time-stamp"&amp;apikey="my api key"&amp;hash="a required hash".</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>This url above acts as a url address whose data can be transformed into JSON, for use in my code.  Originally I thought it was just my apikey, as it was shown in the interactive API portal, however it told me I was missing a hash.  Looking at the documentation, I would need to concatenate a "time-stamp"(any value actually) to my APIkey, and then create a hash.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Hash it out</h2>
<!-- /wp:heading -->

<!-- wp:media-text {"mediaId":85,"mediaType":"image"} -->
<div class="wp-block-media-text alignwide is-stacked-on-mobile"><figure class="wp-block-media-text__media"><img src="https://smushcathome.files.wordpress.com/2020/01/screen-shot-2020-01-15-at-1.16.11-pm.png?w=1024" alt="" class="wp-image-85"/></figure><div class="wp-block-media-text__content"><!-- wp:paragraph {"placeholder":"Content…","fontSize":"large"} -->
<p class="has-large-font-size">Ruby can use this Digest method to give me hash key.  Then all I have to do is send the ts= value, along with my APIkey= value, and the Hash= value, as part of the URL address of my request.  The ts must be sent so they know how the hash has been encrypted.  Now I had my json data to play with!</p>
<!-- /wp:paragraph --></div></div>
<!-- /wp:media-text -->

<!-- wp:paragraph -->
<p>I started to seed my data.  There actually wasn't a whole lot, but the Marvel API did give me a name, an image url, and a description.  So I used these datapoints to create my superhero profile pages.  I ended up creating various as I was going along so that my database seeds could hopefully lead to creating a method of pulling directly from the database.  Originally, I was planning to just save all the info to my database, but they have a limit on how much you can get at a time.  Which was fine, it gave me a creative challenge.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I seeded my data with the Avengers and Defenders superheros and teams, with the ability to send them on missions using a form.  You could assign existing heroes to teams and existing teams to missions that you create.  Very simple but interesting enough.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Bonus Points</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>After getting all the requirements in for Presentation Day, logins, passwords, user-locked access(my forms), I decided I might try to put my methods to work and see if I couldn't pull data live from the API through my web app.  I thought if I could just pull in data from a form, encode it into URI-friendly text, then I should be able to create superhero objects from the API instead of requiring or allow users to add their own superheroes.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I played it with it for a while but couldn't seem to get it working.  So after I had turned my project in, I asked my instructor to take a look and see if he couldn't help me get it working.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":89,"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://smushcathome.files.wordpress.com/2020/01/screen-shot-2020-01-15-at-1.40.22-pm.png?w=1024" alt="" class="wp-image-89"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>As I was describing the problem I tried clicking one of the links and then...</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":90,"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://smushcathome.files.wordpress.com/2020/01/screen-shot-2020-01-15-at-1.41.34-pm.png?w=1024" alt="" class="wp-image-90"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I did a triple take!  It worked...  Somehow I had gotten it working without actually noticing I had been successful.  Just another skill my instructor had, I had tried to show him some broken feature during my first week and it was actually working too...  I successfully had my form using characters?nameStartsWith= to return usable name strings from the Marvel API.  Then I was successfully using the link to send name to my create method, which seed the superhero's info with data straight from the API.  And it worked right in front of my eyes!</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://media.giphy.com/media/XSvEiht5eLeSI/giphy.gif" alt="Image result for double take gif"/><figcaption>Sometimes, unbelievably, stuff just works</figcaption></figure>
<!-- /wp:image -->
