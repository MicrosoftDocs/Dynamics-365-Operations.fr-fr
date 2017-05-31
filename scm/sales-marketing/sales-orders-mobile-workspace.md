---
title: Espace de travail mobile Commandes client
description: "Cette rubrique fournit des informations sur l&quot;espace de travail Commandes client disponible dans l&quot;application mobile Microsoft Dynamics 365 for Operations. Cet espace de travail vous permet de rester à jour de vos commandes client à tout moment et n&quot;importe où."
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
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 11898146a13756a6bb22a769e37e8773484e0d04
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="sales-orders-mobile-workspace"></a>Espace de travail mobile Commandes client

[!include[banner](../includes/banner.md)]


Cette rubrique fournit des informations sur l'espace de travail Commandes client disponible dans l'application mobile Microsoft Dynamics 365 for Operations. Cet espace de travail vous permet de rester à jour de vos commandes client à tout moment et n'importe où. 

<a name="overview-of-the-sales-orders-mobile-workspace"></a>Vue d'ensemble de l'espace de travail mobile Commandes client
---------------------------------------------

L'espace de travail mobile **Commandes client** accède à Microsoft Dynamics 365 for Operations et vous permet d'afficher des informations détaillées sur chaque commande client. Ces informations incluent le statut de la commande, les informations de contact du client, et les informations de contact du responsable de la commande. L'espace de travail mobile **Commandes client** fournit une vue instantanée des commandes client. Vous pouvez afficher toutes les commandes client, afficher les commandes client par client, ou afficher des informations sur une commande client spécifique. 

L'espace de travail mobile fournit deux vues pour vous aider à analyser les commandes client en profondeur.

### <a name="view-all-sales-orders"></a>Afficher toutes les commandes client

Cette vue répertorie toutes les commandes client.

-   Utilisez l'un des filtres suivants pour sélectionner les commandes client que vous souhaitez afficher :
    -   Recherche par commande client
    -   Rechercher par compte client
    -   Recherche par nom de client
    -   Rechercher par statut
    -   Rechercher par statut de lancement
    -   Recherche par date et heure de création
    
-   Après avoir sélectionné les commandes client, vous pouvez afficher les détails de commandes spécifiques. Plus précisément, vous pouvez afficher les informations suivantes :
    -   le nom du client et les informations d'adresse
    -   Plusieurs dates pour la commande client, par exemple la date d'expédition demandée et la date d'expédition confirmée.
    -   les coordonnées de contact du responsable de la commande ;
    -   les coordonnées du client
    -   Lignes de commande
    -   Expéditions qui affichent quand et comment une commande client a été expédiée

### <a name="view-orders-for-a-customer"></a>Afficher les commandes pour un client

Cette vue répertorie les commandes client par client.

-   Utilisez l'un des filtres suivants pour afficher les commandes pour un client :
    -   Rechercher par nom
    -   Rechercher par compte

-   Après avoir sélectionné un client, vous pouvez afficher les informations suivantes :
    -   le nom et le groupe du client
    -   les coordonnées du client
    -   les commandes du client et les détails qui les concernent :
        -   le nom du client et les informations d'adresse
        -   les différentes dates de commande client
        -   les coordonnées de contact du responsable de la commande ;
        -   les coordonnées du client
        -   Lignes de commande
        -   Expéditions qui affichent quand et comment une commande client a été expédiée

## <a name="prerequisites"></a>Conditions préalables
Avant d'utiliser l'espace de travail mobile **Commandes client**, vérifiez que votre administrateur système a effectué les paramétrages suivants.

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
<td>Si vous n'avez pas encore déployé Dynamics 365 for Operations dans votre organisation, votre administrateur système doit consulter la rubrique <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment/">Déployer l'environnement de démonstration de Microsoft Dynamics 365 for Operations</a>.</td>
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
<td>L'espace de travail mobile <strong>Commandes client</strong> doit être publié sur l'application mobile Dynamics 365 for Operations.</td>
<td>Administrateur système</td>
<td><ol>
<li>Démarrez Dynamics 365 for Operations dans votre navigateur.</li>
<li>Dans la page <strong>Paramètres système</strong>, sélectionnez <strong>Gestion des espaces de travail mobiles</strong>.</li>
<li>Sélectionnez l'espace de travail <strong>Commandes client</strong>.</li>
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

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-mobile-workspace"></a>Afficher des informations sur les commandes client pour un client à l'aide de l'espace de travail mobile
1.  Sur votre appareil mobile, sélectionnez l'espace de travail **Commandes client**.
2.  Sélectionnez **Afficher les commandes pour un client**.
3.  Utilisez les informations de compte ou le nom du client pour trouver le client souhaité.
4.  Sélectionnez le client
5.  Sélectionnez **Informations de contact** ou **Commandes client**. Si vous sélectionnez **Commandes client**, une liste des commandes client du client s'affiche.
6.  Sélectionnez **Commandes client**. Vous pouvez maintenant afficher des informations sur les lignes de commande client, les expéditions, les informations de contact du client et les informations de contact de la personne qui a pris la commande.





