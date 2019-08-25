# gsoc2019-report

##### Organization: Apache Software Foundation

##### Project: Apache Incubator Nemo

##### Mentor: Um Taegeon, Yang Youngseok

##### Student: Gao Zhiyuan

### Description

My GSoC project allows Nemo to benefit from serverless computing, more precisely, allowing tasks to be executed by LambdaExecutors running on AWS Lambda Functions. Using or not using LambdaExecutor will not affect any existing feature of the default executor.

User can specify parameters to choose bewteen default executor and LambdaExecutor that I have implemented. User is supposed to prepare AWS credentials, and to do a one line deploy of the LambdaExecutor. A `how-to` Documentation is already filed as a PR, ready to be merge later on into NEMO readme.

There are, unfortunately limitations to current LambdaExecutor. Only single stage applications are implemented, object deserialization suffers from Guava pitfalls, multiple lambda executors are not supported to run, and there is no integration test (e.g. circleCI) for LambdaExecutor. 

They are not simple, and they can take another several months. I am willing to conrtibute to those feature step by step in the upcoming time.

### JIRA Issues

* [NEMO-352: Nemo on AWS Lambda](https://issues.apache.org/jira/browse/NEMO-352)
* [NEMO-385: Support Lambda Pass with lambda policy and lambda resource property](https://issues.apache.org/jira/browse/NEMO-385)(Resolved)
* [NEMO-387: Support Lambda Scheduler](https://issues.apache.org/jira/browse/NEMO-387)(Resolved)
* [NEMO-398: ExecutorRepresenter interface and LambdaExecutorRepresenter](https://issues.apache.org/jira/browse/NEMO-398)(PR available)
* [NEMO-404: Provide user argument to use lambda executor representer](https://issues.apache.org/jira/browse/NEMO-404)(Resolved)
* [NEMO-406: Invoke LambdaExecutor without creating containers](https://issues.apache.org/jira/browse/NEMO-406)(PR available)
* [NEMO-407: LambdaHandler for single-stage execution](https://issues.apache.org/jira/browse/NEMO-407)(PR available)
* [NEMO-408: Netty Connection between LambdaExecutor and Nemo](https://issues.apache.org/jira/browse/NEMO-408)(Implementation Finished)
* [NEMO-415: Multiple LambdaExecutor dispatching](https://issues.apache.org/jira/browse/NEMO-415)
* [NEMO-416: Guava vendor version conflict when deserializing Task object](https://issues.apache.org/jira/browse/NEMO-416)(Bug report)
* [NEMO-417: User documentation on how to use LambdaExecutor](https://issues.apache.org/jira/browse/NEMO-417)

### PR

* [#214 [NEMO-385]LambdaPass, LambdaPolicy and ResourceLambdaProperty](https://github.com/apache/incubator-nemo/pull/214)(Merged)
* [#216 [NEMO-387] LambdaScheduler](https://github.com/apache/incubator-nemo/pull/216)(Closed)
* [#227 [NEMO-398] ExecutorRepresenter interface and DefaultExecutorRepresenter](https://github.com/apache/incubator-nemo/pull/227)(Merged)
* [#228 [NEMO-402] Fix guava version conflict](https://github.com/apache/incubator-nemo/pull/228)(Merged)
* [#229 [NEMO-404] Provide user argument to use lambda executor representer](https://github.com/apache/incubator-nemo/pull/229)(Closed)
* [#230 [NEMO-404] Provide user argument to use lambda executor representer](https://github.com/apache/incubator-nemo/pull/230)(Merged)
* [#231 [NEMO-406] Invoke LambdaExecutor without creating containers](https://github.com/apache/incubator-nemo/pull/231)(Under Review)
* [#237 [NEMO-407] LambdaHandler for single-stage execution](https://github.com/apache/incubator-nemo/pull/237)(Under review)

### Other contributions to Nemo

* [NEMO-410: SLF4J: Failed to load class “org.slf4j.impl.StaticLoggerBinder” on AWS instances](https://issues.apache.org/jira/browse/NEMO-410)(Bug report)
* [NEMO-409: Support multiple serverless framework](https://issues.apache.org/jira/browse/NEMO-409)(Suggestion)
* [NEMO-402: Broken guava version conflicts cause ERROR: Trying to remove a RunningJob that is unknown](https://issues.apache.org/jira/browse/NEMO-402)(Bug report, PR available)
* [NEMO-401: Client stalls on 70th partition under default parallellism](https://issues.apache.org/jira/browse/NEMO-401)(Bug report)
* [REEF-2057: Update Dependencies](https://issues.apache.org/jira/browse/REEF-2057)(Suggestion)

### TODO

* Fix guava version conflict on deserialization
* Support circleCI
* Support Multiple Stage Execution
* Support Multiple Executor dispatch and communication
* Support Default Executor running along with LambdaExecutor
* Support metrics in LambdaExecutor
