# WordPress Heroku

This project is a template for installing and running [WordPress](http://wordpress.org/) on [Heroku](http://www.heroku.com/). The repository comes bundled with:
* [PostgreSQL for WordPress](http://wordpress.org/extend/plugins/postgresql-for-wordpress/)
* [Cloudinary for non ephemeral Image and Video Storage](http://cloudinary.com/)
* [WP Sendgrid](https://wordpress.org/plugins/wp-sendgrid/)
* [Disqus Commenting System](https://disqus.com/)
* [Wordpress HTTPS](https://wordpress.org/plugins/wordpress-https/)

## Development Environment

More to come. Needed to add this to settings.

```

{
    "window.zoomLevel": 0,
    "terminal.integrated.shell.windows": "C:\\Program Files\\Git\\bin\\bash.exe",
    "terminal.integrated.shellArgs.windows": ["-l"]
}

```

This to bottom of profile

```

PATH="${PATH}:/c/Program Files/php7.0.27/"
export PATH

```

Also installed php there, git and visual studio code.

## Installation

Note: This repository is set up to deploy in a local environment using sqlite. The gh-pages version only works with php 7.0.x.

1. Fork [the repository](https://github.com/rhildred/wordpress-heroku) to your own github
1. Add any plugins and themes you need and test
1. Create a new php app on on [Heroku](http://www.heroku.com/).
1. Add a heroku postgres database to your app
1. Deploy to Heroku from github
1. After deployment WordPress has a few more steps to setup the installation by visiting your app and thats it!

## Usage

Because a file cannot be written to Heroku's file system, updating and installing plugins or themes should be done locally and then pushed to Heroku.

Multimedia can also not be stored there for the same reasons. You will need to activate the cloudinary plugin and get your multimedia from cloudinary.

## Updating

Updating is pretty much guaranteed to fail. The postgres database connection won't survive the update. I have tried at various times to fix this and failed. You can see what I have tried on the master branch of this repository. There is definitely some security risk to using this. Only you can decide whether demonstrating your work for free is worth the risk of using outdated software.

Because this can't be updated to newer versions of wordpress newer plugins and themes may also refuse to run. So far this seems to be more of a problem for plugins than themes.

## Deployment optimisation

If you have files that you want tracked in your repo, but do not need deploying (for example, *.md, *.pdf, *.zip). Then add path or linux file match to the `.slugignore` file & these will not be deployed.

Examples:
```
path/to/ignore/
bin/
*.md
*.pdf
*.zip
```

## Wiki (These are links to mhoofman's wiki)

* [Custom Domains](https://github.com/mhoofman/wordpress-heroku/wiki/Custom-Domains)
* [Media Uploads](https://github.com/mhoofman/wordpress-heroku/wiki/Media-Uploads)
* [Postgres Database Syncing](https://github.com/mhoofman/wordpress-heroku/wiki/Postgres-Database-Syncing)
* [Setting Up a Local Environment on Linux (Apache)](https://github.com/mhoofman/wordpress-heroku/wiki/Setting-Up-a-Local-Environment-on-Linux-\(Apache\))
* [Setting Up a Local Environment on Mac OS X](https://github.com/mhoofman/wordpress-heroku/wiki/Setting-Up-a-Local-Environment-on-Mac-OS-X)
* [More...](https://github.com/mhoofman/wordpress-heroku/wiki)
