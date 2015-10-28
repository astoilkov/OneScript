# ![OneScript Logo](https://dl.dropboxusercontent.com/u/4277603/OneScript/OneScript.png) OneScript

HTML, CSS and JavaScript brought together in one complete solution

This is a community project so you could be part of shaping OneScript future.
Let's get the discussion going.

 * [Twitter](https://twitter.com/onescriptio)
 * [Gitter](https://gitter.im/astoilkov/OneScript)
 * [Google Groups](https://groups.google.com/forum/#!forum/onescript/new)

Help OneScript:
 * Star the project
 * Watch it
 * Fork it
 * Share your opinion on Twitter, Facebook, ...
 * Write a blog post about it

## Hello World

```html
<!doctype html>
<html> {
    <head> {
        <title>Hello from OneScript</title>
    }
    <body> {
      <h1>Hello from OneScript</h1>
      <h3>Let's count some numbers</h3>
      <ul> {
          defaultColor = 'blue'

          this.each([1, 2, 3, 5]);

          <css> {
              font-weight: bold;
              color: ${defaultColor};

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
Read more about the power of OneScript CSS functionality [here]().

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

Custom components allow you to extract logic and reuse it multiple items.
They are powerful tool that could help your application architecture.

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

                // set the name of the custom element
                super('SignIn');
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

## Prototyping

Prototyping is overlooked by everyone.
A language/platform should allow quick creation of prototypes for testing, showcase and brainstorming scenarios.

```html
<!doctype html>
<html> {
    <body> {
        <ul> {
            <!-- DUMMY is a reserved word which could be used to generate random data for prototyping purposes -->
            this.each(DUMMY);

            <li>My name is ${firstName} ${lastName} and I am ${age} years old.</li>
        }
    }
}
```

```html
<!doctype html>
<html>
    <body>
        <ul>
            <li>My name is Antonio Stoilkov and I am 23 years old.</li>
            <li>My name is John Doe and I am 41 years old.</li>
            <li>My name is Maria Johnes and I am 27 years old.</li>
            <li>My name is Andrew Fuller and I am 18 years old.</li>
            <li>My name is Robert King and I am 62 years old.</li>
            <li>My name is Laura White and I am 33 years old.</li>
            <li>My name is Anne Peacock and I am 55 years old.</li>
            <li>My name is Michael Leverling and I am 24 years old.</li>
            <li>My name is Nancy Callahan and I am 16 years old.</li>
            <li>My name is Janet Dodsworth and I am 49 years old.</li>
        </ul>
    </body>
</html>
```

## Why OneScript?

* Learn once build using whatever - OneScript would be designed in a way that every framework could adopt it.
Angular, React, jsblocks, Ember or any other framework will be able to implement the syntax and add additional
methods to adopt it to their thinking. This way we could use one base implementation and framework will compete
for performance, debugging experience, extension, community

* [Rise of the Transpilers by Jeremy Ashkenas creator of CoffeeScript](https://youtu.be/DspYurD75Ns?t=38m44s) - this is a great talk where Jeremy talks about CoffeeScript.
I want to point out a specific part in the end where he talks in what he believes the next,
future language should look like. OneScript is trying to achieve one unified experience with already established technologies.
No need to select elements by id from your JavaScript and CSS...the code should be where the markup is defined

* No more code and DSL in attributes. Attributes should be used for what they were created for

* TypeScript/Flow, SASS built-in. Use proven techniques out of the box

* Prototyping - prototyping is something no one is thinking about.
Prototyping should be built-in the languages we love so it is possible to showcase and brainstorm ideas quickly

* Separation between CSS and code through [IDE integration](docs/ide-integration.md)

* Community driven - allowing for a concept to become reality through the community is the perfect way to shape the project.
We rely on companies to decide the perfect way for building applications.
There should be a solution that is for developers from the community.

# Coming soon...

## Documentation

* HTML Syntax
    * Multiline elements
    * Single line elements
    * Expressions
    * Comments
* Coding
    * Introduction
    * VirtualElement methods
    * Components
    * Contexts
    * TypeScript/Flow support
    * Prototyping
* Advanced code principles
    * Dependency management
* Styling
    * Introduction
    * Per element CSS
    * Dynamic CSS
    * Built in SASS
* [IDE Integration](docs/ide-integration.md)
    * [Introduction](docs/ide-integration.md#introduction)
    * [File extension](docs/ide-integration.md#file-extension)
    * [Developer Mode](docs/ide-integration.md#developer-mode)
    * [Designer Mode](docs/ide-integration.md#designer-mode)
    * [Conclusion](docs/ide-integration.md#conclusion)
* Transpilation
    * Introduction
    * React
    * jsblocks
    * AngularJS
    * EmberJS
    * Any other...
