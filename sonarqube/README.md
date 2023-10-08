# Getting started

## Setup sonarqube

1. cd to the sonarqube directory
1. make sure that the WSL linux has the command `sudo sysctl -w vm.max_map_count=262144` run. Use link 1 to run the command at start up.
1. Do `docker compose up` to start up the sonarqube instance
1. Go to [http://localhost:9000](http://localhost:9000) and update the default admin password if it is the first time in.

## Running dotnet scan

### Getting started

1. Install scan tool `dotnet tool install --global dotnet-sonarscanner`
1. Make sure your JDK is installed. If on windows make sure your `JAVA_HOME` is updated to the valid path.

### Scanning

``` bash
dotnet sonarscanner begin /d:sonar.host.url="http://localhost:9000"  /d:sonar.token="<Your Token>"
dotnet build
dotnet sonarscanner end /d:sonar.token="<Your Token>"
```


## Resources

1. https://superuser.com/questions/1717816/how-to-run-command-when-starting-a-machine-in-wsl2
2. https://plainenglish.io/blog/how-to-set-up-sonarqube-locally-on-a-react-typescript-project-ec02cd8e2626
