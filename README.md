### The site lives in S3 now

Once again, I changed my personal site build and hosting :) . The previous one built using frozen-flask approach was hosted on github pages. Now I migrated it to mkdocs based static setup and they are hosted on aws S3. 

I just put up simple index.html hosted with github pages with the following inside html &lt;head&gt;&lt;/head&gt; .

````
<meta http-equiv="refresh" content="0; url=https://grmoktan.net">
````

This basically then redirects the visitors of grmoktan.github.io to grmoktan.net . 

