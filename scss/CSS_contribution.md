## If you are new to CSS or wish to contribute
Please observe the following conventions on the directory structure for your CSS code. To contribute, use the `.scss` extension for consistency's sake as more advanced devs might prefer SCSS syntax when using SCSS, though fear not! Since SASS is a superset of CSS, all CSS syntax works within it and you do not not have to rewrite your existing CSS.

#### Directory structure
```md
simple-contribution (project root)
- .vscode
- image
- scss (directory where all the css goes)
  - banner
  - foundations (colors and dimensions)
  - hamburger
  - scrollbar
  CSS_contribition.md (You are at this file)
```

###### What is a directory?
A directory is a more fancy way of saying it is a folder

#### The purpose of directories
When we say "the purpose of directories", we are referring to all the subfolders of this folder (namely scss).

**foundations**: is used for CSS variables that are foundations to the page, mainly color and dimensions (e.g. padding, background-color).

Within the foundations directory, create a new folder with a descriptive name of your feature (e.g. like_button).

Other directories are used to store CSS code used in features (please give the same name as the one in the foundations directory).

##### Using `@use`
Using `@use` in SASS/SCSS includes the entire contents of another `.scss` file in your current `.scss` file. 
Here is the general flow of SASS's compilation with `@use` files, with relative filepaths to the root directory, and following the outlined conventions in this guide.

[![](https://mermaid.ink/img/pako:eNqNVMluwjAQ_RXLpzaCVOoxh6pACZt6Sk9AhUxiSFQSIy8HBPx7JzYtxHEgPtnzZnvzRj7imCUUB3jLyT5FX_1lgeAItTaGJeaMySU2ZgsSsRC3kAVvmCoSIjNW1LzsRCynqw0lUnHqci1Pb1H1W0H85eqbRr7dgX0I9H2_ER_YiW_61pmR5z29K0GfPa8xSQ91u29o0NDBH1iHaZE8ngyTKeWP5jNcuLxrZIABOLdsJFxUVGw1jYEmG9aBoQGs2pe69mxGpWgvQh529HHZxk1y8BxbarfiNL-zQnNNa-xk1VJS5NJ06tbzuvWvzWs_c8a2ojrVdGZ36FQek7KSUcluJtSZRjcajGuWmbFcDaPScIp6UYRilu-znd68E5oYF10bd3BOeU6yBP6to94eDDxzEDyAa0L4TznQM_gRJVl0KGIcSK5oBz4ztU1xsCE7AS-1h8WmHxkBafJ_K00yyfin-Rb173j-BTFuXXo?type=png)](https://mermaid.live/edit#pako:eNqNVMluwjAQ_RXLpzaCVOoxh6pACZt6Sk9AhUxiSFQSIy8HBPx7JzYtxHEgPtnzZnvzRj7imCUUB3jLyT5FX_1lgeAItTaGJeaMySU2ZgsSsRC3kAVvmCoSIjNW1LzsRCynqw0lUnHqci1Pb1H1W0H85eqbRr7dgX0I9H2_ER_YiW_61pmR5z29K0GfPa8xSQ91u29o0NDBH1iHaZE8ngyTKeWP5jNcuLxrZIABOLdsJFxUVGw1jYEmG9aBoQGs2pe69mxGpWgvQh529HHZxk1y8BxbarfiNL-zQnNNa-xk1VJS5NJ06tbzuvWvzWs_c8a2ojrVdGZ36FQek7KSUcluJtSZRjcajGuWmbFcDaPScIp6UYRilu-znd68E5oYF10bd3BOeU6yBP6to94eDDxzEDyAa0L4TznQM_gRJVl0KGIcSK5oBz4ztU1xsCE7AS-1h8WmHxkBafJ_K00yyfin-Rb173j-BTFuXXo)

If it is too blurry, you can open the diagram and zoom into it.

There should only exist at most one file with `@use` calls per directory (including this directory), e.g. [foundations.scss](./foundations/_foundations.scss), [styles.scss](./styles.scss).

##### If you do not wish to use `@use`
Create a directory with your CSS code split by sub-features (e.g. transition effects). The key is giving a descriptive name telling other contributors what the specific `.scss` file is for. Do give us a heads up in your PR to add `@use` to integrate your snippet with the main stylesheet.

** However, please still follow the concention on where the 

#### The use of CSS variables 
As much as possible, try to use CSS variables e.g.
```css
body{
    --test-class-bg-color: #000000;
}
.test_class{
    background-color: var(--test-class-bg-color);
}
```

If you want to use the value of others CSS variables, you can declare it in a body scope after their code

A CSS variable can have contain many things, such as the `center` in the `text-align: center` of a navbar code, or the `center` in a banner. Hence, we strongly encourage using CSS variables. This makes it easier for you and others to reuse and maintain different color styles by contributors. It also tells maintainers the purpose of your CSS variable.

Since a CSS variable is declarative, to avoid confusion it should be declared once and modified as much as possible. Even if there arises a need to do so (like storing and updating counter using CSS), please keep it to your own variables and not modify others.

You can declare CSS variables under `*`, `.root` or `body`. However, we recommmend using `body` for consistency's sake.

## For advanced devs
This directory defines files which use the `.scss` extension. To compile SCSS/SASS into CSS, install sass [here](https://sass-lang.com/install/).

#### Development with SASS/SCSS
After adding `@use` calls to the directories/directory in which your feature exist, run `sass --no-source-map --watch styles.css ../styles.css` in this directory to compile all SCSS scripts to a single `styles.css` script in the root directory. 



## FAQ

#### Why directories with SCSS, why not just dump all the code in a few CSS files?
