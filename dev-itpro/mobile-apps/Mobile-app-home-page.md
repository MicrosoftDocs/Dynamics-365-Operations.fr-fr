---
title: Page d&quot;accueil de l&quot;application mobile Dynamics 365 for Operations
description: "Cette rubrique décrit l&quot;application mobile Microsoft Dynamics 365 for Operations et fournit des liens vers des ressources qui peuvent vous aider à l&quot;implémentation de votre organisation."
author: sericks007
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations, Platform
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.intro: Platform update 4
ms.search.validFrom: 2017-02-28
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 5962fa36b061382e7f0ad55c08c81ac2cebc047d
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="dynamics-365-for-operations-mobile-app-home-page"></a>Page d'accueil de l'application mobile Dynamics 365 for Operations

[!include[banner](../includes/banner.md)]


Cette rubrique décrit l'application mobile Microsoft Dynamics 365 for Operations et fournit des liens vers des ressources qui peuvent vous aider à l'implémentation de votre organisation.

<a name="overview"></a>Vue d'ensemble
--------

L'application mobile Microsoft Dynamics 365 for Operations permet à votre organisation de rendre ses processus métiers disponibles sur des appareils mobiles. Lorsque votre administrateur informatique active des espaces de travail mobiles pour votre organisation, les utilisateurs peuvent se connecter à l'application et commencer à exécuter les processus métiers depuis leurs mobiles. L'application mobile Dynamics 365 for Operations inclut les fonctions suivantes qui permettent d'augmenter la productivité :

-   Les utilisateurs peuvent afficher, modifier, et agir sur les données commerciales, même avec une connectivité réseau intermittente ou si les appareils mobiles sont entièrement hors ligne. Lorsqu'un appareil rétablira une connexion réseau, les opérations de données hors ligne seront automatiquement synchronisées avec Dynamics 365 for Operations.
-   Les administrateurs ou les développeurs informatiques peuvent générer et publier des espaces de travail mobiles conçus en fonction de leur organisation. L'application utilise vos actifs de code existants. Par conséquent, vous n'aurez pas à réexécuter vos procédures de contrôle, votre logique métier, ou votre configuration de sécurité.
-   Les administrateurs ou les développeurs informatiques peuvent concevoir facilement des espaces de travail mobiles à l'aide du concepteur d'espace de travail inclus dans le client Dynamics 365 for Opérations, par simple pointer-cliquer.
-   Ils peuvent éventuellement optimiser les capacités hors connexion des espaces de travail à l'aide de la technologie d'extensibilité de logique du système. Comme les données continuent à être traitées lorsqu'un appareil est hors ligne, les scénarios mobiles restent riches et fluides, même si les appareils ne sont pas constamment connectés au réseau.

## <a name="elements-of-the-mobile-app"></a>Éléments de l'application mobile
La navigation dans l'application mobile utilise quatre éléments simples : le tableau de bord, les espaces de travail, les pages, et les actions. 

[![Concepts de navigation dans l'application mobile](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

-   Lorsque vous démarrez l'application, vous accédez au **Tableaux de bord**.
-   Dans le tableau de bord, vous pouvez afficher la liste des **espaces de travail** qui sont publiés dans votre environnement Dynamics 365 for Operations.
-   Dans chaque espace de travail, vous pouvez afficher la liste des **pages** disponibles pour cet espace de travail.
-   Dans une page, vous pouvez afficher les données qui sont collectées depuis une ou plusieurs pages dans Dynamics 365 for Operations.
-   Dans une page, vous pouvez accéder à d'autres pages pour consulter les données associées, telles que l'entité ou les lignes.
-   Dans une page, vous pouvez également afficher la liste des **actions** disponibles pour cette page.
-   Les actions permettent de créer ou de modifier les données existantes.

## <a name="implementation-process"></a>Processus d'implémentation
L'illustration suivante présente le processus utilisé pour implémenter l'application mobile Dynamics 365 for Operations dans votre organisation. 

![Processus d'implémentation d'applications mobiles](./media/mobile-implementation-process_4.png)

Le tableau suivant contient des liens vers des ressources qui peuvent vous aider à implémenter l'application mobile Dynamics 365 for Operations dans votre organisation. Les numéros dans la première colonne correspondent aux étapes numérotées dans l'illustration précédente.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Etape</th>
<th>Rôle</th>
<th>Action</th>
<th>Ressources d'aide pour les actions</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>Administrateur système</td>
<td>Implémentez Dynamics 365 for Operations pour l'organisation.</td>
<td>Si vous n'avez pas encore déployé Dynamics 365 for Operations dans votre organisation, consultez la rubrique <a href="../deployment/deploy-demo-environment.md">Déployer l'environnement de démonstration de Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>2</td>
<td>Administrateur système</td>
<td>Téléchargez et installez les KB qui activent les espaces de travail mobiles fournis par Microsoft.</td>
<td>Voir la section &quot;Conditions préalables&quot; de la rubrique qui aborde l'espace de travail mobile que votre organisation souhaite utiliser :
<ul>
<li><a href="/dynamics365/operations/financials/cost-accounting/cost-controlling-mobile-workspace">Espaces de travail mobiles Contrôle des coûts</a></li>
<li><a href="/dynamics365/operations/supply-chain/inventory/inventory-on-hand-mobile-workspace">Stock disponible dans l'espace de travail mobile</a></li>
<li><a href="/dynamics365/operations/supply-chain/sales-marketing/sales-orders-mobile-workspace">Espaces de travail mobiles Commandes client</a></li>
<li><a href="/dynamics365/operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Espace de travail de collaboration fournisseur sur téléphone mobile</a></li>
<li><a href="/dynamics365/operations/financials/project-management/project-time-entry-mobile-workspace">Espace de travail mobile de saisie de l'heure du projet</a></li>
<li><a href="/dynamics365/operations/financials/expense-management/expense-management-mobile-workspace">Espace de travail mobile pour la gestion des dépenses</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>3</td>
<td>Administrateur système</td>
<td>Publiez des espaces de travail mobiles qui sont fournis par Microsoft.</td>
<td><a href="publish-mobile-workspace.md">Publier un espace de travail mobile</a>
</td>
</tr>
<tr class="even">
<td>4</td>
<td>Éditeurs de logiciels indépendants (ISV) ou développeurs</td>
<td>Utilisez la technologie mobile Dynamics 365 for Operations pour créer des espaces de travail mobiles personnalisés.</td>
<td><ul>
<li><a href="mobile-platform.md">Technologie mobile Dynamics 365 for Operations</a></li>
<li><a href="http://ax.help.dynamics.com/en/wiki/operations-mobile-workspace-x-apis/">API X++ d'espace de travail Dynamics 365 for Operations</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>5</td>
<td>ISV</td>
<td>Créez un module déployable contenant des espaces de travail mobiles personnalisés, puis chargez le module dans Microsoft Dynamics Lifecycle Services (LCS).</td>
<td><a href="../deployment/create-apply-deployable-package.md">Créer un package déployable</a></td>
</tr>
<tr class="even">
<td>6</td>
<td>Administrateur système</td>
<td>Appliquez le module déployable contenant les espaces de travail personnalisés fournis par l'ISV.</td>
<td><a href="../deployment/apply-deployable-package-system.md">Appliquer un module déployable à votre système Microsoft Dynamics 365 for Operations</a></td>
</tr>
<tr class="odd">
<td>7</td>
<td>Administrateur système</td>
<td>Publiez les espaces de travail mobiles personnalisés qui sont fournis par l'ISV.</td>
<td><a href="publish-mobile-workspace.md">Publier un espace de travail mobile</a></td>
</tr>
<tr class="even">
<td>8</td>
<td>Utilisateur</td>
<td>Téléchargez et installez l'application mobile Dynamics 365 for Operations.</td>
<td><ul>
<li>Android - <a href="https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile">Dynamics 365 for Operations dans Google Play Store</a></li>
<li>Pour iPhone : <a href="https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8">Dynamics 365 for Operations dans iTunes</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>9</td>
<td>Utilisateur</td>
<td>Connectez-vous à l'application mobile Dynamics 365 for Operations et utilisez-la. L'application inclut les espaces de travail mobiles publiés.</td>
<td>Pour afficher la liste des espaces de travail mobiles fournis par Microsoft, voir <a href="mobile-workspaces-released.md">Espaces de travail mobiles récemment activés pour l'application mobile Dynamics 365 for Operations</a>
</td>
</tr>
</tbody>
</table>






