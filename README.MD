# APK signature verification cracking 
A fork of L-JINBIN's [ApkSignatureKiller](https://github.com/L-JINBIN/ApkSignatureKiller), using a mix of google translator and my brain to make the translation.

## Principles
By inserting code into the Application entry, hook the getPackageInfo method of PackageManager in the program and change the obtained signature information.

## Processing steps
1. Read the signature information of the original APK.
2. Replace or add the name attribute of the application in AndroidManifest.xml.
3. Read PmsHookApplication.smali and replace the signature information. If the original APK modifies the Application, you'll also need to modify the parent class of PmsHookApplication, and finally compile smali and add it to classes.dex.
4. Sign the output APK.

## Instructions
1. To use this tool, you need to install the Java environment first, and nkstool.jar is a compiled file.
2. Modify the configuration information in config.txt as needed, and put the corresponding apk in the project root directory.
3. run, three ways
    - Open the project with IDEA and run the source code
    - Windows system can directly open run.bat to execute。
    - On Linux or MacOS, open a terminal, cd to the project root directory, type java -jar nkstool.jar and press Enter.
4. Test output apk file

## Other
If you do not need the source code, you can only keep nkstool.jar, config.txt, run.bat and other files.

This tool only works for applications whose signatures are only verified by PackageManager.getPackageInfo().signatures.
