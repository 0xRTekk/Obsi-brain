---
tags:
  - Dev
  - Java
---
## 🎯Intro

Un Java **[[BEANS]] CDI (Contexts and Depedency Injection)** est un composant géré par le conteneur CDI dans une application [[Jakarta EE]] ou dans des frameworks comme [[Quarkus]].

## 📌Caractéristiques

- Cycle de vie géré par le conteneur CDI
- Injectable dans d'autre [[BEANS]] grâce à l'annotation `@Inject` 
- Contextualisé dans un scope définit grâce à une annotations (application, requête, session, etc)
- Découvrable automatiquement par le conteneur CDI

## 💡Exemple

```java
@ApplicationScoped
public class UserService {
    @Inject
    private UserRepository repository; // Est aussi un BeanCDI
    
    public User findById(Long id) {
        return repository.findById(id);
    }
    
    public void saveUser(User user) {
        repository.save(user);
    }
}
```

## ℹ️ Détails

Une classe devient un Bean CDI si elle remplit au moins une de ces conditions :
- Possède une annotation de scope
	- `@ApplicationScoped` : Une instance par application
	- `@RequestScoped` : Une instance par requête HTTP
	- `@SessionScoped` : Une instance par session utilisateur
	- `@ConversationScoped` : Une instance par conversation
	- `@Dependent` : Scope par défaut, suit le cycle de vie du bean injecteur
- Possède une annotation de type
	- `@Named`
	- `@Model`
	- etc
- Est explicitement déclarée dans `beans.xml`
- Possède une annotation de définition de bean
	- `@Dependent` (par defaut)