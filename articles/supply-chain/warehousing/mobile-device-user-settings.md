---
title: Paramètres utilisateur d’appareil mobile
description: Cet article explique comment gérer les paramètres utilisateur des appareils mobiles pour les magasiniers.
author: Mirzaab
ms.date: 02/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppDeviceBrand,WHSMobileAppUserDisplaySettings
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 15f9ce1768e1ed9dc6f7e84d245082b46a7f122c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882342"
---
# <a name="mobile-device-user-settings"></a>Paramètres utilisateur d’appareil mobile

[!include [banner](../../includes/banner.md)]

La nouvelle application mobile Gestion des entrepôts dispose d’un ensemble de paramètres spécifiques à l’application qui aident à personnaliser l’expérience utilisateur. Étant donné que l’application peut être utilisée sur des appareils de différentes tailles d’écran et configurations (comme une tablette, un téléphone ou un bras), il peut être utile de gérer ces paramètres de manière centralisée à partir de Microsoft Dynamics 365 Supply Chain Management.

La fonctionnalité *paramètres utilisateur de l’appareil mobile* vous permet de définir les paramètres utilisateur globaux qui seront utilisés sur tous les appareils. Vous pouvez également définir des paramètres utilisateur plus précis pour les marques d’appareils, les modèles d’appareils et / ou les employés. Lorsqu’un collaborateur se connecte à l’application mobile Gestion des entrepôts, l’application récupère et applique le profil de paramètres le plus spécifique stocké dans Supply Chain Management pour la marque, l’appareil et / ou l’ID utilisateur correspondants.

Cette fonctionnalité peut aider les employés à démarrer plus rapidement chaque fois qu’ils commencent à utiliser un nouvel appareil. Voici quelques exemples :

- Les administrateurs peuvent établir un ensemble standard de préférences qui fonctionnent le mieux pour les appareils d’un fabricant spécifique et / ou pour des modèles d’appareils spécifiques. Par conséquent, les collaborateurs peuvent démarrer avec un nouvel appareil sans nécessairement avoir à modifier les paramètres.
- Si votre entreprise dispose d’un pool d’appareils identiques partagés entre les employés, les employés verront leur configuration préférée à chaque fois qu’ils se connecteront, même s’ils n’ont jamais utilisé l’appareil physique spécifique qu’ils ont sélectionné un jour donné.
- Dans Supply Chain Management, les administrateurs peuvent afficher et modifier tous les paramètres stockés, même pour des travailleurs individuels. Cette fonctionnalité peut les aider à dépanner ou à affiner de nouvelles fonctionnalités.

> [!IMPORTANT]
> La fonctionnalité *paramètres utilisateur de l’appareil mobile* s’applique uniquement à la nouvelle application mobile Gestion des entrepôts. Cela ne fonctionne pas avec l’ancienne application d’entrepôt.

## <a name="turn-the-mobile-device-user-settings-feature-on-or-off"></a>Activer ou désactiver la fonctionnalité des paramètres utilisateur de l’appareil mobile

Pour utiliser la fonctionnalité décrite dans cet article, la fonctionnalité *Paramètres utilisateur, icônes et titres d’étape pour la nouvelle application d’entrepôt* doit être activée pour votre système. Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est obligatoire et peut être désactivée. Si vous exécutez une version antérieure à 10.0.25, les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Confirmer les expéditions sortantes à partir des tâches par lots* dans l’espace de travail [Paramètres utilisateur, icônes et titres des étapes pour la nouvelle application d’entrepôt](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="create-and-manage-user-settings"></a>Créer et gérer les paramètres utilisateur

Utilisez la page **Paramètres utilisateur de l’appareil mobile** pour créer, afficher et gérer des profils de paramètres à tous les niveaux de granularité. La première fois qu’un collaborateur modifie ses paramètres utilisateur sur un nouvel appareil, un nouveau profil est automatiquement ajouté sur cette page, s’il n’existe pas déjà. Ce profil est ensuite mis à jour chaque fois que le travailleur effectue une modification.

Vous pouvez également définir un profil de paramètres qui s’applique aux marques d’appareils, les modèles d’appareils et / ou les employés. Vous pouvez ensuite augmenter la granularité en appliquant des paramètres plus spécifiques pour des marques, des modèles et / ou des collaborateurs individuels.

Suivez ces étapes pour créer et gérer les paramètres utilisateur de vos appareils mobiles.

1. Accéder à **Warehouse management \> Configuration \> Appareil mobile \> Paramètres utilisateur d’appareil mobile**.
1. Sélectionnez un profil de paramètres utilisateur existant dans le volet de liste pour ouvrir son enregistrement. Sinon, sélectionnez **Nouveau** dans le volet Actions pour créer un profil.

    Chaque profil du volet de liste est étiqueté pour indiquer la marque, le modèle et / ou l’ID utilisateur auxquels le profil s’applique. Les profils plus généraux ont une valeur de *Tout* pour certaines ou toutes ces caractéristiques.

1. Dans la section d’en-tête de l’enregistrement du profil de paramètres nouveau ou sélectionné, définissez les champs suivants :

    - **Nom de marque de l’appareil** – Sélectionnez le nom de marque de l’appareil auquel le profil doit s’appliquer. Si le profil doit s’appliquer à toutes les marques, laissez ce champ vide. La liste de valeurs comprend toutes les marques qui ont été définies dans votre système. Pour plus d’informations sur la définition de la liste des marques, reportez-vous à la section suivante.
    - **ID du modèle de l’appareil** – Sélectionnez le modèle de l’appareil auquel le profil doit s’appliquer. Si le profil doit s’appliquer à tous les modèles de la marque sélectionnée, laissez ce champ vide. La liste de valeurs comprend tous les modèles qui ont été définis pour la marque sélectionnée dans le champ **Nom de marque de l’appareil**. Pour plus d’informations sur la définition de la liste des modèles de chaque marque, reportez-vous à la section suivante.
    - **ID utilisateur** – Sélectionnez l’ID utilisateur du magasinier auquel le profil de paramétrage doit s’appliquer. Si le profil doit s’appliquer à tous les collaborateurs, laissez ce champ vide.

1. Dans l’organisateur **Général**, définissez les champs suivants :

    - **Position du bouton** – Sélectionnez la manière dont les boutons doivent être positionnés sur l’appareil. Les éléments de l’application seront déplacés pour mieux correspondre à la préférence ou à la latéralité du collaborateur. Les options disponibles sont *En bas à droite (par défaut)*, *En bas à gauche*, *En haut à droite*, et *En haut à gauche*.
    - **Orientation de l’affichage** – Sélectionnez l’orientation d’affichage à appliquer par défaut dans l’application.
    - **Numériser avec l’appareil photo** – Réglez cette option sur *Oui* pour utiliser la caméra de l’appareil pour balayer les champs de saisie où le mode de saisie préféré est défini sur *Balayage*. Si votre appareil dispose d’un scanner intégré, définissez cette option sur *Non* pour utiliser le scanner à la place.
    - **Afficher la photo du produit** – Indiquez si les photos du produit doivent être affichées si elles sont disponibles pour le produit lancé. Pour plus d’informations sur l’ajout d’images de produits, voir [Ajouter une image à un produit](../pim/tasks/add-image-product.md).
    - **Afficher le thème de couleur** – Sélectionnez un thème de couleur pour l’appareil.
    - **Niveau sonore** – Sélectionnez le niveau sonore de l’appareil. Sélectionnez une valeur comprise entre 0 (zéro) et 10. Une valeur de *0* ne représente aucun son et une valeur de *10* représente le volume maximum. La valeur par défaut est *4*.
    - **Niveau de vibration** – Sélectionnez le niveau de vibration de l’appareil. Sélectionnez une valeur comprise entre 0 (zéro) et 5. Une valeur de *0* ne représente aucune vibration et une valeur de *5* représente la vibration maximale. La valeur par défaut est *1*.
    - **Pourcentage de l’échelle du texte** – Spécifiez la taille du texte en pourcentage de la taille standard. Entrez une valeur comprise entre 70 et 400. Une valeur de *70* représente la plus petite échelle de texte et une valeur de *400* représente la plus grande échelle de texte. La valeur par défaut est *100*.
    - **Pourcentage de l’échelle du bouton** – Spécifiez la taille du bouton en pourcentage de la taille standard. Entrez une valeur comprise entre 50 et 200. Une valeur de *50* représente la plus petite échelle de bouton et une valeur de *200* représente la plus grande échelle de bouton. La valeur par défaut est *100*.

## <a name="create-and-manage-mobile-device-brands"></a>Créer et gérer des marques d’appareils mobiles

Utilisez la page **Marques d’appareils mobiles** pour afficher, créer et gérer les marques et modèles d’appareils pouvant être utilisés avec vos profils de paramètres. L’application mobile récupère et soumet automatiquement le nom de la marque locale et l’ID de modèle la première fois qu’un collaborateur modifie ses paramètres sur un appareil donné. Par conséquent, la plupart de ces enregistrements seront généralement générés automatiquement. Cependant, vous pouvez également gérer tous les enregistrements de cette page. Par exemple, vous pouvez donner des descriptions plus utiles à chaque marque et modèle pour vous aider à distinguer les ID de modèle similaires ou cryptiques.

Suivez ces étapes pour créer et gérer les paramètres utilisateur de vos marques et modèles d’appareils mobiles.

1. Allez dans **Warehouse management \> Configuration \> Appareil mobile \> Marques d’appareil mobile**.
1. Dans le volet de liste, sélectionnez une marque d’appareil mobile pour ouvrir ses enregistrements. Sinon, sélectionnez **Nouveau** dans le volet Actions pour créer une marque.
1. Dans la section d’en-tête de l’enregistrement de la marque de l’appareil nouveau ou sélectionné, définissez les champs suivants :

    - **Nom de marque de l’appareil** – Le nom de marque de l’appareil, tel que *Microsoft Corporation*.
    - **Description** – Vous pouvez entrer une description pour aider à distinguer les noms de marque.

1. Le raccourci **Modèles d’appareils mobiles** affiche tous les modèles pour la marque d’appareil sélectionnée. Utiliser les boutons sur la barre d’outils pour ajouter des lignes à la grille ou supprimer des lignes. Pour chaque ligne, définissez les champs suivants :

    - **ID du modèle de l’appareil** – L’ID du modèle de l’appareil, tel que *Surface Book 2*.
    - **Description** – Vous pouvez entrer une description pour aider à distinguer les ID de modèle.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Installer et connecter l’application mobile Gestion des entrepôts](install-configure-warehouse-management-app.md)
- [Affecter des icônes et des titres d’étape pour l’application mobile Warehouse Management](step-icons-titles.md)