# limityjsmemy.cz
Public statically generated website of Czech grassroots climate justice movement.


The site is based on [Hugo](https://gohugo.io) static site generator. Were trying to use [Zen](https://github.com/frjo/hugo-theme-zen) theme as a base, let's see if it will work. The site will be hosted on Github Pages during the development.

## Content structure
We are using these content types:

- page
  - ordinary static page without specific date
  - it's important to specify `url` in the frontmatter, so the URL doesn't contain word `page`,
- post
  - content with a date of publishing, optionally also allows publishing in the future
- event
  - content with date of event. It gets unpublished day after the event ended
- featured
  - isn't published on its own URL, 2 newest items are published on the front page.

## Development

We're using 2 branches:

- `master` contains site code
- `gh-pages` contains site build - the files, that will be actually served to the visitors

Every commit to `master` launches a build according to workflow defined in `.github/workflows/gh-pages.yml` file.

## Hugo update
There are several places, where `hugo` is used:
* local installation. Can be done e.g. by `brew install hugo`
* GitHub workflow. Can be set in `.github/workflows/gh-pages.yml`
* Forestry.io previews. Can be set in  `.forestry/settings.yml`

When updating `hugo` please follow this way:
* update your local installation and check that site is still building fine
* Update both Github and Forestry settings and check that the site is still working fine in both places
* Let other know, that the upgrade was done, so they can updatet heir local installations
