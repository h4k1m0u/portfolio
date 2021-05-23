# Setting up Jekyll on Ubuntu 20.04
## Prerequisites
```console
$ sudo apt install ruby ruby-dev
$ ruby -v
$ gem -v
$ gcc -v
$ make -v
```

## Install package manager in user directory
```console
$ gem install -V --user-install bundler
```

## Create a Gemfile for dependencies
```console
$ vim Gemfile

  source 'https://rubygems.org'
  gem 'jekyll'
```

## Install dependencies with bundler
```console
$ bundle install
```

## Add gems user directory to path
In order for bundler to find executables of installed gems:

```console
$ vim ~/.bashrc

  GEM_HOME=/home/hakim/.gem/ruby/2.7.0
  PATH="$PATH:$GEM_HOME/bin"
```

## Build & run jekyll server
Ensure the right version of the dependency is run with bundler:

```console
$ bundle exec jekyll serve
```

Generated files will be stored inside `_site/` folder.

## Publish on Github
Deployment of a static website to Github-page was already covered here [here][github-deployment]. It was built with the following command (locally, `jekyll serve` won't be affected):

```console
$ bundler exec jekyll build --baseurl /portfolio
```

[github-deployment]: https://github.com/h4k1m0u/snake/tree/master/client#deployment-on-github


# Resources
- [Step-by-step tutorial][tutorial].

[tutorial]: https://jekyllrb.com/docs/step-by-step/01-setup/


# Examples
Websites made with Jekyll:

- [Clangd website][clangd-website]

[clangd-website]: https://github.com/llvm/clangd-www/
