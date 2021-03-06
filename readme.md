##Overview
The IrisApp.qvf runs an R script through a call to a batch file. The R script loads the iris data set from iris.csv. The data is split into training, testing and validation sets. A random forest model is used to predict the species from the data. The predictions of the validation set are appended to the validation data set. It is then exported to a new csv which is picked up by Qlik Sense.

###Link to Iris data information 
https://stat.ethz.ch/R-manual/R-devel/library/datasets/html/iris.html

###Model Var Importance:

![alt tag](https://github.com/kristywedel/IrisQlikSense/blob/master/plot.png)

###Qlik Sense

![alt tag](https://github.com/kristywedel/IrisQlikSense/blob/master/QlikSense.PNG)

##Installation Steps
If R is not installed, it can be downloaded at https://cran.r-project.org/bin/windows/base/
If Qlik Sense is not installed, it can be downloaded at 
http://www.qlik.com/us/try-or-buy/download-qlik-sense

1.) To allow the use of absolute or relative file paths, enable legacy mode by modifying  

    Open C:\Users\{user}\Documents\Qlik\Sense\Settings.ini in a text editor
    If the line 'StandardReload=1' is already in the file, change StandardReload=1 to StandardReload=0. Otherwise, add the line StandardReload=0.
	Insert an empty line at the end of the file
    Save the file

If you don't wish to enable legacy mode, change the paths in the data load editor to use a library. Qlik help link: http://help.qlik.com/en-US/sense/3.1/Subsystems/Hub/Content/LoadData/disable-standard-mode.htm

2.) To allow the execute command and run the R file, modify the settings.ini file as follows 

    Open C:\Users\{user}\Documents\Qlik\Sense\Settings.ini in a text editor
    Insert a new line and type OverrideScriptSecurity=1
	Insert an empty line at the end of the file
	Save the file

Qlik help link: http://help.qlik.com/en-US/sense/3.1/Subsystems/Hub/Content/Scripting/ScriptRegularStatements/Execute.htm 

![alt tag](https://github.com/kristywedel/IrisQlikSense/blob/master/settings.PNG)

3.) Unzip files to desired location. Modify the RunR.bat file with the location of R.exe. Start the Qlik Sense Desktop hub. Drag IrisApp.qvf to the hub to open it.

![alt tag](https://github.com/kristywedel/IrisQlikSense/blob/master/settings1.PNG)

