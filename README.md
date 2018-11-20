# Starting with Local Development

## Options: Local By Flywheel, MAMP and Docker, oh my!

The easiest way I've found to start local development is through Local by Flywheel. The software is provided by Flywheel, a managed WP host, but no purchase is required.

The most popular historical method has been using a suite called MAMP for Mac, or WAMP or LAMP, for Windows and Linus respectively. I recommend this as a fallback if Local by Flywheel does not successfully load on your computer.

There are other methods of local development out there - including using Docker. Feel free to experiment with these if you'd like - but for this tutorial:

### I will be demonstrating with Local by Flywheel: Please follow these [instructions for instructions](https://getflywheel.com/layout/local-wordpress-development-environment-how-to/).

Again, if you have difficulty with Local by Flywheel, I suggest using [MAMP](https://skillcrush.com/2015/04/14/install-wordpress-mac/) or [WAMP](https://www.wpbeginner.com/wp-tutorials/how-to-install-wordpress-on-your-windows-computer-using-wamp/).

## Getting to know your site

The files for your site will, by default, be located in a folder called `Local Sites` in your home directory. Go ahead and find that now. The path to find your WP files will be: `Local Sites > Your Site Name > app > public`

Within the `public` folder there will be `wp-admin`, `wp-includes`, and `wp-content`. It is this last folder that is most important for the purposes of this tutorial.

In the `wp-content` folder you'll find the `themes` folder. This contains all the themes that you'll find on the themes tab of our WP Admin.

Not certain what I'm referring to? Let's explore first:
1. Go to Local by Flywheel where you created your site
2. Make sure the site is started
3. Click on the `ADMIN` button -OR- click on `VIEW SITE` and then type `/wp-admin` behind your `*.local` URL
![Click Admin](/images/1-click-admin.png "Click Admin")
4. Log in to your WP admin dashboard with the credentials you used when creating your site
5. On the left hand menu, you'll see a section called `Appearance`, hover over this and click on `Themes`
![Go to Themes](/images/2-themes.png "Go to Themes")
6. You'll see several themes here, your current one says `Active`

## Adding a new theme

You can feel free to try out different themes here by clicking on `Activate`. You probably won't see too much happen, but there is a lot to add to your pages with
![Activate](/images/3-activate.png "Activate")
So, now you've seen where your themes live in the WP files and in the WP Admin, let's manually add another theme:
1. If you have a theme you like, download it now, or go to [Antreas](https://www.demos.machothemes.com/antreas/) or [download the theme here](/antreas-lite.zip)
2. Unzip the theme contents, and copy the whole folder into your theme directory
![Copy Theme](/images/4-copy-theme.png "Copy Theme")
3. Go to your WP Admin theme page and click refresh - notice now you have the them `Antreas`
4. Go ahead and activate this new theme

If you navigate to your website, you'll notice that the theme has now changed. The next step is **optional** and you don't want to do this on a site that has content on it already:
1. Click on the theme and go to `About Antreas`
![Antreas](/images/5-antreas.png "Antreas")
2. Go to the tab titled `Recommended Actions`
![About Antreas](/images/6-about-antreas.png "About Antreas")
3. Click on `Import Content` - this will load in content and custom post types
![Recommended](/images/7-recommened.png "Recommended")
4. Now go back to your website and click refresh and check out the change!

You can feel free to mess around with the theme if there is time. Otherwise, we will begin our migration to live process.

## Migrating to Live


