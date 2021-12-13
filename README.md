# log4j-hashes
A collection of hashes for all log4j core JAR files.  Use this repo to determine what version of log4j is present on your system.

Inspired by Mubix (https://github.com/mubix/CVE-2021-44228-Log4Shell-Hashes)

Source of the hashes: https://archive.apache.org/dist/logging/log4j/

The log4j / log4shell vulnerability CVE-2021-44228 is not exploitable in version 1 of log4j and is fixed in version 2.15.

Additional details available at https://logging.apache.org/log4j/2.x/security.html

To mitigate CVE-2021-44228: 

In releases >=2.10, this behavior can be mitigated by setting either the system property log4j2.formatMsgNoLookups or the environment variable LOG4J_FORMAT_MSG_NO_LOOKUPS to true. 

For releases from 2.0-beta9 to 2.10.0, the mitigation is to remove the JndiLookup class from the classpath: 

zip -q -d log4j-core-*.jar org/apache/logging/log4j/core/lookup/JndiLookup.class.”
