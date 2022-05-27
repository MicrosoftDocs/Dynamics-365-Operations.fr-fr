---
title: Espace de travail mobile Commandes client
description: Cette rubrique fournit des informations sur l’espace de travail mobile Commandes client. Cet espace de travail vous permet de rester à jour de vos commandes client à tout moment et n’importe où.
author: Henrikan
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: henrikan
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 3a746ae5d7f0c6ca2fd8e69a23114cfcaa24b16b
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675007"
---
# <a name="sales-orders-mobile-workspace"></a>Espace de travail mobile Commandes client

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur l’espace de travail mobile **Commandes client**. Cet espace de travail vous permet de rester à jour de vos commandes client à tout moment et n'importe où. 

Cet espace de travail mobile est destiné à être utilisé avec l'application mobile Finance and Operations.

## <a name="overview"></a>Présentation
L'espace de travail mobile **Commandes client** permet d'afficher des informations détaillées sur chaque commande client. Ces informations incluent le statut de la commande, les informations de contact du client, et les informations de contact du responsable de la commande. L’espace de travail mobile **Commandes client** fournit une vue instantanée des commandes client. Vous pouvez afficher toutes les commandes client, afficher les commandes client par client, ou afficher des informations sur une commande client spécifique. 

L’espace de travail mobile fournit deux vues pour vous aider à analyser les commandes client en profondeur.

### <a name="view-all-sales-orders"></a>Afficher toutes les commandes client
Cette vue répertorie toutes les commandes client.

-   Utilisez l’un des filtres suivants pour sélectionner les commandes client que vous souhaitez afficher :

    -   Recherche par commande client
    -   Rechercher par compte client
    -   Recherche par nom de client
    -   Rechercher par statut
    -   Rechercher par statut de lancement
    -   Recherche par date et heure de création
    
-   Après avoir sélectionné les commandes client, vous pouvez afficher les détails de commandes spécifiques. Plus précisément, vous pouvez afficher les informations suivantes :

    -   le nom du client et les informations d’adresse
    -   Plusieurs dates pour la commande client, par exemple la date d’expédition demandée et la date d’expédition confirmée.
    -   les coordonnées de contact du responsable de la commande ;
    -   les coordonnées du client
    -   Lignes de commande
    -   Expéditions qui affichent quand et comment une commande client a été expédiée

### <a name="view-orders-for-a-customer"></a>Afficher les commandes pour un client
Cette vue répertorie les commandes client par client.

-   Utilisez l’un des filtres suivants pour afficher les commandes pour un client :

    -   Rechercher par nom
    -   Rechercher par compte

-   Après avoir sélectionné un client, vous pouvez afficher les informations suivantes :

    -   le nom et le groupe du client
    -   les coordonnées du client
    -   les commandes du client et les détails qui les concernent :
    
        -   le nom du client et les informations d’adresse
        -   les différentes dates de commande client
        -   les coordonnées de contact du responsable de la commande ;
        -   les coordonnées du client
        -   Lignes de commande
        -   Expéditions qui affichent quand et comment une commande client a été expédiée

## <a name="prerequisites"></a>Conditions préalables
Les conditions préalables varient, en fonction de la version de Microsoft Dynamics 365 qui a été déployée pour votre organisation.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Conditions requises si vous utilisez Supply Chain Management 
Si Supply Chain Management a été déployé pour votre organisation, l’administrateur système doit publier l’espace de travail mobile **Commandes client**. Pour obtenir des instructions, voir [Publier un espace de travail mobile](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Conditions requises si vous utilisez la version 1611 de Dynamics 365 for Operations avec la mise à jour de plateforme 3 ou ultérieure
Si la version 1611 de Dynamics 365 for Operations avec la mise à jour de plateforme 3 ou ultérieure a été déployée pour votre organisation, l’administrateur système doit effectuer les tâches préalables suivantes. 

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

<td>Le KB 4013633 est une mise à jour X++ ou un correctif de métadonnées qui contient l’espace de travail mobile <strong>Commandes client</strong>. Pour implémenter le KB 4013633, un administrateur système doit procéder comme suit :
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Télécharger le correctif de métadonnées depuis Microsoft Dynamics Lifecycle Services</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Installez le correctif de métadonnées</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Créez un module déployable</a> contenant le modèle <strong>SCMMobile</strong> et téléchargez le module déployable vers LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Appliquer le package déployable</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Publiez l’espace de travail mobile <strong>Commandes client</strong>.</td>
<td>Administrateur système</td>
<td>Voir <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publier un espace de travail mobile</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Télécharger et installer l'application mobile
Télécharger et installer l'application mobile Finance and Operations :

-   [Pour téléphones Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Pour les iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Connexion à l'application mobile

1.  Démarrez l’application sur votre appareil mobile.
2.  Entrez votre URL Dynamics 365.
3.  Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer vos nom d’utilisateur et mot de passe. Entrez vos informations d’identification.
4.  Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s’affichent. Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous devrez actualiser la liste des espaces de travail mobiles.

[![Extraire pour actualiser.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-sales-order-mobile-workspace"></a>Afficher des informations sur les commandes client pour un client à l’aide de l’espace de travail mobile Commandes client

1.  Sur votre appareil mobile, sélectionnez l’espace de travail **Commandes client**.
2.  Sélectionnez **Afficher les commandes pour un client**.
3.  Utilisez les informations de compte ou le nom du client pour trouver le client souhaité.
4.  Sélectionnez le client
5.  Sélectionnez **Informations de contact** ou **Commandes client**. Si vous sélectionnez **Commandes client**, une liste des commandes client du client s’affiche.
6.  Sélectionnez **Commandes client**. Vous pouvez maintenant afficher des informations sur les lignes de commande client, les expéditions, les informations de contact du client et les informations de contact de la personne qui a pris la commande.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]