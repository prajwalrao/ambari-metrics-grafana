![Apache Ambari Logo](https://raw.githubusercontent.com/prajwalrao/ambari-metrics-grafana/master/img/apache-ambari-project.jpg)
# Ambari Metrics System Plugin for Grafana 3.x

### Requires
* **Apache Ambari** > 2.2.x
* **Grafana** > 3.x.x (works with betas)

### Install

#### Clone into plugins directory
Either clone this repo into your grafana plugins directory (default /var/lib/grafana/plugins if your installing grafana with package).
Restart grafana-server and the plugin should be automatically detected and used.

```
git clone https://github.com/prajwalrao/ambari-metrics-grafana.git
sudo service grafana-server restart
```
----

### OR

#### Clone into a directory of your choice

The edit your grafana.ini config file (Default location is at /etc/grafana/grafana.ini) and add this:

```ini
[plugin.grafana-ambari-metrics]
path = /home/your/clone/dir/ambari-metrics-grafana
```

Note that if you clone it into the grafana plugins directory you do not need to add the above config option. That is only
if you want to place the plugin in a directory outside the standard plugins directory. Be aware that grafana-server
needs read access to the directory.

----

#### Changelog

##### v 1.0.0 (06/14)
- Inital release