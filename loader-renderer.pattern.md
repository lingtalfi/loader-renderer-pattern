Loader Renderer pattern
=========================
2017-02-17



Here is a cool pattern that I like, just wanted to put it here for my personal convenience.


It's about rendering a template.

A template could contain php content, or just html content.
In other words, a template can be interpreted and produces an interpreted template content.


The pattern is to use a combination of 2 objects:

- Loader
- Renderer


The template is given with variables.

The Loader is responsible for loading the template content from a template name:

```txt
templateContent = Loader->load(templateName)
```

Then the templateContent that we have is uninterpreted (i.e. it could still contain some php code
for instance).

So we use the Renderer to render the template (i.e. obtain the rendered content).

```txt
renderedContent = Render->render(vars)
```

The Render object also has a setTemplateContent method.
We could also add the templateContent as an argument of the render method,
but I believe this is more flexible to separate the two methods: for instance
we can encapsulate the template content with inheritance.


