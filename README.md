# BroadcastReceiver Demo

Application Android en **Java** permettant de démontrer l’utilisation des **BroadcastReceiver**.

## Fonctionnalités

Ce projet permet de :

- Utiliser un **BroadcastReceiver dynamique** pour détecter le **mode avion**
- Utiliser un **BroadcastReceiver statique** pour `BOOT_COMPLETED`
- Envoyer et recevoir un **broadcast personnalisé**
- Comprendre la différence entre **Receiver statique et dynamique**
- Comprendre le fonctionnement de `onReceive()`
- Travailler avec les permissions et les restrictions Android récentes

## Objectif du projet

L’objectif de ce lab est d’apprendre comment une application Android peut réagir aux événements système ou personnalisés via les BroadcastReceiver.

À la fin, vous comprendrez le fonctionnement des événements comme :

- Mode avion
- Démarrage du téléphone
- Batterie, Wi-Fi
- Communications internes entre composants

## Technologies utilisées

- Java
- Android Studio
- Android SDK
- BroadcastReceiver
- Intent / IntentFilter

## Configuration requise

- **Langage :** Java
- **Minimum SDK :** API 24
- Compatible Android 14 / 15 / 16

## Structure du projet

BroadcastReceiverDemo/
├── app/
│   ├── java/com/example/receiverdemo1/
│   │   ├── MainActivity.java
│   │   ├── AirplaneModeReceiver.java
│   │   ├── BootReceiver.java
│   │   └── CustomReceiver.java
│   ├── res/layout/
│   │   └── activity_main.xml
│   └── AndroidManifest.xml

## Fonctionnement

### 1. Receiver dynamique

Le receiver dynamique est enregistré dans `MainActivity` avec :

Intent.ACTION_AIRPLANE_MODE_CHANGED

Il fonctionne uniquement lorsque l’utilisateur active le receiver.

### 2. Receiver statique

Déclaré dans `AndroidManifest.xml`, il écoute :

android.intent.action.BOOT_COMPLETED

Il permet de détecter le démarrage du téléphone.

### 3. Broadcast personnalisé

L’application envoie un broadcast personnalisé :

com.example.receiverdemo.CUSTOM_EVENT

## Interface utilisateur

L’application contient :

- Un TextView pour afficher l’état
- Un bouton pour activer/désactiver le receiver avion
- Un bouton pour envoyer un broadcast personnalisé

## Différence : Statique vs Dynamique

### Receiver dynamique
- Déclaré dans le code Java (registerReceiver)
- Actif uniquement lorsque l’app est ouverte
- Recommandé pour Android moderne

### Receiver statique
- Déclaré dans AndroidManifest.xml
- Peut fonctionner même si l’app est fermée
- Limité par les restrictions Android récentes

## Restrictions Android (14 / 15 / 16)

- Obligation de définir android:exported
- Restrictions sur les broadcasts implicites
- Limitation des tâches en arrière-plan
- Préférence pour les receivers dynamiques

## Permissions

Pour détecter le démarrage :

<uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED" />

## Exemple Manifest

<receiver
    android:name=".BootReceiver"
    android:enabled="true"
    android:exported="true">
    <intent-filter>
        <action android:name="android.intent.action.BOOT_COMPLETED" />
    </intent-filter>
</receiver>

## Exécution

1. Ouvrir le projet dans Android Studio
2. Lancer l’application
3. Tester :
   - Activation du receiver avion
   - Envoi du broadcast personnalisé
   - Vérifier les résultats (UI / logs)

## Compétences acquises

- Utilisation des BroadcastReceiver
- Gestion des Intent et IntentFilter
- Différence statique vs dynamique
- Compréhension des événements système Android
- Gestion des restrictions de sécurité Android

## Auteur

Youness Lahdiri

## Licence

Projet à but pédagogique


<img width="468" height="626" alt="Screenshot 2026-04-06 180933" src="https://github.com/user-attachments/assets/415b6c82-714c-4715-8f90-984ffed8da07" />

<img width="438" height="660" alt="Screenshot 2026-04-06 180938" src="https://github.com/user-attachments/assets/0839e0ee-6d27-4617-bf37-74a1dc58de08" />


<img width="310" height="507" alt="Screenshot 2026-04-06 180945" src="https://github.com/user-attachments/assets/a77992d0-dcfa-475b-980c-9a8735ad21ee" />
