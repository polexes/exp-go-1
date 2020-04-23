Test prepare minify trnaslations production(after all is finished)
prod test all data in inserted
Produce Libraries Needed
Produce UtilJs and common
Produce header common html
Produce Article Page
Produce Cateogry List page
When deploy, test all meta data, og urls etc
Lowercase/not rules communicate them
Produce Suggestions
Generate AMp take some of the needed code form the old one
Produce Subscirbe Email Marketing
Produce Article Reviews
mention careful utf8 & cahracters etc
Test language setup for us and da
test compress html

test footer
dobule check again everything gets replaced
remidner setup json
Setup Font
check altenrative lang
amp always generate(maybe cache 10 min)
-- compress amp future task in the future(and also to check nav menu all devices) --
### TO do Handle:
- auth vs non auth
- year
- language compression
- production
- check entire source code
- dev mode keep only en language
- if font is setup
- setup task for blog subscribe

## Dependencies:
Novobook
## Important
When replacing meta tags, do it globally, as one tag my appear multiple times in the article, the only exception is when we inject json-ld or CSS
- Example of tags that appear multiple times; **__novo_article_meta_description__**,**__novo_article_meta_title__** (they are used for seo title, twitter metadata, facebook metadata)
- Example replace only once: **__novo_article_json_ld__**

## Auth vs Non Auth

## Article List Generate
to setup(check what can overlap
__novo_blog_list_title__
__novo_blog_list_desc__
__novo_blog_list_keyword__
__novo_article_h1__
__novoArticleCanonical__
__novo_code__family_uri__
<articles\-category(\s)?\/\>
<blog\-main\-featured\-articles(\s)?\/\>
<blog\-list\-articles\-suggestions(\s)?\/\>


## Article Page Generate

### Article Ajax Calls

Setup reviews article

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
   - **__novo_article_meta_description__** - seo article description
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
   - 2483
   
- **__novo_article_img_height__**
   - the size of the artigle bg width in numeric value
   - 1299

- **__novo_article_keywords__**
   - Seo keywords, social sahre metadata
   - remove quotes from keywords, and make sure there are utf8 frielndly
   - examples: resume templates, how to write a resume

- **__novo_article_meta_title__**
   - Seo tile,page title, social sahre metadata
   - remove quotes from keywords, and make sure there are utf8 frielndly
 
- **__novo_author_desc__**
   - Seo description, seo title, social sahre metadata
   - remove quotes from keywords, and make sure there are utf8 frielndly

- **__novo_article_top__**
   - 

- **__novo_article_json_ld__**
   - 

- **__novo_author__image__**
   - 


- **__novo_article_optional_bg_css__**
   - 

- **__novo_article_content_blocks__**
   - 

- **<style\>**
   - 





## Article AMP Generate
to do setup

### Article ANP Replace Tags

- **same tags as in ### Article Replace Tags** + the follwoing:
- **__novo_article_top_amp__**
- **__novo_amp_reviews__**
- **__novo_copy_write_year__**
- **__novo_article_amp_suggestions__**
