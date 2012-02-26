![Brutus logo](https://github.com/Nesta/Brutus/raw/master/brutus/logo.jpg)
logo by Lara Garrido <lgarrido@emergya.es>

# Welcome to Brutus theme's. An agile, powerful, easy and accessible theme for theme developers

The main reason for the Brutus theme development is to make the work easier for themer developers.

After many years using Zen (http://www.drupal.org/project/zen), 960 Grid (http://drupal.org/project/ninesixty), Fusion (http://drupal.org/project/fusion), tuning and customizing them we have developed a new theme that provides an agile, powerful, easy and accessible theme development.

Basic became the key piece on the code as it is the only project that uses Sass and Compass (http://drupal.org/project/basic) based on ZEN

_Brutus is yet in alhpa stage so use it carefully_

## Cooking with ruby tools

* Install rake
* Install rubygems
* Install compass
    $ gem install compass
* Clone brutus

### Installation on drupal

Unpack or clone brutus to a dir in the same level of your drupal project, for example:

* repository/
  * Brutus/
  * new_web/

Now you must configure brutus, edit _Brutus/config.rb_ :

* theme_name => is the name of the theme ;)
* theme_path => is where files are copied (theme_path/theme_name)

Next run in the Brutus dir:
    $ rake build

This will compile sass files and copy all to theme dir. You need to run this each time you change some sass file.
You can automatize this using watchr.

Log in as an administrator on your Drupal site and go to:
  
    Administer > Site building > Themes (admin/build/themes)

and make Brutus the default theme.

If you want to change the name of the theme from 'brutus' to another name like 'mytheme', follow these steps (to do BEFORE enabling the theme) :
    
* Edit brutus.info and change the name, description, project (can be deleted)
* In brutus.info, replace the following instances of "brutus_" to "mytheme_"
  * [brutus_zen_tabs]
  * [brutus_block_editing]
  * [brutus_breadcrumb]
  * [brutus_breadcrumb_separator]
  * [brutus_breadcrumb_home]
  * [brutus_breadcrumb_trailing]
  * [brutus_breadcrumb_title]
	  
  * In template.php change each iteration of 'brutus' to 'mytheme'
  * In theme-settings.php change each iteration of 'brutus' to 'mytheme'
  * rename the theme folder to 'mytheme'
	* rename brutus.info to mytheme.info

### Main folder description

* brutus.info => Provides informations about the theme, like regions, css, settings, js ...

* images => Image and graphic resorces folder

* js => Javascript files folder
  * browser.js => (http://rafael.adm.br/css_browser_selector/) Provides classes on HTML tags
  * equalHeight.js => Equal block height function

* css => CSS files folder
  * ie => Internet Explorer CSS files folder
    * ie6.sass => Used to debug IE6
		* ie7.sass => Used to debug IE7
		* ie8.sass => Used to debug IE8
		* ie9.sass => Used to debug IE9
	* partials => This folder will make our work easier
		* _header.sass => Header style file
		* _footer.sass => Footer style file
		* _section.sass => Custom file
		* _grid.sass => Grid overlay file
		* _default.sass => Main info file
		* _menu.sass => Navigator style file
		* _reset.sass => Reset file
		* _skinr.sass => User friendly interface file
		* _tabs.sass => ZEN tabs file
		* _layout.sass => Layout settings and grid definition file
	* brutus.css.sass => Our custom CSS file

* logo.png => Logo file

* templates => Template files folder. One template file for each element
	* block.tpl.php => Template fantastic to edit the blocks
	* node.tpl.php => Template fantastic to edit the nodes
	* page.tpl.php => Template fantastic to edit the page

* template.php => Used to modify drupal's default behavior before outputting HTML through the theme

* theme-settings => Used to create additional settings in the theme settings page

* config.rb => Theme definition after compilation

### Final project folder description

* brutus.info => provide informations about the theme, like regions, css, settings, js ...
* images => Image and graphic resorces folder
* js => Javascript files folder
	* browser.js => (http://rafael.adm.br/css_browser_selector/) Provides classes on HTML tags
	* equalHeight.js => Equal block height function
* css => CSS files folder
	* ie => Internet Explorer CSS files folder
		* ie6.css => Used to debug IE6
		* ie7.css => Used to debug IE7
		* ie8.css => Used to debug IE8
		* ie9.css => Used to debug IE9
	* brutus.css => Final CSS file with all the stuff (compressed and without comments if you wish. You could custom generate it)
* logo.png => Logo file
* templates => Template files folder. One template file for each element (With the addition of a function created by Ignacio Palomo: http://www.3oheme.com/blog/como-hacer-que-drupal-busque-ficheros-tpl-en-todos-los-subdirectorios-de-tu- theme theme has been structured as follows, becoming so neat that one can not find what you are looking for.)
  * block => Folder where the templates are hosted block
  	* block.tpl.php => Template fantastic to edit the blocks
  * nodes => Folder where the templates are hosted nodes
  	* node.tpl.php => Template fantastic to edit the nodes
  * pages => Folder where the templates are hosted pages
  	* page.tpl.php => Template fantastic to edit the page
  * views => Folder where the templates are hosted views
    * views-view-field--title.tpl.php => Accessible Template for listings with titles are also links (this is a plus validation AAA2).
* template.php => Used to modify drupal's default behavior before outputting HTML through the theme
* theme-settings => Used to create additional settings in the theme settings page

### Changing the Layout

The layout used in Brutus is fairly similar to the Holy Grail method. It has been tested on all major browser including IE (5>8), Opera, Firefox, Safari, Chrome ...
The purpose of this method is to have a minimal markup for an ideal display.
For accessibility and search engine optimization, the best order to display a page is the following :

1. header
2. menu
2. content
3. sidebars
4. footer

Thanks for using BRUTUS, and remember to use the issue queue in drupal.org for any question or bug report:
http://drupal.org/sandbox/nguerrero/1116216
