# Лабораторная работа \# 4

## Подробный гайд по запуску моего фронта и бэка на локалке

Убедитесь, что у вас установлен [Git](https://git-scm.com/downloads) и [Node.js](https://nodejs.org/en/).

### Spring и React, Angular

1. Запускаете командную строку и переходите в удобную для вас директорию(например, корень диска D)
2. Клонируем репозиторий со Spring
    ```cmd
    git clone https://github.com/DeltaThreeEight/Spring-Backend-for-Lab4.git
    ```
3. Открываем Spring-Backend-for-Lab4/src/main/resources/application.properties и настраиваем на работу с вашей локальной БД
4. Теперь можно запустить бэкэнд. Переходим в корневую директорию проекта и запускаем при помощи maven или gradle
    ```cmd
    # Переходим в директорию проекта
    cd Spring-Backend-for-Lab4
    
    # Запускает бэкэнд
    # Gradle
    gradlew.bat bootRun
    
    # ...или
    # Maven
    mvnw.cmd spring-boot:run
    ```
5. Настало время запустить наш фронтэнд. Клонируем нужный репозиторий (Angular или React)
    ```cmd
    # Angular
    git clone https://github.com/DeltaThreeEight/Angular-Frontend-for-Lab4.git
    
    # React
    git clone https://github.com/DeltaThreeEight/React-Frontend-for-Lab4.git
    ```
6. Переходим в корневую директорию проекта фронтэнда
    ```cmd
    # Angular
    cd Angular-Frontend-for-Lab4
    
    # React
    cd React-Frontend-for-Lab4
    ```
7. Установливаем нужные для работы модули
    ```cmd
    npm install
    ```
8. Запускаем фронтэнд. Теперь можно открыть браузер, вбить в адресную строку localhost:4200 и тыкаться :)
    ```cmd 
    # В случае с реактом придётся сменить дефолтный порт
    set PORT=4200
    
    npm start
    ```

### Java EE

Здесь вам обязательно будет нужен сервер приложений [WildFly](https://wildfly.org/downloads/)

1. Запускаете командную строку и переходите в удобную для вас директорию(например, корень диска D)
2. Клонируем репозиторий с Java EE
    ```cmd
    git clone https://github.com/DeltaThreeEight/Ejb-Backend-for-Lab4.git
    ```
3. Открываем Ejb-Backend-for-Lab4/src/main/META-INF/persistence.xml и настраиваем под нашу БД
4. Собираем проект 
    ```cmd
    gradlew.bat war
    ```
5. Собранный war лежит в build/libs, теперь его надо переместить в <wildfly-directory>/standalone/deployments
6. Можно запускать сервер приложений WildFly
7. Шаги по запуску фронтэнда аналогичны...
