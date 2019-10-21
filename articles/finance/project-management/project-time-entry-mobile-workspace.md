---
title: Espace de travail mobile de saisie de l'heure du projet
description: Cette rubrique fournit des informations sur l'espace de travail mobile Saisie des heures du projet. Cet espace de travail permet aux utilisateurs d'entrer et de gagner du temps sur un projet à l'aide d'un appareil mobile.
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: ee11f7f392676adb59bd25f6549737482faf5fdb
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250367"
---
# <a name="project-time-entry-mobile-workspace"></a>Espace de travail mobile de saisie de l'heure du projet

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur l'espace de travail mobile **Saisie des heures du projet**. Cet espace de travail permet aux utilisateurs d'entrer et de gagner du temps sur un projet à l'aide d'un appareil mobile.

Cet espace de travail mobile est destiné à être utilisé avec l'application mobile Dynamics 365 Unified Ops. 

## <a name="overview"></a>Présentation
Dans le cadre de leur travail quotidien, les collaborateurs qui travaillent à un projet sont souvent sur site ou en voyage. L'espace de travail mobile **Saisie des heures du projet** permet aux utilisateurs d'entrer les heures facturables ou non facturables pour un projet sur l'appareil mobile de leur choix. Par conséquent, ils peuvent enregistrer les heures à tout moment et n'importe où. Ils peuvent également afficher les heures déjà consignées. 

Spécifiquement, dans l'espace de travail mobile **Saisie des heures du projet**, les utilisateurs peuvent effectuer les tâches suivantes :

-   Pour n'importe quelle date sélectionnée, il permet d'entrer le nombre d'heures que vous avez passées sur une tâche spécifique.
-   Il permet de lancer une recherche par nom de projet ou client pour entrer les heures correspondantes.
-   Il permet de spécifier la catégorie et l'activité qui correspondent aux heures.
-   Il permet d'enregistrer les heures facturables ou non facturables pour le projet.
-   Facultatif : il permet de saisir des commentaires externes ou internes.

## <a name="prerequisites"></a>Conditions préalables
Les conditions préalables varient, en fonction de la version de Microsoft Dynamics 365 qui a été déployée pour votre organisation.

### <a name="prerequisites-if-you-use-dynamics-365-finance"></a>Conditions requises si vous utilisez Dynamics 365 Finance
Si Finance a été déployé pour votre organisation, l'administrateur système doit publier l'espace de travail mobile **Saisie du temps de projet**. Pour obtenir des instructions, voir [Publier un espace de travail mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-version-1611-with-platform-update-3-or-later"></a>Conditions requises si vous utilisez la version 1611 avec Platform Update 3 ou version ultérieure
Si la version 1611 avec Platform Update 3 ou version ultérieure a été déployée pour votre organisation, l'administrateur système doit effectuer les tâches préalables suivantes. 

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

<td>Implémenter KB 4018050.</td>
<td>Administrateur système</td>
<td>Le KB 4018050 est une mise à jour X++ ou un correctif de métadonnées qui contient l'espace de travail mobile <strong>Saisie des heures du projet</strong>. Pour implémenter le KB 4018050, un administrateur système doit procéder comme suit :
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Télécharger le correctif de métadonnées depuis Microsoft Dynamics Lifecycle Services</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Installez le correctif de métadonnées</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Créez un module déployable</a> contenant les modèles <strong>ApplicationSuite</strong> et <strong>ProjectMobile</strong>, et téléchargez le module déployable vers LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Appliquer le package déployable</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Publiez l'espace de travail mobile <strong>Saisie des heures du projet</strong>.</td>
<td>Administrateur système</td>
<td>Voir <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publier un espace de travail mobile</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Télécharger et installer l'application mobile

Télécharger et installer l'application mobile Finance and Operations :

-   [Pour téléphones Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Pour les iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Connexion à l'application mobile
1.  Démarrez l'application sur votre appareil mobile.
2.  Entrez votre URL Dynamics 365.
3.  Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer vos nom d'utilisateur et mot de passe. Entrez vos informations d'identification.
4.  Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s'affichent. Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous devrez actualiser la liste des espaces de travail mobiles.

[![Extraire pour actualiser](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a>Entrer les heures en utilisant l'espace de travail mobile Saisie des heures du projet
1.  Sur votre appareil mobile, sélectionnez l'espace de travail **Saisie des heures du projet**.
2.  Sélectionnez **Saisie des heures**. Les dates civiles pour la semaine en cours sont affichées.
3.  Pour une date sélectionnée, choisissez &gt; **Action** **Nouvelle saisie**.
4.  Entrez le nombre d'heures.
5.  Sélectionnez le projet concerné par la saisie d'heures. Une liste affiche les projets chargés dans votre application pour l'utilisation hors ligne. Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre. Pour plus d'informations, voir [Plateforme mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
6.  Si votre projet ne figure pas dans la liste, sélectionnez **Rechercher**. Recherchez par nom, ou lancez une recherche par nom de projet ou de client.
7.  Permet de sélectionner une catégorie. Une liste affiche les catégories chargées dans votre application pour l'utilisation hors ligne. Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre. Pour plus d'informations, voir [Plateforme mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
8.  Si votre catégorie ne figure pas dans la liste, sélectionnez **Rechercher**. Recherchez par catégorie, ou lancez une rechercher par nom de catégorie.
9.  Permet de sélectionner une activité. Une liste affiche les activités chargées dans votre application pour l'utilisation hors ligne. Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre. Pour plus d'informations, voir [Plateforme mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
10. Si votre activité ne figure pas dans la liste, sélectionnez **Rechercher**. Recherchez par numéro d'activité, ou lancez une rechercher par objectif.

11. Sélectionner la propriété de ligne.
12. Facultatif : saisissez des commentaires externes et internes.
13. Sélectionnez **Terminé**.
