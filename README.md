# Tricol - Fournisseurs (module)

Ce projet fournit un module de gestion des fournisseurs (CRUD) pour l'application Tricol.

Principales caractéristiques
- Entité Fournisseur (societe, adresse, contact, email, telephone, ville, ice)
- Couche Repository (Spring Data JPA)
- Couche Service
- REST API (Spring MVC) : endpoints CRUD
- Configuration Spring (JavaConfig + Dispatcher XML)
- Base de données en mémoire H2 pour le développement

Endpoints
- GET /api/v1/fournisseurs
- GET /api/v1/fournisseurs/{id}
- POST /api/v1/fournisseurs
- PUT /api/v1/fournisseurs/{id}
- DELETE /api/v1/fournisseurs/{id}

Comment lancer (développement)
1. Construire le WAR :

```powershell
mvn clean package
```

2. Déployer `target/Tricol-v1.war` dans un conteneur Servlet (Tomcat 10+ recommandé pour Jakarta).

Notes
- La configuration Java est dans `src/main/java/config/AppConfig.java` (utilise H2 en mémoire)
- Le Dispatcher Servlet XML est dans `src/main/webapp/WEB-INF/dispatcher-servlet.xml` pour activer le scanning des controllers
- Pour tester rapidement, déployer sur Tomcat et utiliser la collection JSON fournie (`collection-fournisseurs.json`)
