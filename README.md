# Eki_Wiki
**Description**
I'm trying to figure out how to build a wiki site from [Bookstack](https://www.bookstackapp.com/) with Windows 10 on my pc!
So this page is a documentation and a log book where I can show you how I proceeded.

I'm going to learn it step by step:

Steps Overview:
1. Browsing the official documentation site
2. Watching tutos
3. Start to documentate what I've learned
4. Buiding things

1. Browsing the official documentation site


I found a super tutorial on youtube:
https://www.youtube.com/watch?v=_v-4BhVz7OI

Here is notes that I took while watching

> 1. Got to bookstackapp.com > Installation and see the requierments:
> BookStack has the following requirements:
>
>   - PHP >= 8.0.2
>   
>   For installation and maintenance, you’ll need to be able to run php from the command line.
>   Required Extensions: OpenSSL, PDO, MBstring, iconv, Tokenizer, GD, MySQL, SimpleXML & DOM.
>   Optional Extensions: LDAP (If wanting to use LDAP Auth)
>      
>    - MySQL >= 5.7 or MariaDB >= 10.2
>    
>   For the storage of BookStack content and data.
>   Single Database (All permissions advised since application manages schema)
>      
>    - Git Version Control
>    
>     For application of updates when following our standard process.
>      
>    - Composer >= v2.0
>    
>    For installation and management of our PHP dependencies.
>    
>    - A PHP Compatible Webserver
>    For usage with PHP and for serving static files.
>    
> 2. Download the right version of XAMPP 
> 
> For php, MySQL,  and A PHP Compatible Webserver
> 
> 3. Go to git-scm.com and download git
> 4. Go to getcomposer.org and download composer
>    go to C:\ProgramData\ComposerSetup\bin and move composer.phar into the folder C:\xampp\htdocs\bookstack\
> 5. Open XAMPP Control Pannel,
>   Click Config of the row of Apache and choose php.ini: open with bloc-note and remove the ";" in front of "extension=gd", "extension=ldap" and "extension=zip"
>   Start Apache
>   Start MySQL 
> 6. Open > click shell :
>   cd htdocs
> The website template folder
> 7. Clone the release branch of the BookStack GitHub repository into a folder.
    git clone https://github.com/BookStackApp/BookStack.git --branch release --single-branch
> 8. Rename the folder cloned into lowercase
> 9. cd into bookstack folder and run 
>       echo @php "%~dp0composer.phar" %*>composer.bat
>       composer install --no-dev.
> 10. Copy the .env.example file to .env and fill with your own database and mail details.
> 11. Ensure the storage, bootstrap/cache & public/uploads folders are writable by the web server ([More information here](https://www.bookstackapp.com/docs/admin/filesystem-permissions/).
> 11. In the application root, Run php artisan key:
>     generate to generate a unique application key.
> If not using Apache or if .htaccess files are disabled you will have to create some URL rewrite rules as shown below.
> Set the web root on your server to point to the BookStack public folder. This is done with the root setting on Nginx or the DocumentRoot setting on Apache.
> Run php artisan migrate to update the database.
> Done! You can now login using the default admin details admin@admin.com with a password of password. You should change these details immediately after logging in for the first time.
> 


