# ![MarkupScript Logo](https://dl.dropboxusercontent.com/u/4277603/MarkupScriptLogo.png) MarkupScript

HTML, CSS and JavaScript brought together in one complete solution

> This a concept project that will be centered around the community interest. If you like what you see please star and share the project. If the project gets more than 5000 stars it will get implemented.

> Let's get the discussion going. Open an issue if you have an idea or improvement suggestion.

## Hello World

```html
<!doctype html>
<html> {
    <head> {
        <title>Hello from MarkupScript</title>
    }
    <body> {
      <h1>Hello from MarkupScript</h1>
      <h3>Let's count some numbers<h3>
      <ul> {
          this.each([1, 2, 3, 5]);
          
          <li>${this}</li>    
      }
    }
}
```

Output:

```html
<!doctype html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Hello from MarkupScript</title>
    </head>
    <body>
        <h1>Hello from MarkupScript</h1>
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

### A lot more to come...

There is a lot more to come. The documentation(specification) will get filled gradually. Watch the repo so you don't miss what's new.
