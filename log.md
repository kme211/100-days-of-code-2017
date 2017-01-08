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

**Link to demo:** [Is it high FODMAP? Demo](http://fodmapper.surge.sh/)

**Link to repo:** [Is it high FODMAP? Git repository](https://github.com/kme211/low-fodmapper)
