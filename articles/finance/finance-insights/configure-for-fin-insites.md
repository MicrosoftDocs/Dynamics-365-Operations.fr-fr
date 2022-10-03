---
title: Configuration de Finance Insights
description: Cet article explique les étapes de configuration qui permettront à votre système d’utiliser les fonctionnalités disponibles dans Finance Insights.
author: ShivamPandey-msft
ms.date: 09/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 05bf5fe5a5ff86bbf52ed58ee6b1e84c15bf2c1e
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573192"
---
# <a name="configuration-for-finance-insights"></a>Configuration de Finance Insights

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Finance Insights combine les fonctionnalités de Microsoft Dynamics 365 Finance avec Dataverse, Azure et AI Builder pour fournir de puissants outils de prévision à votre organisation. Cet article explique les étapes de configuration qui permettront à votre système d’utiliser les fonctionnalités disponibles dans Finance Insights. Pour mener à bien les procédures de cet article, vous devez disposer d’un accès Administrateur système et Personnalisateur de système dans le [Centre d’administration de Power Portal](https://admin.powerplatform.microsoft.com/), un accès administrateur système à Dynamics 365 Finance, et un accès pour créer des environnements dans Microsoft Dynamics Lifecycle Services (LCS).

> [!NOTE]
> Les procédures suivantes de configuration de Finance Insights sont valables pour les versions de Dynamics 365 Finance, version 10.0.21 et versions ultérieures.

## <a name="deploy-dynamics-365-finance"></a>Déployer Dynamics 365 Finance

Procédez comme suit pour déployer les environnements.

1. Dans LCS, créez ou mettez à jour un environnement Dynamics 365 Finance. L’environnement nécessite la version 10.0.21 ou ultérieure.

    > [!NOTE]
    > L’environnement doit être un environnement haute disponibilité (HA). (Ce type d’environnement est également appelé environnement de niveau 2.) Pour plus d’informations, voir [Planification de l’environnement](/fin-ops-core/fin-ops/imp-lifecycle/environment-planning).

2. Si vous configurez Finance Insights dans un environnement bac à sable, vous devrez peut-être copier les données de production dans cet environnement avant que les prédictions fonctionnent. Le modèle de prédiction utilise plusieurs années de données pour créer les prédictions. Les données de démonstration de Contoso ne contiennent pas suffisamment de données historiques pour entraîner correctement le modèle de prédiction. 

## <a name="configure-your-azure-ad-tenant"></a>Configurer votre client Azure AD

Azure Active Directory (Azure AD) doit être configuré pour pouvoir être utilisé avec les applications Dataverse et Microsoft Power Platform. Cette configuration nécessite que le rôle de **Propriétaire du projet** ou le rôle de **Gestionnaire de l’environnement** soit attribué à l’utilisateur dans le champ **Rôle de sécurité du projet** dans LCS.

Vérifiez que la configuration suivante est bien terminée :

- Vous disposez d’un accès **Administrateur système** et **Personnalisateur de système** dans le centre d’administration Power Portal.
- Une licence Dynamics 365 Finance ou équivalente est appliquée à l’utilisateur qui installe le complément Finance Insights.
- Les applications Azure AD suivantes sont enregistrées dans Azure AD.

    |  Application                             | ID d’application                               |
    |------------------------------------------|--------------------------------------|
    | CDS Microservices ERP Microsoft Dynamics | 703e2651-d3fc-48f5-942c-74274233dba8 |

    Pour vérifier que l’application est enregistrée dans Azure AD, vérifiez la liste **Toutes les applications**. Pour obtenir plus de détails, consultez [Afficher les applications d’entreprise](/azure/active-directory/manage-apps/view-applications-portal).
  
    Si l’application n’est pas enregistrée dans Azure AD, contactez le support.
  
## <a name="configure-dataverse"></a>Configurer Dataverse

Procédez comme suit pour configurer Dataverse pour Finance Insights.

- Dans LCS, ouvrez la page d’environnement et vérifiez que la section **Intégration Power Platform** est déjà configurée.

    - Si Dataverse est déjà configuré, le nom d’environnement Dataverse lié à l’environnement Finance doit être répertorié.
    - Si Dataverse n’est pas encore configuré, sélectionnez **Configurer**. La configuration de l’environnement Dataverse peut prendre jusqu’à une heure. Lorsque la configuration est terminée, le nom de l’environnement Dataverse lié à l’environnement Finance devrait figurer dans la liste.
    - Si cette intégration a été configurée avec un environnement Microsoft Power Platform, contactez votre administrateur pour vous assurer que l’environnement lié n’est pas désactivé.

        Pour plus d’informations, voir [Activation de l’intégration de Power Platform](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md). 

        Pour accéder au site d’administration Microsoft Power Platform, allez sur <https://admin.powerplatform.microsoft.com/environments>.

## <a name="configure-the-finance-insights-add-in"></a>Configurer le complément Finance Insights

Si vous avez déjà installé le complément Finance Insights, désinstallez-le avant de réaliser la procédure suivante.

> [!NOTE]
> Si vous avez déjà installé le complément Data Lake dans LCS, Finance Insights l’utilisera pour enregistrer les données requises pour les prédictions. Si vous n’avez pas encore installé le complément Data Lake dans LCS, le complément Finance Insights créera un lac de données géré pour vous.

Suivez ces étapes pour installer le complément Finance Insights.

1. Connectez-vous à LCS, puis, sous le nom de l’environnement sur le côté droit de la page, sélectionnez **Tous les détails**.
2. Dans la section **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.
3. Sélectionnez le complément **Informations financières**.
4. Acceptez les conditions générales d’utilisation, puis sélectionnez **Installer**.

L’installation du complément peut prendre plusieurs minutes.

## <a name="one-last-thing"></a>Une dernière chose...

Une fois le complément correctement installé, il peut s’écouler jusqu’à une heure avant que vous puissiez activer les fonctionnalités Finance Insights dans l’espace de travail **Gestion des fonctionnalités** de Dynamics 365 Finance. Si vous ne voulez pas attendre aussi longtemps, vous pouvez exécuter manuellement le processus **Vérification du statut d’approvisionnement des informations**. 

1. Dans Dynamics 365 Finance, accédez à **Administration système \> Paramétrage \> Automatisation de processus**.
2. Sur l’onglet **Processus en arrière-plan**, recherchez **Vérification du statut d’approvisionnement d’informations**, et sélectionnez **Modifier**.
3. Définissez le champ **Prochaine exécution** sur 30 minutes avant l’heure actuelle.

   Ce changement devrait forcer le processus **Vérification du statut d’approvisionnement d’informations** à s’exécuter immédiatement.

   Une fois le processus **Vérification du statut d’approvisionnement d’informations** exécuté correctement, vous pouvez activer les fonctionnalités Finance Insights dans l’espace de travail **Gestion des fonctionnalités**.

> [!NOTE]
> Si le processus **Vérification du statut d’approvisionnement d’informations** ne s’exécute pas, accédez à **Administration du système** > **Demandes** > **Tâches par lots**. Dans le champ **Système d’interrogation de l’automatisation des processus**, remplacez la valeur par **Attente** pour lancer le processus. 
> 
## <a name="feedback-and-support"></a>Commentaires et support

Si vous souhaitez fournir des commentaires ou si vous avez besoin d’aide, envoyez un e-mail à [Finance Insights (version préliminaire)](mailto:fiap@microsoft.com).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
