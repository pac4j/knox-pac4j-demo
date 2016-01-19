<p align="center">
  <img src="https://pac4j.github.io/pac4j/img/logo-knox.png" width="300" />
</p>

This `knox-pac4j-demo` is a Knox installation to test the [gateway-provider-security-pac4j](http://knox.apache.org/books/knox-0-8-0/user-guide.html#Pac4j+Provider+-+CAS+/+OAuth+/+SAML+/+OpenID+Connect) federation gateway with various authentication mechanisms: Facebook, Twitter, basic auth, CAS, SAML or OpenID Connect.

## Start & test

Start the Knox gateway on [https://127.0.0.1:8443](https://127.0.0.1:8443):

    cd knox-pac4j-demo
    java -jar bin\gateway.jar

Use: `java -agentlib:jdwp=transport=dt_socket,server=y,suspend=y,address=5005 -jar bin\gateway.jar` for debugging.

Assuming you have an Hadoop cluster running with WebHDFS on `http://localhost:50070/webhdfs`, you can call it through the [sandbox](https://github.com/pac4j/knox-pac4j-demo/blob/master/conf/topologies/sandbox.xml) gateway configuration using the following url: [https://127.0.0.1:8443/gateway/sandbox/webhdfs/v1/tmp?op=LISTSTATUS](https://127.0.0.1:8443/gateway/sandbox/webhdfs/v1/tmp?op=LISTSTATUS).

This sandbox configuration requires the SSO session to be established (`SSOCookieProvider`) by the [idp](https://github.com/pac4j/knox-pac4j-demo/blob/master/conf/topologies/idp.xml) topology which is protected by pac4j. By default, you must login via an online CAS server (login = pwd, wait a little before the server wakes up).
You can though configure the pac4j gateway provider to use other authentication mechanisms as described in the [documentation](http://knox.apache.org/books/knox-0-8-0/user-guide.html#Pac4j+Provider+-+CAS+/+OAuth+/+SAML+/+OpenID+Connect).
