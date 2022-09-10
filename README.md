# jmeter-test
'jmeter -n -f -t ./test_plan.jmx -l ./results.jtl -j ./test.log -e -o ./test1'

```shell
jmeter -Dlog_level.jmeter=DEBUG \
	-JTARGET_PROTOCOL=http \
	-JTARGET_HOST=localhost -JTARGET_PORT=3000 \
	-JTARGET_PATH=/api/v1 -JTHREADS=20 \
	-n -f -t ./test-plan.jmx -l ./test-plan.jtl -j ./jmeter.log \
	-e -o ./report
```