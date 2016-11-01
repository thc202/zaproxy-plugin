<table border=0 cellpadding=0 cellspacing=0>
  <tr>
    <td></td>
    <td align=right valign=top>
      <a href='https://jenkins.ci.cloudbees.com/job/plugins/job/zaproxy-plugin/' align="top"><img src='https://jenkins.ci.cloudbees.com/buildStatus/icon?job=plugins/zaproxy-plugin'></a>
    </td>
  </tr>
  <tr>
    <td align=center valign=middle>
      <a href='https://www.owasp.org/index.php/OWASP_Zed_Attack_Proxy_Project/' align="top"><img src='https://www.owasp.org/images/1/11/Zap128x128.png'></a>
    </td>
    <td>
      <font size="10">Official OWASP Zed Attack Proxy Jenkins Plugin</font>
    </td>
  </tr>
</table>


The ZAP Jenkins plugin is a Jenkins plugin which extends the functionality of the ZAP security tool into a CI Environment.

  - Manage Sessions (Load or Persist)
  - Define Context (Name, Include URLs and Exclude URLs)
  - Attack Contexts (Spider Scan, AJAX Spider, Active Scan) 

You can also:
  - Setup Authentication (Form Based or Script Based)
  - Run as Pre-Build as part of a Selenium Build
  - Generate Reports

### Tech

ZAP Jenkins plugin uses a number of open source plugins to work properly:

* [ZAP API] - A REST API which allows you to interact with ZAP programmatically.

And of course the Official ZAP Jenkins plugin is open source with a [public repository][zap jenkins plugin] on GitHub.

### Issue Tracking

Issues can be created on the [Jenkins JIRA](https://issues.jenkins-ci.org/browse/JENKINS-30035?jql=project%20%3D%20JENKINS%20AND%20component%20%3D%20zaproxy-plugin) for the component zaproxy-plugin.

Notice: GitHub Issues have been disabled.

### Installation

ZAP Jenkins plugin requires [Jenkins](https://jenkins.io/) 1.580.1+ to run.

Download and extract the [desired war release](https://updates.jenkins-ci.org/download/war/).

### Requirements

ZAP Jenkins plugin requires [Zed Attack Proxy](https://github.com/zaproxy/zaproxy/wiki/Downloads) 2.5.0+ to run and can be installed via either of the following methods:

* [Custom Tools] - A generic tool installer. You define how tools get installed, and the plugin will automatically install them when needed.
* System Installed - Requires `ZAPROXY_HOME` to be defined as a System Environment Variable.

Documentation, how to setup ZAP for use with Jenkins can be found here:

* [documentation/customtools/README.md] [customtools]
* [documentation/systeminstalled/README.md] [systeminstalled]

### ZAP Plugins

The Official OWASP ZAP Jenkins plugin is currently extended with the following ZAP plugins

* [Export Report] - An official ZAP marketplace extension which allows you to customize content and export in a desired format (XHTML, XML, JSON). Supports GUI, Command line and API calls.
* [JIRA Creator] - An unofficial ZAP extension which allows you to create JIRA issues. It is an add-on NOT bundled with ZAP, nor available in the marketplace. USE AT YOUR OWN RISK AND DISCRETION.

Documentation, how to use them in your own application can be found here:

* [documentation/exportreport/README.md] [exportreport]
* [documentation/jiracreator/README.md] [jiracreator]

### Development

The Official OWASP ZAP Jenkins plugin is a Maven Jelly Project.

Start the local Jenkins instance:

    $ mvn hpi:run

### How to install

Run

    $ mvn clean package -e

to create the plugin .hpi file.

To install:

1. copy the resulting ./target/zaproxy.hpi file to the $JENKINS_HOME/plugins directory. Don't forget to restart Jenkins afterwards.

2. or use the plugin management console (http://example.com:8080/pluginManager/advanced) to upload the hpi file. You have to restart Jenkins in order to find the plugin in the installed plugins list.

For production release:

    $ mvn release:prepare release:perform -B

### Contributors

See [Contributors](CONTRIBUTORS.md)

### Todo's

See [Milestones](MILESTONES.md)

### History

See [History](HISTORY.md)

### License

See [License](LICENSE)

   [zap jenkins plugin]: <https://github.com/jenkinsci/zaproxy-plugin>
   [ZAP API]: <https://github.com/zaproxy/zaproxy/wiki/ApiDetails>
   [Custom Tools]: https://wiki.jenkins-ci.org/display/JENKINS/Custom+Tools+Plugin
   [Export Report]: <https://github.com/zaproxy/zap-extensions/wiki/HelpAddonsExportreportExportreport>
   [JIRA Creator]: <https://github.com/zaproxy/zap-extensions/wiki/HelpAddonsExportreportExportreport>
   
   [customtools]: <https://github.com/zaproxy/zap-extensions/tree/alpha/src/org/zaproxy/zap/extension/exportreport/README.md>
   [systeminstalled]: <https://github.com/zaproxy/zap-extensions/tree/alpha/src/org/zaproxy/zap/extension/exportreport/README.md>
   [exportreport]: <https://github.com/zaproxy/zap-extensions/tree/alpha/src/org/zaproxy/zap/extension/exportreport/README.md>
   [jiracreator]: <https://github.com/zaproxy/zap-extensions/tree/alpha/src/org/zaproxy/zap/extension/exportreport/README.md>