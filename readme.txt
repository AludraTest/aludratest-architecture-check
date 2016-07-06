Purpose
========
This project serves for the architecture assessment of all AludraTest-related projects.
For this purpose it fetches the binary and source builds of all AludraTest-related projects,
extracts them into the target folder and then calls ConQAT to assess the architecture conformance 
of all dependencies. 


ConQAT installation
====================
Installation: 
- download the ConQAT Engine 2015.2 Binary Distribution from https://www.cqse.eu/en/products/conqat/install/
- unpack it
- set the environment variable CONQAT_HOME to the path where you unpacked it to
- on Unix and Mac systems set the access permissions on the executable chmod u+x CONQAT_HOME/bin*.sh
- add conqat.sh to the path


Performing the architecture assessment
=======================================
1. Verify the correctness of the version numbers of all AludraTest dependencies in the pom.xml file
2. Make sure the source jars of the dependent projects are available in the most up-to-date version 
3. Open a console
4. cd to the project directory
5. On the console, invoke 
		mvn clean generate-resources
6. On the console, invoke 
		conqat -f aludratest.architecture.cqr
   on a Windows system or
		conqat.sh -f aludratest.architecture.cqr
   on a Unix or Mac system
   
7. View the architecture assessment report in target/conqat/index.html