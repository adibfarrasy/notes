## What are browsers and how do they work

Web browsers are programs on the computer that allow users to visit websites.

source: https://www.youtube.com/watch?v=BrXPcaRlBqo

### Basic components of a web browser
1. User interface
2. Browser engine
3. Rendering engine
4. Networking
5. JavaScript interpreter
6. UI backend
7. Data persistence (cookies, cache etc.)

### Rendering engine steps
1. Resource gathering - get all the data from HTML
2. Parse HTML & create a Document Object Model (DOM) tree
3. Create a Render tree from the created DOM tree (take all the styles and apply them to the visible elements)
4. Layout - position all the visible elements with their respective styles
5. Painting - the core UI uses the computer's draw library to display all the elements in the correct position. There's also an added z-dimension (overlapping in the layout)

https://www.youtube.com/watch?v=WjDrMKZWCt0