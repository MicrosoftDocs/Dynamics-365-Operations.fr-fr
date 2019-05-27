---
title: Page d'accueil de l'application Dynamics 365 for Unified Operations Mobile
description: Cette rubrique décrit l'application Microsoft Dynamics 365 for Unified Operations Mobile et fournit des liens vers des ressources qui peuvent vous aider à l'implémentation de votre organisation.
author: sericks007
manager: AnnBe
ms.date: 10/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.version: Platform update 4
ms.search.validFrom: 2017-02-28
ms.openlocfilehash: 5666bee776e3d97244ce4830ac59971831848e71
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554460"
---
# <a name="dynamics-365-for-unified-operations-mobile-app-home-page"></a>Page d'accueil de l'application Dynamics 365 for Unified Operations Mobile

[!include [banner](../includes/banner.md)]

Cette rubrique décrit l'application Microsoft Dynamics 365 for Unified Operations Mobile et fournit des liens vers des ressources qui peuvent vous aider à l'implémentation de votre organisation.

> [!NOTE]
> L'application mobile a été précédemment nommée *Microsoft Dynamics 365 for Finance and Operations*.

<a name="overview"></a>Présentation
--------

L'application mobile permet à votre organisation de rendre ses processus métiers disponibles sur des appareils mobiles. Lorsque votre administrateur informatique active des espaces de travail mobiles pour votre organisation, les utilisateurs peuvent se connecter à l'application et commencer à exécuter les processus métiers depuis leurs mobiles. L'application mobile inclut les fonctions suivantes qui permettent d'augmenter la productivité :

- Les utilisateurs peuvent afficher, modifier, et agir sur les données commerciales, même avec une connectivité réseau intermittente ou si les appareils mobiles sont entièrement hors ligne. Lorsqu'un appareil rétablira une connexion réseau, les opérations de données hors ligne seront automatiquement synchronisées avec Dynamics 365 for Finance and Operations.
- Les administrateurs ou les développeurs informatiques peuvent générer et publier des espaces de travail mobiles conçus en fonction de leur organisation. L'application utilise vos actifs de code existants. Par conséquent, vous n'aurez pas à réexécuter vos procédures de contrôle, votre logique métier, ou votre configuration de sécurité.
- Les administrateurs ou les développeurs informatiques peuvent concevoir facilement des espaces de travail mobiles à l'aide du concepteur d'espace de travail inclus dans le client, par simple pointer-cliquer.
- Ils peuvent éventuellement optimiser les capacités hors connexion des espaces de travail à l'aide de la technologie d'extensibilité de logique du système. Comme les données continuent à être traitées lorsqu'un appareil est hors ligne, les scénarios mobiles restent riches et fluides, même si les appareils ne sont pas constamment connectés au réseau.

## <a name="elements-of-the-mobile-app"></a>Éléments de l'application mobile
La navigation dans l'application mobile utilise quatre éléments de base : le tableau de bord, les espaces de travail, les pages, et les actions. 

[![Concepts de navigation dans l'application mobile](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

1. Lorsque vous démarrez l'application, vous accédez au **Tableaux de bord**.
2. Dans le tableau de bord, vous pouvez afficher la liste des **espaces de travail** qui ont été publiés.
3. Dans chaque espace de travail, vous pouvez afficher la liste des **pages** disponibles pour cet espace de travail.
4. Lorsque vous êtes sur une page, vous pouvez exécuter plusieurs actions. Voici quelques exemples :

    - Afficher les données détaillées.
    - Accéder à d'autres pages pour consulter les données associées, telles que l'entité ou les lignes.
    - Voir la liste des **actions** disponibles pour cette page. Les actions permettent de créer ou de modifier les données existantes.

## <a name="implementation-process"></a>Processus d'implémentation
L'illustration suivante présente le processus pour implémenter les deux espaces de travail mobiles qui sont fournis par Microsoft et les espaces de travail mobiles personnalisés. 

[![Processus d'implémentation d'applications mobiles](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)

Le tableau suivant contient des liens vers des ressources qui vous aident à implémenter les deux espaces de travail mobiles qui sont fournis par Microsoft et les espaces de travail mobiles personnalisés. Les numéros dans la première colonne correspondent aux étapes numérotées dans l'illustration précédente.

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
<td>Implémentez Finance and Operations dans votre organisation.</td>
<td><ul><li>Si vous n&#39;avez pas encore déployé une version de Microsoft Dynamics 365, voir <a href="../deployment/deploy-demo-environment.md">Déployer un environnement de démonstration</a>.</li><li>Pour afficher la liste des espaces de travail mobiles qui peuvent être utilisés, voir <a href="mobile-workspaces-released.md">Espaces de travail mobiles récemment publiés</a>.</li></ul></td>
</tr>
<tr class="even">
<td>2</td>
<td>Administrateur système</td>
<td><strong>Si vous utilisez Microsoft Dynamics 365 for Operations version 1611 :</strong> téléchargez et installez les KB qui activent les espaces de travail mobiles fournis par Microsoft.</td>
<td>Voir les rubriques suivantes pour plus d'informations :
<ul>

<li><a href="../../financials/cost-accounting/cost-controlling-mobile-workspace.md">Espaces de travail mobiles Contrôle des coûts</a></li>
<li><a href="../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Stock disponible dans l'espace de travail mobile</a></li>
<li><a href="../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Espaces de travail mobiles Commandes client</a></li>
<li><a href="../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Espace de travail de collaboration fournisseur sur téléphone mobile</a></li>
<li><a href="../../financials/project-management/project-time-entry-mobile-workspace.md">Espace de travail mobile de saisie de l'heure du projet</a></li>
<li><a href="../../financials/expense-management/expense-management-mobile-workspace.md">Espace de travail mobile pour la gestion des dépenses</a></li>

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
<td>Utilisez la plateforme mobile pour créer des espaces de travail mobiles personnalisés.</td>
<td><a href="platform/mobile-platform-home-page.md">Plateforme mobile</a></td>
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
<td>Appliquez le package déployable qui contient les espaces de travail personnalisés fournis par l'éditeur de logiciels indépendant (ISV).</td>
<td><a href="../deployment/apply-deployable-package-system.md">Appliquer un package déployable</a></td>
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
<td>Téléchargez et installez l'application mobile.</td>
<td>
<a href="https://go.microsoft.com/fwlink/?linkid=850662">Application Unified Operations pour Android</a><BR/>
<a href="https://go.microsoft.com/fwlink/?linkid=850663">Application Unified Operations pour iOS</a><BR/>
(Windows Phone non pris en charge)
</td>
</tr>
<tr class="odd">
<td>9</td>
<td>Utilisateur</td>
<td>Connectez-vous et utilisez l'application mobile. L'application inclut les espaces de travail mobiles publiés par l'administrateur système.</td>
<td>Pour afficher la liste des espaces de travail mobiles qui sont fournis par Microsoft, voir <a href="mobile-workspaces-released.md">Espaces de travail mobiles récemment publiés</a>.
</td>
</tr>
</tbody>
</table>
