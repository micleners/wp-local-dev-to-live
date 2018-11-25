Welcome to my tutorial on setting up local development and migrating to live. This was written for our local [Des Moines WordPress Meetup](https://www.meetup.com/wordpressdsm/). If you are in the area come check us out! This was written late 2018, so if the instructions have gotten out of date, but you find it useful, feel free to submit a PR.

# Part 1: Setting Up Local Dev

## Options for Local Dev: Local By Flywheel, MAMP and Docker, oh my!

The easiest way I've found to start local development is through Local by Flywheel. The software is provided by Flywheel, a managed WP host, but no purchase is required.
### I will be demonstrating with Local by Flywheel: Please follow these [instructions for installation](https://getflywheel.com/layout/local-wordpress-development-environment-how-to/).

The most popular historical method has been using a suite called MAMP for Mac, or WAMP or LAMP, for Windows and Linus respectively. I recommend this as a fallback if Local by Flywheel does not successfully load on your computer.
#### If you have difficulty with Local by Flywheel, I suggest using [MAMP](https://skillcrush.com/2015/04/14/install-wordpress-mac/) or [WAMP](https://www.wpbeginner.com/wp-tutorials/how-to-install-wordpress-on-your-windows-computer-using-wamp/).

There are other methods of local development out there - including using Docker. Feel free to experiment with these if you'd like - but for this tutorial:

# Part 2: Exploring WP Files and Database

## WordPress Architecture

This info graphic contains the overall architecture and a preview of each component that builds up your WP Site:
<br>
<br>
<img src="/images/0-wordpress-architecture.png" title='WP Architecture' alt='WP Architecture' height="100%" width="100%">
<br>

The key players in a WordPress site is the `Database` and the `Site Files`. You can download a fresh copy of the WP Files from [WordPress.org](https://wordpress.org/download/) or [download the files here](/wordpress-4.9.8.zip).

Within the main folder you'll find important files like `wp-config.php` for database setup, `.htaccess` for server configuration, and `index.php` for initializing the website.

You'll also find three folders in the parent directory: `wp-admin`, `wp-includes`, and `wp-content`. Here is one approach to unpacking these folders and the database:
<ul>
  <li>`wp-admin` contains the files that build up the `Admin Dashboard`</li>
  <li>The `Admin Dashboard `allows you to set and customize themes and add content to your WP Site</li>
  <li>The content (posts, pages, etc) and settings in the `Admin Dashboard `get saved into the `Database`</li>
  <li>The themes, plugins, and other uploads are stored in the `wp-content` folder</li>
  <li>The `wp-includes` folder contains core WP files</li>
  <li>The site that you see when you navigate to the URL in your browser:
  <ul>
    <li>Renders the contents from the `Database`</li>
    <li>To the specifications set in the `Admin Dashboard`</li>
    <li>With the help of the `WordPress Files`</li>
  </ul>
</ul>

## Checking out our Database

As discussed, the `Database` contains all the content and settings for your website. I'll show you how to locate your DB in Local by Flywheel. If you are familiar with investigating databases feel free to poke around, but be careful! Many changes here are irreversible.
<ol>
  <li>In Local by Flywheel again, click on the `DATABASE` tab</li>
<img src="/images/8-database.png" title='Database Management' alt='Database Management' height="50%" width="50%">
  <li>Click on the `ADMINER` button</li>
<img src="/images/9-adminer.png" title='Adminer' alt='Adminer' height="50%" width="50%">
  <li>Here you can see what content is kept in the database: Posts, Pages, Comments, Users, etc</li>
<img src="/images/10-databases.png" title='Databases' alt='Databases' height="50%" width="50%">
  <li>If you are familiar with SQL you can perform queries here</li>
  <li>You can also import and export your database with this interface</li>
  <li>Together the WP files (the folder that contains `wp-content`, `wp-includes` and `wp-admin`) and the database contain all the information in your WP site</li>
</ol>

## Getting to know your site

The files for your site will, by default, be located in a folder called `Local Sites` in your home directory. Go ahead and find that now. The path to find your WP files will be: `Local Sites > Your Site Name > app > public`

Within the `public` folder there will be `wp-admin`, `wp-includes`, and `wp-content`. It is this last folder that is most important for the purposes of this tutorial.

In the `wp-content` folder you'll find the `themes` folder. This contains all the themes that you'll find on the themes tab of our WP Admin.

# Part 3: Investigating Local Site and Updating theme

Let's check out our local site from the `Admin Dashboard`:
<ol>
  <li>Go to Local by Flywheel where you created your site
  <li>Make sure the site is started
  <li>Click on the `ADMIN` button -OR- click on `VIEW SITE` and then type `/wp-admin` behind your `*.local` URL
<img src="/images/1-click-admin.png" title='Click Admin' alt='Click Admin' height="50%" width="50%">
  <li>Log in to your WP admin dashboard with the credentials you used when creating your site
  <li>On the left hand menu, you'll see a section called `Appearance`, hover over this and click on `Themes`
<img src="/images/2-themes.png" title='Go to Themes' alt='Go to Themes' height="50%" width="50%">
  <li>You'll see several themes here, your current one says `Active`
</ol>

## Adding a new theme

You can feel free to try out different themes here by clicking on `Activate`. You probably won't see too much happen, but there is a lot to add to your pages with
<br><img src="/images/3-activate.png" title='Activate' alt='Activate' height="50%" width="50%"><br>
So, now you've seen where your themes live in the WP files and in the WP Admin, let's manually add another theme. Either brows around on the internet, or use theme provided here:

<ol>
  <li>If you have a theme you like, download it now, or go to <a href="https://www.demos.machothemes.com/antreas/">Antreas</a> or <a href="/antreas-lite.zip">download the theme here</a></li>
  <li>Unzip the theme contents, and copy the whole folder into your theme directory</li>
<img src="/images/4-copy-theme.png" title='Copy Theme' alt='Copy Theme' height="75%" width="75%"></li>
  <li>Go to your WP Admin theme page and click refresh - notice now you have the them `Antreas`.</li>
  <li>Go ahead and activate this new theme.</li>
</ol>

If you navigate to your website, you'll notice that the theme has now changed. The next step is **optional** and you don't want to do this on a site that has content on it already:
<ol>
  <li>Click on the theme and go to `About Antreas`</li>
<img src="/images/5-antreas.png" title='Antreas' alt='Antreas' height="50%" width="50%">
  <li>Go to the tab titled `Recommended Actions`</li>
<img src="/images/6-about-antreas.png" title='About Antreas' alt='About Antreas' height="50%" width="50%">
  <li>Click on `Import Content` - this will load in content and custom post types</li>
<img src="/images/7-recommended.png" title='Recommended' alt='Recommended' height="50%" width="50%">
  <li>Now go back to your website and click refresh and check out the change!</li>
</ol>

You can feel free to mess around with the theme if there is time. For now, we will take a short introduction to the database.

# Part 4: Migrating to Live

While you can manually migrate your website by copying your files and exporting your DB - we will use a plugin to make this easier. In the tutorial I will be demonstrating using [Duplicator with this tutorial](https://premium.wpmudev.org/blog/guide-to-migrating-localhost-wordpress-to-live-site/), but the alternative is  [WP All-In-One-Migration](https://researchasahobby.com/migrate-big-website-new-domain-subdomain-free-testing-easiest-way/).

If you have trouble downloading your duplicator files (or just want to see where the files got saved), navigate to the `public` folder we looked at earlier with `wp-content`, `wp-includes` and `wp-admin`. Within this folder you will find `wp-snapshots` - the two files you need from in here are `...archive.zip` and the `...installer.php`.
<br>
<img src="/images/12-duplicator-files.png " title='Duplicator Files' alt='Duplicator Files' height="50%" width="50%">
<br>

Getting the above files onto your WP site is probably the most challenging part of this entire migration process. The following steps may help:
<ol>
  <li>Go to your hosting site > cPanel > File Manager -OR- FTP into your file system</li>
  <li>Navigate to your `public_html` directory, where you may or may not already have WordPress installed</li>
  <li>Create a new folder called `test-site` (name doesn't matter, but it can't have spaces!)</li>
  <li>Upload both the installer and the .zip file in this directory</li>
  <li>Navigate to the URL: `your-domain.com/test-site/installer.php`</li>
  <li>Continue to follow the instructions</li>
</ol>

If you are struggling with getting the Duplicator files up to your website. You can try to use [WP All-In-One-Migration](https://researchasahobby.com/migrate-big-website-new-domain-subdomain-free-testing-easiest-way/).

# Closing: Best of Luck!

This is where our tutorial ends. I hope that you learned something useful! If you have questions or suggestion on this tutorial, my email is mb.johnsonbece@gmail.com and please come checkout our local [Des Moines WordPress Meetup](https://www.meetup.com/wordpressdsm/)!
