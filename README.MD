# APK signature verification cracking 
A fork of L-JINBIN's [ApkSignatureKiller](https://github.com/L-JINBIN/ApkSignatureKiller), using a mix of google translator and my brain to make the translation. Note this isn't a one to one translation, nor is it meant to be. This fork is for my english speaking homies that what to use this program with relitive ease.

## How it works
ApkSignaturKiller works by inserting code into the Application entry, hooking the getPackageInfo method of PackageManager then changing the signature.

## Processing steps
1. Read the signature information of the original APK.
2. Replace or add the name attribute of the application in AndroidManifest.xml.
3. Read PmsHookApplication.smali and replace the signature information. If the original APK modifies the Application, you'll also need to modify the parent class of PmsHookApplication, and finally compile smali and add it to classes.dex.
4. Sign the output APK.

## Instructions
1. To use this tool, you'll need to install Java first, allowing you to run nkstool.
2. Modify the configuration information in config.txt as needed, and put the corresponding apk in the project root directory.
3. You can run the project in three ways:
    - Open the project with IntelliJ IDEA and run the source code
    - On Windows you can directly execute run.bat
    - On Linux or MacOS, open a terminal, cd to the project root directory, then run `java -jar nkstool.jar`
4. Now you're done! Test output apk file.

## Other
If you do not need the source code, you only really need to keep nkstool.jar, config.txt, run.bat and all other files that aren't `src`.

<br /><br />
<h3><p align='center'>this tool only works for applications whose signatures are only verified by PackageManager.getPackageInfo().signatures.</p></h3>
