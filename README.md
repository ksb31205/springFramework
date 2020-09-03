# Introduce
It is my practice repository learning markdown language and **spring framework**.

# Useful Link
+ To check markdown language writing result : https://stackedit.io/app#
+ To learn about web programming including spring framework : https://www.edwith.org/boostcourse-web

# Setting
- JAVA JDK
	+ Download Link : https://www.oracle.com/java/technologies/javase-downloads.html
	+ Download Date : 2020. 09. 02   
	+ Version : JDK-14.0.2 windows 64bit
- Environment Variable for JDK
	+ System Variable
		+ JAVA_HOME : "C:\Program Files\Java\jdk-14.0.2"
		+ CLASSPATH : ".;%JAVA_HOME%\lib\tools.jar"
		+ Path Edit : add "JAVA_HOME%\bin"
- Version Check in CMD
	+ java -version
	+ javac -version
		※ If versions of JDK and JRE are both not same, javac command does not run.
		※ If versions of JDK is after 11, delete JRE. If not, Make the both versions the same.
- Eclipse IDE for Enterprise JAVA Developers
	+ Download Link : https://www.eclipse.org/downloads/packages/
	+ Download Date : 2020. 09. 02
	+ Version : 2020-06 windows 64bit
- Additional Settings for Eclipse
	+ My Workspace Setting
		+ C:\Users\SeongBo\eclipse-workspace-2020
	+ Encoding Setting
		1. Run Eclipse
		2. Go "Window" -> "Preferences" -> "General" -> "Workspace"
		3. In the "Text file encoding" settings, change "Other" to "UTF-8"
		4. Go "Window" -> "Preferences" -> "Web" -> "CSS Files"
		5. In the Encoding settings of "Creating files", change "Korean, EUC-KR" to "ISO 10646/Unicode(UTF-8)"
		6. Go "Window" -> "Preferences" -> "Web" -> "HTML Files"
		7. In the Encoding settings of "Creating files", change "Korean, EUC-KR" to "ISO 10646/Unicode(UTF-8)"
		8. Go "Window" -> "Preferences" -> "Web" -> "JSP Files"
		9. In the Encoding settings of "Creating files", change "Korean, EUC-KR" to "ISO 10646/Unicode(UTF-8)"
- Tomcat
	+ Download Link : https://tomcat.apache.org/download-80.cgi
	+ Download Date : 2020. 09. 02
	+ Version : apache-tomcat-8.5.57-windows-x64
	※ Unzip to the directory "C:\apps"
	※ To use tomcat, execute "C:\apps\apache-tomcat-8.5.57\bin\startup.bat"
	※ After executing, you can see first web page through the URL "http://localhost:8080/"
- Environment Variable for Tomcat
	+ System Variable
		+ CATALINA_HOME : "C:\apps\apache-tomcat-8.5.57"
		+ Path Edit : add "CATALINA_HOME%\bin"
# Error Handling
- None