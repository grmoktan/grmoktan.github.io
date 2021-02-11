### The site lives in S3 now

Once again, I again changed my personal site :) . The previous one built using frozen flask approach was hosted on github pages. Now I migrated it to mkdocs based static setup and they are hosted on aws S3. 

This inside the html &lt;head&gt;&lt;/head&gt; basically redirects to wherever you want:

````
<meta http-equiv="refresh" content="time; URL=new_url" />
````