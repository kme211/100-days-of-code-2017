# 100 Days Of Code - Log

### Day 1: Thursday, January 5, 2017

**Today's Progress:** Separated frontend from backend. React up and running. Haven't tested backend routes yet since separation.

**Thoughts:** Still not sure about how I'm going to design the structure of the
Canvas with React. I also need to test saving the Canvas data as the Buffer
file type ([possible solution](http://stackoverflow.com/questions/22228552/serialize-canvas-content-to-arraybuffer-and-deserialize-again))
in NodeJS. Previously I was using [HTMLCanvasElement.toDataURL()](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/toDataURL)
to save drawings as a data URI and saving those to MongoDB.

**Link to repo:** [Exquisite Corpse (collaborative drawing app)](https://github.com/kme211/exquisite-corpse)

### Day 2: Friday, January 6, 2017

**Today's Progress:** Setup Mocha and Supertest in backend and added a test to test `drawings/new` route.

**Thoughts:** Still need to add error handling to routes.

**Link to repo:** [Exquisite Corpse (collaborative drawing app)](https://github.com/kme211/exquisite-corpse)

### Day 3: Saturday, January 7, 2017

**Today's Progress:** Added more backend tests. Added CORS to Express. Wrote a
util for making sure an object has required properties and that the props are
the correct type. Converted Canvas imageData to binary using method [here](http://stackoverflow.com/questions/22228552/serialize-canvas-content-to-arraybuffer-and-deserialize-again) but connection timed out while trying to save it to MongoDB.

**Link to repo:** [Exquisite Corpse (collaborative drawing app)](https://github.com/kme211/exquisite-corpse)

### Day 4: Sunday, January 8, 2017

**Today's Progress:** Used what I learned in [Javascript30](https://javascript30.com/)
to make a low FODMAP food type ahead search app.

**Thoughts:** I want to make this a progressive web app and maybe have it work
offline.

**Link to repo:** [Is it high FODMAP? Git repository](https://github.com/kme211/fodmapr)

### Day 5: Monday, January 9, 2017

**Today's Progress:** Used [sw-precache](https://github.com/GoogleChrome/sw-precache)
to add offline capability to my fodmapr app. I also attempted to deploy to
[Netlify](https://www.netlify.com) because service workers will only work on a
secure site and Surge's SSL doesn't seem to be working. I also created an icon
for it but I'm not in love with it.

**Thoughts:** When using a service-worker it won't work if you try to use in a
subdirectory. I used gulp-connect to serve the files with `app` as the root.

**Link to repo:** [fodmapr Git repository](https://github.com/kme211/fodmapr)

### Day 6: Tuesday, January 10, 2017

**Today's Progress:** Secured fodmapr on Netlify so that the service-worker would work.
Updated the homepage layout a little it. Troubleshot problems with livereload
(it was the service worker's fault).

**Thoughts:** I probably want to start using a CSS pre-processor soon.

**Link to demo:** [fodmapr progressive web app](https://fodmapr.net/)

**Link to repo:** [fodmapr Git repository](https://github.com/kme211/fodmapr)

### Day 7: Wednesday, January 11, 2017

**Today's Progress:** Created a Grid component in my exquisite-corpse drawing app
so that users will be able to specify how many sections will be in the completed
drawing. Attempted to figure out Canvas scaling solution for different sized
devices.

**Thoughts:** I need to figure out how to scale the drawings to be 500x500 (or
  whatever I decide) before saving them as an image (using [HTMLCanvasElement.toDataURL()](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/toDataURL) since I decided binary wasn't the way to go) since users will be on
  different sized devices. I think when the drawing has all the completed sections
  that I should use some sort of job queue ([monq](https://www.npmjs.com/package/monq))
  to piece the sections together, save the completed drawing, delete the
  sections and then email the contributors.

### Day 8: Thursday, January 12, 2017

**Today's Progress:** Created a `Saved` component to let the user choose which
section to pass on to the next person.

**Thoughts:** I experienced a lot of issues which this one. I think the `Grid`
component is getting kind of complex and I should start trying to keep util type
of functions outside of components and write tests for them.

**Link to repo:** [Exquisite Corpse (collaborative drawing app)](https://github.com/kme211/exquisite-corpse)

### Day 9: Friday, January 13, 2017

**Today's Progress:** Installed Jest and wrote a few tests. Very easy to get
setup with. I also included an object in my `package.json` file so that Jest knows
to look for stuff in the `src` directory. I haven't tested to make sure it works
yet though.

```
"jest": {
    "moduleDirectories": [
      "src",
      "node_modules"
    ]
  }
```

I also spent some time fixing the `Saved` component and styling it. It needs to
be renamed though.

**Thoughts:** I should probably make it so that when a user hits a section URL,
the backend is pinged so that the section can be marked as "claimed". I'm just
imagining people posting URLs to Twitter... You don't want multiple people working
on the same section and then some user(s) not being able to save because it was
already saved by someone else.

**Link to repo:** [Exquisite Corpse (collaborative drawing app)](https://github.com/kme211/exquisite-corpse)

### Day 10: Saturday, January 14, 2017

**Today's Progress:** Worked on making some re-usable components including a text
input, a form label and a modal. I also made a `Welcome` page to gather user data
and save it to `localStorage`. The app will redirect users to this page if no
app data can be found in the `localStorage` when the app mounts.

I plan on also saving the drawing IDs for the drawings that the user has worked
on in `localStorage` and then they will be able to see when the drawings are
complete. I also want to notify users by email when drawings are complete.

**Thoughts:** I need to make sure users can update their data if they'd like. I
can probably re-use the welcome form component.

**Link to repo:** [Exquisite Corpse (collaborative drawing app)](https://github.com/kme211/exquisite-corpse)

### Day 11: Sunday, January 15, 2017

**Today's Progress:** I managed to make a backend job to piece together the
drawing sections and save them to disk when all the sections have been completed.
I still need it to delete the `canvasData` in mongo and let the user know
that the drawing is complete by email or sockets.io or both. I used this [repo](https://github.com/northernv/mastering-mean/blob/video-8-2/backend/worker.js)
as a guide to creating the job using [monq](https://www.npmjs.com/package/monq).

**Thoughts:** I want to upload the images to [cloudinary](https://www.npmjs.com/package/cloudinary) instead of keeping them
on my backend server.

**Link to repo:** [Exquisite Corpse (collaborative drawing app)](https://github.com/kme211/exquisite-corpse)

### Day 12: Monday, January 16, 2017

**Today's Progress:** Did my first #dailycssimages challenge and made some minor
enhancements to [fodmapr](https://github.com/kme211/fodmapr/pull/3).

**Thoughts:** I need to get the fodmapr livereload thing working. I thought I had
it working but still seems to have trouble.

**Link to demo:** [CSS Zombie](http://codepen.io/kme211/pen/dNpEYG)

### Day 13: Tuesday, January 17, 2017

**Today's Progress:** Added functionality to save user drawings to localStorage
and then show them on the home page.

### Day 14: Wednesday, January 18, 2017

**Today's Progress:** Added cloudinary so that the `process-drawing` job
workflow is now like this:

- Resize and piece together sections of drawings
- Save drawing to Node server
- Upload drawing to cloudinary
- Remove drawing from Node server
- Update drawing data in MongoDB
  - Remove image data from `canvasData`
  - Add URL for cloudinary image

I also now show the completed images on the home page.

### Day 15: Thursday, January 19, 2017

**Today's Progress:** Fixed backend tests. Added Morgan logger to backend. Started
changing how I deal with `canvasData`. It's getting harder to just work on this project
(exquisite-corpse) for just an hour. The problems I'm facing need a lot more attention
and time than I have during my lunch hour so I might have to start working on
smaller projects during the week and work on exquisite-corpse on the weekends.

### Day 16: Sunday, January 22, 2017

**Today's Progress:** Missed two days for no real good reason, however I did get
a lot of cleaning done around the house. I did manage to partially get [Auth0](https://auth0.com/)
setup today. I used a lot of code from this [tutorial](https://medium.com/javascript-scene/passwordless-authentication-with-react-and-auth0-c4cb003c7cde#.k80zo7bgy). I need to set up the callback URL, I believe. I first tried using [Passwordless](https://github.com/florianheinemann/passwordless)
but the [example](https://github.com/billstron/passwordless-stateless-angular) code was confusing because it didn't look like it was meant for
production but I could be wrong.

### Day 17: Monday, January 23, 2017

**Today's Progress:** Instead of working on authentication today, I figured I
should try to fix all the bugs in my current code so I can get a build on
Netlify (frontent)/Heroku (backend). I have the borders working now. They will
need further testing though.

**Thoughts:** I'm wondering if I should have the images overlap like I used to
have them. I'm worried that users will draw inside the borders but not go all
the way to the edge and then the pieced together drawing won't look seamless. I
think I removed it because I thought it was getting in the way, meaning that if
you drew over it, it sometimes tried to drag the image. I should try to figure
out if I can grab the canvas data from just the edges (25px) and then insert that
data into the other section.

### Day 18: Tuesday, January 24, 2017

**Today's Progress:** I resisted the temptation to work on Exquisite Corpse today
and worked on creating a weather app using React. I'm trying to learn how to
utilize [React Motion](https://github.com/chenglou/react-motion)
and this [codepen by Sarah Drasner](http://codepen.io/sdras/pen/ZWeJem?editors=1010) was really helpful. I still need to create a toggle or some way to change the temperature
scale. I think it would also be cool to have some CSS images in the background.
It would be a good opportunity to work on that skill.

**Link to demo:** [Weather App](http://codepen.io/kme211/pen/zNoave)

**Thoughts:** Here are some of my thoughts regarding my Exquisite Corse app.

- Do I want to have a `Section` schema?
- If I do want to make a `Section` schema...
  - What all is in the schema?
    - `_id`
    - contributor
    - image data
    - partial image data from the bordering sections? or would the server get those
    parts when it recieves a request for the section?
- What's the best way to store/find the user's drawings (ones they have contributed to)?
  - Do I store user data such as `drawings` in MongoDB? If so, how would I do that while
  using Auth0?
  - Or do I add `contributors` to the `Drawing` schema

### Day 19: Wednesday, January 25, 2017

**Today's Progress:** I worked a little on my [React weather app](http://codepen.io/kme211/pen/zNoave)
and made a CSS [elephant](http://codepen.io/kme211/pen/vgJMRZ) for #dailycssimages.
I even added a little trunk swinging action. I don't have much experience with animation in CSS
so it's good to get some practice.

### Day 20: Thursday, January 26, 2017

**Today's Progress:** I wanted to add some particle effects to my weather app so
I found a repo called [react-snowfetti](https://github.com/danillouz/react-snowfetti)
I could have just dropped into my project but I thought it would be
fun to write my own React component using react-snowfetti as a guide. It turned out
pretty nice and I really didn't have to write all that much code. Mine isn't advanced
as react-snowfetti but it does the job. Right now it just does snow but I want to
add rain to it and maybe the rain can have different levels of intensity depending
on the [weather code](http://openweathermap.com/weather-conditions) that's
received from the [OpenWeatherMap API](http://openweathermap.com/current).

**Link to demo:** [Snow particles](http://codepen.io/kme211/pen/XpeqjG)

### Day 21: Friday, January 27, 2017

**Today's Progress:** I worked on making the rain in my [`Particles`](http://codepen.io/kme211/pen/XpeqjG) component look
more realistic. I still have a lot to learn about the Canvas API. It's not as easy
as making shapes/images in CSS. I also managed to incorporate the `Particles`
component into my [weather app](http://codepen.io/kme211/pen/zNoave).

### Day 22: Saturday, January 28, 2017

**Today's Progress:**  Worked on my exquisite-corpse app but didn't really make
a lot of progress. I really think I should have planned it better. I feel like
I'm writing terrible code.

### Day 23: Sunday, January 29, 2017

**Today's Progress:** Continued to work on my exquisite-corpse app. Got the `get`
and `save` methods working on the backend for `sections`. Feeling slightly better about
it today than yesterday. Sometimes I feel like I get caught up in "Yes, that would
work but is it the most efficient way?" I honestly have no idea what the most efficient
way is when dealing with databases. Maybe I'm stressing out about a really tiny
performance impact. 

### Day 24: Monday, January 30, 2017

**Today's Progress:**  Changed my `Particles` component name to `Sky` and added 
some animated stars as part of the `clear` prop type. I also integrated it into my weather app. It took a while to convert some code that someone else wrote to something that would 
work for my use case. 

I had to initalize the star particles with the usual `radius`, `opacity`, `x`, and
 `y` but then I also had to add a `degreeX` and `degreeY`. Then in the function 
 that draws the stars each animation frame, I had to do this: 
 ```
  particle.degreeX += 0.025 * speed
  particle.degreeY += 0.025 * speed
  const xcenter = width/2
  const ycenter = height + 5
  const radian = (particle.degreeX/180) * Math.PI // Radian of the night sky
  particle.x = xcenter + Math.cos(radian) * particle.radian
  particle.y = ycenter + Math.sin(radian) * particle.radian
```

There do however seem to be more stars clustered at the bottom center than anywhere else.

**Link to demo:** [Sky component](http://codepen.io/kme211/pen/XpeqjG)

### Day 25: Wednesday, February 1, 2017

**Today's Progress:** Did the HTML5 Video player tutorial on Javascript 30 and learned 
how to make a custom video player using CSS and vanilla JS. I also created a sun 
animation for my `Sky` component and added it to weather app. 

Weather conditions I may still want to animate: 
- thunderstorm
- drizzle

**Link to demo:** [Sky component](http://codepen.io/kme211/pen/XpeqjG)

### Day 26: Thursday, February 2, 2017

**Today's Progress:** Started reading [Making Games](http://www.allitebooks.com/making-games/) 
to learn how to make a platform game using [PixiJS](http://www.pixijs.com/). 
Instead of copying and pasting the code, I wrote out each line in a 
[Codepen pen](http://codepen.io/kme211/pen/jyzJgO). 

### Day 27: Friday, February 3, 2017

**Today's Progress:** Continued going through Making Games book. 

### Day 28: Sunday, February 5, 2017

**Today's Progress:** Continued going through Making Games book and completed 
the day 3 #dailycssimages challenge--beaver.

**Link to demo:** [Beaver](https://t.co/yx4O3Nuccm)

### Day 29: Monday, February 6, 2017

**Today's Progress:** Started making a portfolio page. I am using [this portfolio page](http://heuze.co.uk/) 
as inspiration. Still needs work but it's roughly there and styled.

**Link to demo:** [Portfolio](http://codepen.io/kme211/full/ZLjpJG/)

### Day 30: Tuesday, February 7, 2017

**Today's Progress:** Continued to work on building my portfolio. I decided it was time 
to start working on it outside of Codepen because I want to be able to build 
the portfolio (or Work) section dynamically--that way it's easier to make changes. 
I got node-sass working and now I need to get [Nunjuks](https://mozilla.github.io/nunjucks/) working. 

**Link to repo:** [Portfolio](https://github.com/kme211/static-portfolio)

### Day 31: Wednesday, February 15, 2017

**Today's Progress:** I worked on tweaking the CSS for my Simon Game (part of FCC 
  curriculum). I used that handy [clip path maker](http://bennettfeely.com/clippy/) 
  to make pie slice shapes for the buttons. 
  
  **Link to demo:** [Pie slices](http://codepen.io/kme211/pen/ggEQVZ)
  **Link to repo** [Simon Game](https://github.com/kme211/simon-game)

### Day 32: Thursday, February 16, 2017

**Today's progress:** I added functionality for what happens when you press the 
wrong button in my Simon Game. I also changed my start button. Still need to add 
some sort of "Yay!" animation for when user makes it to 20 (count).

**Link to repo** [Simon Game](https://github.com/kme211/simon-game)

### Day 33: Friday, February 17, 2017

**Today's progress:** I added functionality for what happens when you win (get up to 20). 
The whole thing spins like a pinwheel. I also added a restart button. I had to make sure that 
I cleared all the intervals that get set when the sequence is run when the restart button gets pushed.
I'm becoming more comfortable with keyframe animations in CSS.

**Link to repo** [Simon Game](https://github.com/kme211/simon-game)

**Link to demo** [Simon Game hosted on Netlify](http://preacher-jessie-81250.netlify.com/)


### Day 34: Saturday, February 18, 2017

**Today's progress:** Worked on adding a strict mode check box to the header of my Simon game. Had some trouble with the CSS but got it sort of working. "Strict mode" label text looks like it gets nudged a pixel or two when you check the box. 

**Link to repo** [Simon Game](https://github.com/kme211/simon-game)


### Day 35: Sunday, February 19, 2017

**Today's progress:** Finished adding strict mode to my Simon Game. Fixed the checkbox pixel nudging by adding `float: right` to the label.

**Link to repo** [Simon Game](https://github.com/kme211/simon-game)

**Link to demo** [Simon Game hosted on Netlify](http://preacher-jessie-81250.netlify.com/)

### Day 36: Monday, February 20, 2017

**Today's progress:** Change Simon Game counter to show how many steps are in the current series of button presses. 
Added animation names and properties to `constants.js` to keep code more DRY. Game will now restart after the win animation.

I also completed the ["No repeats please"](https://www.freecodecamp.com/challenges/no-repeats-please) challenge on FreeCodeCamp. The permutations 
part of it was pretty confusing. I used this [stackoverflow answer](http://stackoverflow.com/questions/9960908/permutations-in-javascript#answer-20871714) to help me. 

**Link to repo** [Simon Game update](https://github.com/kme211/simon-game/commit/f2faf2d9a458b585504ea54616532869790cf4ed)

### Day 37: Tuesday, February 21, 2017

**Today's progress:** Completed day 5 of #dailycssimages: Favorite Animated Animal. I did Bender from Futurama (party animal). It's probably the most complex CSS image I've done so far and I'm pretty proud of it. `z-index` was kind of pain on this one and I should probably do some more reading on the subject.

**Link to demo** [Bender](http://codepen.io/kme211/pen/bgXQgB)


### Day 38: Wednesday, February 22, 2017

**Today's progress:** Took yesterday's CSS image (Bender) and made him a part of new random quote generator. I need to collect more Bender quotes and randomize them. I added a blink animation and a bored-eyes animation and I want to add some more expressions for different quotes. 

**Link to demo** [Bender Quotes](http://codepen.io/kme211/pen/JWPLgQ)


### Day 39: Thursday, February 23, 2017

**Today's progress:** Added eyelid animations to Bender Quotes. Different quotes will start different animations depending on how I think Bender's eyes should look during the quote. Added a function to shuffle the array of quotes. Added functionality to remove the antenna hint animation when there are no more quotes. I also added a header that says "Bender Quotes."

**Link to demo** [Bender Quotes](http://codepen.io/kme211/pen/JWPLgQ)
