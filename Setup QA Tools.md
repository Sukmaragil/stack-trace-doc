<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Setup QA Tools</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h1 id="setup-qa-environment">Setup QA Environment</h1>
<p>This is guide to setup testing environment for automated test in ICEHOUSE. OS using macOS for base installment, for another OS you can search on google :)</p>
<h3 id="requirement">Requirement</h3>
<ul>
<li>Android SDK</li>
<li>ADB</li>
<li>Appium Desktop</li>
<li>IntelliJ IDEA</li>
<li>Maven</li>
</ul>
<h2 id="setup-intellij-idea">Setup IntelliJ IDEA</h2>
<p>IntelliJ IDEA contains all the features found in Android Studio. Setup for Android development is, however, a bit more involved since it does not include the Android SDK by default.</p>
<h3 id="prerequisites">Prerequisites</h3>
<ul>
<li>Install <a href="http://www.oracle.com/technetwork/java/javase/downloads">JAVA JDK</a></li>
<li>Install <a href="https://www.jetbrains.com/idea/download/">IntelliJ IDEA</a></li>
<li>Install <a href="https://github.com/codepath/android_guides/wiki/Installing-Android-SDK-Tools">Android SDK Tools</a></li>
<li>Install ADB (Android Debug Bridge)</li>
</ul>
<h4 id="install-java-jdk">Install JAVA JDK</h4>
<p>On some device maybe have been pre-installed on the OS, try this command in terminal</p>
<pre><code>$ java -version
java version "x.x.x"
Java(TM) SE Runtime Environment (build x.x.x)
Java HotSpot(TM) x-Bit Server VM (build x.x, mixed mode)
</code></pre>
<p>and</p>
<pre><code>$ javac -version
javac x.x.x
</code></pre>
<blockquote>
<p>Notes to download java version 8 to compatible with the IntelliJ IDEA</p>
</blockquote>
<p>if there is no available java installed, follow this:</p>
<ol>
<li>Go to java download page, <a href="http://www.oracle.com/technetwork/java/javase/downloads/index.html">http://www.oracle.com/technetwork/java/javase/downloads/index.html</a></li>
<li>Download Java Platform (JDK) for macOS</li>
<li>Open downloaded file jdk-x.x.x_OS-x64_bin.dmg file</li>
<li>Follow the installation instruction</li>
<li>After successfully installed try the <code>java -version</code> and <code>javac -version</code> command on your terminal</li>
</ol>
<p>You must set the JAVA_HOME PATH to system, follow this instructions :<br>
<a href="http://www.sajeconsultants.com/how-to-set-java_home-on-mac-os-x/">http://www.sajeconsultants.com/how-to-set-java_home-on-mac-os-x/</a></p>
<h4 id="install-intellij-idea">Install IntelliJ IDEA</h4>
<ol>
<li>Go to download page, <a href="https://www.jetbrains.com/idea/download/">https://www.jetbrains.com/idea/download/</a></li>
<li>Download IntelliJ IDEA for macOS</li>
<li>open the DMG file</li>
<li>Drag the IntelliJ IDEA to Application</li>
<li>You have successfully install IntelliJ IDEA<br>
<img src="http://gauravpandey.com/wordpress/wp-content/uploads/2017/04/firstScreen.png" alt=""></li>
</ol>
<p>Now, configure the IntelliJ IDEA :</p>
<ol>
<li>Open the application</li>
<li>Click on <strong>Configure</strong> &gt; <strong>Project Defaults</strong> &gt; <strong>Project Structure</strong><br>
<img src="https://raw.githubusercontent.com/codepath/android_guides/master/images/intellij_idea_welcome_screen.png" alt="IntelliJ IDEA"></li>
<li>Select <strong>SDKs</strong>, add Java development kit<br>
<img src="https://raw.githubusercontent.com/codepath/android_guides/master/images/intellij_idea_add_sdk.png" alt=""></li>
<li>Navigate to JDK location, e.g.<br>
<code>/Library/Java/JavaVirtualMachines/jdk1.7.0_79.jdk/Home</code> , usually system will automatically redirect the path and you just click <strong>Open</strong></li>
<li>Install Android SDK, please follow this instruction for details process<br>
<a href="https://github.com/codepath/android_guides/wiki/Installing-Android-SDK-Tools">https://github.com/codepath/android_guides/wiki/Installing-Android-SDK-Tools</a></li>
<li>Try to Start new Android Project, the Android SDK requirement will be downloaded automatically with the default step</li>
</ol>
<h3 id="install-adb">Install ADB</h3>
<p>source : <a href="https://www.xda-developers.com/install-adb-windows-macos-linux/">https://www.xda-developers.com/install-adb-windows-macos-linux/</a></p>
<ol>
<li>Delete your old installation (optional)<br>
<code>rm -rf ~/.android-sdk-macosx/</code></li>
<li>Navigate to <a href="https://developer.android.com/studio/releases/platform-tools.html">https://developer.android.com/studio/releases/platform-tools.html</a> and click on the <code>SDK Platform-Tools for Mac</code> link</li>
<li>Go to your downloads folder<br>
<code>cd ~/Downloads</code></li>
<li>Unzip the tools you downloaded<br>
<code>unzip platform-tools-latest*.zip</code></li>
<li>Move them to somewhere you won’t accidentally delete them</li>
</ol>
<pre><code>mkdir ~/.android-sdk-macosx
mv platform-tools/ ~/.android-sdk-macosx/platform-tools
</code></pre>
<ol start="6">
<li>Add <code>platform-tools</code> to your path<br>
<code>echo export PATH=$PATH:~/.android-sdk-macosx/platform-tools/' &gt;&gt; ~/.bash_profile</code></li>
<li>Refresh your bash profile (or restart your terminal app)<br>
<code>source ~/.bash_profile</code></li>
<li>Start using adb<br>
<code>adb devices</code></li>
</ol>
<p><strong>important</strong> system sometimes using the <code>~/.profile</code>, if after installation and try using <code>adb devices</code> not found the command, try to input the <code>PATH</code> to <code>~/.profile</code></p>
<h3 id="install-appium-desktop">Install Appium Desktop</h3>
<ol>
<li>Download appium zip file for mac <a href="https://github.com/appium/appium-desktop/releases/tag/v1.5.0">https://github.com/appium/appium-desktop/releases/tag/v1.5.0</a></li>
<li>Open the zip file and it will extracting the appium</li>
<li>Launch the app by clicking extracted file, and appium is ready to use<br>
<img src="http://blog.xebia.in/wp-content/uploads/2017/09/Screen-Shot-2017-09-30-at-10.03.50-AM.png" alt=""></li>
</ol>
<h3 id="install-maven">Install Maven</h3>
<p>For easy install of maven try this command<br>
<code>brew install maven</code><br>
after successfully installed, try this command on you terminal<br>
<code>mvn -version</code><br>
if you encountered error that show</p>
<pre><code>$ mvn -version
The JAVA_HOME environment variable is not defined correctly
This environment variable is needed to run this program
NB: JAVA_HOME should point to a JDK not a JRE
</code></pre>
<p>set <code>$JAVA_HOME</code> at this file <code>~/.mavenrc</code><br>
open the file with this command<br>
<code>nano ~/.mavenrc</code><br>
and added this following line<br>
<code>export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-x.x.x.jdk/Contents/Home</code><br>
and try <code>mvn -version</code> and it will show this</p>
<pre><code>mvn -v
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=1024m; support was removed in 8.0
Apache Maven 3.5.0 (ff8f5e7444045639af65f6095c62210b5713f426; 2017-04-03T15:39:06-04:00)
Maven home: /usr/local/Cellar/maven/3.5.0/libexec
Java version: 1.8.0_141, vendor: Oracle Corporation
Java home: /Library/Java/JavaVirtualMachines/jdk1.8.0_141.jdk/Contents/Home/jre
Default locale: en_CA, platform encoding: UTF-8
OS name: "mac os x", version: "10.12.6", arch: "x86_64", family: "mac"
</code></pre>
</div>
</body>

</html>
