# jmeter-test

## Run in local

```shell
jmeter -Dlog_level.jmeter=DEBUG \
	-JTARGET_PROTOCOL=http \
	-JTARGET_HOST=localhost -JTARGET_PORT=3000 \
	-JTARGET_PATH=/api/v1 -JTHREADS=20 \
	-n -f -t ./test-plan.jmx -l ./test-plan.jtl -j ./jmeter.log \
	-e -o ./report
```

## Run from docker

```shell
docker run --rm --name jmeter -i \
	-v ${PWD}:/opt/test -w /opt/test \
	-e IMAGE_TIMEZONE='America/Guayaquil' \
	--add-host=host.docker.internal:host-gateway \
	justb4/jmeter:5.4 \
	-Dlog_level.jmeter=DEBUG \
	-JTARGET_PROTOCOL=http \
	-JTARGET_HOST=192.168.1.121 -JTARGET_PORT=3000 \
	-JTARGET_PATH=/api/v1 -JTHREADS=20 \
	-n -f -t ./test-plan.jmx -l ./test-plan.jtl -j ./jmeter.log \
	-e -o ./report
```