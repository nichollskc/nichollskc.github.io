---
title:  "Blog setup"
toc: true
toc_sticky: true
date:   2020-03-06 12:07:25 +0000
categories:
  - blogging
---

I followed [this](https://www.linode.com/docs/applications/project-management/jupyter-notebook-on-jekyll/) guide to using jupyter notebooks with Jekyll, and also [this guide](https://help.github.com/en/github/working-with-github-pages/creating-a-github-pages-site-with-jekyll) to using Jekyll for github pages.

# Jekyll Setup

To install Jekyll I needed a working version of make and a recent version of Ruby.

On a mac, it is best to install ruby within [Ruby Version Manager](https://rvm.io/).

## Install Ruby with RVM

Get RVM and rails:

```>> curl -sSL https://get.rvm.io | bash -s stable --rails```

Install Ruby:

```bash
>> rvm install ruby
...
Install of ruby-2.6.3 - #complete
```

Ask rvm to make this version of Ruby the active one:

```bash
>> /bin/bash --login
Restored session: Thu  5 Mar 2020 08:24:39 GMT
>> rvm use 2.6
Using ~/.rvm/gems/ruby-2.6.3
>> which ruby
~/.rvm/rubies/ruby-2.6.3/bin/ruby
>> ruby -v
ruby 2.6.3p62 (2019-04-16 revision 67580) [x86_64-darwin18]
```

## Install Jekyll

`>> gem install jekyll bundler`

# Example blog

Create an example

```bash
jekyll new exampleblog
cd exampleblog
bundle exec jekyll serve --host=0.0.0.0
```

Go to `http://0.0.0.0:4000/`

# Github pages setup

## Creating Jekyll repository

I created a new repository with the name `<user>.github.io`.

```bash
git clone https://github.com/nichollskc/nichollskc.github.io.git
cd nichollskc.github.io/
jekyll new ./
```

### Editing Gemfile

There is an instruction in the Gemfile telling us to change a few lines to have things set up with GitHub pages.

The GitHub pages guide also tells us to include the dependency version of github-pages, which you find at [this site](https://pages.github.com/versions/) and when I checked it was '204'.

```>> vim Gemfile```

Originally:

```ruby
# This will help ensure the proper Jekyll version is running.
# Happy Jekylling!
gem "jekyll", "~> 4.0.0"
# This is the default theme for new Jekyll sites. You may change this to anything you like.
gem "minima", "~> 2.5"
# If you want to use GitHub Pages, remove the "gem "jekyll"" above and
# uncomment the line below. To upgrade, run `bundle update github-pages`.
# gem "github-pages", group: :jekyll_plugins
```

After edit

```ruby
# This will help ensure the proper Jekyll version is running.
# Happy Jekylling!
# gem "jekyll", "~> 4.0.0"
# This is the default theme for new Jekyll sites. You may change this to anything you like.
gem "minima", "~> 2.5"
# If you want to use GitHub Pages, remove the "gem "jekyll"" above and
# uncomment the line below. To upgrade, run `bundle update github-pages`.
gem "github-pages", "~> 204", group: :jekyll_plugins
```

### Changing name of index.markdown

As described in the 'Errors' section below, it is important for GitHub pages to see an index.md file or index.html file.

`mv index.markdown index.md`

## Testing

`bundle exec jekyll serve --livereload --open-url`

This command will launch a locally hosted version of the website and update it whenever changes are made (except changes to `_config.yml`).

## Testing online

Push code to github:

`git add . && git commit && git push`

The site should now be viewable at `https://<user>.github.io/` e.g. `https://nichollskc.github.io/`

## Change theme

I switched to the theme [here](https://github.com/mmistakes/mm-github-pages-starter). Probably it would have been easier just to start with a clone of this repo.

# Errors

Here is a record of the various errors I encountered and how I fixed them.

## Errors in Jekyll installation

### Don't run inside a conda environment

```bash
Error running '__rvm_make -j12',
please read ~/.rvm/log/1583487087_ruby-2.6.3/make.log

There has been an error while running make. Halting the installation.
```

In this file was the error:

```bash
/anaconda3/envs/jupyter_bic_comp/bin/x86_64-apple-darwin13.4.0-ar: illegal option -- n
```

It seems that it was using the compiler from my conda environment.

### GPG

Retrying the command to install RVM I then got this warning about missing GPG software to validate the download. It seemed to install anyway.

```bash
Downloading https://github.com/rvm/rvm/archive/1.29.9.tar.gz
Downloading https://github.com/rvm/rvm/releases/download/1.29.9/1.29.9.tar.gz.asc
Found PGP signature at: 'https://github.com/rvm/rvm/releases/download/1.29.9/1.29.9.tar.gz.asc',
but no GPG software exists to validate it, skipping.
...
Upgrade of RVM in ~/.rvm/ is complete.
```

### `which rvm` failing

Initially `which rvm` would return nothing. RVM adds a command to your .bashrc file to add itself to the path. Either do source ~/.bashrc or just start a new shell to have easy access to rvm.

### "RVM is not a function"

```bash
>> rvm use 2.6

RVM is not a function, selecting rubies with 'rvm use ...' will not work.

You need to change your terminal emulator preferences to allow login shell.
Sometimes it is required to use `/bin/bash --login` as the command.
Please visit https://rvm.io/integration/gnome-terminal/ for an example.
```

As the error message suggests I need to use the following command:

```bash
>> /bin/bash --login
Restored session: Thu  5 Mar 2020 08:24:39 GMT
>> rvm use 2.6
Using ~/.rvm/gems/ruby-2.6.3
```

https://stackoverflow.com/questions/23963018/rvm-is-not-a-function-selecting-rubies-with-rvm-use-will-not-work

## Errors in building blog

### Could not find gem github-pages

```bash
>> bundle exec jekyll serve --host=0.0.0.0 docs/
Could not find gem 'github-pages (~> 204)' in any of the gem sources listed in your Gemfile.
Run `bundle install` to install missing gems.
```

I fixed this with `bundle update jekyll`

### GitHub pages only displaying README.md

By default GitHub will host the whole repository, or if it finds an index.html file or index.md file it will prioritise that. Since the index file was named index.markdown it wasn't hosting the site properly, and instead just displaying the README file instead.

