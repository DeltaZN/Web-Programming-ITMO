### Установка кастомного DataSource в WildFly
Вместо того, чтобы хардкодить в приложении данные для подключения к БД, можно просто получить dataSource по его имени и пользоваться.  
Это так же хорошо с точки зрения безопасности, т.к. программистам не придётся знать данные для подключения к БД, их будет знать только администратор сервера приложений.

1. Откройте файл \<wildfly-directory\>/standalone/configuration/standalone.xml
1. Ищем тег \<datasources\>
1. Добавляем внутрь 
```xml
<datasource jndi-name="java:jboss/datasources/yourDS" pool-name="database-datasource" enabled="true" use-java-context="false">
	<connection-url>jdbc:postgresql://pg:5432/studs</connection-url>
	<driver>postgresql-42.2.5.jar</driver>
	<security>
		<user-name>s******</user-name>
		<password>*****</password>
	</security>
</datasource>
```
Тут приведён пример для подключения к postgres на helios  
В разделе security вводите свои данные для подключения к гелиосу
