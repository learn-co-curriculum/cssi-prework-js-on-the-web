
# JavaScript on the Web
After this lesson, you'll be able to understand:
+ The browser represents html pages with the document object model (DOM)
+ We can use JavaScript and jQuery to select and modify elements

So far, we have used JavaScript to do some math and work with some data. Today, we get to use JavaScript on its home turf - manipulating HTML elements in the browser.

Let’s start with a little example, to give you a taste of the power of JavaScript before getting into the nitty-gritty of the DOM.

1. Go to https://twitter.com/taylorswift13
2. Open the console using <kbd>Command</kbd>+<kbd>Option</kbd>+<kbd>j</kbd>
3. Run these two statements, with replacing 'Your Name' with, you guessed it, your name:
  * `names = $('.fullname');`
  * `names.text('Your Name');`

4. Look at the tweets Taylor has sent out very closely

BAM! You are a Twitter master! How cool are you! So popular!

Now, how did that work?

##The DOM
Your browser keeps all of the elements of the webpage in a tree structure called the Document Object Model. Basically, it keeps track of all of the html elements from the html page, their styles, and the relationships between them - who is nested in who, which elements have which parents and children.
```html
 <body>
  <ul>
    <li>
      <p>Shady Grove</p>
      <p>Aeolian</p>
    </li>
    <li>
      <p>Over the River, Charlie</p>
      <p>Dorian</p>
    </li>
  </ul>
</body>
```
A way to visualize the DOM for that table would be:

![Tree representation of the elements above](http://i.imgur.com/8fj2Uka.png)

JavaScript can speak the browser’s language - it IS the browser’s language. It is AWESOME for picking elements on a webpage and doing something to them - like picking all the elements on the twitter page and changing them to my name.

Let’s look a little bit more closely at the code we ran to change twitter:

```javascript
names = $('.fullname');
names.text('Your Name');
```

First we needed to select all of the names on Taylor's Twitter pages. By inspecting the page, you can see that these names have a class of `fullname`. Just like with CSS selectors, we can select all the elements in the DOM with the class `fullname` by using `.fullname` surrounded by parenthesis. Unlike CSS selectors, we have to wrap the selector in quotes and precede the selector with a '$'. This '$' is short for jQuery which you will learn more about soon.

Once we get all of the DOM elements with the fullname class, we assign that array to the variable `names`.

Once we have all the elements we want, we can update them with another new method - `.text()`. This method accesses the  text inside an element. Since we passed the .text method a string - 'Your Name'-  all the text inside every element in the `names` array was changed to 'Your Name'

Try selecting other HTML elements on the page and updating their text! What happens?

The selector syntax - $() - and the .text() method actually aren't part of the JavaScript baked into the browser. They actually come from the **jQuery library** - a big, commonly used set of useful JavaScript functions. In order to use this syntax on our pages, we'll need to link up to a JavaScript library.

Manipulating web pages is the bread and butter of jQuery. You will learn exactly what jQuery is and how it works in the next series of lessons.
