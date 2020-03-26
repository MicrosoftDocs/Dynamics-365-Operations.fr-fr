---
title: Configurer SQL Server Reporting Services pour des déploiements sur site
description: Cette rubrique fournit des informations sur la configuration de SQL Server Reporting Services (SSRS) pour un déploiement sur site.
author: PeterRFriis
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: perahlff
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: e3acd96e686260da3ed67b8ac823be45b8ea870f
ms.sourcegitcommit: 708b3966b1c2bd4999f528d4a03a89d9bb530616
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2020
ms.locfileid: "3100496"
---
# <a name="configure-sql-server-reporting-services-for-on-premises-deployments"></a>Configurer SQL Server Reporting Services pour des déploiements sur site

[!include [banner](../includes/banner.md)]

Procédez comme indiqué dans cette rubrique pour Configurer SQL Server Reporting Services pour un déploiement sur site de Microsoft Dynamics 365 Finance + Operations (on-premises).

1. Ouvrez l'application Gestionnaire de configuration de Reporting Services.
2. Laissez la valeur par défaut de **Nom de serveur**, qui doit être le nom de la machine actuelle, et **Instance de serveur d'états**, **MSSQLSERVER**.
3. Cliquez sur **Connecter**.

    [![Connexion de la configuration Reporting Services](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)

4. Cliquez sur l'onglet **Compte de service** et vérifiez que les paramètres correspondent au graphique suivant.

    [![Onglet Compte de service](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)

5. Cliquez sur l'onglet **URL de service Web** et vérifiez que les paramètres correspondent au graphique suivant.

    [![Onglet URL de service Web](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)

6. Cliquez sur l'onglet **Base de donnés** et vérifiez que **Nom de la base de données** et **Paramètres des informations d'identification** correspondent au graphique suivant.

    > [!NOTE]
    > Vous devez créer une base de données. Pour ce faire, cliquez sur **Modifier la base de données**, puis vérifiez que le nom de la nouvelle base de données est : **DynamicsAxReportServer**.

    [![Onglet Base de données](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)

7. Cliquez sur l'onglet **URL du portail Web** et vérifiez que les paramètres correspondent au graphique suivant.

    > [!NOTE]
    > Vous devez cliquer sur **Appliquer** pour créer et configurer correctement le portail.

    [![Onglet URL du portail Web](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)

    Une fois le portail configuré, l'onglet **Portail Web** correspondra au graphique suivant.

    [![Onglet Portail Web](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)

8. Cliquez sur l'URL des états pour afficher le portail Web SQL Server Reporting Services.
9. Lorsque vous êtes dans le portail, créez un dossier nommé **Dynamics**.

    [![Dossier Dynamics](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)

10. Dans **Gestionnaire de configuration Reporting Services**, cliquez sur l'onglet **Paramètres d'e-mail** et vérifiez que les paramètres correspondent au graphique suivant.

    [![Onglet Paramètres d'e-mail](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)

11. Cliquez sur l'onglet **Compte d'exécution** et vérifiez que les paramètres correspondent au graphique suivant.

    [![Onglet Compte d'exécution](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)

    Ne modifiez pas les paramètres par défaut de l'onglet **Clés de chiffrement**.

    [![Onglet Clés de chiffrement](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)

12. Cliquez sur l'onglet **Paramètres d'abonnement** et vérifiez que les paramètres correspondent au graphique suivant.

    [![Onglet Paramètres d'abonnement](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)

    Ne modifiez pas les paramètres par défaut de l'onglet **Déploiement avec montée en puissance parallèle**.

    [![Onglet Environnement de déploiement avec montée en puissance parallèle](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)

    Ne modifiez pas les paramètres par défaut de l'onglet **Intégration Power BI**. 

    [![Onglet Intégration Power BI](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)

13. Cliquez sur **Quitter** pour fermer le **Gestionnaire de configuration de Reporting Services**.

    [![Fermer le Gestionnaire de configuration de Reporting Services](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)
