# Assurity
To upload the performance Assignment with Assurity

#Performance Assignment#


Install JMeter


Step 1: The following JMeter tool need to be set up
        
	You can download JMeter 5.5 from https://jmeter.apache.org/download_jmeter.cgi (Required Java 8+)
	
Step2: Install Plugins Manger to JMeter as using some of additional elements.
        
	Download  plugins-manager.jar https://jmeter-plugins.org/install/Install/ and put it into lib/ext directory, then restart JMeter.
	
Step3: Download the script folder along with test data file

Step4: Open JMeter and open the Assignment_AnnRoshaliSilva.jmx file

Step5: Install the elements which are not in the initial JMeterfrom Plugin Manager


Test Execution


Step1 : In the test plan all the values needed for test execution have been paramterized. If you want you can go ahead and change the following before you run the test

        pRampup - Ramp Up time (In the assignment scheduled for 5 seconds as asked 1 thread per second and there were 5 threads) - This is used in Ultimate Thread Group
	
        pSteadystate - Hold Duration time((In the assignment scheduled for 60seconds / 1 min) This is used in Ultimate Thread Group
	
        pThroughput - Request per minute (In the assignment it is 10 request in staedy period)
	
        pThreadcount - No of threads/ VUsers required for testing (In the assignment asked for half of category ID counts, it was 10 category IDs, therefore used 5 as threadcount) This is used in Ultimate Thread Group - This is used in Constant Througput timer
	
	 pServer- Also parameterized the server details
	
	
Step 2: The following paths need to be changed in the scripts after downloading.

*File Path in Test Plan which is parameterised in CSV Data Config Element. (${FilePath}\TestData\TestData_CategoryID.csv)
	
*Also change the file path in Bean Shell Post Processor to write the correlation values into CSV

*Change the file name in Listners such as Aggregate report and enable summary report and view resuts tree if you need


Step3 : The folowing steps can follow when running the test in Non GUI mode

You can copy the script in to the bin folder in JMeter location. 

Then open the command Prompt and change the directory to JMeter Bin and execute the following command

         jmeter -n -t <jmx file name with path> -l <log file name with path>

         Example: C:\Program Files\apache-jmeter-5.5\bin>jmeter -n -t Assignment_AnnRoshaliSilva.jmx -l testresult.jtl
	 
	 **To generate the HTML report when execute through Non GUI mode
	 
	 jmeter -n -t <jmx file name with path> -l <log file name with path> -e -o <path of folder to save HTML report>
	 
	 Example: C:\Program Files\apache-jmeter-5.5\bin>jmeter -n -t Assignment_AnnRoshaliSilva.jmx -l testresult.jtl -e -o C:\HTMLReport


Test Results

        
Summary

	
**The objective of the test is to verify the response of the API whether it is within SLA of 500ms during the load test.
	
**Four rounds of test were executed in both GUI and non GUI mode. 
	
**During the second test observed 90th percent response time was 504ms which has breached SLA. Therefore, executed another round of test and response times were within SLA.
	
**There was an error rate which was due to one Assertion failed for 1 test data in all rounds. It get the different response and response assretion was failed.
	
**Considering all the test results this test can be marked as PASS as 3 test were within SLA.
	
	
Observation:

#The following was 90th Percentile response time during 4 round of test execution

	Test 1 - 454ms - Within SLA of 500ms
	
	Test 2 - 504ms - Exceeded SLA of 500ms
	
	Test 3 - 453ms - Within SLA of 500ms
	
	Test 4 - 418ms - Within SLA of 500ms - Executed via Non GUI mode
	
	
#Test was executed only for 1 min and ramp up was just 5 second with 5 virtual users. Response time will get more accurate if the test execute for longer duration as the data set will get increased.
	
#Observed failure in 1 request in every test for the Category ID 6331 as it returns "CanRelist":false but the assertion was "CanRelist": true. Therefore the request has failed.



Files in the Repo

Script - JMeter Script "Assignment_AnnRoshaliSilva.jmx"

Test Data -CSV file "TestData_CategoryID.csv"

Test Results 

	Print files - All the files printed with correlations values for each test execution.
	
	Aggregate Test - The files with Aggregate test logs and aggregate results table for each test execution.
        
        JTL file of the results of Non GUI mode  - testresult.jtl - This one can be opend from JMeter tool as well
        
	HTML Report - Genarted the HTML report from the Non GUI test results as an additional thing as test round 5 which has not considred for the analysis

Performance Test Results Analysis Report - Assurity Assignment - Word Document whcich has executive summary, observations and recommendations.
	
Assumptions

	**There were 10 category IDs so considered half the count and take the VUser count as 5 

 	**Did not consider ramp down time

	**Added HTTP Cache Manager and Cookie Manager to simulate the browser behaviour

 	**Executed the test in local machine and did not consider the distrubted architecture as test for 1 min and very low load
	
	
	
