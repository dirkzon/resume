# Minimalistic markdown resume

This repository contains the code for my [resume site](https://dirkzon.github.io/resume/), built with [Jekyll](https://jekyllrb.com/), a static site generator that transforms Markdown files into a clean, maintainable webpage. By using Markdown, the resume is lightweight, easy to update, and focused on content rather than styling. [Minima](https://github.com/jekyll/minima) is used as the default theme, providing a simple and minimalist design with basic styling. The resume is based on the template from [markdownresume.app](https://markdownresume.app/), as it provides a professional looking and ATS-friendly design in markdown.

## Hosting

The site is hosted on GitHub Pages, which offers an [easy integration](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll) with Jekyll, and deploys from a branch. This out of the box deployment only supports version [2.5.1](https://pages.github.com/versions/) of Minima. The [`jekyll`](.github/workflows/jekyll.yml) workflow does support version 3 of Minima.

## Export to PDF

To export the resume as a PDF file press `Crtl + P` in any browser. Styling of the exported document is determined by the [`print.css`](/assets//css/print.css) file.

## Spelling check

When the resume in [`index.md`](index.md) is updated the spelling is checked by the [`spelling_check`](./.github/workflows/spelling_check.yml) workflow which uses [PySpelling](https://facelessuser.github.io/pyspelling/). The [`wordlist`](.wordlist.txt) holds a list of words that are ignored during the spellcheck process.

## Local Development

A local development environment is important because to see the final site with Jekyll and Minima, there is no need to constantly push to the repository and wait for GitHub Pages to build and deploy the resume. Github provides a [guide](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll) on how to do this, but it requires the installation of Jekyll, Ruby and Bundler. Instead this repository allows local devlopment with only [Docker](https://www.docker.com/). So, make sure you have Docker running in the background, whether via the docker engine or Docker Desktop, and have [Git](https://git-scm.com/downloads) installed to clone this repository.

### Start

1. Clone the repository.
```sh
git clone https://github.com/dirkzon/resume.git
```

2. Cd into the repo.
```sh
cd resume
```

3. Run the [`docker-compose.yml`](docker-compose.yml) file. It could take a little bit before it starts up.
```sh
docker compose up
```

4. Visit the site on [localhost:4000](http://localhost:4000/).

### Refershing page

The [`index.md`](index.md) markdown file which holds the resume reloads automatically on saving, only the browser must be refreshed. The [`_config.yaml`](_config.yaml) file does not automatically reload, but can be reloaded by restarting the docker container: `docker compose restart jekyll`.

### Stop
1. Stop the docker container.
```sh
docker compose down
```

## Licence

[MIT](./LICENCE)
