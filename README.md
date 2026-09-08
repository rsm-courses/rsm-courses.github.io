# rsm-courses.github.io

Source for the RSM Courses site, built with Jekyll and hosted on GitHub Pages.

## Local preview (optional)

You don't need Ruby/Jekyll installed locally — GitHub Pages builds it
automatically on push. But if you want to preview locally:

    gem install bundler jekyll
    bundle init
    bundle add jekyll-remote-theme jekyll-relative-links
    bundle exec jekyll serve

Then open http://localhost:4000

## Publishing

1. Push this repo's contents to the `main` branch of `rsm-courses.github.io`.
2. In the repo's Settings → Pages, set Source to the `main` branch (root).
3. Live within a minute or two at https://rsm-courses.github.io

## Adding a new course

Create a new file in `_courses/`, e.g. `_courses/my-new-course.md`, with the
same frontmatter shape as the others (`title`, `summary`, `status`,
optionally `partners`). It shows up automatically on the homepage and
`/courses/`.