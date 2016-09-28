# Command Line Guide

An intro to the command line for total newbies.

# Development

This site is built with [Middleman] and [RevealJS].

## Dev Process

Prereq: install Ruby. Once you have that, clone this repo, `cd` to it, and run

    bundle install

Then, once all of the dependencies are installed, run the site locally with

    bundle exec middleman

and then visit `localhost:4567` in your browser.

Now when you edit the files in the `source` folder, you'll automatically see the changes.

## Deployment

Once things look good and you want to deploy, run

    bundle exec middleman build

and a static version of the site will be compiled into the `build` directory.

The deployed site is hosted on AWS S3 and CloudFront. The deploy strategy was
taken from [Atomic Object]. Here's how it works:

You'll need a "config.yml" file with the S3 bucket, CloudFront ID, and AWS
creds. Then run

    bundle exec rake aws:deploy

And the files in the `build` directory will be pushed to S3 and the CloudFront
distribution will be invalidated. Deployed!

  [Middleman]: https://middlemanapp.com/
  [RevealJS]: https://github.com/hakimel/reveal.js/
  [Atomic Object]: http://spin.atomicobject.com/2013/09/23/deploy-aws-s3-rake/
