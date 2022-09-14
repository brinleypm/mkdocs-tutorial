# Create an industry-standard documentation website using MkDocs and Material Design

## Why use MkDocs?

[MkDocs](https://www.mkdocs.org/) is a static site generator that turns Markdown 
files into HTML. It does 100% of the work to generate all of the HTML for a fast 
and beautiful Read The Docs-style website, so you can focus all your energy on 
writing content!

Here are a few potential use cases for MkDocs:
* Documenting a large software project
* Hosting an open-source textbook
* Hosting material for an online course

## Prerequisites

* [Python](https://www.python.org/) and [pip](https://pypi.org/project/pip/) 
installed on your computer
* Knowledge of how to write files in [Markdown](https://www.markdownguide.org/)

## Step 1. Install MkDocs

Install MkDocs:
```bash
pip install mkdocs
```

## Step 2. Create and serve your first MkDocs site

```bash
mkdocs new my-mkdocs-site # This will create a directory named my-mkdocs-site with a starter MkDocs site
cd my-mkdocs-site
mkdocs serve # This will start your MkDocs site on http://127.0.0.1:8000
```
Open up `http://127.0.0.1:8000` in your browser to see what your starter MkDocs
site looks like!

## Step 3. Update your site's name

At the root of your MkDocs site directory, `my-mkdocs-site`, you'll see your
site's configuration file: `mkdocs.yml`.

Open up `mkdocs.yml` and change `site_name` to the name your want to give your
site (e.g., `My First MkDocs Site`).

Notice that, as soon as you save your changes to `mkdocs.yml`, your MkDocs site 
on `http://127.0.0.1:8000` will automatically reload to reflect this change. 
The fancy term for this is **Hot Reloading.** MkDocs will automatically reload any 
time you make a change :)

## Step 4. Create a new page

All your site's pages will be housed under the root of your MkDocs site
directory in `/docs`. 

Go into `/docs` and create a new page:
```bash
cd docs
touch about.md
```
Now, add some content to `about.md`:
```markdown
# About

This is my about page!

## This is a subcategory

blah blah blah blah

## This is another subcategory

blah blah blah blah
```

Notice your `about.md` page will now show up on the top bar of your site and 
your `about.md` page's subcategories will show up on `about.md`'s left sidebar.

## Step 5. Beautify your site with the Material for MkDocs theme

Next, add the `Material for MkDocs` theme to your site to make it look nice and 
sleek.

> **Note:** `Material Design` is Google's specification for the best practices of user 
> interface design. `Material for MkDocs` was built around this specification.

To do this, first install `Material for MkDocs`:
```bash
pip install mkdocs-material
```

Then, add the following lines to `mkdocs.yml`:
```yml
theme:
  name: material
```
Now you'll notice your site has a `Material Design` inspired style.

> **Note:** Material for MkDocs is by far the most popular theme for MkDocs but 
> there are other themes as well. Here's a full list of themes for MkDocs: 
> https://github.com/mkdocs/mkdocs/wiki/MkDocs-Themes

### Bonus: Add a dark theme toggle

You can add a dark theme toggle to your MkDocs site by going into
`mkdocs.yml` and replacing
```yml
theme:
  name: material
```

with
```yml
theme: 
  name: material
  palette: 

    # Palette toggle for light mode
    - scheme: default
      toggle:
        icon: material/weather-night
        name: Switch to dark mode

    # Palette toggle for dark mode
    - scheme: slate
      toggle:
        icon: material/weather-sunny
        name: Switch to light mode
```
## Step 6 (Optional). Deploy your MkDocs Site to Github Pages

You can deploy your MkDocs site to pretty much anywhere. Deploying to Github
Pages is the easiest option and works well if you're code is hosted in a Github
Repo, so this tutorial will focus on deploying to Github Pages. 

If you don't already have your MkDocs Site in a Github repository, you've got 
two options:
1. Create a fresh Github repo and connect your local MkDocs site to that repo
2. Copy your MkDocs site into an existing Github repo on your local machiine

Be sure that BOTH your `.mkdocs.yml` file AND your `docs` folder are at the root
of your Github repository. 

Once you've got these files in your Github repository, you just need to run a 
single command to deploy your site to Github Pages:
```bash
mkdocs gh-deploy
```
This will deploy your MkDocs site to `https://{your-github-username}.github.io/{your-repo-name}`

> **Note:** You may have to wait a few minutes for this deployment to finish.
