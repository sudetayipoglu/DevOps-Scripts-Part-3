📌 **Introduction**
<br><br>
This repository contains essential DevOps & Cloud Engineering scripts for monitoring, backup and deployment. These scripts demonstrate best practices in DevOps and cloud automation, making this repository a valuable asset for any Cloud Engineer or DevOps professional.
# DevOps Scripts Part 3
🔹 **Monitoring & Logging**
<br><br>
**Log Monitoring - Real-time Error Detection (Bash Script)**

```yaml
#!/bin/bash
# Monitor syslog in real time and detect errors
tail -f /var/log/syslog | while read LINE
do
  if [[ "$LINE" == *"error"* ]]; then
    echo "ERROR DETECTED: $LINE"
  fi
done
```
✅ **Usage:**
```yaml
chmod +x log-monitor.sh
./log-monitor.sh
```

🔹 **Backup & Recovery**
<br><br>
**MySQL Database Backup Script**

```yaml
#!/bin/bash
# Define backup variables
TIMESTAMP=$(date +"%F")
BACKUP_DIR="/backup"
MYSQL_USER="root"
MYSQL_PASSWORD="password"
DATABASE="mydb"

# Create backup directory if not exists
mkdir -p $BACKUP_DIR

# Dump the database into a backup file
mysqldump -u $MYSQL_USER -p$MYSQL_PASSWORD $DATABASE > "$BACKUP_DIR/$DATABASE-$TIMESTAMP.sql"
echo "Backup completed!"
```
✅ **Usage:**
```yaml
chmod +x backup-db.sh
./backup-db.sh
```

🔹 **Deployment & Rollback**
<br><br>
**Rolling Deployment (Bash Script)**

```yaml
#!/bin/bash
# Deploy a new version of the application
echo "Deploying new version..."
docker pull myapp:latest  # Pull latest Docker image
docker stop myapp  # Stop the existing container
docker rm myapp  # Remove the old container
docker run -d --name myapp -p 3000:3000 myapp:latest  # Start new container
echo "Deployment successful!"
```
✅ **Usage:**
```yaml
chmod +x deploy.sh
./deploy.sh
```
🎯 **Conclusion**

This repository provides a comprehensive collection of scripts for DevOps, Cloud Engineering, and Automation. If you're preparing for a Cloud Engineer or DevOps role, these scripts will demonstrate your skills in Infrastructure as Code, CI/CD, Containerization, Security, and Monitoring.

✅ Star this repository ⭐ and start using these scripts in your DevOps projects! 🚀
