Шаблонизатор Twig для Yii
=========================

Данное расширение позволяет использовать [Twig](http://www.twig-project.org/) как шаблонизатор.

###Полезные ссылки
* [SVN](http://code.google.com/p/yiiext/source/browse/trunk/app/extensions#extensions/yiiext/renderers/twig)
* [Twig](http://www.twig-project.org/)
* [Обсуждение](http://yiiframework.ru/forum/viewtopic.php?f=9&t=238)
* [Соощить об ошибке](http://code.google.com/p/yiiext/issues/list)

###Требования
* Yii 1.0 и выше

###Установка
* Распаковать в `protected/extensions`.
* [Скачать](http://www.twig-project.org/installation) и распаковать все файлы
  Twig из `fabpot-Twig-______.zip\fabpot-Twig-______\lib\Twig\` в `protected/vendors/Twig`.
* Добавить следующее в файл конфигурации в секцию 'components':
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

###Использование
* См. [синтаксис Twig](http://www.twig-project.org/book/02-Twig-for-Template-Designers).
* Свойства текущего контроллера доступны как {{this.pageTitle}}.