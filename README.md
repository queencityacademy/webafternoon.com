# Your Local Web Afternoon Website

So, you're hosting a Web Afternoon. Great! This repo has everything you need to setup your own local website for your event. Just [fork it to your account](https://help.github.com/articles/fork-a-repo) to get started.


## Setup
There's really no need to setup a local environment if you don't want to. You can commit your changes to the [event info](#adding-your-event-info), [speakers](#adding-your-speakers), and [sponsors](#adding-your-sponsors) files and the site should work fine.

---

### Installing Locally
To get running you'll need to install [Jekyll](http://jekyllrb.com/), [Bower](http://bower.io/), and [Compass](http://compass-style.org/). This assumes you already have

#### Setting up Jekyll

First, make sure you have the Jekyll gem.

    gem install jekyll

Then install the Compass gem.

    gem install compass

Then install Bower. It depends on [Node](http://nodejs.org/) and [npm](http://npmjs.org/). It's installed globally using npm:

    npm install -g bower

*Also make sure that [git](http://git-scm.com/) is installed as some bower packages require it to be fetched and installed.*

**Now that things are installed**

Move into your webafternoon.com directory and start the Jekyll server.

    cd webafternoon.com
    jekyll serve -w

Now you can view your out-of-the-box website by going to [http://localhost:4000](http://localhost:4000).

Notes: We use [Sass](http://sass-lang.com/) installed via Bower.

---

## Adding Your Event Info

Look in the `_data` directory for a file named `event-info.yml`. This is where all the details about the event are stored. It looks something like this:

    ---
    city: Atlanta, GA
    date: 10/02/2014
    time: 13:00
    venue-name: Awesome Theater
    venue-address: 123 Awesome Street, Atlanta, GA 30309
    venue-website: www.awesome-venue.com
    ...

Just change the default info to the info for your event and save the file. Really. That's it.

### Adding your CNAME

Open the `CNAME` file and change *city.webafternoon.com* to use your city as the subdomain.

---

## Adding Your Speakers

Each speaker will get their own page in the `_posts` directory. You'll need to follow the [Jekyll naming convention for posts](http://jekyllrb.com/docs/posts/). It's pretty simple. Just use the date of your event, then the speaker's name. Here's an example.

    2014-10-02-speaker-name.md

### Inside the Speaker's File

Here's an example of a speaker's file. It's written in YAML/Markdown, just like posts in Jekyll.

    ---
    layout: speaker
    category: speaker
    date: 2014-10-02 13:20:00
    title: Spock
    name: Spock
    role: First Mate
    company: Starship Enterprise
    biography: Spock serves aboard the starship Enterprise...
    bio-photo: spock.jpg
    facebook-profile: spock
    twitter-handle: spock
    website-url: www.spock.com
    talk-title: Illogical, Captain
    ---
    Talk description goes here... written in Markdown

**Important:** Do not edit these variables:
- layout
- category

The rest are up to you.
- **date:** The date and time of this speaker's talk
- **title:** Title of the speaker's web page
- **name:** The speaker's name
- **role:** The speaker's role at their company (Visual Designer, CEO, etc.)
- **company:** Where the speaker works
- **biography:** Plain text bio, all on one line - best to keep it under 300 words
- **bio-photo:** The filename of the headshot image you placed in `/img/speakers/`
- **facebook-profile:** Just the part of their profile url that comes after www.facebook.com/
- **twitter-handle:** No @, just the handle
- **website-url:** Just the apex domain name, without http://
- **talk-title:** The title of their talk
---

## Adding Your Sponsors

Sponsors are much easier to add than speakers (phew). Just open the `sponsors.yml` file in the `_data` directory. Each sponsor entry looks like this.

    - name: Nine Labs
      url: ninelabs.com
      image: ninelabs.png

Just add the sponsors in the order you want them to appear. The fields are pretty self-explainatory, but here's an explaination anyway:

- **name:** The name of the company
- **url:** The URL of their website, without http://
- **image:** The filename of the image you placed in `/img/sponsors/`

---

## About Images

- Speaker Headshots: We ask speakers for a color image 600x600 or larger. You should resize/crop them to 200x200.
- Sponsor Images: Look in the `/img/source/` directory for a file named `sponsor-logo-master.psd`. This file has the guides in place for sizing of the sponsor images.
