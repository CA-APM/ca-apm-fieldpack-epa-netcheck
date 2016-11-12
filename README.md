# EPAgent Plug-in for Simple Network and Server Health Check

# Description

An EPAgent plug-in that monitors server and port ping and socket connections.

The datafile.txt file is list of servers and ports to be tested (includes sample format in the header).

The netCheck.pl file is the main PERL program.

For installation instructions, see the README.md file.

# Short Description

An EPAgent plug-in that monitors server and port ping and socket connections.

# APM Version

Tested with CA APM 9.7.1 Enterprise Manager, EPAgent 9.7.1, and Perl 5.10+.

# Dependencies

Tested with CA APM 9.7.1 Enterprise Manager, EPAgent 9.7.1, and Perl 5.10+.

# Licensing
Apache License, version 2.0. See [Licensing](https://www.apache.org/licenses/LICENSE-2.0)

# Prerequisite
An installed and configured EPAgent.

Find the version 9.6 to 10.x documentation on [the CA APM documentation wiki.](https://docops.ca.com)

# Install and Configure EPAgent Plug-in for Simple Network and Server Health Check

1. Extract the plug-in to <*EPAgent_Home*>\epaplugins.
2. Configure the IntroscopeEPAgent.properties file in <*EPAgent_Home*>.

  * a. Add a stateful plug-in entry for NMON LogReader.
   
  * b. Add stateless plug-in properties.
  
       For example:
	   
	   introscope.epagent.plugins.stateless.names=NETCHECK (can be appended to a previous entry)
	  
	   introscope.epagent.stateless.NETCHECK.command=perl <*EPAgent_Home*>/epaplugins/netcheck/netCheck.pl <*EPAgent_Home*>/epaplugins/netcheck/datafile.txt"
       
	   introscope.epagent.stateless.NETCHECK.delayInSeconds=900

3. (Optional) Install modules Net::Ping and IO::Socket::INET if your PERL distribution does not have them.

# Use EPAgent Plug-in for Simple Network and Server Health Check

Start the EPAgent using the control script in the <*EPAgent_Home*>/bin directory.

# Debug and Troubleshoot
Update the root logger in <*EPAgent_Home*>/IntroscopeEPAgent.properties from INFO to DEBUG, then save. No managed appklication restart needed.

You can also manually execute the plug-in from a console and use the PERL built-in debugger.

# Support
This document and plug-in are made available from CA Technologies. They are provided as examples at no charge as a courtesy to the CA APM Community at large. This plug-in might require modification for use in your environment. However, this plug-in is not supported by CA Technologies, and inclusion in this site should not be construed to be an endorsement or recommendation by CA Technologies. This plug-in is not covered by the CA Technologies software license agreement and there is no explicit or implied warranty from CA Technologies. The plug-in can be used and distributed freely amongst the CA APM Community, but not sold. As such, it is unsupported software, provided as is without warranty of any kind, express or implied, including but not limited to warranties of merchantability and fitness for a particular purpose. CA Technologies does not warrant that this resource will meet your requirements or that the operation of the resource will be uninterrupted or error free or that any defects will be corrected. The use of this plug-in implies that you understand and agree to the terms listed herein.
Although this plug-in is unsupported, please let us know if you have any problems or questions. You can add comments to the CA APM Community site so that the author(s) can attempt to address the issue or question.
Unless explicitly stated otherwise this plug-in is only supported on the same platforms as the CA APM Java agent.

# Support URL
https://github.com/htdavis/ca-apm-fieldpack-epa-netcheck/issues

# Product Compatibilty Matrix
http://pcm.ca.com/

# Change Log
Changes for each plug-in version.

Version | Author | Comment
--------|--------|--------
1.0 | Hiko Davis | First version of the plug-in.