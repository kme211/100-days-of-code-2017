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
