# ![OneScript Logo](https://dl.dropboxusercontent.com/u/4277603/OneScript/OneScript.png) OneScript

HTML, CSS and JavaScript brought together in one complete solution

This a concept project that will be centered around the community interest.
If you like what you see you could star, watch and share the project.
If the project gets more than 5000 stars it will get implemented.

Let's get the discussion going. Open an issue if you have an idea or improvement suggestion.

## Hello World

```html
<!doctype html>
<html> {
    <head> {
        <title>Hello from OneScript</title>
    }
    <body> {
      <h1>Hello from OneScript</h1>
      <h3>Let's count some numbers<h3>
      <ul> {
          defaultColor = 'blue'
          
          this.each([1, 2, 3, 5]);
          
          <css> {
              font-weight: ${defaultColor};
              color: blue;
              
              li:nth-child(even) {
                  color: yellow;
              }
          }
          
          <li>${this}</li>    
      }
    }
}
```

> ***What...what...what? So you write code in the HTML?***

> Yes. You could write code in the beginning of opened HTML tag.
Tags could be opened with curly braces - this makes it more code-ish and the ending of a tag could be seen more clearly.
You could read more about it [here]().

> ***What is that CSS in the `<ul>`?***

> That's how OneScript handles CSS. This way the CSS is exactly where it should be.
Read more about the power of OneScript CSS functionality [here](https://github.com/astoilkov/MarkupScript/wiki/Handling-CSS).

The result of the OneScript above will be:

```html
<!doctype html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Hello from OneScript</title>
        <style>
            ul {
                font-weight: bold;
                color: blue;
                
                li:nth-child(even) {
                    color: yellow;
                }
            }
        </style>
    </head>
    <body>
        <h1>Hello from OneScript</h1>
        <h3>Let's count some numbers<h3>
        <ul>
            <li>1</li>
            <li>2</li>
            <li>3</li>
            <li>5</li>
        </ul>
    </body>
</html>
```

## Components

```html
<SignIn> : <form> {
    username = ''
    password = ''
    
    signIn() {
        if (this.username == 'admin' && this.password == 'admin') {
            alert('login successful');
        } else {
            alert('username or password was incorrect try with admin admin');
        }
    }
    
    <h1>Sign In</h1>
    <input placeholder="Enter your username"> {
        this.val(username);
    }
    <input placeholder="Enter your password"> {
        this.val(password);
    }
    <button>Sign in</button> {
        this.click(this.signIn);
    }
}

<!doctype html>
<html> {
    <body> {
        <h1>Hello Components</h1>
        <SignIn>
    }
}
```

Result:

```html
<html>
    <head>
        <script>
            // the SignIn form will inherit VirtualElement
            function SignIn() {
                this.username = '';
                this.password = '';
                
                // use Object.observe to observe the object
                this.observe();
                
                this.find('#inp1').val(this.username);
                this.find('#inp2').val(this.password);
                this.find('#btn1').click(this.signIn);
            }
            
            SignIn.prototype.signIn = function () {
                if (this.username == 'admin' && this.password == 'admin') {
                    alert('login successful');
                } else {
                    alert('username or password was incorrect try with admin admin');
                }
            };
        </script>
    </head>
    <body>
        <h1>Hello Componenets</h1>
        <form>
            <h1>Sign In</h1>
            <input id="inp1" placeholder="Enter your username">
            <input id="inp2" placeholder="Enter your password">
            <button id="btn1">Sign in</button>
        </form>
    </body>
</html>
```

## Why OneScript?

* Learn once build using whathever - OneScript would be designed in a way that every framework could addopt it.
Angular, React, jsblocks, Ember or any other framework will be able to implement the syntax and add additional
methods to adopt it to their thinking. This way we could use one base implementation and framework will compete
for performance, debugging experience, extension, community and so on.

* [Rise of the Transpilers by Jeremy Ashkenas creator of CoffeeScript](https://youtu.be/DspYurD75Ns?t=38m44s) - this is a great talk where Jeremy talks about CoffeeScript. I want to point out a specific part in the end where he talks in what he believes the next,
future language should look like. It is exactly what OneScript is trying to achieve one unified experience with already established technologies.
No need to select elements by id from your JavaScript and CSS...the code should be where the markup is defined.

* No more code and DSL in attributes. Attributes should be used for what they were created for.

* TypeScript/Flow, SASS built-in. Use proven techniques out of the box.

# Coming soon...

## Documentation

* HTML Syntax
    * Single line elements
    * Multiline elements
    * Expressions
* Coding
    * Introduction
    * VirtualElement methods
    * Components
    * Contexts
    * TypeScript/Flow support
    * Prototyping
* Styling
    * Introduction
    * Per element CSS
    * Dynamic CSS
    * Built in SASS
* IDE Integration
    * Introduction
    * Developer Mode
    * Designer Mode
* Transpilation
    * Introduction
    * React
    * jsblocks
    * AngularJS
    * EmberJS
    * Any other...
