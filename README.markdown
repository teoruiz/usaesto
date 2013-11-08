## Installation

```
$ gem install jekyll sass i18n
```

## Running for development
```
$ jekyll serve --watch
```
In another terminal:

```
$ rake sass
```

## Building for deployment
```
$ jekyll build
$ sass --update assets/sass:assets/css
```