---
title: Page d’accueil Application mobile
description: Cet article décrit l’application mobile de finances et d’opérations (Dynamics 365) et fournit des liens vers des ressources qui peuvent vous aider à l'implémenter dans votre organisation.
author: sericks007
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2017-02-28
ms.dyn365.ops.version: Platform update 4
ms.custom: intro-internal
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.openlocfilehash: a0979df7c0cd685f810c0ab743fbede740e7aacb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284066"
---
# <a name="mobile-app-home-page"></a>Page d’accueil Application mobile

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../includes/mobile-app-deprecation-banner.md)]

Cet article décrit l’application mobile de **finances et d’opérations (Dynamics 365)** et fournit des liens vers des ressources qui peuvent vous aider à l’implémenter dans votre organisation.

## <a name="overview"></a>Présentation

L’application mobile permet à votre organisation de rendre ses processus métiers disponibles sur des appareils mobiles. Lorsque votre administrateur informatique active des espaces de travail mobiles pour votre organisation, les utilisateurs peuvent se connecter à l’application et commencer à exécuter des processus métiers depuis leurs appareils mobiles. L’application mobile inclut les fonctions suivantes qui permettent d’augmenter la productivité :

- Les utilisateurs peuvent afficher, modifier, et agir sur les données commerciales, même avec une connectivité réseau intermittente ou si leurs appareils mobiles sont entièrement hors ligne. Lorsqu’un appareil rétablit une connexion réseau, les opérations de données hors ligne sont automatiquement synchronisées.
- Les administrateurs ou les développeurs informatiques peuvent générer et publier des espaces de travail mobiles conçus en fonction de leur organisation. L’application utilise vos actifs de code existants. Par conséquent, vous n’aurez pas à réimplémenter vos procédures de validation, votre logique métier, ou votre configuration de sécurité.
- Les administrateurs ou les développeurs informatiques peuvent concevoir facilement des espaces de travail mobiles à l’aide du concepteur d’espace de travail pointer-cliquer inclus avec le client web.
- Les administrateurs ou les développeurs informatiques peuvent en option optimiser les capacités hors connexion des espaces de travail en utilisant le cadre d’extensibilité logique métier. Comme les données continuent à être traitées lorsqu’un appareil est hors ligne, vos scénarios mobiles restent riches et fluides, même si les appareils ne sont pas constamment connectés au réseau.

## <a name="elements-of-the-mobile-app"></a>Éléments de l’application mobile
La navigation dans l’application mobile utilise quatre concepts de base : le tableau de bord, les espaces de travail, les pages, et les actions. 

[![Concepts de navigation dans l’application mobile.](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

1. Lorsque vous démarrez l’application, vous accédez au **Tableau de bord**.
2. Sur le tableau de bord, vous pouvez voir une liste des **espaces de travail** qui ont été publiés.
3. Dans chaque espace de travail, vous pouvez voir une liste des **pages** disponibles pour cet espace de travail.
4. Lorsque vous êtes sur une page, vous pouvez exécuter plusieurs actions. Voici quelques exemples :

    - Afficher les données détaillées.
    - Accéder à d’autres pages pour les données associées, telles que les détails ou les lignes de l’entité.
    - Voir une liste des **actions** disponibles pour cette page. Les actions vous permettent de créer ou de modifier les données existantes.

## <a name="implementation-process"></a>Processus d’implémentation
L’illustration suivante présente le processus pour implémenter les deux espaces de travail mobiles qui sont fournis par Microsoft et les espaces de travail mobiles personnalisés. 

[![Processus d’implémentation d’applications mobiles.](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)

Le tableau suivant contient des liens vers des ressources qui vous peuvent vous aider à implémenter les deux espaces de travail mobiles qui sont fournis par Microsoft et les espaces de travail mobiles personnalisés. Les numéros dans la première colonne correspondent aux étapes numérotées dans l’illustration précédente.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Étape</th>
<th>Rôle</th>
<th>Action</th>
<th>Ressources pour vous aider à terminer l'action</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>Administrateur système</td>
<td>Implémentez l’application de finances et d’opérations dans votre organisation.</td>
<td><ul><li>Si vous n'avez pas&#39;encore déployé une version de Microsoft Dynamics 365, voir <a href="../deployment/deploy-demo-environment.md">Déployer un environnement de démonstration</a>.</li><li>Pour voir une liste des espaces de travail mobiles qui peuvent être utilisés, voir <a href="mobile-workspaces-released.md">Espaces de travail mobiles récemment publiés</a>.</li></ul></td>
</tr>
<tr class="even">
<td>2</td>
<td>Administrateur système</td>
<td><strong>Si vous u&#39;tilisez la version 1611 de Microsoft Dynamics 365 for Operations :</strong> Téléchargez et installez les KB qui activent les espaces de travail mobiles fournis par Microsoft.</td>
<td>Voir les rubriques suivantes pour plus d’informations :
<ul>

<li><a href="../../../finance/cost-accounting/cost-controlling-mobile-workspace.md">Espaces de travail mobiles contrôle des coûts</a></li>
<li><a href="../../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Stock disponible de l’espace de travail mobile</a></li>
<li><a href="../../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Espaces de travail mobiles avec commandes client</a></li>
<li><a href="../../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Espace de travail mobile de collaboration fournisseur</a></li>
<li><a href="/dynamics365/project-operations/prod-pma/project-time-entry-mobile-workspace">Espace de travail mobile d’entrée de temps de projet</a></li>
<li><a href="/dynamics365/project-operations/prod-exp/expense-management-mobile-workspace">Espace de travail mobile de gestion des dépenses</a></li>

</ul></td>
</tr>
<tr class="odd">
<td>3</td>
<td>Administrateur système</td>
<td>Publiez les espaces de travail mobiles qui sont fournis par Microsoft.</td>
<td><a href="publish-mobile-workspace.md">Publier un espace de travail mobile</a>
</td>
</tr>
<tr class="even">
<td>4</td>
<td>Développeur ou fournisseur de logiciel indépendant (ISV)</td>
<td>Utilisez la plateforme mobile pour créer des espaces de travail mobiles personnalisés.</td>
<td><a href="platform/mobile-platform-home-page.md">Plateforme mobile</a></td>
</tr>
<tr class="odd">
<td>5</td>
<td>ISV</td>
<td>Créez un package déployable contenant des espaces de travail mobiles personnalisés, puis chargez le package surs Microsoft Dynamics Lifecycle Services (LCS).</td>
<td><a href="../deployment/create-apply-deployable-package.md">Créer un package déployable</a></td>
</tr>
<tr class="even">
<td>6</td>
<td>Administrateur système</td>
<td>Appliquez le package déployable qui contient les espaces de travail personnalisés fournis par le fournisseur de logiciel indépendant (ISV).</td>
<td><a href="../deployment/apply-deployable-package-system.md">Appliquer un package déployable</a></td>
</tr>
<tr class="odd">
<td>7</td>
<td>Administrateur système</td>
<td>Publiez les espaces de travail mobiles personnalisés qui sont fournis par l’ISV.</td>
<td><a href="publish-mobile-workspace.md">Publier un espace de travail mobile</a></td>
</tr>
<tr class="even">
<td>8</td>
<td>Utilisateur</td>
<td>Téléchargez et installez l’application mobile.</td>
<td>
<a href="https://go.microsoft.com/fwlink/?linkid=850662">Application de finances et d’opérations pour Android</a><BR/>
<a href="https://go.microsoft.com/fwlink/?linkid=850663">Application de finances et d’opérations pour iOS</a><BR/>
(Windows Phone non pris en charge)
</td>
</tr>
<tr class="odd">
<td>9</td>
<td>Utilisateur</td>
<td>Connectez-vous et utilisez l’application mobile. L’application inclut les espaces de travail mobiles publiés par l’administrateur système.</td>
<td>Pour voir une liste des espaces de travail mobiles qui sont fournis par Microsoft, voir <a href="mobile-workspaces-released.md">Espaces de travail mobiles récemment publiés</a>.
</td>
</tr>
</tbody>
</table>

## <a name="troubleshooting"></a>Résolution des problèmes
[Ressources de plateforme mobile](platform/mobile-platform-home-page.md#troubleshooting-the-app)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

