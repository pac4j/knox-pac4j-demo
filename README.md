# knox-pac4j-demo
Knox demo to test the gateway-provider-security-pac4j

java -agentlib:jdwp=transport=dt_socket,server=y,suspend=y,address=5005 -jar bin\gateway.jar

java -jar bin\gateway.jar

https://127.0.0.1:8443/gateway/sandbox/webhdfs/v1/tmp?op=LISTSTATUS
