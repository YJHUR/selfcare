# AGENTS.md

## Cursor Cloud specific instructions

### Project overview
This is a Jekyll 4.2.2 static blog ("SelfCare Blog") using the LightSpeed theme. It generates a Korean-language self-care/wellness blog served from the `/selfcare` base path. There are no backend services, databases, or Docker dependencies.

### Ruby version
The `Gemfile` pins `ruby "3.0.2"`. On Ubuntu 24.04 this version does not compile against the system OpenSSL 3; `rbenv` with the latest `ruby-build` (which automatically downloads and builds OpenSSL 1.1) resolves this. Ruby 3.0.2 is installed at `~/.rbenv/versions/3.0.2`.

### Running the dev server
```
eval "$(rbenv init -)"
bundle exec jekyll serve --host 0.0.0.0 --port 4000
```
The site is served at `http://localhost:4000/selfcare/`.

### Build
```
bundle exec jekyll build
```
Output goes to `_site/`. A non-fatal warning about a missing `autopage_collection.html` layout is expected and harmless.

### Lint / Tests
There is no linter or test suite configured in this repository. Verification is done by building the site (`bundle exec jekyll build`) and visually inspecting the output.

### Adding a blog post
Create a markdown file under `<category>/_posts/` following the `YYYY-MM-DD-title.md` naming convention with YAML front matter (`layout: post`, `title`, `date`, `categories`). The dev server auto-regenerates on file changes.
