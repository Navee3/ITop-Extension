# Extension Non-IT Device

You've just created a new iTop extension, congratulations!

## What to do next ?

  - Adjust the iTop mininum version (by default iTop 2.6.0) if needed by editing the `version` in the datamodel XML file (`<itop_design xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" version="1.6">`)
  - Install this (empty) extension in your iTop using the setup
  - Get the [toolkit](https://www.itophub.io/wiki/page?id=latest%3Acustomization%3Adatamodel) and update your iTop (check the option "symbolic links")
  - Update your code then refresh the iTop pages to see the magic happen... or not (ah, ah, debug!!)

### Autoloader
If you declare some PHP classes in the `src` folder, you'll have to build/update the autoloader with [Composer](https://getcomposer.org). The command line (to be launched from the root directory of your extension) is the following:

```
composer update
composer dump-autoload -o
```

### Hooks
If you implement some "Hooks" (i.e. classes implementing one of the [Extension APIs](https://www.itophub.io/wiki/page?id=2_7_0%3Acustomization%3Aextensions_api), for example iApplicationExtension), put them in the `src/Hook` folder and add the file `datamodel` section of the `module` file for an explicit inclusion. The same rule applies if you declare some datamodel classes in plain PHP.

```
		//
		'datamodel' => array(
			'vendor/autoload.php',
			'model.test-extension.php', // contains the PHP code generated from the datamodel.test-extension.xml
			'src/Hook/MyHook.php', // Explicit include, hooks cannot benefit from the autoloader
		),

```

# ITop Non-IT Extension

## Building from the source

If you want to build **ITop extenstion** from the source code:

1. Use module creation wizard to create module using below link: (https://www.itophub.io/wiki/page?id=2_1_0:customization:start#creating_a_module)

## Deploying extension

If you want to add **ITop extenstion** to your source code:

1. Follow this step by step procedure: (https://www.itophub.io/wiki/page?id=2_1_0:customization:add-class-sample)

2. Add **non-it-device** folder to extension folder in iTop

3. Remove Read-only property of Config-itop.php file which found in conf folder

4. Run http://your_itop/setup/ on browser to setup