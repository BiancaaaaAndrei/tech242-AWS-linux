```
#!/bin/bash

sudo systemctl start apache2

# Run the Spring Boot application
echo "Running..."
cd ~/repo/springapi/
mvn spring-boot:start
echo "Done"
```