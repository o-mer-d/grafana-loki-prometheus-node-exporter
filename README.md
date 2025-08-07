# Monitoring Application

A comprehensive monitoring solution that leverages the powerful combination of **Grafana**, **Loki**, **Promtail**, **Prometheus**, and **Node Exporter** to effortlessly monitor your systems and aggregate logs with precision and efficiency.

## 🚀 Components

### Grafana
An open-source platform for monitoring and observability. It lets you query, visualize, and alert on your metrics to better understand system performance.

### Prometheus
An open-source monitoring system that collects and stores time-series metrics from applications and infrastructure. It uses a powerful query language (PromQL) to analyze data and supports alerting based on defined conditions.

### Loki
A horizontally-scalable, highly-available log aggregation system inspired by Prometheus. It is designed for efficiently collecting, storing, and querying logs from multiple sources. Unlike traditional logging systems, Loki indexes only metadata, making it cost-effective and easy to integrate with Grafana.

### Promtail
An agent that collects logs from local sources and ships them to Loki.

### Node Exporter
A Prometheus exporter that collects hardware and OS-level metrics from Linux servers. It provides detailed system information like CPU, memory, disk usage, and network statistics to be scraped by Prometheus.

## 🏃‍♂️ Running the Application

Use the following command to run the application:

```bash
docker compose up -d
```

This command starts the applications using the Docker Compose file.

**Default Credentials:**
- Username: `admin`
- Password: `admin`

> ⚠️ **Note:** You will be required to change the initial password after logging in for the first time.

## 🔍 Checking the Status of Services

You can check the status of the services by visiting the following URLs:

- **`<vm-or-host-ip>:3100/metrics`** - Shows various metrics related to the application
- **`<vm-or-host-ip>:9090`** - Prometheus dashboard where you can query your metrics
- **`<vm-or-host-ip>:3000`** - Access Grafana

> 📝 **Important:** Replace `<vm-or-host-ip>` with your VM's IP address if running on a virtual machine, or your host's IP address if running on the host machine.

## ⚙️ Configuration

### Prometheus Configuration
The Prometheus configuration is located in the `./config/prometheus/prometheus.yml` file. This file tells Prometheus which services to collect metrics from. By default, it is configured to collect metrics from the Node Exporter container.

### Promtail Configuration
The Promtail configuration is located in the `./config/promtail/config.yml` file. This file specifies which directories Promtail will collect logs from and where it will send them. By default, logs under the `/var/log` directory are configured to be sent to the Loki container.

### Node Exporter
Node Exporter is a tool that collects information about the system, including CPU, disk, memory, temperature, network, and more. It presents this information in a format that Prometheus can use.

## 📊 Create a New Dashboard

Follow these steps to set up monitoring dashboards:

### 1. Create Data Sources
Create two new data sources in Grafana:

- **Prometheus Data Source:**
  - URL: `http://prometheus:9090`

- **Loki Data Source:**
  - URL: `http://loki:3100`

### 2. Import Dashboards
Import pre-built dashboards or create your own:

- **Prometheus Monitoring Dashboard:**
  - Import dashboard with ID: `14513`
  - Or create a custom dashboard

- **Loki Monitoring Dashboard:**
  - Import dashboard with ID: `23129`
  - Or create a custom dashboard

## 📋 Quick Start Checklist

- [ ] Clone the repository
- [ ] Run `docker compose up -d`
- [ ] Access Grafana at `<your-ip>:3000`
- [ ] Login with admin/admin credentials
- [ ] Change default password
- [ ] Configure data sources
- [ ] Import monitoring dashboards
- [ ] Start monitoring your systems!

## 🛠️ Troubleshooting

If you encounter any issues:

1. Check if all containers are running: `docker compose ps`
2. View container logs: `docker compose logs <service-name>`
3. Verify network connectivity between services
4. Ensure proper configuration files are in place

---

**Happy Monitoring! 📈**
