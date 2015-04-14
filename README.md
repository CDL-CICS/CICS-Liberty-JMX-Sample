# CICS-Liberty-JMX-Sample
Using WebSphere MBeans to monitor your applications in CICS V5.3

 What is JMX:

The Java  Management Extensions API (JMX) is used for resource monitoring and management.
JMX is a Java framework and API that provides a way of exposing your application's internals using a widely accepted implementation, allowing it to be picked up and used by any tool that conforms to that implementation, JConsole for example.

 

What is Mbeans:
Managed beans (MBeans), non-static Java classes with public constructors. Get and set methods of the Bean are exposed as 'attributes', whilst all other methods are exposed as 'operations'.

 

Two types of Mbeans:

    Provided Mbeans

For example:

WebSphere:type=JvmStats

Management interface: com.ibm.websphere.monitor.jmx.JvmMXBean
Comments: Available when the monitor-1.0 feature is enabled
Heap information
CPU information
GC information

    User written Mbeans,

need to register your Mbeans

You can access the attributes and call the operations of Java? Management Extensions (JMX) management beans (MBeans) on the Liberty profile. In addition, you can register your own MBeans from an application running on the Liberty profile.

 

How to access:

 JMX client    -----connector---->  JMX Server(Liberty Profile)

     JMX client:

Jconsole and Your written JMX Client

    Connectors:

There are two JMX connectors supported on the Liberty profile,

        The local connector is enabled through the Liberty feature localConnector-1.0. Access through the local connector is protected by the policy implemented by the SDK in use. Currently the SDKs require that the client runs on the same host as the Liberty profile, and under the same user ID.
        The REST connector is enabled through the Liberty feature restConnector-1.0. Remote access through the REST connector is protected by a single administrator role. In addition, SSL is required to keep the communication confidential. The restConnector-1.0 feature already includes the ssl-1.0 feature.

 

Example in CICS Liberty:

Using WebSphere MBeans to monitor your applications:

    Server.xml

        <feature>localConnector-1.0</feature>
        <feature>monitor-1.0</feature> 
