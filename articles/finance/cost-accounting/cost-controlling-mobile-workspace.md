---
title: Espace de travail mobile Contrôle des coûts
description: Cette rubrique fournit des informations sur l’espace de travail mobile Contrôle des coûts. Cet espace de travail permet aux responsables de centre de coût d’afficher des informations sur les performances du centre de coût à tout moment et n’importe où.
author: AndersGirke
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMMobileCostObjectOverviewDetailsCurrentPeriod, CAMMobileCostObjectList, CAMMobileCostObjectOverviewDetailsPreviousPeriod, CAMMobileCostObjectOverview, CAMMobileCostObjectOverviewDetailsYearToDate, CAMMobileCostControlWorkspaceConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: cd86fdf640e59885e5e8aea841dc1c1c9604825b0f18d3b741c5a2777f8e9ff8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728791"
---
# <a name="cost-controlling-mobile-workspace"></a>Espace de travail mobile Contrôle des coûts

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur l’espace de travail mobile **Contrôle des coûts**. Cet espace de travail permet aux responsables de centre de coût d’afficher des informations sur les performances du centre de coût à tout moment et n’importe où.

Cet espace de travail mobile est destiné à être utilisé avec l’application mobile Finance and Operations.

## <a name="overview"></a>Vue d’ensemble
L’espace de travail mobile **Contrôle des coûts** fournit une vue instantanée des performances actuelles des centres de coût en comparant les coûts réels aux coûts budgétés. Vous pouvez accéder au statut des éléments de coût individuels.

Par exemple, un employé reçoit une invitation à une conférence internationale, mais l’organisation doit couvrir toutes les dépenses de déplacement. L’employé demande à son responsable s’il peut assister à la conférence. Le responsable ouvre rapidement l’espace de travail **Contrôle des coûts** sur son téléphone portable de voir s’il dispose du budget nécessaire.

### <a name="data-security"></a>Sécurité des données
Les données de l’espace de travail **Contrôle des coûts** sont sécurisées par les informations d’identification de l’utilisateur. Les responsables de centre de coût sont uniquement autorisés à consulter les données de leur propre centre de coût. La sécurité au niveau de l’accès est gérée dans le module **Contrôle de gestion**.

Les contrôleurs de gestion définissent la configuration de l’espace de travail mobile **Contrôle des coûts** dans le module **Contrôle de gestion**. Une fois que l’espace de travail est publié sur l’application mobile, il est disponible dans l’application mobile. Par conséquent, tous les responsables de centre de coût de l’organisation peuvent consultent les données au même format.

### <a name="actions-views-and-links"></a>Actions, vues et liens
L’espace de travail mobile **Contrôle des coûts** fournit les actions, les vues et les liens suivants :

-   **Actions :**

    -   Utilisez **Sélectionner une configuration** pour sélectionner une mise en page.
    -   Utilisez **Sélectionner un objet de coût** pour sélectionner les centres de coût et filtrer les données en fonction.
    
        > [!NOTE]
        > Les centres de coût qui figurent dans la liste dépendent de l’accès qui est accordé dans le module **Contrôle de gestion**.

-   **Vues :** selon la sélection des actions et la configuration du module **Contrôle de gestion**, vous pouvez afficher les informations suivantes dans les cartes :

    -   Comparatif Réel/Budget (période actuelle)
    -   Comparatif Réel/Budget révisé (période actuelle)
    -   Réel/Budget (période précédente)
    -   Réel/Budget révisé (période précédente)
    -   Réel/Budget (année en cours)
    -   Réel/Budget révisé (année en cours)

    Les montants suivants sont affichés dans chaque carte : Réel, Budget, Écart, et Écart en %.

-   **Liens :**

    -   Détails pour la période actuelle
    -   Détails pour la période précédente
    -   Détails pour l’année en cours

    Lorsque vous sélectionnez un lien, une carte est affichée pour chaque élément de coût. Les montants suivants sont affichés sur chaque carte : réel, budget, écart budgétaire, écart budgétaire en %, budget révisé, écart budgétaire révisé et écart budgétaire révisé en %.
    
    [![Carte pour un élément de coût.](./media/Cost-controlling.png)](./media/Cost-controlling.png)

## <a name="prerequisites"></a>Conditions préalables
Les conditions préalables varient, en fonction de la version de Microsoft Dynamics 365 qui a été déployée pour votre organisation.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-finance"></a>Conditions requises si vous utilisez Microsoft Dynamics 365 Finance
Si Finance a été déployé pour votre organisation, l’administrateur système doit publier l’espace de travail mobile **Contrôle des coûts**. Pour obtenir des instructions, voir [Publier un espace de travail mobile](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-version-1611-with-platform-update-3-or-later"></a>Conditions requises si vous utilisez la version 1611 avec Platform Update 3 ou version ultérieure
Si la version 1611 avec Platform Update 3 ou version ultérieure a été déployée pour votre organisation, l’administrateur système doit effectuer les tâches préalables suivantes.

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

<td>Le KB 4013633 est une mise à jour X++ ou un correctif de métadonnées qui contient l’espace de travail mobile <strong>Contrôle des coûts</strong>. Pour implémenter le KB 4013633, un administrateur système doit procéder comme suit :
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Télécharger le correctif de métadonnées depuis Microsoft Dynamics Lifecycle Services</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Installez le correctif de métadonnées</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Créez un module déployable</a> contenant le modèle <strong>SCMMobile</strong> et téléchargez le module déployable vers LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Appliquer le package déployable</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Publiez l’espace de travail mobile <strong>Contrôle des coûts</strong>.</td>
<td>Administrateur système</td>
<td>Voir <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publier un espace de travail mobile</a>.</td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a>Télécharger et installer l’application mobile
Télécharger et installer l’application mobile Finance and Operations :

-   [Pour téléphones Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Pour les iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Connexion à l’application mobile

1.  Démarrez l’application sur votre appareil mobile.
2.  Entrez votre URL Dynamics 365.
3.  Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer vos nom d’utilisateur et mot de passe. Entrez vos informations d’identification.
4.  Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s’affichent. Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous devrez actualiser la liste des espaces de travail mobiles.

[![Extraire pour actualiser.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a>Afficher les performances de votre centre de coût à l’aide de l’espace de travail mobile Contrôle des coûts

1.  Sur votre appareil mobile, sélectionnez l’espace de travail **Contrôle des coûts**.
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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]