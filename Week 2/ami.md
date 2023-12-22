```
#!/bin/bash

sudo systemctl start apache2

# Run the Spring Boot application
echo "Running..."
cd ~/tech242-2-tier-deploy-with-world-api/WorldProject
mvn spring-boot:start
echo "Done"
```