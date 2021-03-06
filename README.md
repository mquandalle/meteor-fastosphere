# Fastosphere

**Fastosphere** is a [website](http://fastosphere.meteor.com) and a [CLI](http://en.wikipedia.org/wiki/Command-line_interface) to search Meteor packages really quickly thanks to [Algolia](http://algolia.com) search engine.

## Website

http://fastosphere.meteor.com provides you a very quick and easy way to find Meteor packages. You'll have basic information like package name, description, latest version, latest release date, GitHub Url, number of GitHub stars.

It's an alternative to [Atmosphere](https://atmospherejs.com). **The main advantages are it's freesoftware and a lot faster than Atmosphere.**

## Command Line Interface (CLI)

The command line has a few really cool features.

### Install

    sudo npm -g install fastosphere

or if you have an older version

    sudo npm update -g

### Search

It's an alternative to `meteor search`. **The main advantage is it gives you real information about packages to help you to choose which one you want to install** (GitHub stars, sort by score, GitHub Urls). So you don't have to leave your terminal to find which package to install.

If you want to compare, do this test:

    $ meteor search moment
    $ npm -g install fastosphere
    $ fastosphere search moment -l

![3__acemtp_macbook-pro-de-vianney____m_meteor-fastosphere-changelog-test__zsh_](https://cloud.githubusercontent.com/assets/103561/5565008/f89a4d1c-8ede-11e4-8baf-1ff3d667e907.png)

You can also test:

    $ fastosphere search mo           # lazy
    $ fastosphere search m            # really lazy
    $ fastosphere search moomment     # dyslexic
    $ fastosphere search moment -n 2  # 2 results
    $ fastosphere search moment -g    # GitHub Urls (⌘ + click on the url to open the url)
    $ fastosphere search moment -l    # long format (more info)

### Changelog

With `fastosphere`, you can see what is new in the packages (and Meteor) you use in a Meteor project. Go inside a Meteor project and type:

    $ fastosphere

It'll display all changelogs between your current version and the most up to date.

If you want to do a test from scratch:

    $ git clone https://github.com/acemtp/meteor-fastosphere-changelog-test.git
    $ cd meteor-fastosphere-changelog-test
    $ fastosphere

![22__acemtp_macbook-pro-de-vianney____m_meteor-fastosphere-changelog-test__zsh__and_fastosphere_meteor_com](https://cloud.githubusercontent.com/assets/103561/5564995/7b741246-8ede-11e4-8149-a437297ccf39.png)

You can also use `fastosphere -v` to have more information.

It'll work only for packages who have a *valid* GitHub Url inside `package.js` and a CHANGELOG.md or a History.md (case insensitive) in the root folder of the GitHub project. If you have some packages, you can check the status on the [fastosphere website](http://fastosphere.meteor.com), it'll tell you if something is wrong. If you log on with your github account, you'll be able to force refresh the package so fastosphere will try to get the github/changelog file again (it's not reactive, you'll have to refresh the webpage to see if the error message left).

So if you like the feature, create changelogs or ask package maintainers to create them.


### Add

Do you feel lucky? You can use `fastosphere` to install a Meteor package without the need to know the name of the maintainer or which one if the best one.

You want to install `momentjs:moment`? Just do:

    $ fastosphere add mo

It'll install the first result of the search `fastosphere search mo`.


## Fork this project

If you want to fork this project, please change analytics ID with yours in `<head>` part of `client.html`. Also `cp settings.example.json settings.js`, create an account on Algolia and fill your `settings.json` with the Algolia generated keys. Do the same for github api keys.
