## Monitoring and Logging in Google Cloud Platform for VM Instances

### Monitoring

To view the metrics and status of your VM instance we get every option since ops agent is installed:

1. **Access Cloud Monitoring Dashboard**:
   - Go to the **Google Cloud Console**.
   - Navigate to **Monitoring** by selecting the **Monitoring** option from the side menu.
   - Under **Monitoring**, click on **Dashboards**.
   - Locate and select the **Compute Engine** dashboard, which provides various performance metrics for VM instances.

2. **Customize Metrics**:
   - To view specific metrics like CPU, memory, or disk usage, select the instance you wish to monitor.
   - Customize charts and add metrics as needed to observe resource utilization over time.

### Logging with Docker `gcplogs` Driver

Since you’ve configured the Docker containers on your VM with the `gcplogs` driver, logs are sent directly to Google Cloud Logging. Here’s how to access and query them for specific containers.

1. **Access Cloud Logging**:
   - In the **Google Cloud Console**, go to **Logging** by selecting **Logs Explorer** from the side menu under **Operations**.

2. **Query Logs for Specific Containers**:
   - In the **Logs Explorer**, create a new query to locate logs for specific containers by name.

   #### Log Query for `/app-server-1` Container
   - Enter the following query to view logs for the `/app-server-1` container:
     ```plaintext
     jsonPayload.container.name="/app-server-1"
     ```

   #### Log Query for `/app-client-1` Container
   - To view logs for the `/app-client-1` container, enter:
     ```plaintext
     jsonPayload.container.name="/app-client-1"
     ```

3. **Apply and View Logs**:
   - After entering the query, click **Run Query**.
   - Logs specific to your containers `/app-server-1` and `/app-client-1` will display.
   - You can further filter logs by time, severity level, or message content as needed.

### Additional Tips

- **Set Alerts**: Use Cloud Monitoring to set alerts for critical metrics. For example, configure an alert if CPU usage goes above a certain threshold.
- **Log-based Metrics**: Create log-based metrics in Cloud Logging if you need specific insights, such as tracking errors over time.

---


