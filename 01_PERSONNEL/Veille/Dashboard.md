## 📊 Tableau des entreprises par domaine
```dataview
table domaine, sous-domaine, site, etat, communauté
from "Veille/Entreprises"
where type = "entreprise"
sort domaine asc
```

---

## 📚 Articles classés par tendance
```dataview
table domaine, tendance, source, date
from "Veille/Articles"
where type = "article"
sort date desc
```

---

## 🔍 Tendances en cours (liste auto)
```dataview
list
from "Veille/Tendances"
```
