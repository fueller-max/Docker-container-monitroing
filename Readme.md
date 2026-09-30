## Docker containers monitroing via Grafana

For Docker containers monitroing use such stack: Prometheus, cAdvisor, and Grafana inside our Docker environment.
* cAdvisor (Container Advisor): This is a lightweight tool built by Google that connects directly to the Docker socket. It collects real-time resource usage (CPU, memory, network, and disk I/O) for every running container.
* Prometheus: Acts as the time-series database to scrape and store metrics from cAdvisor.
* Grafana: Connects to Prometheus to display beautiful, real-time dashboards and handle alerting.

#### Grafana setup after service has stared:

1. Log in with the default credentials (admin / admin)
2. Add a new Data Source, select Prometheus, and point it to http://prometheus:9090.
3. To avoid building a dashboard from scratch, click Dashboards -> New -> Import, and use Dashboard ID 14282 or 10619 (popular, pre-built community dashboards designed specifically for Docker + cAdvisor metrics).

#### Example of Grafan`s dashboard:

![](/monitoring/pics/dashboard_cadvisor.png)