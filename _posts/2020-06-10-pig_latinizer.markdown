---
layout: post
title:      "Pig Latinizer"
date:       2020-06-10 22:41:03 +0000
permalink:  pig_latinizer
---


<!-- wp:cover {"url":"https://smushcathome.files.wordpress.com/2019/12/coverphoto-1.jpeg","id":22,"hasParallax":true,"dimRatio":30,"gradient":"cool-to-warm-spectrum","className":"alignfull"} -->
<div class="wp-block-cover has-background-dim-30 has-background-dim has-parallax has-background-gradient alignfull" style="background-image:url(https://smushcathome.files.wordpress.com/2019/12/coverphoto-1.jpeg)"><span aria-hidden="true" class="wp-block-cover__gradient-background has-cool-to-warm-spectrum-gradient-background"></span><div class="wp-block-cover__inner-container"><!-- wp:heading {"align":"center","level":1} -->
<h1 class="has-text-align-center">the Pig Latinizer</h1>
<!-- /wp:heading --></div></div>
<!-- /wp:cover -->

<!-- wp:paragraph -->
<p>This is the first blog post to commemorate my journey through the world of programming.  I am currently in week 4 as a new developer, taking the Immersive Engineering Program at Flatiron School.  It has been a rollercoaster so far, every day brings new challenges and obstacles and being able to grow and learn is a fresh experience that seems to be an active part of this new career path I've decided to take on.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I overheard someone say, "what is the point of this?"  He was actually asking about why anyone would ever need a pig latinizer.  Such a serious question.  I think sometimes as programmers we may never fully understand what it is we are trying to do or why, but our employers decide that, not us...  However, it kinda gave me a heads-up of what I would be dealing with as I hadn't yet run into the lab he was talking about.</p>
<!-- /wp:paragraph -->

<!-- wp:media-text {"mediaPosition":"right","mediaId":25,"mediaType":"image"} -->
<div class="wp-block-media-text alignwide has-media-on-the-right is-stacked-on-mobile"><figure class="wp-block-media-text__media"><img src="https://smushcathome.files.wordpress.com/2019/12/giphy.gif?w=320" alt="" class="wp-image-25"/></figure><div class="wp-block-media-text__content"><!-- wp:paragraph {"placeholder":"Content…","fontSize":"large"} -->
<p class="has-large-font-size">Sometimes we just gotta do what we're told, just so we can learn something, even if it doesn't make sense.</p>
<!-- /wp:paragraph --></div></div>
<!-- /wp:media-text -->

<!-- wp:paragraph -->
<p>In our current module we are ramping up to Ruby on Rails, but before we can do that, we are using Sinatra to create dynamic web routes and forms to generate content.  We combine this with ActiveRecord in order to manage our Ruby Objects for us,  organizing them into SQL tables to track everything and create the relationships we need.  This particular lab though, is just about creating a website where we take a line, turn it into Pig Latin, and generate the website on the other end.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":26,"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://smushcathome.files.wordpress.com/2019/12/bewitchedremorsefulfattaileddunnart-size_restricted.gif?w=517" alt="" class="wp-image-26"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>So, really, this lab wasn't much about forms or websites, at all.  It wasn't really teaching us that, and more about taking the opportunity to get us to brush up on our Ruby..</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Back to the Mines!</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>It actually didn't take long for me to come up with a solution for this.  My solution basically involved a lot of breaking strings up, running some iterators, breaking them up more, and doing some checks on the letters at the beginning of the words, before chopping them up and then putting it all back together.  It was funny though, as I looked around on Google for a way to detect if a character was a vowel, I started to realize the pig latinizer was a fairly common test that beginner programmers seem to have to deal with.  In less than an hour I had written my code.  At first I was using =~ regexp but I'm not all that familiar yet, so I fell back on to something that was more inside my realm of understanding. </p>
<!-- /wp:paragraph -->

<!-- wp:media-text {"mediaId":31,"mediaType":"image"} -->
<div class="wp-block-media-text alignwide is-stacked-on-mobile"><figure class="wp-block-media-text__media"><img src="https://smushcathome.files.wordpress.com/2019/12/screen-shot-2019-12-12-at-7.42.15-pm.png?w=742" alt="" class="wp-image-31"/></figure><div class="wp-block-media-text__content"><!-- wp:paragraph {"placeholder":"Content…","fontSize":"large"} -->
<p class="has-large-font-size">The regexp thing I tried to use was returning 0, which I thought would be the reason things weren't working.  I instead chose to use .include? against an array of vowels.  I also had early issues with rspec looking for very specific ways of running this code on a string(we were to create a PigLatinizer Object, then to actually run it, make an instance of it, and run #piglatinize() on that instance with the string as an argument).</p>
<!-- /wp:paragraph --></div></div>
<!-- /wp:media-text -->

<!-- wp:paragraph -->
<p>I jumped through all these hoops, as necessary, and I still couldn't get things to run correctly.  Truly there was a reason we were going back to Ruby to try some weird stuff, because we needed to make sure we could still think in these terms after learning all the new things about SQL databases and now dynamic webpages.  I put a pin in it and moved on to the next lab, knowing I could ask about it the next morning. </p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>The Next Morning...</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>For a minute, I was looking at it with one of the coaches, and we all tried to point to where things seemed to be going wrong.  I had even run through every step itself in the console(which actually did help me get more familiar with running things live) but everything acted as I expected.  She had to go to a meeting, and it was then that I asked out-loud what I thought was a very stupid question.  </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"style":{"color":{"text":"#38492c"}}} -->
<p class="has-text-color" style="color:#38492c">"What does map do again?"  My instructor was sitting across from me, and responded, "spits out a new array."  It completely dawned on me.  If map is spitting out a new array, I need to grab it!  These are the moments that make me feel like I'm a real programmer.  I'm sitting here, watching others struggle with the very idea of pig-latinizing words, and I'd forgotten that in order for map to do anything I had to save it to a variable.  You get so used to things like Ruby's implicit returns you forget where the "last line" is and start to think map is "doing the work" for you.  I guess I was doubly complacent since I was relying on the slice! method to chop the beginning letters of my words and creating suffixes, as in "ill-way, the an-may, on the ance-day oor-flay."  Which, in the case of slice!, actually does alter the original array, at the same time as it gives you a new one.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>So, what did I learn?  Don't be afraid to ask stupid questions out loud, you may get a stupid answer, but you never know where your eureka moment will come from.  Even if you don't really have much trouble with the "hard stuff."</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":32,"width":310,"height":310,"sizeSlug":"large"} -->
<figure class="wp-block-image size-large is-resized"><img src="https://smushcathome.files.wordpress.com/2019/12/illway-the-anmay.jpg?w=600" alt="" class="wp-image-32" width="310" height="310"/><figcaption>I also learned, I will never forget the lyrics to this song...</figcaption></figure>
<!-- /wp:image --># Enter your title here

The content of your blog post goes here.
