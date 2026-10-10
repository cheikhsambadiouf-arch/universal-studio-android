# Universal Studio — APK Android

Ce dossier contient l’application HTML d’origine emballée avec Capacitor, ainsi qu’un workflow GitHub Actions qui compile automatiquement un APK Android dans le cloud. Il est adapté à un usage depuis un téléphone Android, sans installer Android Studio sur le téléphone.

## Méthode la plus directe depuis un téléphone

1. Téléchargez et décompressez ce ZIP.
2. Sur GitHub, créez un dépôt **privé** nommé `universal-studio-android`.
3. Importez tous les fichiers et dossiers de ce projet dans la racine du dépôt, notamment le dossier caché `.github/workflows/build-apk.yml`.
4. Ouvrez l’onglet **Actions** du dépôt et sélectionnez **Build Universal Studio APK**.
5. Appuyez sur **Run workflow**. Le premier build peut prendre plusieurs minutes.
6. Quand le workflow est terminé avec une coche verte, ouvrez son exécution et téléchargez l’artefact **universal-studio-debug-apk**.
7. Décompressez l’artefact téléchargé sur votre téléphone, puis ouvrez `app-debug.apk` pour l’installer. Android peut demander d’autoriser temporairement l’installation depuis cette source.

Le workflow se relance aussi automatiquement quand un commit est poussé sur `main` ou `master`.

## Limites importantes

- Cet APK est un **APK debug** installable pour test, pas une version signée de production prête pour Google Play.
- Le build cloud n’a pas encore été exécuté ni testé sur un téléphone au moment de la préparation de ce dossier.
- L’application originale conserve son fonctionnement et ses appels à l’API Agnes AI. La compilation ne garantit pas que les clés API, les appels vidéo/images ou toutes les fonctions fonctionneront sans tests réels.
- Ne distribuez pas publiquement l’application avec des clés API secrètes enregistrées côté navigateur. Pour une diffusion publique, placez les secrets derrière un backend sécurisé.
