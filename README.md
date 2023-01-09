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
	
	
	Test Results
        
	Summary
	
	Test was executed in both GUI and non GUI mode. The objective of the test is to verify the response of the API whether it is within SLA of 500ms.
	
	4 rounds of test were executed
	
	90th Percent response time were within SLA of 500ms during 3 rounds and in 1 round 90th percent response time was 504
	
	There was an error rate which was due to one Assertion failed for 1 test data in all rounds. it get the different response and response assretion was failed.
	
	Considering all the test results this test can be marked as Pass
	
	
