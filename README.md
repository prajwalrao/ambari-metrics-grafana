![Apache Ambari Logo](https://raw.githubusercontent.com/prajwalrao/ambari-metrics-grafana/master/img/apache-ambari-logo-sm.png)
# Ambari Metrics System Datasource for Grafana 3.x

![Screenshot](https://raw.githubusercontent.com/prajwalrao/ambari-metrics-grafana/master/img/ams-screenshot.png)

##### Ambari Metrics System ("AMS") is a system for collecting, aggregating and serving Hadoop & other Stack services and system metrics in Ambari-managed clusters.

This datasource plugin allows you to visualize all the metrics that are available via the [AMS Collector API](https://cwiki.apache.org/confluence/display/AMBARI/Metrics+Collector+API+Specification). 

### Requires
* **Apache Ambari** > 2.2.x
* **Grafana** > 3.x.x

----

### Install

#### Install via the Grafana CLI

Use the grafana-cli tool to install Ambari Metrics System Datasource from the commandline:

````
grafana-cli plugins install praj-ams-datasource
````

The plugin will be installed into your grafana plugins directory; the default is /var/lib/grafana/plugins. [More information on the cli tool](http://docs.grafana.org/v3.0/plugins/installation/).

#### OR

#### Clone into plugins directory
Either clone this repo into your grafana plugins directory (default /var/lib/grafana/plugins if your installing grafana with package).

Restart grafana-server and the plugin should be automatically detected and used.

```
cd /var/lib/grafana/plugins
git clone https://github.com/prajwalrao/ambari-metrics-grafana.git
sudo service grafana-server restart
```

#### OR

#### Clone into a directory of your choice

The edit your grafana.ini config file (Default location is at /etc/grafana/grafana.ini) and add this:

```ini
[plugin.ambari-metrics-grafana]
path = /home/your/clone/dir/ambari-metrics-grafana
```

Note that if you clone it into the grafana plugins directory you do not need to add the above config option. That is only if you want to place the plugin in a directory outside the standard plugins directory. Be aware that grafana-server needs read access to the directory.

----

### Dashboard Import

You can automatically import pre-built dashboards for AMS & Ambari by editing the grafana.ini config file (Default location is at /etc/grafana/grafana.ini) and editing this (should be at the end of the file).

```
[dashboards.json]
;enabled = false
;path = /var/lib/grafana/dashboards
```

to

```
[dashboards.json]
enabled = true
path = /var/lib/grafana/plugins/ambari-metrics-grafana/dashboards
```

If you've cloned the plugin elsewhere, replace the path above with that accordingly.

**You can always import individual dashboards by using the "Import" option from the dropdown on the top left of the page (next to the logo)**

----

#### Changelog

##### v1.0.1 (06/28)
- Edited Logo
- Added Ambari Home Dashboard
- Updated README


##### v1.0.0 (06/14)
- Inital release

