---
title: Nouveautés ou modifications dans l’application mobile Warehouse Management
description: Cette rubrique répertorie les fonctionnalités nouvelles et modifiées pour chaque version publiée de l’application mobile Warehouse Management pour Microsoft Dynamics 365 Supply Chain Management.
author: ivanv-microsoft
ms.date: 06/07/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 61124728942c0b8162de9f687ae752773c47d07e
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261776"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a>Nouveautés ou modifications dans l’application mobile Warehouse Management

[!include [banner](../includes/banner.md)]

Cette rubrique répertorie les nouvelles fonctionnalités, les correctifs, les améliorations et les problèmes connus pour chaque version publiée de l’application mobile Warehouse Management pour Microsoft Dynamics 365 Supply Chain Management.

## <a name="version-2060"></a>Version 2.0.6.0

### <a name="new-features-fixes-and-improvements-in-version-2060"></a>Nouvelles fonctionnalités, correctifs et améliorations dans la version 2.0.6.0

Cette version introduit les nouvelles fonctionnalités, les correctifs et les améliorations suivants :

- Le mode de démonstration affiche désormais toutes les étiquettes dans la langue de l’appareil.
- Vous êtes moins susceptible de recevoir le message d’erreur suivant : « Impossible de trouver une vue appropriée pour la taille spécifiée. »
- La hauteur minimale des fiches de travail a été augmentée (pour les cas où trois champs ou moins sont configurés pour la liste de travail).
- Les marges (le fondu) au bas des cartes de détails ont été améliorées.
- Les symboles non valides dans les fichiers XML échangés avec le serveur sont désormais gérés correctement. (Par exemple, les caractères non imprimables sont désormais gérés correctement et n’empêchent plus l’application de répondre.)
- Les erreurs HTTP (telles que « erreur 503 ») lorsqu’une requête serveur est soumise sont désormais traitées correctement.
- Lorsqu’une erreur est affichée, la liste des options n’est plus affichée automatiquement pour les contrôles de zone de liste.
- L’application ne cesse plus de répondre en raison de l’orientation d’affichage sélectionnée dans les paramètres utilisateur.
- Les images des produits sont désormais affichées dans des environnements en libre service. (Cette modification s’applique uniquement aux versions basse résolution. Le service de gestion de fichiers ne prend pas en charge les images en taille réelle dans les environnements en libre service.)
- Un problème qui impliquait des prélèvements partiels de quantité nulle (zéro) a été corrigé.
- L’application ne cesse plus de répondre lorsqu’une carte de détails affiche plusieurs champs identiques.

### <a name="known-issues-in-version-2060"></a>Problèmes connus dans la version 2.0.6.0

Cette version présente les problèmes connus suivants :

- L’application (en particulier la liste de travail) devient plus lente au fil du temps.
- **Version Windows :** lorsqu’un pistolet USB est utilisé pour la lecture sous Windows, des résultats incohérents entraînent une confusion des symboles numérisés.

## <a name="version-2050"></a>Version 2.0.5.0

Cette version introduit les nouvelles fonctionnalités, les correctifs et les améliorations suivants :

- Le secret client n’est plus masqué dans la configuration des paramètres de connexion.
- Vous pouvez maintenant appuyer longuement sur n’importe quel texte pour le voir complètement.
- Le message d’erreur lorsque les autorisations de stockage sont absentes a été amélioré.
- De nouvelles séquences de contrôle ont été ajoutées pour certains flux.
- Le bouton d’envoi ne devient plus disponible de manière incorrecte en raison de la taille de la fenêtre.
- Les curseurs peuvent désormais fonctionner sur des écrans plus petits lorsque des tailles de boutons plus grandes sont utilisées.
- La superposition à quatre boutons n’est plus tronquée.
- Le clavier prend désormais en charge le bouton Supprimer.
- Un problème de luminosité pouvant survenir lors de l’utilisation du clavier a été corrigé.
- Divers problèmes des données de démonstration ont été corrigés.
- Un problème qui affectait les champs numériques sur la page des détails a été corrigé.
- Le clavier virtuel ne disparaît plus occasionnellement sur certains appareils.
- Divers bogues de l’interface utilisateur (IU) ont été corrigés, tels que des bogues affectant la couleur et le positionnement de l’arrière-plan.
- L’interface utilisateur en russe a été améliorée.
- Divers problèmes qui empêchaient le système de répondre ont été corrigés.
- Un problème lié à la réouverture de la calculatrice a été corrigé.
- **Version Android :** un problème en raison duquel Android 4.4 cessait de répondre au démarrage a été corrigé.
- **Version Android :** la mise à l’échelle minimale a été réduite à 50 pour cent.

## <a name="version-2040"></a>Version 2.0.4.0

La version 2.0.4.0 était la première version en disponibilité générale de l’application mobile Warehouse Management.

### <a name="new-features-fixes-and-improvements-in-version-2040"></a>Nouvelles fonctionnalités, correctifs et améliorations dans la version 2.0.4.0

Cette version introduit les nouvelles fonctionnalités, correctifs et améliorations suivants qui n’étaient pas disponibles dans la version préliminaire :

- Si une carte de détails comprend deux étiquettes portant des données identiques, l’une des étiquettes est masquée.
- Les caractères spéciaux sont désormais affichés par défaut et l’option de les masquer a été supprimée des paramètres utilisateur.
- Les boutons d’envoi désactivés sont désormais affichés comme non disponibles dans la vue compacte à bout de bras.
- Une modification de la logique de séquençage des contrôles garantit une mise à l’échelle plus fluide entre les appareils. Par conséquent, il est moins nécessaire d’ajuster la mise à l’échelle des polices ou des boutons.
- Le thème de couleur par défaut a été changé en *Sombre*.
- L’icône manquante pour le bouton d’envoi désactivé a été ajoutée dans la vue de ruban.
- Les exceptions d’expiration de délai d’attente vous amènent désormais à la page de connexion au lieu d’afficher une erreur de connexion.
- Si aucune action d’envoi n’est disponible (comme **OK**, **Oui**, **Accepter**, **Terminé** ou **Fini**), le bouton d’envoi est désactivé.
- La stabilité de l’application a été améliorée.
- Il existe un correctif pour la vulnérabilité de la sécurité [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).
- **Version Windows :** un problème sous Windows, où les menus ne répondaient plus après le redimensionnement de la fenêtre, a été corrigé.

### <a name="known-issue-in-version-2040"></a>Problème connu dans la version 2.0.4.0

Cette version présente le problème connu suivants :

- Cette version présente un problème avec les appareils qui utilisent Android 4.4. Vous pouvez rencontrer des problèmes lorsque vous utilisez l’application sur cette version d’Android.
