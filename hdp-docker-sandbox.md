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
raj_ops	     raj_ops        -- for Ambari UI
holger_gov	holger_gov     -- Atlas login creds
amy_ds	     amy_ds
admin          admin          -- for atlas


If holger_gov doesn't work:
===========================
edit the users-credentials.properties (/usr/hdp/current/atlas-server/conf) file using vi or any editor

holger_gov=<ROLE YOU want to give>::<sha256sum of the password>

in order to generate the sha256sum use the below command in *nix terminal

echo -n "yourpassword" | sha256sum

it will give you some output like below

4d20573d20756b4b2cd80e41def04b52907710000b038f0f901d4b568e254fc6 -

copy the sum till 6 leave out the space and - (dash) and paste it in the users-credentials.properties files.

Restart you ATLAS server from ambari, and it will work(https://community.cloudera.com/t5/Support-Questions/ATLAS-UI-authnetication-with-holger-gov-gives-invalid/td-p/243759)

NOTE:
just in case you are getting port bind errors. Get the list of all retricted ports, run the following on windows
netsh interface ipv4 show excludedportrange protocol=tcp
in proxy-deploy script , replace all restricted host ports with new ports which are not blocked. And launch the proxy shell script again.
Proxy shell script ia available in sandbox\proxy
Also check, the mount paths given with option -v are in doube quotes.



Additional instructions (optional):
===================================
1. set hive.cli.print.header=true; on hive prompt if column headers are not printed.
2.

