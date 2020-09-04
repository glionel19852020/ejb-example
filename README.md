# ejb-example

/SCRIPT CREACION DE TABLA SQL DEVELOPER
create table producto(
id Integer primary key,
nombre varchar2(100),
fecha_produccion varchar2(100),
pais varchar2(100),
descripcion varchar2(200)
)


/DEPENDENCIAS DEL PROYECTO ARCHIVO POM.XML DEL PROYECTO
<dependency>
    <groupId>org.hibernate</groupId>
    <artifactId>hibernate-core</artifactId>
     <version>5.2.11.Final</version>
 </dependency>
    <dependency>
    <groupId>org.hibernate.javax.persistence</groupId>
    <artifactId>hibernate-jpa-2.1-api</artifactId>
    <version>1.0.0.Final</version>
  </dependency>
 
 <dependency>
    <groupId>org.primefaces</groupId>
    <artifactId>primefaces</artifactId>
    <version>8.0</version>
    <type>jar</type>
 </dependency>
 
 
/EJEMPLO DE PERSISTENCIA
 
 <?xml version="1.0" encoding="UTF-8"?>
<persistence version="2.2" xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence http://xmlns.jcp.org/xml/ns/persistence/persistence_2_2.xsd">
  <!-- Define Persistence Unit -->
  <persistence-unit name="my_persistence_unit" transaction-type="JTA">
   <provider>org.hibernate.jpa.HibernatePersistenceProvider</provider>
    <jta-data-source>Orajdbc</jta-data-source>
         <exclude-unlisted-classes>false</exclude-unlisted-classes>
    <properties>
     <property name="hibernate.dialect" value="org.hibernate.dialect.Oracle12cDialect"/>
      <property name="hibernate.transaction.jta.platform" value="org.hibernate.service.jta.platform.internal.SunOneJtaPlatform"/>
      <property name="hibernate.show_sql" value="true"/>
    </properties>
  </persistence-unit>
</persistence>



/DEPENDENCIAS DE JSF A CONFIGURAR EN PAGINA XHTML
xmlns:f="http://java.sun.com/jsf/core"
    xmlns:p="http://primefaces.org/ui"
	  
	  
/CREACION DE TABLA PAGINA WEB PRIMEFACES
<p:dataTable value="#{personabean.persona}" var="p">
            <p:column headerText="CODIGO">
                <h:outputText value="#{p.id}"/>
             </p:column>
            
              <p:column headerText="NOMBRES">
                  <h:outputText value="#{p.nombres}"/>
             </p:column>
            
              <p:column headerText="APELLIDOS">
                  <h:outputText value="#{p.apellidos}"/>
             </p:column>
            
              <p:column headerText="DUI">
                  <h:outputText value="#{p.dui}"/>
             </p:column>
            
             <p:column headerText="DIRECCION">
                <h:outputText value="#{p.direccion}"/>
             </p:column>
            
             <p:column headerText="TIP_SANGRE">
                  <h:outputText value="#{p.tipSangre}"/>
             </p:column>
            
             <p:column headerText="CORREO">
                  <h:outputText value="#{p.email}"/>
             </p:column>     
