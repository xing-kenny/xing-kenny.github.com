<h2><font size="16" color="blue">Apache Tomcat 7 :: JNDI Datasource HOW-TO :: MySQL DBCP Example</font></h2>

### method1
#### Context configuration : Configure the JNDI DataSource in Tomcat by adding a declaration for your resource to your Context

    <Context>
      <Resource name="jdbc/TestDB"
      ...
    </Context>	

#### web.xml configuration

    <resource-ref>
      <description>DB Connection</description>
      <res-ref-name>jdbc/TestDB</res-ref-name>
      <res-type>javax.sql.DataSource</res-type>
      <res-auth>Container</res-auth>
    </resource-ref>
   
### method2
#### server.xml
    <GlobalNamingResources>
      <Resource   

#### Context configuration

    <Context>
      <ResourceLink name="jdbc/tiguAS" global="jdbc/tiguAS" type="javax.sql.DataSource"/>

see [JNDI Datasource HOW-TO]    

[JNDI Datasource HOW-TO]: http://tomcat.apache.org/tomcat-7.0-doc/jndi-datasource-examples-howto.html	     