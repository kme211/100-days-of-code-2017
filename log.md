# 100 Days Of Code - Log

### Day 0: Thursday, January 5, 2017

**Today's Progress:** Separated frontend from backend. React up and running. Haven't tested backend routes yet since separation.

**Thoughts:** Still not sure about how I'm going to design the structure of the 
Canvas with React. I also need to test saving the Canvas data as the Buffer 
file type ([possible solution](http://stackoverflow.com/questions/22228552/serialize-canvas-content-to-arraybuffer-and-deserialize-again)) 
in NodeJS. Previously I was using [HTMLCanvasElement.toDataURL()](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/toDataURL)
to save drawings as a data URI and saving those to MongoDB.

**Link to repo:** [Exquisite Corpse (collaborative drawing app)](https://github.com/kme211/exquisite-corpse)

### Day 1: Thursday, January 6, 2017

**Today's Progress:** Setup Mocha and Supertest in backend and added a test to test `drawings/new` route.

**Thoughts:** Still need to add error handling to routes.

**Link to repo:** [Exquisite Corpse (collaborative drawing app)](https://github.com/kme211/exquisite-corpse)