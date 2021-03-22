# Setup-guides
Setup instructions for hortonworks docker sandbox
1.	Install docker desktop for windows
2.	In Docker settings>resources   - CPUs -4 , Memory – 16 GB, Swap – 1GB, Disk Size – 64 Gb 
3.	Install power shell on windows
4.	Download docker installation from https://www.cloudera.com/downloads/hortonworks-sandbox/hdp.html - select version 2.65
5.	Extract the zip
6.	run bash shell in administrator mode
7.	Navigate to the directory where you have extracted the file and run 
     sh docker-deploy-hdp265.sh
8. In windows hosts file (C:\Windows\System32\drivers\etc) create the following entry 
   127.0.0.1  localhost sandbox-hdp.hortonworks.com sandbox-hdf.hortonworks.com
9. Ambari UI is available on localhost:8080
   http://sandbox-hdp.hortonworks.com:1080/splash.html
   
10. List of credentials user/password
maria_dev  	maria_dev
raj_ops	     raj_ops
holger_gov	holger_gov
amy_ds	     amy_ds
   

NOTE:
just in case you are getting port bind errors. Get the list of all retricted ports, run the following on windows
netsh interface ipv4 show excludedportrange protocol=tcp
in proxy-deploy script , replace all restricted host ports with new ports which are not blocked. And launch the proxy shell script again.
Proxy shell script ia available in sandbox\proxy



Additional instructions (optional):
===================================
1. set hive.cli.print.header=true; on hive prompt if column headers are not printed.
2.

