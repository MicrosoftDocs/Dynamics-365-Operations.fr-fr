---
title: "Espace de travail mobile Contrôle des coûts"
description: "Cette rubrique fournit des informations sur l&quot;espace de travail Contrôle des coûts disponible dans l&quot;application mobile Microsoft Dynamics 365 for Operations. Cet espace de travail permet aux responsables de centre de coût d&quot;afficher des informations sur les performances du centre de coût à tout moment et n&quot;importe où."
author: YuyuScheller
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 09383c24b0dd2ad61a836f6c8dc97f4389915772
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="cost-controlling-mobile-workspace"></a>Espace de travail mobile Contrôle des coûts

[!include[banner](../includes/banner.md)]


Cette rubrique fournit des informations sur l'espace de travail Contrôle des coûts disponible dans l'application mobile Microsoft Dynamics 365 for Operations. Cet espace de travail permet aux responsables de centre de coût d'afficher des informations sur les performances du centre de coût à tout moment et n'importe où. 

<a name="overview-of-the-cost-controlling-mobile-workspace"></a>Vue d'ensemble de l'espace de travail mobile Contrôle des coûts
-------------------------------------------------

L'espace de travail mobile **Contrôle des coûts** fournit une vue instantanée des performances actuelles des centres de coût en comparant les coûts réels aux coûts budgétés. Vous pouvez accéder aux statuts des éléments de coût individuels. 

Par exemple, un employé reçoit une invitation à une conférence internationale, mais l'organisation doit couvrir toutes les dépenses de déplacement. L'employé demande à son responsable s'il peut assister à la conférence. Le responsable ouvre rapidement l'espace de travail **Contrôle des coûts** sur son téléphone portable de voir s'il dispose du budget nécessaire.

### <a name="data-security"></a>Sécurité des données

Les données de l'espace de travail **Contrôle des coûts** sont sécurisées par les informations d'identification de l'utilisateur. Les responsables de centre de coût sont uniquement autorisés à consulter les données de leur propre centre de coût. La sécurité au niveau de l'accès est gérée dans le module **Contrôle de gestion**. 

Les contrôleurs de gestion définissent la configuration de l'espace de travail mobile **Contrôle des coûts** dans le module **Contrôle de gestion**. Une fois que l'espace de travail est publié sur l'application mobile Microsoft Dynamics 365 for Operations, il est disponible dans l'application mobile. Par conséquent, tous les responsables de centre de coût de l'organisation peuvent consultent les données au même format.

### <a name="actions-views-and-links"></a>Actions, vues et liens

L'espace de travail mobile **Contrôle des coûts** pour l'application Dynamics 365 for Operations fournit les actions, les vues et les liens suivants :

-   **Actions :**
    -   Utilisez **Sélectionner une configuration** pour sélectionner une mise en page.
    -   Utilisez **Sélectionner un objet de coût** pour sélectionner les centres de coût et filtrer les données en fonction. **Remarque :** les centres de coût qui figurent dans la liste dépendent de l'accès qui est accordé dans le module **Contrôle de gestion**.
-   **Vues :** selon la sélection des actions et la configuration du module **Contrôle de gestion**, vous pouvez afficher les informations suivantes dans les cartes.
    -   Réel/Budget (période actuelle)
    -   Réel/Budget révisé (période actuelle)
    -   Réel/Budget (période précédente)
    -   Réel/Budget révisé (période précédente)
    -   Réel/Budget (année en cours)
    -   Réel/Budget révisé (année en cours)

    Les montants suivants sont affichés dans chaque carte : Réel, Budget, Écart, et Écart en %.
-   **Liens :**
    -   Détails pour la période actuelle
    -   Détails pour la période précédente
    -   Détails pour l'année en cours

    Lorsque vous sélectionnez un lien, une carte est affichée pour chaque élément de coût. Les montants suivants sont affichés sur chaque carte : réel, budget, écart budgétaire, écart budgétaire en %, budget révisé, écart budgétaire révisé et écart budgétaire révisé en %. 
    
    [![Carte pour un élément de coût ](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="prerequisites"></a>Conditions préalables
Avant d'utiliser l'espace de travail mobile **Contrôle des coûts**, vérifiez que votre administrateur système a effectué les paramétrages suivants.

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
<td>Dynamics 365 for Operations version 1611 avec la mise à jour de plateforme 3 ou ultérieure.</td>
<td>Administrateur système</td>
<td>Si vous n'avez pas encore déployé Dynamics 365 for Operations dans votre organisation, votre administrateur système doit consulter la rubrique <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Déployer l'environnement de démonstration de Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>Le KB 4013633 doit être implémenté.</td>
<td>Administrateur système</td>
<td>Le KB 4013633 (mise à jour X++ ou correctif de métadonnées) contient les quatre espaces de travail mobiles pour la gestion de la chaîne d'approvisionnement. Pour implémenter le KB 4013633, un administrateur système doit procéder comme suit :
<ol>
<li>Téléchargez le KB 4013633 depuis Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Installez le correctif de métadonnées</a>.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Créez un module déployable</a> contenant le modèle <strong>SCMMobile</strong> et téléchargez le module déployable vers LCS.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Appliquez le module déployable</a> à votre système Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>L'espace de travail mobile <strong>Contrôle des coûts</strong> doit être publié sur l'application mobile Dynamics 365 for Operations.</td>
<td>Administrateur système</td>
<td><ol>
<li>Démarrez Dynamics 365 for Operations dans votre navigateur.</li>
<li>Dans la page <strong>Paramètres système</strong>, sélectionnez <strong>Gestion des espaces de travail mobiles</strong>.</li>
<li>Sélectionnez l'espace de travail <strong>Vue d'ensemble de l'objet de coût</strong>.</li>
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

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a>Afficher les performances de votre centre de coût à l'aide de l'espace de travail mobile Contrôle des coûts
1.  Sur votre appareil mobile, sélectionnez l'espace de travail **Contrôle des coûts**.
2.  Sélectionnez **Contrôle des objets de coût**.
3.  Sélectionnez **Actions**.
4.  Sélectionnez **Sélectionner une configuration** pour sélectionner une mise en page de contrôle des coûts.
5.  Sélectionnez **Terminé**.
6.  Sélectionnez **Actions**.
7.  Sélectionnez **Sélectionner un objet de coût** pour sélectionner les centres de coût auxquels vous êtes autorisé à accéder.
8.  Sélectionnez **Terminé**.
9.  Affichez les performances globales de votre centre de coût.
10. Sélectionnez le lien **Détails pour la période actuelle**.
11. Affichez les performances des éléments de coût individuels.
12. Vous pouvez également rechercher des éléments de coût spécifiques.





