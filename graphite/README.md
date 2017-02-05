## how to run

1. `docker-compose up -d`
2. send metric with netcat

```
for i in `seq 1 1000`; do  echo "local.testing.cpuUsage `ps -A -o %cpu | awk '{s+=$1} END {print s/100}'`  `date +%s`" | nc -c 127.0.0.1 2003; sleep 2 && echo $i; done
```
3. open `http://localhost:10088/?target=local.testing.cpuUsage&from=-25min&vtitle=CPUUsage&yMin=0&yMax=1&minXStep=0&lineMode=slope`  , use `guest/guest` to login
4. the corresponding whisper file is created in container with path `/opt/graphite/storage/whisper/local/testing/cpuUsage.wsp`

[graphite docker image](https://hub.docker.com/r/sitespeedio/graphite/)