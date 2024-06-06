---
index: false
---

<style>

h2 {
  margin: 1.5rem 0 1rem 0;
  font-size: 2rem;
}
.margin-note {
    width: 200px;  /* Set the width of the image */
    float: right;  /* Align the image to the right */
    margin-left: 20px; /* Space between the text and the image */
    margin-right: -280px; /* Pull the image into the right margin */
    position: relative; /* Position relative to its normal position */
    top: 0; /* Align the top of the image with the top of the paragraph */
    box-shadow: 0 0 0 0.75px rgba(128, 128, 128, 0.2), 0 6px 12px 6px rgba(0, 0, 0, 0.4);
}
.model-container {
    margin: 1.5rem 0 1rem 0;
    position: relative;
    border: 1px solid black;
    border-radius: 6px;
    box-shadow: 1px 1px 30px rgba(252, 220, 252, 1);
  }
.cta {
  display: flex;
  align-items: center;
  gap: 2rem;
}

@container not (min-width: 400px) {
  .cta {
    flex-direction: column;
    align-items: start;
    gap: 0;
  }
  .cta .observablehq-pre-container,
  .cta pre:not(.observablehq-pre-container pre) {
    width: 100%;
  }
}

/* Gallery */

.gallery {
  margin: 4rem -1rem;
  gap: 2rem;
  max-width: calc(840px + 2rem);
}

.gallery a {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
}

.gallery img {
  max-width: 100%;
  border-radius: 8px;
  box-shadow: 0 0 0 0.75px rgba(128, 128, 128, 0.2), 0 6px 12px 0 rgba(0, 0, 0, 0.2);
  aspect-ratio: 2500 / 1900;
}

@media (prefers-color-scheme: dark) {
  .gallery img {
    box-shadow: 0 0 0 0.75px rgba(128, 128, 128, 0.2), 0 6px 12px 0 rgba(0, 0, 0, 0.4);
  }
}

.gallery a:not(:hover, :focus) {
  color: var(--theme-foreground-muted);
}

.gallery a:hover img,
.gallery a:focus img {
  box-shadow: 0 0 0 0.75px var(--theme-foreground-focus), 0 6px 12px 0 rgba(0, 0, 0, 0.2);
}

.gallery figcaption {
  font-size: 12px;
  color: inherit;
}

.arrow {
  font-weight: 500;
}

.arrow::after {
  content: "→";
  display: inline-block;
  margin-left: 0.25rem;
}





@media (prefers-color-scheme: light) {
  h1 {
    --theme-red: #d75c48;
  }
}

</style>


# Welcome
_Overthinking McElreath's Rethinking._

McElreath's _Statistical Rethinking_ is a journey into statistical madness.  
<img src="https://m.media-amazon.com/images/I/81cEpsiTCFL._AC_UF1000,1000_QL80_.jpg" alt="golem wiki" class="margin-note"/>
When systems do not comply to random controlled experiments, we need to do our best. 
This book is doing its best for us to do our best. 
But i keep going back to it, as this book (and accompanying lectures) keeps evolving and getting better. 
This is my place where I keep track of my (interactive) notes and thoughts, for myself and others.

<details><summary>How to get started with Observable Framework</summary>

## 

This is (also) an [Observable Framework](https://observablehq.com/framework) project. To start the local preview server, run:

```
npm run dev
```

Then visit <http://localhost:3000> to preview your project.

For more, see <https://observablehq.com/framework/getting-started>.

#### Project structure

A typical Framework project looks like this:

```ini
.
├─ docs
│  ├─ components
│  │  └─ timeline.js           # an importable module
│  ├─ data
│  │  ├─ launches.csv.js       # a data loader
│  │  └─ events.json           # a static data file
│  ├─ example-dashboard.md     # a page
│  ├─ example-report.md        # another page
│  └─ index.md                 # the home page
├─ .gitignore
├─ observablehq.config.js      # the project config file
├─ package.json
└─ README.md
```

**`docs`** - This is the “source root” — where your source files live. Pages go here. Each page is a Markdown file. Observable Framework uses [file-based routing](https://observablehq.com/framework/routing), which means that the name of the file controls where the page is served. You can create as many pages as you like. Use folders to organize your pages.

**`docs/index.md`** - This is the home page for your site. You can have as many additional pages as you’d like, but you should always have a home page, too.

**`docs/data`** - You can put [data loaders](https://observablehq.com/framework/loaders) or static data files anywhere in your source root, but we recommend putting them here.

**`docs/components`** - You can put shared [JavaScript modules](https://observablehq.com/framework/javascript/imports) anywhere in your source root, but we recommend putting them here. This helps you pull code out of Markdown files and into JavaScript modules, making it easier to reuse code across pages, write tests and run linters, and even share code with vanilla web applications.

**`observablehq.config.js`** - This is the [project configuration](https://observablehq.com/framework/config) file, such as the pages and sections in the sidebar navigation, and the project’s title.

#### Command reference

| Command           | Description                                              |
| ----------------- | -------------------------------------------------------- |
| `npm install`            | Install or reinstall dependencies                        |
| `npm run dev`        | Start local preview server                               |
| `npm run build`      | Build your static site, generating `./dist`              |
| `npm run deploy`     | Deploy your project to Observable                        |
| `npm run clean`      | Clear the local data loader cache                        |
| `npm run observable` | Run commands like `observable help`                      |

##

</details>

<br>

