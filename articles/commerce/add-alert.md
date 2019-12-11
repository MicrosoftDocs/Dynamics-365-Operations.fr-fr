---
title: Module Alerte
description: Cette rubrique couvre les modules d'alerte et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 82138dd7f0934f732215f67a3726638eb87075d4
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785350"
---
# <a name="alert-module"></a>Module Alerte

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules d'alerte et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module d'alerte est utilisé pour afficher des messages d'information intégrés sur une page. Les modules d'alerte prennent en charge un texte et un lien. Ils peuvent être utilisés pour afficher des promotions à l'échelle du site qui figurent sur toutes les pages d'un site de commerce électronique. 

Les modules d'alerte sont pilotés par les données du système de gestion de contenu (CMS) et peuvent être placés dans n'importe quelle page.

## <a name="examples-of-alert-modules-in-e-commerce"></a>Exemples de modules d'alerte dans le commerce électronique

Les modules d'alerte peuvent être utilisés dans l'en-tête de site pour indiquer des promotions ou des messages à l'échelle du site. Voici quelques exemples :

« Les soldes annuelles se terminent dans 10 jours »

« Réalisez des économisez avec les soldes de la rentrée. Achetez dès maintenant. »

## <a name="alert-module-properties"></a>Propriétés du module d'alerte

| Nom de la propriété  | Valeur                              | Description |
|----------------|------------------------------------|-------------|
| Détails           | Détails                               | Texte qui s'affiche dans le module d'alerte. |
| Alignement du texte | **Droite**, **Gauche** ou **Centre** | Valeur qui définit la manière dont le texte est aligné dans le module d'alerte. |
| Ignorer l'alerte  | **Vrai** ou **Faux**              | Si la valeur est définie sur **Vrai**, le client peut ignorer l'alerte. |
| Lien           | URL                                | URL pour un lien supplémentaire. |

## <a name="add-an-alert-module-to-a-page"></a>Ajouter un module d'alerte à une page 

Pour ajouter un module d'alerte à une page et définir les propriétés requises, procédez comme suit.

1. Créez un modèle de page nommé **modèle d'alerte**.
1. À l'emplacement **Principal** de la page par défaut, ajoutez un module d'alerte.
1. Archivez le modèle, et publiez-le. 
1. Utilisez le modèle d'alerte que vous venez de créer pour créer une page qui s'appelle **page d'alerte**. 
1. À l'emplacement **Principal** de la nouvelle page, ajoutez un module d'alerte.
1. Dans les paramètres du module d'alerte, entrez le texte d'alerte. Vous pouvez modifier les autres propriétés si vous souhaitez personnaliser le module d'alerte davantage.
1. Enregistrez et affichez un aperçu de la page. En haut de la page, vous devez voir une alerte avec le texte que vous avez ajouté.
1. Archivez la page, et publiez-la. 

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Carrousel](add-carousel.md)

[Module de bloc de contenu riche](add-content-rich-block.md)

[Module Placement de contenu](add-content-placement-modules.md)

[Module Fonctionnalité](add-feature-module.md)

[Module Bannière](add-hero-module.md)

[Module Lecteur vidéo](add-video-player.md)
