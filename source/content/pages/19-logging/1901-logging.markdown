title: Logging
category: page
slug: logging
sort-order: 19

# Logging
Logging is a common mechanism for monitoring web applications written with a
web framework. Runtime exceptions that prevent code from running are 
important to log to investigate and fix the source of the problems. 
Informational and debugging logging also helps to understand how the 
application is performing even if code is working as intended.

Logging is often grouped into several categories:

1. Information
2. Debug
3. Warning
4. Error

Logging errors that occur while a web framework is running is crucial to
understanding how your application is performing. 
[Raven](http://raven.readthedocs.org/en/latest/) is a Python client for the
[Sentry](https://github.com/getsentry/sentry) exception logging and 
aggregation application. Raven provides the way to send exceptions to
Sentry, which should be deployed on a separate server from your production
infrastructure. Raven can also be used by Python scripts to send other
log data to Sentry for aggregation. Sentry provides a clean web application
interface for viewing the exceptions. Sentry can also be configured with a
mail plugin to send emails when exceptions occur.

## Logging Aggregators
When you are running your application on several servers, it is helpful
to have a monitoring tool called a "logging aggregator". You can configure your
application to forward your system and application logs to one location that 
provides tools such as to viewing searching, and monitoring logging events across your cluster. 

Another advantage of log aggregatortion tools is they allow you to set up custom alerts
and alarms so you can get notified when error rates breach a certain threshold.

### Log Aggregator Third Party Services
* [loggly](https://www.loggly.com/) Loggly is a third party cloud based application that
aggregates logs. They have instructions for every major language, including python. It includes email
alerting on custom searches. 
* [papertrail](https://papertrailapp.com/) Paper trail is similar to both loggly and splunk and provides
integration with S3 for 
* [splunk](http://www.splunk.com/) Splunk offers third party cloud and self hosted solutions 
for event aggregation. It excells at searching and data mining any text based data. 

### Open Source Log Aggregators
* [Graylog2](http://graylog2.org/) Provides a central server for log aggregation as well as a GUI for
browsing and searching through log events. There are libraries for most major languages, including python.
Saves data in elasicache.
* [Logstash](http://logstash.net/) Similar to Graylog2, logstash offers features to programatically
configure log data workflows.
* [Scribe](https://github.com/facebook/scribe) A project written by facebook to aggregate logs. It's designed
to run on multiple servers and scale with the rest of your cluster. Uses the Thrift messagaing format so it can
be used with any language. 
