# EJS Partials :

Partials come in handy when you want to reuse the same HTML across multiple views. Think of partials as functions, they make large websites easier to maintain as you don’t have to go and change a piece of text in every page it appears in. Instead, you define that reusable bundle of code in a file andinclude it wherever you need it.
Our blog will consist of a home page which lists all the blog posts and a post page which will display a single post. Our home page will look like so:

As you can see from the screenshots above, the same navigation bar and footer appear in both the home and post view. This makes them perfect candidates for partials!
Let’s go ahead and create those partials. Under the views/partials/ directory create a file callednavbar.ejs which will contain only the HTML for the navigation bar at the top of the home and post pages:

`<!-- views/partials/navbar.ejs -->`
    `<div class="header clearfix">`
        `<nav>`
            `<ul class="nav nav-pills pull-right">`
                `<li role="presentation"><a href="/">Home</a></li>`
            `</ul>`
            `<h3 class="text-muted">Node.js Blog</h3>`
     `   </nav>`
    `</div>`

    Now that we have our partials defined, we can use them in our home.ejs and post.ejs templates! In EJS, any JavaScript or non-HTML syntax you include in your templates is always surrounded by <% %> delimiters (you could change these delimiters if you really wanted to).
Including a partial in EJS is quite straightforward. You use <%- include( PARTIAL_FILE ) %> where the partial file is relative to the template you use it in.

