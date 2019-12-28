# Установка кастомного DataSource в WildFly
Вместо того, чтобы хардкодить в приложении данные для подключения к БД, можно просто получить dataSource по его имени и пользоваться.  
Это так же хорошо с точки зрения безопасности, т.к. программистам не придётся знать данные для подключения к БД, их будет знать только администратор сервера приложений.

1. Надо скачать драйвер для нашей базы данных и задеплоить его(да, задеплоить jar файл). Как это сделать можно найти в руководстве по установке WildFly
1. Откройте файл \<wildfly-directory\>/standalone/configuration/standalone.xml
1. Ищем тег \<datasources\>
1. Добавляем внутрь 
```xml
<!--Пример датасорса для Postgres -->
<datasource jndi-name="java:jboss/datasources/postgresDS" pool-name="database-datasource-postgres" enabled="true" use-java-context="false">
	<connection-url>jdbc:postgresql://pg:5432/studs</connection-url>
	<driver>postgresql-42.2.5.jar</driver>
	<security>
		<user-name>s******</user-name>
		<password>*****</password>
	</security>
</datasource>
<!--Пример датасорса для Oracle -->
<datasource jndi-name="java:jboss/datasources/oracleDS" pool-name="database-datasource-orbis" enabled="true" use-java-context="false">
        <connection-url>jdbc:oracle:thin:@localhost:1521:orbis</connection-url>
        <driver>ojdbc6.jar</driver>
        <security>
                <user-name>s******</user-name>
                <password>******</password>
        </security>
</datasource>

```  
Внутри тега security вводите свои данные для подключения к гелиосу.  
В теге driver надо указать название драйвера, который мы задеплоили.  

### Замечание

Если вы устанавливали WildFly 1-ым способом (см. руководство по установке WildFly), 
то там уже установлены драйверы и соответсвующие датасорсы для баз данных Oracle и Postgres,
вам надо только ввести ваши логин и пароль, а также установить аттрибут enabled из "false" в "true" в теге \<datasource\>

