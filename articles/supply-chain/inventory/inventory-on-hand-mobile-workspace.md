---
title: Stock disponible dans l’espace de travail mobile
description: Cet article fournit des informations sur l’espace de travail mobile Stock disponible. Cet espace de travail vous permet d’acquérir des connaissances mobiles sur les stocks réservés et disponibles à tout moment et n’importe où.
author: yufeihuang
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yufeihuang
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: d493164b754b86a9df9ce4dcf9df8b20eeb55c5c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859428"
---
# <a name="inventory-on-hand-mobile-workspace"></a>Stock disponible dans l’espace de travail mobile

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

Cet article fournit des informations sur l’espace de travail mobile **Stock disponible**. Cet espace de travail vous permet d’acquérir des connaissances sur les stocks réservés et disponibles à tout moment et n’importe où.

Cet espace de travail mobile est destiné à être utilisé avec l’application mobile Finance et Opérations (Dynamics 365).

## <a name="overview"></a>Présentation
Généralement, les sociétés ont plusieurs expéditions et plusieurs réceptions de stock chaque jour. Ces mouvements modifient constamment le statut du stock disponible. L’espace de travail **Stock disponible** vous permet de voir l’état du stock en ligne afin d’obtenir les dernières informations sur les données de stock sur votre appareil mobile. Que vous travailliez dans l’entrepôt, les achats, les ventes, la fabrication ou la gestion, ou que vous ayez d’autres rôles, vous pouvez accéder aux données de stock en temps réel à tout moment et n’importe où. 

L’espace de travail mobile fournit une vue instantanée du statut du stock disponible de plusieurs établissements. Il vous permet d’afficher le stock disponible entre différents sites, les réservations de nomenclature actuelles, et le stock disponible non réservé. Vous pouvez également entrer les numéros d’article pour rechercher le stock disponible, puis effectuer une recherche filtrée des produits ou des variantes disponibles. 

Spécifiquement, l’espace de travail mobile fournit ces fonctions :

-   Vous pouvez rechercher le numéro ou le nom du produit pour trouver des produits et afficher le statut du stock disponible.
-   Vous pouvez afficher les informations suivantes pour les produits sélectionnés :

    -   Stock disponible par site
    -   Stock disponible par entrepôt
    -   Stock disponible par emplacement
    -   Stock disponible par lots (pour les produits contrôlés par lots)
    -   Stock disponible par statut de stock
    
-   Le stock de produits disponible est affiché comme suit :

    -   Par stock physique (cette vue représente la quantité totale.)
    -   Par quantité physique réservée (cette vue représente la quantité réservée.)
    -   Par quantité physique disponible (cette vue représente la quantité disponible qui n’est pas réservée.)

## <a name="prerequisites"></a>Conditions préalables
Les conditions préalables varient, selon la version de Supply Chain Management qui a été déployée pour votre organisation.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Conditions requises si vous utilisez Supply Chain Management
Si Supply Chain Management a été déployé pour votre organisation, l’administrateur système doit publier l’espace de travail mobile **Stock disponible**. Pour obtenir des instructions, voir [Publier un espace de travail mobile](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-platform-update-3-or-later"></a>Conditions requises si vous utilisez Platform Update 3 ou version ultérieure 
Si Platform Update 3 ou version ultérieure a été déployée pour votre organisation, l’administrateur système doit effectuer les tâches préalables suivantes. 

<table>
<thead>
<tr class="header">
<th>Logiciel requis</th>
<th>Rôle</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implémenter KB 4013633.</td>
<td>Administrateur système</td>

<td>Le KB 4013633 est une mise à jour X++ ou un correctif de métadonnées qui contient l’espace de travail mobile <strong>Stock disponible</strong>. Pour implémenter le KB 4013633, un administrateur système doit procéder comme suit :
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Télécharger le correctif de métadonnées depuis Microsoft Dynamics Lifecycle Services</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Installez le correctif de métadonnées</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Créez un module déployable</a> contenant le modèle <strong>SCMMobile</strong> et téléchargez le module déployable vers LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Appliquer le package déployable</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Publiez <strong>Stock disponible</strong> dans l’espace de travail mobile.</td>
<td>Administrateur système</td>
<td>Voir <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publier un espace de travail mobile</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Télécharger et installer l’application mobile

Téléchargez et installez l’application mobile Finance et Opérations (Dynamics 365) :

-   [Pour téléphones Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Pour les iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Connexion à l’application mobile

1.  Démarrez l’application sur votre appareil mobile.
2.  Entrez votre URL Dynamics 365.
3.  Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer vos nom d’utilisateur et mot de passe. Entrez vos informations d’identification.
4.  Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s’affichent. Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous devrez actualiser la liste des espaces de travail mobiles.

    [![Extraire pour actualiser.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-on-hand-inventory-for-a-product-by-using-the-inventory-on-hand-mobile-workspace"></a>Afficher le stock de disponible pour un produit à l’aide de l’espace de travail mobile Stock disponible

1.  Sur votre appareil mobile, sélectionnez l’espace de travail **Stock disponible**.

2.  Sélectionnez **Vérifier la disponibilité d’un article**. Vous découvrez une liste des produits chargés dans votre application pour l’utilisation hors ligne. Par défaut, jusqu’à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre. Pour plus d’informations, les développeurs doivent consulter [Plateforme mobile](../../fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
3.  Si votre article ne figure pas dans la liste, sélectionnez **Rechercher plus**. Recherchez le nombre de produits ou basculez vers une recherche par nom de produit.

4.  Sélectionnez un produit. Si l’article est une image, l’image s’affiche.
5.  Sélectionnez l’une des options suivantes pour afficher le statut du stock disponible :

    -   Afficher la disponibilité par site
    -   Afficher la disponibilité par entrepôt
    -   Afficher la disponibilité par emplacement
    -   Afficher la disponibilité par lots (pour les produits contrôlés par lots)
    -   Afficher la disponibilité par statut du stock

    Le stock de produits disponible est affiché comme suit :
    -   Par stock physique (cette vue représente la quantité totale.)
    -   Par quantité physique réservée (cette vue représente la quantité réservée.)
    -   Par quantité physique disponible (cette vue représente la quantité disponible qui n’est pas réservée.)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
