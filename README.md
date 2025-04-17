# Hospital Database Management Application

## Contexte du projet
Ce projet a été réalisé en trinôme dans le cadre d'un TP de gestion de base de données et d’application Java. Il a consisté à :

- Implémenter le schéma relationnel d'une base de données pour la gestion d'un hôpital dans **SQLite Studio**.
- Créer une **interface JAVA** permettant l'insertion, la modification, la suppression et la recherche de données.
- Connecter l'application à la base de données avec **SQLite JDBC**.

---

## Description de SQLite
**SQLite** est une bibliothèque C proposant un moteur de bases de données relationnelles intégré directement dans les programmes. Contrairement aux systèmes client-serveur (ex: MySQL), SQLite stocke la base dans un fichier unique. Ses principaux avantages :

- Portable et simple d’utilisation
- Accès rapide aux données
- Standard SQL supporté
- Typage dynamique des colonnes

---

## Conception de la base de données

Nous avons créé toutes les tables nécessaires à la gestion d'un hôpital, telles que :

- **Chambre**, **Lit**, **Malade**, **Médecin**, **Infirmière**, **Pharmacien**, **Service**, **Unite Fonctionnelle**, etc.

Les tables respectent les contraintes d'intégrité (clés primaires et étrangères).

---

## Application Java : Interface utilisateur

L'application propose une interface principale permettant de :
- Accéder aux gestions par tables (Unite Fonctionnelle, Service, Laboratoire, etc.)
- Ajouter, modifier, supprimer, rechercher des enregistrements pour chaque table

Chaque fonctionnalité est accessible via des fenêtres dédiées.


## Connexion à la base de données

La connexion à la base se fait via la librairie **sqlite-jdbc-3.7.2** :
```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

try {
    Class.forName("org.sqlite.JDBC");
    Connection con = DriverManager.getConnection("jdbc:sqlite:hopital.db");
    // Exécution des requêtes
    con.close();
} catch (ClassNotFoundException | SQLException e) {
    e.printStackTrace();
}
```

---

## Quelques exemples d'interrogations affichées

- Liste des services
- Liste des unités fonctionnelles
- Liste des pharmaciens
- Liste des laboratoires
- Liste des malades

Toutes ces listes sont présentées dans des composants JTable de l'interface Java.

---

## Conclusion

Ce projet nous a permis de :
- Comprendre comment créer une base de données relationnelle cohérente
- Créer une application Java connectée à une base de données
- Travailler en équipe efficacement sur un projet d'ingénierie logicielle

---

## Technologies utilisées
- **Base de données** : SQLite
- **Langage** : Java
- **Outils** : SQLiteStudio, NetBeans / IntelliJ IDEA

---

## Membres du trinôme
- Aliou Sow
- Fatoumata Binta Keita
- Hamady Gackou

