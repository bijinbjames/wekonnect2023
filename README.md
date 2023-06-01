# Documentation
Install [xampp](https://www.apachefriends.org/) go to the xampp installed directory then extract the repo in the htdocs folder. 
Run the xampp software and start Apache and MySQL servers.
open the browser and type http://localhost/wekonnekt in the url.

The installation should start, go throught the setup process
type in the  sitename and the database url.
**This installation is only nessery if you are trying to install and edit through a local machine. The EC2 intance has these setups already done.**

redirect non www to www, or www to non www. Also it is important to setup SSL for your site, Please follow the steps below to do so.

-   Open .htaccess file located in root directory.
-   To redirect your website to SSL, copy and paste the code below after  **RewriteEngine On**
    
 
 `RewriteCond %{HTTPS} off`
 
 `RewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI} [R,L]`
 
 
 
    
-   To redirect your website to www, copy and paste the code below after  **RewriteEngine On**
 
 `RewriteCond %{HTTP_HOST} ^[^.]+\.[^.]+$`
 
`RewriteCond %{HTTPS}s ^on(s)|`
 
 `RewriteRule ^ http%1://www.%{HTTP_HOST}%{REQUEST_URI} [L,R=301]`
    																												
    
-   If you made any changes above, last step is to update your domain name in  `config.php`  file.



##### To modify the HTML tamplates

   You can find the layout files in  `./themes/wowonder/layout/`
##### To edit the stylesheet from

-   You can edit the stylesheet from  `./themes/wowonder/stylesheet/`
-   The general style file is:  **style.css**
