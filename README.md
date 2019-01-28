# pssdiag
Preconfigured pssdiags

These pssdiag files are specific to the instance of SQL Server in which you need to run them.  

These collections do not include server-side trace events or extended event captures.  

Here is how to run the pssdiag:

PSSDIAG must be executed locally at SQL Server on the ACTIVE NODE.  
The zip file contains a set of collection utilities.  You’ll need to run the pssdiag.cmd file to start the collection.  

1. Create a folder named PSSDIAG on your SQL server machine. This folder should be on a drive with plenty of space as diagnostic file collections can be quite large. Also avoid a disk where databases or transaction logs are present. 
2. Download the zip file I mention above from the file transfer site and save to the PSSDIAG folder 
3. Open a command prompt under administrator credentials, this account MUST BE part of Local Administrators and also SQL Administrator.  
4. Change the current directory to your PSSDIAG folder and run pssd.exe to extract its contents. 
5. Stop all other profiler traces that may be running on the server, as well as any perfmon monitoring tool 
6. Run PSSDIAG.cmd at the command prompt to start the collection process. 
7. Once PSSDIAG displays the message, “Collection started,” start your test. (note that you should not close the command prompt window while the trace is running.) 
8. As soon as the test is finished you should stop the PSSDIAG. Stop PSSDIAG by pressing CTRL+C once. Wait for the collector to shutdown. 
          Do not stop the batch file, let the batch file complete. If questioned to stop the batch file answer “N” 

Notes: 
• Do not run any out of the ordinary processes, such as index maintenance or DBCC commands.  Backups or any other operation that may skew the regular server operation. 

• Do not have other SQL profiler traces running concurrently with PSSDIAG 

• Do not have perfmon or other Windows performance counters collection tools started, as this may cause PSSDIAG not to collect perfmon counters 
