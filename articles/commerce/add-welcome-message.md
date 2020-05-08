---
title: Ajouter un message de bienvenue
description: Cette rubrique décrit la procédure d'ajout d'un message d'accueil à votre site web Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d2a125b4e71016ad620f128af2e3c9f29aa04f4c
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269611"
---
# <a name="add-a-welcome-message"></a>Ajouter un message de bienvenue


[!include [banner](includes/banner.md)]

Cette rubrique décrit la procédure d'ajout d'un message d'accueil à votre site web Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un message de bienvenue de votre site web de commerce électronique peut informer les visiteurs sur les soldes en cours, les mises à jour du site, ou de la disponibilité des collections de la saison. Le message de bienvenue est défini à l'aide du module d'alerte.

Le module d'alerte doit être ajouté à l'emplacement **Messages d'erreur/d'information** du fragment d'en-tête. Le module d'alerte vous permet de spécifier le texte qui s'affiche, la couleur du texte, et l'alignement. Il vous permet également de spécifier si les visiteurs du site peuvent ignorer le message.

Lorsqu'un message de bienvenue est ajouté à un fragment d'en-tête partagé, il s'affiche sur chaque page qui utilise le modèle dans lequel ce fragment d'en-tête partagé est utilisé.

Pour ajouter un message de bienvenue à votre site, procédez comme suit.

1. Dans le générateur de site Commerce, accédez à votre site.
1. Sélectionnez **Fragments**.
1. Sélectionnez le fragment d'en-tête pour ajouter le message.
1. Dans l'arborescence du contour, développez **Messages d'erreur/d'information**.
1. Sélectionnez le module d'alerte, puis sélectionnez **OK**. Si un module d'alerte n'existe pas encore, sélectionnez d'abord le bouton représentant des points de suspension (**...**) en regard de **Messages d'erreur/d'information**, et sélectionnez **Ajouter le module**.
1. Dans le volet de propriété de droite, sous l'onglet **Données**, sélectionnez **Ajouter une source de données**, puis sélectionnez **Contenu**.
1. Dans le champ **Texte entré**, entrez le texte du message de bienvenue.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment d'en-tête, puis **Publier** pour le publier. 

Le message de bienvenue apparaît désormais en haut de chaque page du site qui utilise le fragment d'en-tête sélectionné.

## <a name="additional-resources"></a>Ressources supplémentaires

[Ajouter un logo](add-logo.md)

[Sélectionner un thème pour le site](select-site-theme.md)

[Utilisation de fichiers de remplacement CSS](css-override-files.md)

[Ajouter une icône de favori](add-favicon.md)

[Ajouter un avis de droits d'auteur](add-copyright-notice.md)

[Ajouter des langues à votre site](add-languages-to-site.md)

[Ajout d'un code de script aux pages de site pour prendre en charge la télémétrie](add-telemetry.md)

