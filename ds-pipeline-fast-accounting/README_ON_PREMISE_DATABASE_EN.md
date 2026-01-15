To enable Data Suite to display your actual data on reports, you need to install the Data Collector Agent on your server. The Agent extracts data from the Fast Accounting database and sends it to Data Suite as raw data. This raw data is then processed through the ETL pipeline and becomes ready for display.

1. Click "Download Agent Code" above, extract it to get the **./repo** folder.
2. Upload the **./repo** folder to your server.
3. Edit the file **./repo/agent.env** to add database connection details. Note: use an account with read permissions on the Fast Accounting database.
4. Install Docker and Docker Compose on the server 
	``` $ cd ./repo
	$ apt update
	$ apt install docker.io
	$ apt install docker-compose-plugin ```
5. Build and run the agent
	``` $ docker compose build
	$ docker compose up -d ```
6. To stop the agent
	``` $ docker compose down ```
7. Check the list on the left to confirm raw data has been uploaded to Data Suite. When the "Run Pipeline" button lights up, the system is ready.
8. Click "Run Pipeline" to run the ETL process and see real data appear on the reports.