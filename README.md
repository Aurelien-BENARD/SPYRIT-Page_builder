SpyritPageBuilderBundle
=======================

# About 

A page builder for Symfony and Doctrine.

**Notice**: this bundle is highly experimental, there may be important changes without warning.

# Installation

Install the bundle with composer:

`composer require spyrit/page-builder-bundle`

**Warning**: In yout composer.json you may need to set "minimum-stability" to "dev".

# Database

You will need to set up your .env file to set up a database.

You will need to create entities, if needed they can extend interface provided by the bundle (PageInterface, ZoneInterface, BlockInterface)

# How to use

#### Add a widget

* If you create a new Widget, you *must* generate a migration to allow a new ENUM value in column `block`.`widget`. To do so, open a SQL client and remove the comment `(DC2Type:Widget)` for that column and then run `bin/console d:m:di`.
* Add a new Widget class that heritate from BaseWidget.
* Add 1 or 2 templates for your widget (one editor template and one front template if needed)
* Create your widget's form


#### Use a widget

To use a widget you can use the editor provided via the bundle ('editor.html.twig' and 'editor_js.html.twig')


#### Render
	
* To render a page you will need to call the renderPage method from the renderManager Class.
```
$html = $renderManager->renderPage($page);
return $this->render('template.html.twig', ['html'=>$html]);
```
* The first argument is the page, the second one is a boolean (true for editor, false or nothing for front)




