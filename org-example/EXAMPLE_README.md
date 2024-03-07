# Curriculum Platform

## What is it?

This is a white label multi-tenant platform for us and our code school friends to use to manage our curricula. It's built on top of [Hugo](https://gohugo.io/) and [Netlify CMS](https://www.netlifycms.org/).

- confirm what kind of netlify setup if any someone using this for the first time needs to 

The platform, layout, styles and components are all developed in the Hugo module [/common-theme](/common-theme).

The content is developed in the Hugo module [/common-content](/common-content). This content is all headless blocks. It doesn't create any pages on your site unless you call it somewhere.

Multi-language support is provided by [Hugo's i18n support](https://gohugo.io/content-management/multilingual/).

Each org builds its own Hugo site that uses the common theme and content modules, and then makes any customisations they need and deploys it wherever they want.

## Examples

- [CodeYourFuture](/org-cyf/) => [https://org-cyf-theme.netlify.app/](https://org-cyf-theme.netlify.app/)
- [MigraCode](/org-mcb/) => [https://org-mcb-theme.netlify.app/](https://org-mcb-theme.netlify.app/) (couldn't find an svg logo)

## To build a new site

1. In the root of this repo, navigate to:

```bash
cd org-example
```


Look at the [org-cyf](/org-cyf/) and [org-mcb](/org-mcb/) examples for more details and options.

To customise the css, make a dir `assets/custom-theme` and throw any scss in there. It will be compiled and added last.

To add site logo/s, make a dir and add svgs to `assets/custom-images/site-logo/`. They will be added to the site header.

Add your content to `content/` and customise the site config in `config.toml`. Please contribute any improvements you make back to the common theme and content modules.

For each module you import, add a `replace` directive to your `go.mod` file - if you forget to do this, you won't get live updates to your site when shared content changes. CI will remind you if you forget.

## To locally develop your site

Check [org-cyf/README.md](/org-cyf/README.md) on how to set up your local environment. Once that is done you can `cd` into the site you wish to develop, and run `npm run start:dev` to get a live preview.
