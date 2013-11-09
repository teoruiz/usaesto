## Installation

```
$ gem install jekyll sass i18n
```

## Running for development
```
$ jekyll serve -s jekyll_site/ --watch
```
In another terminal:

```
$ rake sass
```

## Building for deployment
```
$ sass --update jekyll_site/assets/sass:jekyll_site/assets/css
$ jekyll build -s jekyll_site/
```