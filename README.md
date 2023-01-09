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
        
