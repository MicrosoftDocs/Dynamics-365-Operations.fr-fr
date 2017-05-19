---
title: Stock disponible dans l&quot;espace de travail mobile
description: "Cette rubrique fournit des informations sur l&quot;espace de travail Stock disponible dans l&quot;application mobile Microsoft Dynamics 365 for Operations. Cet espace de travail vous permet d&quot;acquérir des connaissances mobiles sur les stocks réservés et disponibles à tout moment et n&quot;importe où."
author: YuyuScheller
manager: AnnBe
ms.date: 04/21/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e703ae80800b993ebca1c7bee455af1be41c7d5f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="inventory-on-hand-mobile-workspace"></a>Stock disponible dans l'espace de travail mobile

[!include[banner](../includes/banner.md)]


Cette rubrique fournit des informations sur l'espace de travail Stock disponible dans l'application mobile Microsoft Dynamics 365 for Operations. Cet espace de travail vous permet d'acquérir des connaissances mobiles sur les stocks réservés et disponibles à tout moment et n'importe où.

<a name="overview-of-the-inventory-on-hand-mobile-workspace"></a>Vue d'ensemble de l'espace de travail mobile Stock disponible
--------------------------------------------------

Généralement, les sociétés ont plusieurs expéditions et plusieurs réceptions de stock chaque jour. Ces mouvements modifient constamment le statut du stock disponible. L'espace de travail **Stock disponible** vous permet de voir l'état du stock en ligne afin d'obtenir les dernières informations sur les données de stock sur votre appareil mobile. Que vous travailliez dans l'entrepôt, les achats, les ventes, la fabrication ou la gestion, ou que vous ayez d'autres rôles, vous pouvez accéder aux données de stock en temps réel à tout moment et n'importe où. L'espace de travail mobile fournit une vue instantanée du statut du stock disponible de plusieurs établissements. Il vous permet d'afficher le stock disponible entre différents sites, les réservations de nomenclature actuelles, et le stock disponible non réservé. Vous pouvez également entrer les numéros d'article pour rechercher le stock disponible, puis effectuer une recherche filtrée des produits ou des variantes disponibles. Spécifiquement, l'espace de travail mobile fournit ces fonctions :

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
    -   Par quantité physique disponible (cette vue représente la quantité disponible qui n'est pas réservée.)

## <a name="prerequisites"></a>Conditions préalables
Avant d'utiliser l'espace de travail mobile **Stock disponible**, vérifiez que votre administrateur système a effectué les paramétrages suivants.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Logiciel requis</th>
<th>Rôle</th>
<th>description ;</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Microsoft Dynamics 365 for Operations version 1611 avec la mise à jour de plateforme 3 ou ultérieure.</td>
<td>Administrateur système</td>
<td>Si vous n'avez pas encore déployé Dynamics 365 for Operations dans votre organisation, votre administrateur système doit consulter la rubrique <a href="http://ax.help.dynamics.com/en/wiki/deploy-an-ax7-demo-environment/">Déployer l'environnement de démonstration de Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>Le KB 4013633 doit être implémenté.</td>
<td>Administrateur système</td>
<td>Le KB 4013633 (mise à jour X++ ou correctif de métadonnées) contient les quatre espaces de travail mobiles pour la gestion de la chaîne d'approvisionnement. Pour implémenter le KB 4013633, un administrateur système doit procéder comme suit :
<ol>
<li>Téléchargez le KB 4013633 depuis Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/configuring-and-installing-a-metadata-hotfix-package/">Installez le correctif de métadonnées</a>.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/create-and-apply-a-deployable-package/">Créez un module déployable</a> contenant le modèle <strong>SCMMobile</strong> et téléchargez le module déployable vers LCS.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/apply-a-deployable-package-on-a-dynamics-ax-system/">Appliquez le module déployable</a> à votre système Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>L'espace de travail mobile <strong>Stock disponible</strong> doit être publié sur l'application mobile Dynamics 365 for Operations.</td>
<td>Administrateur système</td>
<td><ol>
<li>Démarrez Dynamics 365 for Operations dans votre navigateur.</li>
<li>Dans la page <strong>Paramètres système</strong>, sélectionnez <strong>Gestion des espaces de travail mobiles</strong>.</li>
<li>Sélectionnez l'espace de travail <strong>Stock disponible</strong>.</li>
<li>Cliquez sur <strong>Publier l'espace de travail mobile</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Télécharger et installer l'application mobile Dynamics 365 for Operations
Dans votre magasin d'applications mobiles, téléchargez et installez l'application mobile Dynamics 365 for Operations.

-   Android - [Dynamics 365 for Operations dans Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   Pour iPhone : [Dynamics 365 for Operations dans iTunes](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Connexion à l'application mobile Dynamics 365 for Operations
1.  Démarrez l'application sur votre appareil mobile.
2.  Entrez votre URL Dynamics 365 for Operations.
3.  Entrez la société à laquelle vous vous connectez. Par exemple, entrez **USMF**.
4.  Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer le nom d'utilisateur et le mot de passe de votre compte Dynamics 365 for Operations. Entrez vos informations d'identification.
5.  Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s'affichent. Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous pouvez l'extraire pour actualiser la liste des espaces de travail portables. 

    [![Extraire pour actualiser](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-onhand-inventory-for-a-product-by-using-the-inventory-onhand-mobile-workspace"></a>Afficher le stock de disponible pour un produit à l'aide de l'espace de travail mobile Stock disponible
1.  Sur votre appareil mobile, sélectionnez l'espace de travail **Stock disponible**.
2.  Sélectionnez **Vérifier la disponibilité d'un article**. Vous découvrez une liste des produits chargés dans votre application pour l'utilisation hors ligne. Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre. Pour plus d'informations, les développeurs doivent consulter [Plateforme mobile Dynamics 365 for Operations d'opérations](http://ax.help.dynamics.com/en/wiki/mobile-development-handbook/).
3.  Si votre article ne figure pas dans la liste, sélectionnez **Rechercher plus** pour effectuer une recherche en ligne dans Dynamics 365 for Operations. Recherchez le nombre de produits ou basculez vers une recherche par nom de produit.
4.  Sélectionnez un produit. Si l'article est une image, l'image s'affiche.
5.  Sélectionnez l'une des options suivantes pour afficher le statut du stock disponible :
    -   Afficher la disponibilité par site
    -   Afficher la disponibilité par entrepôt
    -   Afficher la disponibilité par emplacement
    -   Afficher la disponibilité par lots (pour les produits contrôlés par lots)
    -   Afficher la disponibilité par statut du stock

    Le stock de produits disponible est affiché comme suit :
    -   Par stock physique (cette vue représente la quantité totale.)
    -   Par quantité physique réservée (cette vue représente la quantité réservée.)
    -   Par quantité physique disponible (cette vue représente la quantité disponible qui n'est pas réservée.)






