# PicConvert

Une extension de navigateur légère qui convertit des images entre les formats PNG, JPG, WEBP et AVIF — entièrement localement, sans upload de données.

> Basé sur Chromium · Manifest V3 · Aucun suivi · 100% traité dans le navigateur

[English](README.md) | [中文](README_zh.md) | [Español](README_es.md) | [Deutsch](README_de.md) | [日本語](README_ja.md) | Français

---

## Pourquoi PicConvert ?

La plupart des outils de conversion d'images nécessitent d'uploader vos fichiers sur un serveur distant. PicConvert fait tout dans votre navigateur avec l'API Canvas — vos données ne quittent jamais votre appareil.

| Avantage | Détail |
|----------|--------|
| 🔒 **100% Privé** | Tout le traitement se passe en mémoire dans votre navigateur. Pas de serveurs, pas d'uploads, pas de suivi. |
| ⚡ **Conversion Instantanée** | Les images ≤5MB se convertissent en moins de 500ms. Pas d'attente de réponse serveur. |
| 🎯 **Zéro Dépendance** | Construit avec JavaScript natif et les API Chrome natives. Pas de frameworks, pas de surcharge. |
| 🌍 **6 Langues** | Détecte automatiquement la langue de votre navigateur — anglais, espagnol, allemand, japonais, français, chinois. |
| 📋 **Copier et Enregistrer** | Clic droit sur une image pour enregistrer comme fichier OU copier directement dans le presse-papiers. |
| 📁 **Glisser-Déposer** | Déposez des images locales sur le popup pour une conversion rapide. |

---

## Fonctionnalités

| Fonctionnalité | Description |
|----------------|-------------|
| 🖼️ **4 Formats** | Convertir en PNG (sans perte), JPG (haute qualité), WEBP (compact) ou AVIF (meilleure compression) |
| 📋 **Copier dans le Presse-papiers** | Clic droit → Copier en PNG/JPG/WEBP/AVIF — coller directement dans les e-mails, chats, documents |
| 📊 **Comparaison de Taille** | Notification toast affiche la taille originale vs convertie avec le pourcentage d'économie |
| 🎚️ **Qualité Ajustable** | Ajustez finement la qualité d'exportation pour JPG, WEBP et AVIF via les curseurs dans le popup |
| 🔗 **Nettoyage Intelligent des Liens** | Supprime les paramètres de suivi CDN (`w=`, `h=`, `format=`, `watermark=`, etc.) pour obtenir les images originales |
| 📁 **Glisser-Déposer** | Déposez des fichiers image locaux sur le popup pour convertir sans clic droit |
| 🌐 **Support Cross-Origin** | Récupère les images de n'importe quel site web via Service Worker — contourne les problèmes CORS et canvas taint |
| 🔤 **i18n en 6 Langues** | Le menu contextuel et l'UI s'adaptent automatiquement à la langue de votre navigateur (EN/ES/DE/JA/FR/ZH-CN) |
| 🛡️ **Remplissage Blanc JPG** | Remplit automatiquement les fonds transparents avec du blanc lors de la conversion PNG → JPG |
| ⏱️ **Protection contre les Doublons** | Ignore les clics répétés sur la même image dans les 2 secondes |
| 📦 **Gestion des Grandes Images** | Les images >20MB affichent un indicateur de traitement asynchrone au lieu de geler l'UI |

---

## Aperçu

<!-- Remplacer par de vraies captures d'écran -->
<p align="center">
  <img src="assets/popup.png" alt="PicConvert Popup" width="360">
</p>

<p align="center">
  <img src="assets/context-menu.png" alt="Menu Contextuel PicConvert">
</p>

---

## Navigateurs Supportés

| Navigateur | Statut |
|------------|--------|
| Google Chrome | ✅ Entièrement supporté |
| Microsoft Edge | ✅ Entièrement supporté |
| Brave | ✅ Supporté |
| Opera | ✅ Supporté |
| Vivaldi | ✅ Supporté |
| Tout navigateur basé sur Chromium | ✅ Supporté (Manifest V3) |

---

## Installation

### Depuis le Code Source (Mode Développeur)

1. Ouvrez la page des extensions de votre navigateur :
   - **Chrome** : `chrome://extensions/`
   - **Edge** : `edge://extensions/`
2. Activez le **Mode développeur** (interrupteur en haut à droite)
3. Cliquez sur **Charger l'extension non empaquetée** et sélectionnez le dossier `pic-convert`
4. L'icône ✨ PicConvert apparaîtra dans votre barre d'outils

---

## Utilisation

### Conversion par Clic Droit

1. Faites un clic droit sur une image sur une page web
2. Sélectionnez **PicConvert** dans le menu contextuel
3. Choisissez **Enregistrer sous** ou **Copier en tant que**
4. Choisissez votre format : PNG, JPG, WEBP ou AVIF
5. Terminé — le fichier se télécharge instantanément, ou l'image est copiée dans le presse-papiers

### Glisser-Déposer

1. Cliquez sur l'icône PicConvert dans votre barre d'outils pour ouvrir le popup
2. Déposez un fichier image local sur la zone de dépôt
3. Sélectionnez votre format cible
4. Le fichier converti se télécharge automatiquement

### Paramètres de Qualité

Ouvrez le popup pour ajuster la qualité d'exportation pour JPG, WEBP et AVIF à l'aide des curseurs. PNG est toujours sans perte. Les paramètres sont sauvegardés automatiquement.

---

## Structure du Menu Contextuel

```
PicConvert
├── Enregistrer sous PNG (Sans perte)
├── Enregistrer sous JPG (Haute qualité)
├── Enregistrer sous WEBP (Compact)
├── Enregistrer sous AVIF (Meilleure compression)
├── Copier en tant que PNG (Sans perte)
├── Copier en tant que JPG (Haute qualité)
├── Copier en tant que WEBP (Compact)
└── Copier en tant que AVIF (Meilleure compression)
```

Les menus **Copier en tant que** et **Enregistrer sous** n'apparaissent qu'en faisant un clic droit sur des images ou des liens pointant vers des fichiers image (`.png`, `.jpg`, `.jpeg`, `.webp`, `.avif`, `.gif`, `.bmp`, `.jfif`, `.svg`).

---

## Confidentialité

PicConvert est construit avec la confidentialité comme principe fondamental :

- ✅ **Zéro upload de données** — Tout le traitement des images se passe en mémoire dans votre navigateur
- ✅ **Pas d'analyse** — Pas de suivi, pas de télémétrie, pas d'appels distants
- ✅ **Pas de cookies** — Pas de lecture ni d'écriture de cookies du navigateur
- ✅ **Pas d'historique de navigation** — Pas d'accès à vos données de navigation
- ✅ **Mémoire temporaire uniquement** — Les images existent en mémoire pendant la conversion et sont détruites immédiatement après
- ✅ **Permissions minimales** — Ne demande que ce qui est strictement nécessaire : `contextMenus`, `downloads`, `offscreen`, `storage`, `clipboardWrite`

---

## Comment ça Fonctionne

```
Clic droit sur une image
       ↓
Service Worker récupère le blob de l'image (contourne CORS)
       ↓
Envoie le blob au document Offscreen (DOM caché avec accès Canvas)
       ↓
Canvas dessine l'image à la résolution native
       ↓
Exporte au format cible avec la qualité spécifiée
       ↓
Retourne l'URL de données → déclenche le téléchargement ou copie dans le presse-papiers
       ↓
Détruit toutes les ressources temporaires (blob, canvas, élément image)
```

> **Pourquoi Offscreen ?** Le Manifest V3 de Chrome exécute l'arrière-plan en tant que Service Worker, qui n'a pas accès au DOM. L'API Canvas nécessite un DOM, nous utilisons donc l'API Offscreen de Chrome pour créer un document caché pour le traitement des images.

---

## Qualité d'Exportation par Défaut

| Format | Qualité | Notes |
|--------|---------|-------|
| PNG | Sans perte | Pas de réglage de qualité — préserve toujours la qualité totale et la transparence |
| JPG | 92 | Haute qualité, bon équilibre entre taille et netteté |
| WEBP | 90 | Format moderne, ~25-35% plus petit que JPG à qualité équivalente |
| AVIF | 70 | Prochain format, ~20-30% plus petit que WEBP, idéal pour la livraison web |

Toutes les valeurs de qualité sont ajustables via les curseurs dans le popup (plage : 10–100).

---

## Licence

Copyright © 2026 PicConvert. Tous droits réservés.

---

## ❤️ Soutenir

Si PicConvert vous est utile, envisagez de soutenir le projet !

<!-- Ajoutez votre lien de soutien ici -->
**[👉 Soutenir PicConvert](https://annmax1983.github.io/PicConvert/)**

---

> **Note :** Toutes les fonctionnalités de conversion principales resteront toujours gratuites et sans limitations.
