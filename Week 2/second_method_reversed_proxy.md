## Reverse Proxy Configuration - Option Number 2
Instead of repeatedly rewriting the file, employ a conditional check to dynamically modify it only if necessary.

## Testing Approach:

- Begin with a functional script without reverse proxy configuration.
- Install, start, and enable Apache, add the necessary modules, and restart Apache.
- Navigate to the /etc/apache2/sites-available/ directory.
- Create a backup of the 000-default.conf file: cp 000-default.conf 000-default.conf.bk.
- Manually test the file editing line (sed) with proper escaping for forwardslashes.
- Manually test the if statement with a file containing and lacking the ProxyPass statement.
- Evaluate the script in a fresh instance.
- Assess the script in user data.
- Create an Amazon Machine Image (AMI) from the functional instance.
- Launch an instance from the generated AMI.
  
This refined method ensures a streamlined and efficient process for configuring and testing the reverse proxy setup.

## Code:
```
if grep -q 'ProxyPreserveHost On' /etc/apache2/sites-available/000-default.conf; then
    echo "Reverse proxy already configured."
else
    sudo sed -i '/DocumentRoot \/var\/www\/html/ a\ProxyPreserveHost On\nProxyPass \/ http:\/\/localhost:5000\/\nProxyPassReverse \/ http:\/\/localhost:5000\/\n' /etc/apache2/sites-available/000-default.conf
    fi
```