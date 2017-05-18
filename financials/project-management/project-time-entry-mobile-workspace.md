---
title: "Espace de travail mobile Saisie des heures du projet pour l&quot;application Microsoft Dynamics 365 for Operations"
description: "Cette rubrique fournit des informations sur l&quot;espace de travail mobile Saisie des heures du projet. Cet espace de travail permet aux utilisateurs d&quot;entrer et de gagner du temps sur un projet à l&quot;aide d&quot;un appareil mobile."
author: annbe
manager: AnnBe
ms.date: 04/21/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: annbe
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e3e0be36c045acc3750efbb739d79d81ab937c65
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="project-time-entry-mobile-workspace"></a>Espace de travail mobile de saisie des heures du projet

[!include[banner](../includes/banner.md)]

« [!include[banner](../includes/banner.md)] »


Cette rubrique fournit des informations sur l'espace de travail Saisie des heures du projet disponible dans l'application mobile Microsoft Dynamics 365 for Operations. Cet espace de travail permet aux utilisateurs d'entrer et de gagner du temps sur un projet à l'aide d'un appareil mobile.

<a name="overview-of-the-project-time-entry-mobile-workspace"></a>Vue d'ensemble de l'espace de travail mobile de saisie des heures du projet
---------------------------------------------------

Dans le cadre de leur travail quotidien, les collaborateurs qui travaillent à un projet sont souvent sur site ou en voyage. L'espace de travail mobile **Saisie des heures du projet** permet aux utilisateurs d'entrer les heures facturables ou non facturables pour un projet sur l'appareil mobile de leur choix. Par conséquent, ils peuvent enregistrer les heures à tout moment et n'importe où. Ils peuvent également afficher les heures déjà consignées. 

Spécifiquement, l'espace de travail mobile **Saisie des heures du projet** fournit ces fonctions :

-   Pour n'importe quelle date sélectionnée, il permet d'entrer le nombre d'heures que vous avez passées sur une tâche spécifique.
-   Il permet de lancer une recherche par nom de projet ou client pour entrer les heures correspondantes.
-   Il permet de spécifier la catégorie et l'activité qui correspondent aux heures.
-   Il permet d'enregistrer les heures facturables ou non facturables pour le projet.
-   Facultatif : il permet de saisir des commentaires externes ou internes.

Pour implémenter l'espace de travail mobile **Saisie des heures du projet**, consultez les sections suivantes dans cette rubrique.

## <a name="prerequisites"></a>Conditions préalables
Avant de mettre en œuvre l'espace de travail mobile **Saisie des heures du projet**, vérifiez que votre administrateur système a effectué les paramétrages suivants.

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
<td>Si vous n'avez pas encore déployé Dynamics 365 for Operations dans votre organisation, votre administrateur système doit consulter la rubrique <a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Déployer l'environnement de démonstration de Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>Le KB 4018050 doit être implémenté.</td>
<td>Administrateur système</td>
<td>Le KB 4018050 est une mise à jour X++ ou un correctif de métadonnées qui contient l'espace de travail mobile <strong>Saisie des heures du projet</strong>. Pour implémenter le KB 4018050, un administrateur système doit procéder comme suit :
<ol>
<li>Téléchargez le KB 4018050 depuis Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Installez le correctif de métadonnées</a>.</li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Créez un module déployable</a> contenant les modèles <strong>ApplicationSuite</strong> et <strong>ProjectMobile</strong>, et téléchargez le module déployable vers LCS.</li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Appliquez le module déployable</a> à votre système Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>L'espace de travail mobile <strong>Saisie des heures du projet</strong> doit être publié sur l'application mobile Dynamics 365 for Operations.</td>
<td>Administrateur système</td>
<td><ol>
<li>Démarrez Dynamics 365 for Operations dans votre navigateur.</li>
<li>Dans la page <strong>Paramètres système</strong>, sous l'onglet <strong>Gestion des espaces de travail mobiles</strong> sélectionnez l'espace de travail <strong>Saisie des heures du projet</strong>.</li>
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

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a>Entrer les heures en utilisant l'espace de travail mobile Saisie des heures du projet
1.  Sur votre appareil mobile, sélectionnez l'espace de travail **Saisie des heures du projet**.
2.  Sélectionnez **Saisie des heures**. Vous pouvez afficher les dates civiles pour la semaine en cours.
3.  Pour une date sélectionnée, choisissez &gt; **Action** **Nouvelle saisie**.
4.  Entrez le nombre d'heures.
5.  Sélectionnez le projet concerné par la saisie d'heures. Vous verrez la liste des projets chargés dans votre application pour l'utilisation hors ligne. Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre. Pour plus d'informations, les développeurs doivent consulter [Plateforme mobile Dynamics 365 for Operations d'opérations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
6.  Si votre projet ne figure pas dans la liste, sélectionnez **Rechercher** pour effectuer une recherche en ligne dans Dynamics 365 for Operations. Recherchez par nom, ou lancez une recherche par nom de projet ou de client.
7.  Permet de sélectionner une catégorie. Vous verrez la liste des catégories chargées dans votre application pour l'utilisation hors ligne. Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre. Pour plus d'informations, les développeurs doivent consulter [Plateforme mobile Dynamics 365 for Operations d'opérations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
8.  Si votre catégorie ne figure pas dans la liste, sélectionnez **Rechercher** pour effectuer une recherche en ligne dans Dynamics 365 for Operations. Recherchez par catégorie, ou lancez une rechercher par nom de catégorie.
9.  Permet de sélectionner une activité. Vous verrez la liste des activités chargées dans votre application pour l'utilisation hors ligne. Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre. Pour plus d'informations, les développeurs doivent consulter [Plateforme mobile Dynamics 365 for Operations d'opérations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
10. Si votre activité ne figure pas dans la liste, sélectionnez **Rechercher** pour effectuer une recherche en ligne dans Dynamics 365 for Operations. Recherchez par numéro d'activité, ou lancez une rechercher par objectif.
11. Sélectionner la propriété de ligne.
12. Facultatif : saisissez des commentaires externes et internes.
13. Sélectionnez **Terminé**.






