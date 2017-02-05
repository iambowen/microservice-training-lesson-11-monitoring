## how to run

1. `docker-compose up -d`
2. visit `http://localhost:8100/` , use `admin:password` to login
3. add datasource as influxdb by following [this](http://docs.grafana.org/datasources/influxdb/)
4. feed riemann with command `watch -n 1 ruby tests/sample_request.rb`
5. create graphs in grafana from influxdb metrics
6. visit `http://localhost:1080` and you can see the alert emails

