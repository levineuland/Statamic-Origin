![Origin Theme for Statamic](http://levineuland.com/github/origin-header.jpg)

Origin is a no-style theme for Statamic that gives you a foundation to help you implement your own front-end design as quickly and easily as possible. 

**What it does:**

* Simplifies the theme implementation process
* Introduce useful global variables for common static website content
* Automates site meta and social sharing tags with strong support for Facebook, Twitter, and Google+
* Provides quick setup for Google and Bing Webmaster Tools
  
---

## Basic Installation

1. Clone the repo into the `_themes` directory of your Statamic site  
2. Open your `_config/settings.yaml` file and point to the origin theme: `_theme: Statamic-Origin`  
3. Copy the `Statamic-Origin/_config/sitemeta.yaml` file into your root `_config` folder
4. Copy the `Statamic-Origin/_content/_sitemap.md` file into your root `_content` folder  

---

## Core Theme

The core of the theme includes an empty stylesheet and javascript file for your styling pleasure. A few basic template files are included to give your project a head start:

1. **default.html** - Includes the page title and main content
2. **entry-list.html** - Basic entry listing including title, date, excerpt/content (truncated), categories, and pagination.
3. **entry-detail.html** - Entry detail including title, date, content, categories, and comments (If enabled)
4. **404.html** - Includes the page title and main content
5. **sitemap.html** - Required template for proper sitemap generation
    
---

## Meta Customization

The provided `sitemeta.yaml` file contains all of the core variables used throughout the theme's `<head>` tag to provides search engines and social media sites with the expected meta content. Hooks are in place that allow you to override certain values on a page by page basis.  

### Entry Meta

By adding these field types to your content you can override the default meta information the theme displays to third party sites.

`headline` - The page's headline (Overrides `title`)  
`excerpt` - A summary of the page's content (Overrides `_site_description` or your truncated `content`)  
`keywords` - Relevant page or entry keywords (Overrides `_keywords`)  
`author_gplus_url` - The Google+ url of the page's author  (Overrides `_gplus_url`)  
`author_twitter` - The Google+ url of the page's author  (Overrides `_twitter_id`)  
`social_image` - Image to be displayed on social media sites (Smart cropped to 200x200px, replaces your default share image)

### Title Formatting

The title tag is dynamic, pulling in your site content where possible. The following demonstrates the logic flow for formatting the headlines:

* **Homepage:** Site Name - Title Modifier||Site Description  
* **Internal Page:** Headline||Title - Site Name  

### Description Formatting
The description tag  is customized on page-by-page basis, pulling whichever content is available to fill the tag. In the event your `content` field is empty, your default site description is used.

* **Homepage:** Site Description  
* **Internal Page:** Excerpt||Content||Site Description

*Note:* The content tag is heavily formatted to meet the requirements for meta tags. All HTML tags are stripped, whitespace removed, and the content is truncated to a maxiumum length of 150-200 characters. It's highly recommended you utilize a custom `excerpt`, if possible.

### Share/Favico/Homescreen Images

To ease the pain and suffering of creating all of the many images required for proper social sharing I've created a Photoshop template that helps to automate the process. You can download the PSD file [here](https://layervault.com/levineuland/Origin%20Theme/origin-theme-icons.psd/1). Click the Download link in the upper-right to save a local copy of the file. Follow the instructions inside and export the images from the template into your `_themes/origin/img/meta` directory.

If you are not interested in any of these images, they can be omitted from your site by changing the following tag in your `Statamic-Origin/theme.yaml` file: `meta_images: false`.
    
---

## Additional Features
There are a few optional features that have been added to the theme to aid in site tracking and overall search engine optimization.

### Analytics

Google Analytics will automatically be embedded if two conditions are met:

1. Your `sitemeta.yaml` file has content in the `_ga_tag` field  
2. Your site environment is "live", based on your standard Statamic `settings.yaml` file  

In addition, if you are looking to validate your site with Google Webmaster Tools or Bing Webmaster Tools you can utlize the `_gwt_tag` or `_bing_tag` variables to automatically add the validation meta tag to the top of the site. Once validated, point your webmaster tools accounts at yoursite.com/sitemap so it will crawl your site.


### Facebook App / Admin IDs

Facebook administration and analytics tags can also be inserted by customizing the `_fb_admin` and `fb_app_id` values in your `sitemeta.yaml` file. By adding these tags, administrators will be provided with addtional analytics insights when logged in to Facebook.


### Sitemap (Beta)

Origin provides a simple sitemap file that displays all pages and entries of your site. The sitemap template provides three variables you can use on your pages and entries to override the default settings. Please reference [sitemaps.org](http://sitemaps.org) for information about how to properly set these field's values.

`changefreq` - The frequency that the page is updated  
`lastmod` - The last date the page was modified  
`page_priority` - The crawl priority for that particular page (Overrides default value of 0.5)  
  
---

## Version History
1.0 - Official Release


## Author
Created by Levi Neuland. Have a question or suggestion? Feel free to reach out.  
Twitter: [@levineuland](http://twitter.com/levineuland/)  
Website: [levineuland.com](http://levineuland.com)  
