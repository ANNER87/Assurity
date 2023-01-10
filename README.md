# Assurity
To upload the performance Assignment with Assurity

#Performance Assignment#



Install JMeter


Step 1: The following JMeter tool need to be set up
        
	You can download JMeter 5.5 from https://jmeter.apache.org/download_jmeter.cgi (Required Java 8+)
	
Step2: Install Plugins Manger to JMeter as using some of additional elements.
        
	Download  plugins-manager.jar https://jmeter-plugins.org/install/Install/ and put it into lib/ext directory, then restart JMeter.
	
Step3: Download the sscript folder along with test data file

Step4: Open JMeter and open the .jmx file

Step5: Install the elements which are not in the initial JMeter


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



	
Test Results

        
Summary

	
**The objective of the test is to verify the response of the API whether it is within SLA of 500ms.
	
**4 rounds of test were executed in both GUI and non GUI mode. 
	
**90th Percent response time were within SLA of 500ms during 3 rounds and in 1 round 90th percent response time was 504ms
	
**There was an error rate which was due to one Assertion failed for 1 test data in all rounds. it get the different response and response assretion was failed.
	
**Considering all the test results this test can be marked as PASS
	
	
Observation:

#The following was 90th Percentile respponse time during 4 round of test execution

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
	
	Aggregate Test - The files with Aggreate test logs and aggreate results table for each test execution.
	
	
	
	
	
	
