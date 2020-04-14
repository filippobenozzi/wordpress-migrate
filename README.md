# SQL query to migrate a Wordpress site

When you migrate a wordpress site you need to chage the URLs in every table becouse some URLs could be serialized. These sets of query can help you achive the migration without headache.

Just simply change the http://www.oldurl and the http://www.newurl in each query and run the queries in your DB.

```
UPDATE wp_options SET option_value = replace(option_value, 'http://www.oldurl', 'http://www.newurl') WHERE option_name = 'home' OR option_name = 'siteurl';

UPDATE wp_posts SET guid = replace(guid, 'http://www.oldurl','http://www.newurl');

UPDATE wp_posts SET post_content = replace(post_content, 'http://www.oldurl', 'http://www.newurl');

UPDATE wp_postmeta SET meta_value = replace(meta_value,'http://www.oldurl','http://www.newurl');
```
