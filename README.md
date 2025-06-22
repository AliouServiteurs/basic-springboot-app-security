# Login x Registration Spring Boot App
Basic login and registration endpoints using Spring Security and MySQL
# Springboot-App-Security

## Description

Ce projet est une application Spring Boot sécurisée avec authentification JWT.  
Il permet de gérer les utilisateurs, de s’authentifier avec un username et mot de passe,  
et de générer un token JWT pour sécuriser les accès aux endpoints.

## Fonctionnalités

-   Inscription et connexion des utilisateurs
-   Hashage des mots de passe avec BCrypt
-   Authentification via JWT (JSON Web Token)
-   pas encore : Gestion des rôles utilisateur (ex : ADMIN, USER)
-   pas encore : Sécurisation des endpoints avec Spring Security
-   Utilisation de JPA avec MySQL pour la persistance des données

## Prérequis

-   Java 17 ou supérieur  
-   Maven  
-   MySQL (ou autre base compatible)  
-   IDE (IntelliJ, Eclipse, VSCode...)

## Installation et lancement

1. **Cloner le dépôt**

---> bash
git clone https://github.com/ton-utilisateur/ton-repo.git
cd ton-repo

2. **Configurer la base de données**

Modifier src/main/resources/application.properties :

spring.application.name=springboot-app

spring.datasource.url=jdbc:mysql://localhost:3306/${spring.application.name}?createDatabaseIfNotExist=true
spring.datasource.username=ton_user
spring.datasource.password=ton_mot_de_passe
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect

app.secret-key=UneCléSecrèteLongueEtSûre1234567894464646494946645494894849498494984949849494949984498498
app.expiration-time=900000


3. **Construire et lancer**

mvn clean install
mvn spring-boot:run

L’application sera disponible sur http://localhost:8080

-#-> API principales
--- POST /login
Permet de se connecter et de récupérer un token JWT.

Exemple de corps JSON :

{
  "username": "monuser",
  "password": "monmdp"
}

Réponse :

{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "type": "Bearer"
}

--- POST /register
Permet d’inscrire un nouvel utilisateur (à implémenter).

-#-> Technologies utilisées
-  Spring Boot

-   Spring Security

-   JPA / Hibernate

-   MySQL

-   JWT (jjwt)

-   BCryptPasswordEncoder

-#-> Structure du projet
-   configuration : sécurité et JWT

-   controller : endpoints REST

-   service : logique métier et UserDetailsService

-   repository : accès base via JPA

-   entity : entités JPA

## Auteur

Aliou Diop
alioudiop463@gmail.com
