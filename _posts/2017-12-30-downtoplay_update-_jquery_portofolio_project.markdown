---
layout: post
title:      "DownToPlay Update- JQuery Portofolio Project"
date:       2017-12-30 18:36:06 -0500
permalink:  downtoplay_update-_jquery_portofolio_project
---


Another one knocked off the list! This project was not as difficult as I was expecting, especially after the hard time I had when starting the JS/JQuery sections. When I first started the JavaScript section I was extremely discouraged and frustrated, because the syntax was so much more different than Ruby (It took me about 15 minutes during a lab to realize that an if statement conditional needed to be wrapped in parenthesis’). I had to re-read every lesson and watched countless YouTube videos, but I can say I finally ‘understood’. I still have a lot to learn in JS, but I gained enough knowledge to complete this project.

The updates in my project consist of 3 parts:

1. User can now view their planned games in their profile page, without a link redirecting to a different page.

2. A ‘Quick Game Form’ was added to plan a game instantaneously and have it render to the game list without reloading the page.

3. When viewing a planned game. Users now have a “Next” button to cycle through all of their planned games.

![](https://cdn-images-1.medium.com/max/800/1*LPDFCH0dew7nC7igf4BoLA.png)

                           *Form and Table rendered after clicking “Planned Games.*

All AJAX calls create a Game JS object whose attributes are then appended to the DOM.

I’d say the most difficult part the project, was posting to the database. I kept getting an 400 Bad Request error, I figured out that this was because my form was not submitting with the game strong_params. After hours and hours of research I still could not get it to work. Then I had a Eureka moment! I was curious to see what the quick-form params looked like at submission instead of continuously trying to wrap the serialized form data in “game{}” with no luck. After placing a binding.pry in the create action and submitting the form, I got the following:

``` "#"=>{"planner_id"=>"1","title"=>"test","location"=>"park".......} ```

As soon as I saw that I knew how to fix it. I went back to the quick game form and saw this:

```<%= form_for '#' do |f|%>```

Once I change the ‘#’ to ‘game’, I was able to successfully post to the database.

Check out DownToPlay here: [DownToPlay](https://github.com/Booligan/down_to_play_rails)
