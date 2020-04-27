# Description
Explains how to deploy the category lists, articles, amp

## To do when deploy is done:
- subscribe
- rename projects, ez frontend to admin_gui, and then blog_view to visitor_gui
- subscribe email marketing
- amp deployed and compressed
- amp minify images
- test auth mode
- test amp alternative lang is not added
- amp json ld
- review article
- test facebook counts still okay
- share count
- test article suggestion hover
- test amp footer
- generate sitemap
- move gitignore in root
- test other langs
- add public files to d.novoresume.com and do old images seo redirects
- test crsf token
- improve page handler to more generic

## To do test when deploy:
- allow Access-Control-Allow-Origin https://d.novoresume.com/https://novoresume.com
- auth vs non-auth page
- implement json-ld
- test field limits
- test fb, linkedin, twitter metadata
- remove seo page lists
- test all shares links
- test non seo images
- test category is selected in uri + documentation other langs
- test everything is replace in terms of tags
- year
- test footer
- all lists, and load async all articles if more than 12
- test font loaded
- test all code is minified(includign content blocks)
- test all metadata + json is setup
- test language metadata
- test articles look the same
- test seo important images vs non
- test amp compress



## to do explain how to serve pages

## How to start

To compile files:

- npm node_modules
- grunt lib
- grunt (for prod)
- grunt defaultDev (dev mode, only **us** language supported, no compression)
- grunt watch (watch prod)
- grunt watch:dev (watch dev)

To play with test-index.js you need to:
- create a folder **certificates**
- add **private.key** and **public.crt**

## Notes:
- private>novo_lib
Has generic components of frontend for novoresume.com
- public>images
Contains generic images needed for the blog pages
- public>client
Contains the scripts(in lib and novo)
- public>nwf
Contains fonts


## Dependencies:
- Novobook Repo in root folders (novoresume)


## Important
When replacing meta tags, do it globally, as one tag my appear multiple times in the article, the only exception is when we inject json-ld or CSS
- Example of tags that appear multiple times; **__novo_article_meta_description__**,**__novo_article_meta_title__** (they are used for seo title, twitter metadata, facebook metadata)
- Example replace only once: **__novo_article_json_ld__**

## Auth vs Non Auth

IF users are auth we should serve the auth page, if not we should serve the non-auth,
For AMP we use the non-auth page only


## Article List Generate
- write documentation what is needed!!!!!
- uri img should be based on document + guidelines cdn + mention mobile version for suggestions
- date based on last update settigns return in given format

!!!!!!!!!!!! setup article header,keywords,desc,title!!!!!!!!!!!!!!!!!!!!!

- **__novo_article_category_text__** 
   - category text
   - examples: Resume & CV Writing Tips, Cover Letter Writing Tips

- **__novo_code__family_uri__** 
   - family category of the article uri
   - examples: /create-cover-letter, /write-resume-cv, /find-a-job
   - basically the different article categori list unique part of the uri

- **__novo_article_canonical__** 
   - Canonical Link to the article
   - exampels: https://novoresume.com/career-blog/how-to-write-a-resume-guide


## Article Page Generate

### Article Ajax Calls

Setup reviews article

- GET /authors
<pre> Get all authors </pre>

### Article Replace Tags

- **__novo_code__family_uri__** 
   - family category of the article uri
   - examples: /create-cover-letter, /write-resume-cv, /find-a-job
   - basically the different article categori list unique part of the uri

- **__novo_article_category_group__** 
   - family category
   - examples: Cover Letter Writing Tips,Personal Development
 

- **__novo_article_canonical__** 
   - Canonical Link to the article
   - exampels: https://novoresume.com/career-blog/how-to-write-a-resume-guide

- **__novo_article_meta_description__** 
   - seo article description

- **__novo_article_meta_title__** 
   - meta title

- **__novo_article_meta_url__** 
   - the full url of the article(including https and novoresume.com)
   - example: https://novoresume.com/career-blog/how-to-write-a-resume-guide

- **__novo_article_img__**
   - full url pointing to article background image
   - example: https://d.novoresume.com/images/blogs/how-to-write-resume/bg-cover-article.png
   - example:https://d.novoresume.com/images/blogs/**article_id**/bg-cover-article.**bg_file_extension**

- **__novo_article_img_extension__** 
   - article image extension (useful for seo/share metadata)
   - example: png,jpeg,jg

- **__novo_article_img_width__**
   - the size of the artigle bg width in numeric value
   - exampple: 2483
   
- **__novo_article_img_height__**
   - the size of the artigle bg width in numeric value
   - exampple: 1299

- **__novo_article_keywords__**
   - Seo keywords, social sahre metadata
   - Max 1,2 keywords
   - Max 80 characters 
   - remove quotes from keywords, and make sure there are utf8 frielndly
   - examples: resume templates, how to write a resume

- **__novo_article_meta_title__**
   - Seo tile,page title, social sahre metadata
   - **adviced** 60, max 80 characters
   - remove quotes from keywords, and make sure there are utf8 frielndly
 
- **__novo_article_meta_description__**
   - Seo description, seo title, social sahre metadata
   - max 160 characters
   - remove quotes from keywords, and make sure there are utf8 frielndly

- **__novo_article__header1__**
   - Html + title of article(visible to user)
   - it contains h1
   - example code: 

- **__novo_article_date__**
   - date when the article was created(or updated based on the settings)
   - year month(in words) day (use 0 if the date is for example 01)
   - Examples:
   - 2019 January 8
   - January 8(if current year) 
   - Today (if date is today) 

- **__novo_article__min__**
    - number of minutes to read the article

- **__novo_article_json_ld__**
   - json-ld data for the article
   - we want images here, reviews for seo, list of images seo important images etc


- **__novo_author_id__img__**
   - author id image

- **__novo_author_full_name__**
   - author full name

- **__novo_author_title__**
   - author title

- **__novo_article_optional_bg_css__**
   - optionale article source imagem if not place emptry string
   - example:
```
<section class="holder-bg-sr"><div class="article-sc"><i>Source:${bg_src}</i></div></section>
```
- **__novo_article_content_blocks__**
   - the main content of the article, text, lists, images etc
   - the content/html should be compressed

- **<style\>**
   - inserts extra css, for example mobile, medium screen background source
   - notice we do not close the tag, as the closing tag is already in the code
   - make sure no extra whitespaces will be included **we want the final file to stay compressed**
   - example:
```
<style >
#holder-article-bg #article-bg{background:url("<cdn-location/>/images/blogs/${article_id}/bg-cover-article.${bg_extension}") ${bg_css};}
@media screen and (max-width:1650px){#holder-article-bg #article-bg{ background:url("<cdn-location/>/images/blogs/${article_id}/bg-cover-article-mid.${bg_extension}") ${bg_css};}}
@media screen and (max-width:650px){ #holder-article-bg #article-bg{background:url("<cdn-location/>/images/blogs/${article_id}/bg-cover-article-mobile.${bg_extension}") ${bg_css};}}
```



## Article AMP Generate
- to do setup
- amp refresh every 2 hours? or make it fresh all of the time

### Article ANP Replace Tags
use code from old project
add special cases:amp__novo_article_top__, author tags, style tag,__novo_article_optional_bg_cs etc
!!!! fix amp transatiosn for author data
- **same tags as in ### Article Replace Tags** + the follwoing:
- **__novo_article_top_amp__**
- **__novo_amp_reviews__**
- **__novo_copy_write_year__**
- **__novo_article_amp_suggestions__**
