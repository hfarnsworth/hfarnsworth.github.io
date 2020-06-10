---
layout: post
title:      "Dr. Sluglove"
date:       2020-06-10 22:43:28 +0000
permalink:  dr_sluglove
---


<!-- wp:cover {"url":"https://smushcathome.files.wordpress.com/2019/12/coverphoto-1.jpeg","id":22,"hasParallax":true,"gradient":"cool-to-warm-spectrum","className":"alignfull is-style-default"} -->
<div class="wp-block-cover has-background-dim has-parallax has-background-gradient alignfull is-style-default" style="background-image:url(https://smushcathome.files.wordpress.com/2019/12/coverphoto-1.jpeg)"><span aria-hidden="true" class="wp-block-cover__gradient-background has-cool-to-warm-spectrum-gradient-background"></span><div class="wp-block-cover__inner-container"><!-- wp:paragraph {"align":"center","placeholder":"Write title…","fontSize":"large"} -->
<p class="has-text-align-center has-large-font-size">Or How I Learned to Stop Worrying and Love Ruby on Rails</p>
<!-- /wp:paragraph --></div></div>
<!-- /wp:cover -->

<!-- wp:paragraph -->
<p>There's a Domain that we've come back to time and time again in my early weeks at Flatiron.  It makes sense, there's a few models we come back to often because they are common formats for websites, apps or social networks.  Things like Twitter and blog posting come up as models quite often in our labs and homework.  This one we've done a few times, this time it was called Playlister and I was doing it with Sinatra after learning how to use Rack earlier in the week to set up a web server.  The model is pretty straightforward.  You've got Artists, Songs, and Genres.  This time it was specifically that Songs were treated as a join class between Artists and Genres.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"width":314,"height":314} -->
<figure class="wp-block-image is-resized"><img src="https://res.cloudinary.com/teepublic/image/private/s--E_FEtwoW--/c_crop,x_10,y_10/c_fit,w_830/c_crop,g_north_west,h_1038,w_1038,x_-104,y_-155/l_upload:v1565806151:production:blanks:vdbwo35fw6qtflw9kezw/fl_layer_apply,g_north_west,x_-215,y_-266/b_rgb:0f7b47/c_limit,f_jpg,h_630,q_90,w_630/v1563567218/production/designs/5362422_1.jpg" alt="Image result for slugs tiny toons" width="314" height="314"/><figcaption>I finally have an excuse to reference this amazing gag from Tiny Toons.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Starting out, this lab wanted us to define 2 methods.  A #slug method which would turn the song's name into a slug.  This instantly became something interesting to me as its usage is very obvious.  Even still we often use url pointers which show an instance's information using the id number.  This is very useful in action, but I can see why it's not a very practical idea in a real-world situation.  So this slugify thing was a great thing to remember, and something that was great to get working, though it took some time and effort.</p>
<!-- /wp:paragraph -->

<!-- wp:media-text {"mediaId":60,"mediaType":"image","mediaWidth":42} -->
<div class="wp-block-media-text alignwide is-stacked-on-mobile" style="grid-template-columns:42% auto"><figure class="wp-block-media-text__media"><img src="https://smushcathome.files.wordpress.com/2019/12/screen-shot-2019-12-29-at-7.47.15-pm.png?w=810" alt="" class="wp-image-60"/></figure><div class="wp-block-media-text__content"><!-- wp:paragraph {"placeholder":"Content…","fontSize":"normal"} -->
<p class="has-normal-font-size">The artist#slug method was pretty easy to figure out.  There's a ruby method call #parameterize, which transforms a string into nothing but lowercase letter words, separated by hyphens instead of spaces.  It was the next method that caused me some trouble.  Eventually I came up with a fairly elegant solution.  Song.find_by_slug worked by going through every instance and parameterizing(slugifying) the name value and then comparing it against the slug that was fed in as an argument.  If it finds a match it will return that Song instance.  I was hoping to use a find or find_by method, which may or may not be faster, I only needed to find one match, not to look through every single one, but at least my solution worked.</p>
<!-- /wp:paragraph --></div></div>
<!-- /wp:media-text -->

<!-- wp:paragraph -->
<p>While this took some time, it was great to see it working.  Now, instead of using songs/id as a url pointer to show my Song instance's information, I was able to use a url based on the name of the Song instead, which is a lot more real-world friendly, and a much nicer url to see in your address bar when loading up a dynamic page.  Getting this all working was a great feeling that made me feel like I was finally learning valuable techniques that I would want to remember when writing code on a real project.</p>
<!-- /wp:paragraph -->

<!-- wp:media-text {"mediaPosition":"right","mediaId":59,"mediaType":"image"} -->
<div class="wp-block-media-text alignwide has-media-on-the-right is-stacked-on-mobile"><figure class="wp-block-media-text__media"><img src="https://smushcathome.files.wordpress.com/2019/12/screen-shot-2019-12-29-at-7.48.56-pm.png?w=742" alt="" class="wp-image-59"/></figure><div class="wp-block-media-text__content"><!-- wp:paragraph {"placeholder":"Content…","fontSize":"normal"} -->
<p class="has-normal-font-size">Next we had to seed the data using a premade Object class called LibraryParser.  The project file had about 100 mp3 files which this object would go through in order to generate an ActiveRecord database for use in this lab.  We were supposed to figure out how to use it by looking at the code in order to figure out the proper way to use it.  I kinda cheated a little, as we were told to write a seed file which used LibraryParser.  However, I just used the console in Ruby to run LibraryParser the one time, and from there I had a database to dynamically generate my Domain website.<br>To get it working I just saved a LibraryParser.new to a variable which I named lp. Then I ran lp.parse and it populated my database based on the mp3s provided.</p>
<!-- /wp:paragraph --></div></div>
<!-- /wp:media-text -->

<!-- wp:paragraph -->
<p>The rest of my day I was figuring out how to get all my urls pointing to each other so that you could navigate to a Genre from a Song's show page and then from that Genre's page, see all the songs which existed in that Genre.  It took most of my day but I was able to get everything up and running and it was a pretty good feeling.  The website felt good even if it didn't look great.  It lead me everywhere from everywhere else.  I had a website which was generating pages dynamically from a SQL database.  I was using ActiveRecord associations to populate information to be displayed in the form of a website and suddenly things were starting to make sense.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":67,"width":419,"height":474,"sizeSlug":"large"} -->
<figure class="wp-block-image size-large is-resized"><img src="https://smushcathome.files.wordpress.com/2019/12/screen-shot-2019-12-29-at-7.48.06-pm.png?w=905" alt="" class="wp-image-67" width="419" height="474"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>My website worked and you could get around quickly.  I was able to generate links by using the #slug and .find_by_slug methods.  I didn't get to everything in this lab, we still needed to add a form that would allow us to add our own information to the database using the website and I didn't get far enough to get it working.  I was merely happy to have technically created a website built out of over 100 pages within the span of one day.  Using Ruby to create it was also kind of a surprise to me, but it was great to see it in action.  It was also great to put to use everything I had been learning.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>And then I found Rails</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Or rather, it found me.  We had been building up to rails in a week of quick trainings.  We used ActiveRecord, then Rack, then Sinatra, all for about a day or 2.  After that we had the weekend to crank on Rails, which was putting to work everything we had learned.  I knew it was important and spent all weekend on those labs, to prepare myself for the next week of intense training, which would build up to a coding challenge the upcoming friday.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Rails was great.  We could generate a lot of files automatically, we could create routes for the most commonly used actions one could want to use for their models.  By default it gives you your most basic CRUD actions as well as a show all in the form of an Index.  Basically, everything we had been learning in Rails, piece by piece, was to set us up for Rails and to have a full understanding of what Rails was doing, and how.</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://i.stack.imgur.com/RyM1b.png" alt="Image result for http actions"/><figcaption>CRUD actions</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>These weekend Rails labs culminated in something familiar.  It wasn't called Playlister, but it sure quacked like a duck.  It was a Song/Genre/Artist model once again.  The lab didn't require slugs, but it did have us starting from scratch using our newly-learned Rails knowledge.  In about an hour, I had duplicated all my work from literally 3 days prior.  I had generated a dynamic website, including the forms this time, with dynamically generated links and pages using Rails all in an hour instead of what had just taken me all day.  It felt amazing.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The rest of the week threw me back into the depths of doubt, trying to wrap my head around more complex forms, errors, validations, and more.  But for a day I felt great and I hope I'll continue to have these "aha" moments in my bootcamp and coding career experience.  In less than 2 months I've gone from knowing practically nothing about code to being able to write code designed for the purposes of real-world solutions and I'm excited to expand my abilities as I continue this course.</p>
<!-- /wp:paragraph -->
