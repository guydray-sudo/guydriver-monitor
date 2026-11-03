# Guy Driver — surveillance extérieure

Contrôle gratuit des seules pages publiques de https://guydriver.com/, sans identifiants IONOS, données clients, SMTP ni IA payante.

- Exécution sur un serveur GitHub standard toutes les quinze minutes : minutes 00, 15, 30 et 45 en UTC. Les horaires sont indicatifs et peuvent être retardés par GitHub.
- Vérifie l’accueil, la santé du site, le concierge sans IA payante et la protection de la configuration (HEAD uniquement, contenu privé jamais lu).
- Deux contrôles en cas d’échec avant l’alerte. Notification GitHub au propriétaire au début de l’incident, puis au maximum une fois par 24 heures si l’incident persiste.
- Le réglage du compte propriétaire utilise les e-mails pour les exécutions échouées. Aucun destinataire client n’est utilisé.
- Le test manuel `test_alert` provoque uniquement une notification de contrôle. Il n’altère ni le site ni son état public.
- [État actuel](status.json) : `ok` ou `incident`. Une exécution réussie du workflow signifie que le contrôle a été traité ; un incident déjà signalé peut persister sans nouvelle notification.
- Une mise à jour hebdomadaire du petit registre public garde le dépôt actif. Le jeton éphémère du workflow est limité au contenu de ce dépôt et sert seulement à ce registre. Aucun secret durable n’est ajouté.
- Aucun artefact, cache, déploiement du site ni action de marketplace n’est utilisé. Le dépôt privé du site reste distinct.

Ce contrôle n’effectue pas de sauvegarde, ne restaure rien et ne garantit pas une disponibilité absolue de GitHub. Les sauvegardes et les alertes internes restent sur IONOS. Le statut public ne contient que l’état général et les dates, sans détail de configuration.

[Exécutions](https://github.com/guydray-sudo/guydriver-monitor/actions/workflows/availability.yml)
