# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md

    Inside of the router, you define your routes (`this.route('about')`).
    Inside of the route, you set up your model hook/define your interactions
    with data.

    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    
    ember g route campus/boston

    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    
    {{#link-to 'campus.boston'}}Boston Campus{{/link-to}}

    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    
    The first definition is a nested route. The URL for the parent route will
    look like /products, and the child route (which on its own is something
    like /7) will look like /products/7.

    The second is a single route that looks like /products/7, with no 'parent'
    products route.

    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    
    We'll pass `params` to the model hook as an argument and use
    params.movie_id to access the id.

    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    
    Data is passed from a route to a template as `model`, so we can use
    {{model}} to access it. If it's an array of data, we can use something
    like {{#each model as |product|}} (do stuff here) {{/each}}.

    ```
