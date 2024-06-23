# Test Plan

*This is the template for your test plan. The parts in italics are concise explanations of what should go in the corresponding sections and should not appear in the final document.*

**Author**: \<Shengying Li（Team075)\>

## 1 Testing Strategy

### 1.1 Overall strategy

*This section should provide details about your unit-, integration-, system-, and regression-testing strategies. In particular, it should discuss which activities you will perform as part of your testing process, and who will perform such activities.*

Unit test: 
a)input-save for current job 
b)input-save for job offer
c)choose-compare for multiple job offers
d)adjust-save for comparison settings

Integration test:
a)current job is able to be compared after edited and saved
b)job offers is able to be compared after edited and saved
c)comparison settings is able in job comparison after edited

system test:
test the whole system from main menu, entering job offer and save, entering current job, adjusting comparison setting and job comparison.

Regression testing:
After modification, test whether each function could work or not.


### 1.2 Test Selection

*Here you should discuss how you are going to select your test cases, that is, which black-box and/or white-box techniques you will use. If you plan to use different techniques at different testing levels (e.g., unit and system), you should clarify that.*

black-box: entering complete job offer and testing all functions: job offer saving, job offer comparison, comparison adjusting 
white-box: testing edge case and invalid input, such as blank input in job offer, invalid string input for integer feature, minimum and largest value in comparison weight, invalid value in comparison weight

### 1.3 Adequacy Criterion


*Define how you are going to assess the quality of your test cases. Typically, this involves some form of functional or structural coverage. If you plan to use different techniques at different testing levels (e.g., unit and system), you should clarify that.*

Test all app function: job offer/current job entering and saving, job comparison, comparison setting adjustment

Test all user behavior: correct input，edge input(defulat value, maximum value and minimum value), invalid input(blank input, wrong input type), incomplete input


### 1.4 Bug Tracking

*Describe how bugs and enhancement requests will be tracked.*

There will be bug tracking table, recording the situation how the bug showed up, the description of the bug, the steps of how the bug occured, the status of the bug and the way of fixing the bug after the bug has been fixed.


### 1.5 Technology

*Describe any testing technology you intend to use or build (e.g., JUnit, Selenium).*

JUNIT will be used to write and run test.


## 2 Test Cases

*This section should be the core of this document. You should provide a table of test cases, one per row. For each test case, the table should provide its purpose, the steps necessary to perform the test, the expected result, the actual result (to be filled later), pass/fail information (to be filled later), and any additional information you think is relevant.*


| No. | Purpose | Steps | Expected Result | Actual Result(filled later) | Pass/Fail (filled later) | Additional Information |
|--------------|---------|-------|---------|---------|-----------|-----------------|
|1|Test case when user enter non-complete job detail | 1.run app 2.only enter the job title and company 3.save job offer  | error message: "please fill in all the detail" |  
|2|Test case when user enter correct job offer| 1.run app 2.enter complete job offer 3.save job offer|complete job offer in job list|  
|3|Test case when user enter job offer already in the database| 1.run app 2.enter job offer with the same title and company 3.save job offer|error message:"This job offer has already been  saved"| 
|4|Edit current job and save successfully| 1.run app 2.choose edit current job from main menu 3.edit current job detail and save|current job detail has been updated|  
|5|Edit a current job without saving| 1.Start app 2.edit current job detail 3.cancel and back to main menu|current job detail should not been changed|
|6|Enter current job for the first time| 1.Start app in the initial state 2.enter job detail 3.click the current job radio button 4.save job |current job in job list|
|7|Could not enter a second current job| 1.Start app 2.enter job detail 3.click the current job radio button 4.save job |error message:"Only one current job is allowed"|
|8|Test case when user enter string input on integer feature | 1.run app 2.enter a complete job offer with Yearly salary = 'abc', cost of living as 'def', yearly bonus as 'ghi' 3.save job offer | error message:"invalid input" |
|9|Test case when user enter decimal input on integer feature | 1.run app 2.enter a complete job offer with Yearly salary = 3.5, cost of living =-2, yearly bonus =2.5 3.save job offer | error message:"invalid input" |
|10|Test case when user enter edge input on integer feature | 1.run app 2.enter a complete job offer with yearly bonus =0 3.save job offer | shows job details in job offer list with year bonus=0 |
|11|Test case when user cancel their input | 1.run app 2.enter the job offer 3.cancel job offer| Back to main menu | 
|12|Test case when user save their input | 1.run app 2.enter the job offer 3.save job offer| Back to main menu | 
|13|Start a new job offer when user finish enter job offer| 1.Start app 2.enter all job detail 3.save job offer 4.click enter another offer button |Show a new job offer enter interface |
|14|Compare the complete job offer with current job| 1.Start app 2.enter new job offer 3.save job offer 4.click compare with current job |Show the job compare page for the two jobs |
|15|Compare two job offers| 1.Start app 2.go to all job list  3.choose two jobs for comparison |Show the job compare page for the two jobs|
|16|Trying to compare more than two jobs| 1.Start app 2.go to all job list  3.choose three jobs for comparison |error message:"please choose two jobs."|
|17|Be able to go on other comparison | 1.Start app 2.go to all job list  3.choose two jobs for comparison 4.show job comparison detail 5.back to all job list and choose other pair of jobs|show new job detail comparison|
|18|Cancel comparison | 1.Start app 2.go to all job list  3.choose two jobs for comparison 4.back to main menu|show main menu|
|19|Test case when only one job in app| 1.Start app and ensure nothing in database 2.click compare job offers on main menu |error message:"no job offer in database" |
|20|Default comparison weight| 1.Start app 2.enter multiple job offers 3.save and go to all job list | Show job list ranked with default weight|
|21|Save adjusted comparison setting| 1.Start app 2.go to comparison setting page 3.change the comparison setting 4.save setting |Show new job score and rank on job list |
|22|Cancel adjusted comparison setting| 1.Start app 2.go to comparison setting page 3.change the comparison setting 4.cancel adjustment |Back to main menu and job score keep the same in all job list |
|23|Decimal input on comparison setting| 1.Start app 2.go to comparison setting page 3.set one of the weight as 0.5 4.save setting |error message:"invalid comparison setting" |
|24|Comparison setting not complete| 1.Start app 2.go to comparison setting page 3.set one of the weight as blank 4.save setting |error message:"invalid comparison setting" |
|25|Minimum edge case on comparison setting| 1.Start app 2.go to comparison setting page 3.set all the weight as 0 4.save setting|show job comparison list and all job score as 0 |
|26|Maximum edge case on comparison setting| 1.Start app 2.go to comparison setting page 3.set all the weight as 10 4.save setting|show job comparison list |
|27|Rank job by score in all job list| 1.Start app 2.enter multiple job offers with different AYS, AYB, etc. 3.save job and go to all job list|show job comparison list ranked correctly by score |
|28|Edge case when job score equal| 1.Start app 2.enter two complete job offer with same AYS,AYB,TDF,LT and RWT 3.save job offer 4. go to job comparison list with weight as default|show job comparison list ranked only by title and company|
|29|Edit the comparison setting without saving| 1.Start app 2.choose adjust comparison setting on main menu 3.change weight 4.cancel and back to main menu|job score should be the same on job list as before|
|30|Comparison weight too large| 1.start app 2.choose adjust comparison setting on main menu 3.set weight as 15 4.save comparison setting|error message:"invalid comparison setting"|
|31|Test case for user edit the current job as no longer current| 1.start app 2.go to current job editing page 3.cancel the current job radio box 4.save and back to main menu| current job been shown as no longer current in job list|
|32|Test case for user want to see the job list| 1.start app 2.from the main menu choose job compare |Show all job list|
