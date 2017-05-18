---
title: "Espace de travail mobile pour la gestion des dépenses"
description: "Cette rubrique fournit des informations sur l&quot;espace de travail pour la gestion des dépenses disponible dans l&quot;application mobile Microsoft Dynamics 365 for Operations. Cet espace de travail permet aux utilisateurs de capturer et charger une réception, afin de pouvoir l&quot;associer à un état de dépenses ultérieurement. L&quot;espace de travail mobile permet également aux utilisateurs de créer rapidement une ligne de dépense à l&quot;aide d&quot;une réception associée."
author: annbe
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: end user, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: annbe
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 8bc47c5b170fd7dd8f6288682aad6eae1d2dc09a
ms.openlocfilehash: 9d3b7a4d5184c3c4958f4298f1d3dd4de0cd06d6
ms.contentlocale: fr-fr
ms.lasthandoff: 04/26/2017


---

# <a name="expense-management-mobile-workspace"></a>Espace de travail mobile pour la gestion des dépenses

[!include[banner](../includes/banner.md)]

« [!include[banner](../includes/banner.md)] »


Cette rubrique fournit des informations sur l'espace de travail pour la gestion des dépenses disponible dans l'application mobile Microsoft Dynamics 365 for Operations. Cet espace de travail permet aux utilisateurs de capturer et charger une réception, afin de pouvoir l'associer à un état de dépenses ultérieurement. L'espace de travail mobile permet également aux utilisateurs de créer rapidement une ligne de dépense à l'aide d'une réception associée.

<a name="overview-of-the-expense-management-mobile-workspace"></a>Vue d'ensemble de l'espace de travail mobile pour la gestion des dépenses
---------------------------------------------------

Plusieurs organisations exigent qu'une copie du reçu soit ajoutée à un état de dépenses de voyage ou commerciales afin que l'employé soit remboursé. L'espace de travail mobile **Gestion des dépenses** permet aux utilisateurs de créer rapidement de nouvelles lignes de dépense sur l'appareil mobile de leur choix en joignant la photo du reçu. Alternativement, les utilisateurs peuvent prendre en photo le reçu puis l'associer à un état de dépenses ultérieurement. Spécifiquement, l'espace de travail mobile **Gestion des dépenses** permet à l'utilisateur de :

-   Prendre une photo d'un reçu, et la télécharger dans Microsoft Dynamics 365 for Operations. Un utilisateur peut ensuite joindre cette photo à un état de dépenses ultérieurement.
-   Charger un fichier contenant le reçu capturé. Un utilisateur peut ensuite joindre ce fichier à un état de dépenses ultérieurement.
-   Créer une nouvelle ligne de dépense à l'aide d'un reçu joint. Un utilisateur peut alors ajouter une ligne à un état de dépenses ultérieurement, et l'envoyer pour approbation et remboursement.

Les autres sections de cette rubrique expliquent comment mettre en œuvre et utiliser l'espace de travail mobile **Gestion des dépenses**.

## <a name="prerequisites"></a>Conditions préalables
Avant de mettre en œuvre l'espace de travail mobile **Gestion des dépenses**, vérifiez que votre administrateur système a effectué les paramétrages suivants.

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
<td>Le KB 4019015 doit être implémenté.</td>
<td>Administrateur système</td>
<td>Le KB 4019015 (mise à jour X++ ou correctif de métadonnées) contient les quatre espaces de travail mobiles pour la gestion de la chaîne d'approvisionnement. Pour implémenter le KB 4019015, un administrateur système doit procéder comme suit :
<ol>
<li>Téléchargez le KB 4019015 depuis Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/configuring-and-installing-a-metadata-hotfix-package/">Installez le correctif de métadonnées</a>.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/create-and-apply-a-deployable-package/">Créez un module déployable</a> contenant le modèle <strong>ApplicationSuite</strong> et <strong>ExpenseMobile</strong>, et téléchargez le module déployable vers LCS.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/apply-a-deployable-package-on-a-dynamics-ax-system/">Appliquez le module déployable</a> à votre système Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>L'espace de travail mobile <strong>Gestion des dépenses</strong> doit être publié sur l'application mobile Dynamics 365 for Operations.</td>
<td>Administrateur système</td>
<td><ol>
<li>Démarrez Dynamics 365 for Operations dans votre navigateur.</li>
<li>Dans la page <strong>Paramètres système</strong>, sélectionnez <strong>Gestion des espaces de travail mobiles</strong>.</li>
<li>Sélectionnez l'espace de travail <strong>Gestion des dépenses</strong>.</li>
<li>Cliquez sur <strong>Publier l'espace de travail mobile</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Télécharger et installer l'application mobile Dynamics 365 for Operations
Dans votre magasin d'applications mobiles, téléchargez et installez l'application mobile Dynamics 365 for Operations.

-   Android - [Dynamics 365 for Operations dans Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   Pour iPhone : [Dynamics 365 for Operations dans iTunes](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)
-   Pour Windows Phone (Universal Windows Platform \[UWP\]) : prévu prochainement !

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Connexion à l'application mobile Dynamics 365 for Operations
1.  Démarrez l'application sur votre appareil mobile.
2.  Entrez votre URL Dynamics 365 for Operations.
3.  Entrez la société à laquelle vous vous connectez. Par exemple, entrez **USMF**.
4.  Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer le nom d'utilisateur et le mot de passe de votre compte Dynamics 365 for Operations. Entrez vos informations d'identification.
5.  Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s'affichent. Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous pouvez l'extraire pour actualiser la liste des espaces de travail portables. [![Extraire pour actualiser](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="capture-a-receipt-by-using-the-expense-management-mobile-workspace"></a>Capturer un reçu à l'aide de l'espace de travail mobile Gestion des dépenses
1.  Sur votre appareil mobile, sélectionnez l'espace de travail **Gestion des dépenses**.
2.  Sélectionnez **Capturer le reçu**.
3.  Sélectionnez **Prendre une photo** ou **Choisir une image**.
4.  Si vous sélectionnez **Prendre une photo**, procédez comme suit :
    1.  L'appareil-photo s'ouvre sur votre appareil mobile, pour vous permettre de prendre une photo du ticket de caisse. Lorsque vous avez terminé de prendre la photo, cliquez sur **Ajouter** pour accepter la photo.
    2.  Facultatif : entrez un nom pour la photo, puis entrez des notes.

     ou si vous sélectionnez **Choisir une image**, procédez comme suit :
    1.  Sélectionnez une image dans la liste.
    2.  Facultatif : entrez un nom pour l'image, puis entrez des notes.

5.  Sélectionnez **Terminé**.

## <a name="quick-expense-entry-by-using-the-expense-management-mobile-workspace"></a>Entrer rapidement une dépense à l'aide de l'espace de travail mobile Gestion des dépenses
1.  Sur votre appareil mobile, sélectionnez l'espace de travail **Gestion des dépenses**.
2.  Sélectionnez **Entrée rapide de dépense**.
3.  Sélectionnez la catégorie de la dépense. Vous verrez la liste des catégories de dépense dans votre application pour l'utilisation hors ligne. Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre. Pour plus d'informations, les développeurs doivent consulter [Plateforme mobile Dynamics 365 for Operations d'opérations](http://ax.help.dynamics.com/en/wiki/mobile-development-handbook/). Si votre catégorie ne figure pas dans la liste, sélectionnez **Rechercher** pour effectuer une recherche en ligne dans Dynamics 365 for Operations. Recherchez par catégorie de dépense, ou lancez une recherche par type de dépense.
4.  Entrez la date de transaction de la dépense.
5.  Facultatif : entrez le marchand pour la dépense.
6.  Entrez le montant de la dépense.
7.  Ssélectionnez la devise de la dépense. Vous verrez la liste des codes de devise dans votre application pour l'utilisation hors ligne. Par défaut, jusqu'à 400 dévises sont chargées, mais votre développeur peut modifier ce nombre. Pour plus d'informations, les développeurs doivent consulter [Plateforme mobile Dynamics 365 for Operations d'opérations](http://ax.help.dynamics.com/en/wiki/mobile-development-handbook/). Si votre dévise ne figure pas dans la liste, sélectionnez **Rechercher** pour effectuer une recherche en ligne dans Dynamics 365 for Operations. Recherchez par devise, ou lancez une rechercher par nom.
8.  Sélectionnez **Prendre une photo** ou **Choisir une image**.
9.  Si vous avez sélectionné **Prendre une photo**, l'appareil-photo s'ouvre sur votre appareil mobile, pour vous permettre de prendre une photo du ticket de caisse. Lorsque vous avez terminé de prendre la photo, cliquez sur **Ajouter** pour accepter la photo.  ou si vous préférez **Choisir une image**, sélectionnez une image dans la liste.
10. Sélectionnez **Terminé**.






