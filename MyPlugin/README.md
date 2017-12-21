* Install Java JDK 9.0.1 on Windows7 (after uninstalling previous versions)
http://www.oracle.com/technetwork/java/javase/downloads/jdk9-downloads-3848520.html

* Install Eclipse for RCP and RAP Developers using Advanced Mode, 
** select Version "Latest(Photon)" 
** select jre-9.01
https://www.eclipse.org/downloads/download.php?file=/oomph/epp/oxygen/R2/eclipse-inst-win64.exe

* Create plugin using the new wizard and the template "View contribution using 4.x API"

* Create module-info.java in src folder that requires org.eclipse.swt:

module MyPlugin {
	requires java.base;
	requires org.eclipse.swt;	
}

* Edit Java Build Path: Remove Plug-in Dependencies from Classpath and add them to the Modulepath 

=> swt imports do not work any more, see SampleView.java or this related SO question:

https://stackoverflow.com/questions/47773079/how-to-add-org-eclipse-swt-and-other-plugin-dependencies-as-an-automatic-java9


![alt text](https://i.stack.imgur.com/3akm4.png)
