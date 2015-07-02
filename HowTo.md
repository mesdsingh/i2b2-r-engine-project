# Contents #

**it.fsm.i2b2.recell.zip**: contains the i2b2 REngine Cell code.

**REngineFiles\_opt.zip**: contains the REngine Cell configuration file, the Kaplan Meier jar file and the runtime folder used to store the i2b2 data

**RECell\_plugin.zip**: contains the REngine CEll i2b2 plug-in engine code

**KaplanMeierStat\_plugin.zip**: contains the Kaplan Meier web client plug-in

**KMModule\_source.zip**: contains the Kaplan Meier jar source files


# How to install #

  * deploy the RECell on your apache tomcat extracting the it.fsm.i2b2.recell.zip conents and running in the it.fsm.i2b2.rengine extracted folder this script:

```
ant -f master_build.xml build-all
ant -f build.xml jboss_deploy

[old version fir i2b2 1.3] ant -f build.xml tomcat-deploy
```

  * extract the REngineFiles\_opt.zip contents into the /opt/REngineFiles folder. You con change this folder path modifying the `savingBaseDir` and `jarFile` suffix in the config.properties file. Verify the other properties in the config.properties file:
    * `javaCmd`: your java command path
    * `jriLibrary`: your jri folder path
    * `jarFile`: runKManalysis.jar path
    * `R_HOME`: your R home
    * `KMresultFolder`: the results folder into the i2b2 webclient plug-in
**You need to have installed the R software (http://www.r-project.org/) and the jri libraries (http://www.rforge.net/JRI/)**

  * extract the RECell\_plugin.zip contents unted your i2b2 webclient installation folder. e.g. `/var/www/i2b2/js-i2b2` . This file allows new plug-ins to call the RECell functions.

  * extract the KaplanMeierStat\_plugin.zip contents unted your i2b2 webclient installation folder. e.g. `/var/www/i2b2/js-i2b2/cells`. Register your web plug-in in the i2b2\_loader.js file in your /var/www/i2b2/js-i2b2 folder.

**In order to use the RECell plug-in you have to download jquery-1.4.1.min.js and include this script in the i2b2 webclient default.html page**

```
<script type="text/javascript" src="js-ext/jquery-1.4.1.min.js"></script>
<script>
  var $j = jQuery.noConflict();
</script>
```