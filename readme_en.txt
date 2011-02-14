Twig view renderer
==================

This extension allows you to use [Twig](http://www.twig-project.org/) templates in Yii.

###Resources
* [SVN](http://code.google.com/p/yiiext/source/browse/)
* [Twig](http://code.google.com/p/yiiext/source/browse/trunk/app/extensions#extensions/yiiext/renderers/twig)
* [Discuss](http://www.yiiframework.com/forum/index.php?/topic/4919-twig-view-renderer/)
* [Report a bug](http://code.google.com/p/yiiext/issues/list)

###Requirements
* Yii 1.0 or above

###Installation
* Extract the release file under `protected/extensions`.
* [Download](http://www.twig-project.org/installation) and extract all Twig files from `fabpot-Twig-______.zip\fabpot-Twig-______\lib\Twig\` under `protected/vendors/Twig`.
* Add the following to your config file 'components' section:
~~~
[php]
 'viewRenderer'=>array(
     'class'=>'ext.yiiext.renderers.twig.ETwigViewRenderer',
     'fileExtension' => '.html',
     'options' => array(
     	'autoescape' => true,
     ),
     'extentions' => array(
		'My_Twig_Extension',
	 ),
  ),
~~~

###Usage
* See [Twig syntax](http://www.twig-project.org/book/02-Twig-for-Template-Designers).
* Current controller properties are accessible via {{this.pageTitle}}.