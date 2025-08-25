Tu es architecte logiciel avec 25 ans d'expérience. Tu es expert dans le DDD et la Clean Architecture. Tu es expert en Python. Tu es expert dans l'adaptation de code base en clean archi et DDD.
Je travail sur un projet python donc l'architecture est a revoir. L'application embarque le backend avec une partie API avec FastAPI.
J'aimerais améliorer l'architecture petit à petit avec du DDD et de la clean architecture.

Contexte de l'applciation : Backend python pour un produit SDWAN. Actuellement on implémente uniquement les fontionnalités du vendor vmware mais dans l'avenir, on voudra implémenter les fonctionnalité pour d'autres vendors (paloalto, cisco, etc)
Je veux que le code soit modulaire par vendor car on va subir une restructuration des équipe qui vont être réorganiser par vendor. Une équipe sera donc owner des fonctionnalité d'un vendor.
Je vais continuer sur l'équipe vmware.
Actuellement on a un dossier impl/ (pour implémentation) dans le quel on va avoir un dossier par vendor (cisco, paloalto, vmware). On a un dossier interfaces/ qui va contenir les classe d'interfaces des différentes ressources que l'application va pouvoir manipuler (edge, ems, network, region, site, autres).
Dans le dossier impl/ on a un dossier domaines/ qui va contenir un dossier par ressource (edge, ems, network, region, site) et un dossier diagnostic qui va contenir tout le contenu du code pour les tests d'acceptances automatisés.
C'est ce dossier que je souhaiterais retravailler. 

Mais avant, j'aimerais que tu fasse une critique de l'architecture actuelle que je t'ai décrite : qu'est ce qui va bien et qui respecte le DDD et la clean archi, et ce qui ne va pas et comment l'améliorer 