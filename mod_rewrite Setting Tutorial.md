### mod_rewrite Setting Tutorial<br/>
<hr/>
#### Summary<br/>
The mod_rewrite module is one of Apache's build-in modules. You can define the mapping rule between user's url request and server's file path according to your requirements. Every time, when any request comming in, it will map the rule and response the matched resource. Unlike the web redirect mechanism, the displayed url on the browser will remain the same as which is being typed initially. Using this mechanism can effectively enhance the security and make your url more easy remembered.<br/>

#### Version Info.<br/>
● Apache v.2.4.10<br/>

#### Prerequisite<br/>
The mod_rewrite module is an Apache's build-in feature, so you need to install Apache first. About how to install Apache, you can reference the tutorial [LAMP Installation Tutorial](https://github.com/andychen1060/Ubuntu-Server/blob/master/LAMP%20Installation%20Tutorial.md).<br/>

#### Setting Steps<br/>
Please follow the steps list below：<br/>
1.Enable mod_rewirte Module<br/>
You can check if the the mod_rewirte module is enabled by using the command that follow:
```
<?php echo phpinfo();?>
``` 
If the module is disabled, please reference the article [Enabling mod_rewrite](https://github.com/andychen1060/Ubuntu-Server/blob/master/Enabling%20mod_rewrite.md) to enable mod_rewrite module.<br/>
2.Create the File .htaccess<br/>
Create the .htaccess on your website's root directory.<br/>

3.Create the mapping rule <br/>
Write down the mapping rule in the .htaccess file.<br/>
For example, you have a website whose root directory is named mod_rewrite. In this directory you have the webpage.html file and the content of it is:
```
<html>
   <head>
      <title>webpage</title>
   </head>
   <body>
      <p>
         This is webpage
      </p>
   </body>
</html>
``` 
To link the webpage.html page, you need to type "http://127.0.0.1/mod_rewrite/webpage.html" on your web browser. Intuitively, the url doesn't look good. By reading the url, your actual website directory can be guessed easily. To transfer the url implicitly, one way you can do is to add the file named .htaccess on the website's root directory and type the commands that follow.
```
RewriteEngine on
RewriteRule ^$ webpage.html
```
Now, if you link the url "http://127.0.0.1/mod_rewrite/", and Apache will response the correspondent webpage.html. 
