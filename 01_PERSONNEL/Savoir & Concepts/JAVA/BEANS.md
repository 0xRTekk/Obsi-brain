---
tags:
  - Dev
  - Java
---
## 🎯Intro

Composant logiciel [[JAVA]] réutilisable encapsulant plusieurs objet en une seul : le **BEAN**.
Le but est de faciliter la manipulation et l'accessibilité des ces objets par d'autres composants.

## 📌Caractéristiques

- Classe publique
- Constructeur sans arguments
- Getter & Setter
- Encapsulation (private properties)
- Sérialisable (implémente java.io.Serializable)

## 💡Exemple

```java
public class PersonBean implements Serializable {
    private String name;
    private int age;
    
    // Constructeur sans argument
    public PersonBean() {}
    
    // Getters et setters
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    
    public int getAge() { return age; }
    public void setAge(int age) { this.age = age; }
}
```

## ℹ️ Détails

### Sérialisable
- Un bean est sérialisable pour permettre de mémoriser son state. On transforme le state complet en flux d'octets afin de le stocker ou le transmettre.
- Permet l'utilisation des composants dans des systèmes distribués
- Technique daté et plus mandatory dans les framework modern