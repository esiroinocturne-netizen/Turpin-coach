# Turpin Coach — installation

Tous les fichiers de ce dossier sont prêts. Aucun abonnement, compte dans l’application, compilation ou renouvellement hebdomadaire. Les performances restent sur ton appareil.

## 1. Héberger gratuitement avec GitHub Pages

Un compte GitHub est nécessaire uniquement pour héberger, pas pour utiliser l’app.

1. Sur github.com, connecte-toi puis choisis **New repository**.
2. Nom : **turpin-coach**. Choisis **Public**, puis **Create repository**. Le code et le programme seront publics ; tes performances locales ne sont jamais envoyées au dépôt.
3. Choisis **uploading an existing file** (ou **Add file → Upload files**).
4. Dépose le contenu du dossier Turpin-Coach-PWA à la racine du dépôt : index.html, app.js, engine.js, program.js, style.css, sw.js, manifest.webmanifest, les deux icônes et ce guide. Ne dépose pas seulement le ZIP, ni le dossier parent.
5. Clique **Commit changes**.
6. Ouvre **Settings → Pages → Build and deployment**.
7. Source : **Deploy from a branch**. Branche : **main**, dossier : **/(root)**. Clique **Save**.
8. Attends la fin du déploiement (quelques minutes). Reviens sur Pages et ouvre l’adresse affichée : généralement https://TON-PSEUDO.github.io/turpin-coach/.

Documentation : https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## 2. Installer sur iPhone

1. Ouvre l’adresse HTTPS dans **Safari** avec Internet.
2. Attends quelques secondes pour la première mise en cache.
3. **Partager → Sur l’écran d’accueil**. Active **Ouvrir comme app web** si proposé, puis **Ajouter**.
4. Lance **Turpin Coach** depuis cette icône.
5. Teste le mode avion en fermant puis rouvrant l’app. Le programme et les données doivent rester disponibles.

Guide Apple : https://support.apple.com/guide/iphone/bookmark-a-website-iph42ab2f3a7/ios

Ouvrir simplement index.html dans Fichiers ne permet pas l’installation ni le service worker. L’hébergement HTTPS est nécessaire. L’app fonctionne aussi sur ordinateur.

## Pendant la séance

- Choisis le jour. Chaque série possède sa propre charge.
- Renseigne charge, reps et RIR puis touche le cercle : il passe au vert et lance le repos.
- Modifier un champ dévalide la série : valide-la à nouveau.
- Charge dips/tractions = lest seulement. 0 kg = poids du corps.
- Unilatéral : renseigne la charge par côté/main selon ton repère ; reps du côté le plus faible, travail effectué des deux côtés.
- Maintiens : note des secondes ; le champ RIR devient la marge en secondes. Le choix de variante se note dans la note de séance.
- Les incréments se règlent par exercice dans **Réglages & consignes**. Une hausse proposée ne change les charges qu’après ton clic de validation.
- **Séance terminée** conserve les séries validées. Une séance partielle est acceptée après confirmation. Le brouillon reste enregistré avant cette étape.
- Samedi : décocher la technique du roumain remplace ses deux lignes par deux séries de Leg Curl ; les quatre séries de Leg Curl du jour restent présentes.
- Historique : les repères sont séparés par jour/exercice pour comparer des séances comparables. Les courbes ont deux échelles indiquées. Aucun e1RM utilisé pour les recommandations.

## Données et durabilité

IndexedDB est utilisé en priorité ; localStorage sert de repli si IndexedDB est inaccessible. Une confirmation apparaît après écriture. En cas d’échec, exporte immédiatement. Les données ne sont pas synchronisées entre appareils ou entre Safari et une autre origine. Installe l’app avant de commencer ton historique principal.

**Chaque semaine : Données & cadre → Exporter tout en JSON**, puis conserve le fichier dans iCloud/Fichiers. L’export contient historique complet, réglages et séances en cours. L’import valide le fichier puis remplace les données après confirmation : exporte avant de remplacer. Les anciennes sauvegardes du HTML initial ne sont pas compatibles avec le nouveau suivi série par série ; conserve ce HTML comme archive.

Safari peut effacer le stockage local ; aucun stockage exclusivement local ne remplace une sauvegarde externe. N’utilise pas le mode privé. Aucun historique n’est tronqué à 60 séances. Pas de date d’expiration : le programme reste accessible après le 15 décembre.

Le chrono utilise une heure de fin : il retrouve le bon temps après verrouillage/rechargement. iOS peut suspendre les notifications pendant que l’app est fermée ; le repos terminé s’affiche à la réouverture, sans garantie de son en arrière-plan.

## Mettre à jour

Exporte les données, remplace les fichiers du dépôt en gardant la même adresse. Lors d’une modification, change le numéro CACHE dans sw.js (par exemple v1 → v2). Ferme tous les écrans de l’app puis rouvre deux fois pour activer la nouvelle version. Les données sont conservées indépendamment du cache hors ligne. Ne supprime pas les données Safari.
