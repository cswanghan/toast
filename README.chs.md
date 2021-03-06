## 介绍

TOAST 是 "Toast Open Automation System for Test" 的简写。

TOAST是一个自动化测试执行系统，简单地说，这是一个可以在远程测试机器或者集群上运行自动化测试用例或自动化代码的工具，并可以通过邮件或者网页查看运行结果。

对于所有的自动化测试，使用统一的执行方式是困难的。特别是对于一个大型工程组织，例如阿里巴巴，如果想使用相同的执行平台，那么这个平台必须支持各种各样的自动化测试。这不是一件简单的事，但这也是我们为什么开发使用这个工具的原因之一。

更多使用方面的帮助，参见 [用户使用手册](https://github.com/alibaba/toast/wiki)

## Features

* Test Script/Command invoking in Remote Agent Box, like a Test Runner.
* Test Job definition, including varietal amount of stage and command.
* Test Machine Management.
* Open API.
* Four methods to run a test job: on-demmand, crontab, source depoit code check in and via Open API;
* Test Reporting.
* Test Case Management. (Ongoing, not finished yet)


## Basic Design  

About automation test case, actually if a test case was automated, a corresponding test code (usually based on a specific programming test framework, such as Xunit, Selenium or etc.) having been written already, from running aspect we look test code (usually a test method in souce code) as test case. Test code is built to excutable binary and it will run on a test box against deployed test environment. Since test code is written based on a framework, the output is formatted. 

TOAST design baed on above assumption. Test code runs in test box and TOAST can get the running output, then parsing this output and TOAST can know how many case passed, failed, or something wrong during running.

For Example, test code based JUnit always print the same formatted output to screen so that we can know the detailed running result of test case. TOAST also can recognise or parse these formatted screen output. 


## Setup & Usage

TOAST compose of three parts:
  * Front End, including Web UI and DB. {Linux}
  * Back End, or Controller. {Linux}
  * Test Box, we call it as "test agent" or "agent". {Linux or Windows}

for each part installation, see [Setup Part in User Guides](https://github.com/taobao/toast/wiki).

Here is the whole process,
  * write a script(shell, batch file etc) which can drive your test code running. 
  * keep the scirpt in a specific test box.
  * add this test box into toast machine pool.
  * in toast web UI, create a test job and input required information, such as: crontab run time, test machine, test stage, test command in each test stage, test case parser for each test command and so on.
  * manaully run this job, or by crontab.
  * get test result return from remote test box and parse case information.
  * test report will show how many cases have been passed or failed.


TOAST can also monitor souce code depoit, like svn, once specific svn url is changed TOAST job will run immediately (test report will include who is committer and what the code change is). From this point, we can look TOAST as a continuous integration infrastructure. Actually this is what we use in Taobao inc.


## Bug tracker

Have a bug or a feature request? [Please open a new issue](https://github.com/taobao/toast/issues). Before opening any issue, please search for existing issues and read the [Issue Guidelines](https://github.com/taobao/toast/issue-guidelines).


## What's difference with Existing tool
  * STAF
  * Hudson Jenkins

(to be)

## Mailing lists
Mailing lists are usually good places to ask questions. We highly recommend you subscribe Toast's mailing lists below:
  * http://code.taobao.org/mailman/listinfo/tengine (English) 
  * http://code.taobao.org/mailman/listinfo/tengine-cn (Chinese)

english version:

## Introduction

TOAST is short for "Toast Open Automation System for Test". 
TOAST is a test execution system, and general speaking, it's a tool to run your automation test case or code in a specific test box or test cluster and then show the test result back to you via Email notification or from web UI test result page.

Automation of test execution can be a difficult service to provide in a universal way. For a large engineering organization to share common test execution infrastructure, that infrastructure must support execution of a variety of testing jobs. This is why we built TOAST at Taobao.

For more usage information, see [User Guides](https://github.com/alibaba/toast/wiki)

## Features

* Test Script/Command invoking in Remote Agent Box, like a Test Runner.
* Test Job definition, including varietal amount of stage and command.
* Test Machine Management.
* Open API.
* Four methods to run a test job: on-demmand, crontab, source depoit code check in and via Open API;
* Test Reporting.
* Test Case Management. (Ongoing, not finished yet)


## Basic Design  

About automation test case, actually if a test case was automated, a corresponding test code (usually based on a specific programming test framework, such as Xunit, Selenium or etc.) having been written already, from running aspect we look test code (usually a test method in souce code) as test case. Test code is built to excutable binary and it will run on a test box against deployed test environment. Since test code is written based on a framework, the output is formatted. 

TOAST design baed on above assumption. Test code runs in test box and TOAST can get the running output, then parsing this output and TOAST can know how many case passed, failed, or something wrong during running.

For Example, test code based JUnit always print the same formatted output to screen so that we can know the detailed running result of test case. TOAST also can recognise or parse these formatted screen output. 


## Setup & Usage

TOAST compose of three parts:
  * Front End, including Web UI and DB. {Linux}
  * Back End, or Controller. {Linux}
  * Test Box, we call it as "test agent" or "agent". {Linux or Windows}

for each part installation, see [Setup Part in User Guides](https://github.com/taobao/toast/wiki).

Here is the whole process,
  * write a script(shell, batch file etc) which can drive your test code running. 
  * keep the scirpt in a specific test box.
  * add this test box into toast machine pool.
  * in toast web UI, create a test job and input required information, such as: crontab run time, test machine, test stage, test command in each test stage, test case parser for each test command and so on.
  * manaully run this job, or by crontab.
  * get test result return from remote test box and parse case information.
  * test report will show how many cases have been passed or failed.


TOAST can also monitor souce code depoit, like svn, once specific svn url is changed TOAST job will run immediately (test report will include who is committer and what the code change is). From this point, we can look TOAST as a continuous integration infrastructure. Actually this is what we use in Taobao inc.


## Bug tracker

Have a bug or a feature request? [Please open a new issue](https://github.com/taobao/toast/issues). Before opening any issue, please search for existing issues and read the [Issue Guidelines](https://github.com/taobao/toast/issue-guidelines).


## What's difference with Existing tool
  * STAF
  * Hudson Jenkins

(to be)

## Mailing lists
Mailing lists are usually good places to ask questions. We highly recommend you subscribe Toast's mailing lists below:
  * http://code.taobao.org/mailman/listinfo/tengine (English) 
  * http://code.taobao.org/mailman/listinfo/tengine-cn (Chinese)
