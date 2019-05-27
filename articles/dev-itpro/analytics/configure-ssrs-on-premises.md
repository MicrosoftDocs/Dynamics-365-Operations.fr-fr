---
title: Configurer SQL Server Reporting Services pour des déploiements sur site
description: Cette rubrique fournit des informations sur la configuration de SQL Server Reporting Services (SSRS) pour un déploiement sur site.
author: sarvanisathish
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
ms.author: sarvanis
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: 166d419f16866f699b96013222ce8da147a5ec21
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548717"
---
# <a name="configure-sql-server-reporting-services-for-on-premises-deployments"></a><span data-ttu-id="f9130-103">Configurer SQL Server Reporting Services pour des déploiements sur site</span><span class="sxs-lookup"><span data-stu-id="f9130-103">Configure SQL Server Reporting Services for on-premises deployments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f9130-104">Procédez comme indiqué dans cette rubrique pour Configurer SQL Server Reporting Services pour un déploiement sur site de Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f9130-104">Use the steps in this topic to configure SQL Server Reporting Services (SSRS) for your Microsoft Dynamics 365 for Finance and Operations (on-premises) deployment.</span></span>

1. <span data-ttu-id="f9130-105">Ouvrez l'application Gestionnaire de configuration de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="f9130-105">Open the Reporting Services Configuration Manager application.</span></span>
2. <span data-ttu-id="f9130-106">Laissez la valeur par défaut de **Nom de serveur**, qui doit être le nom de la machine actuelle, et **Instance de serveur d'états**, **MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="f9130-106">Leave the default **Server name**, which should be the name of the current machine, and the **Report Server Instance**, **MSSQLSERVER**.</span></span>
3. <span data-ttu-id="f9130-107">Cliquez sur **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="f9130-107">Click **Connect**.</span></span>

    <span data-ttu-id="f9130-108">[![Connexion de la configuration Reporting Services](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span><span class="sxs-lookup"><span data-stu-id="f9130-108">[![Reporting services configuration connection](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span></span>

4. <span data-ttu-id="f9130-109">Cliquez sur l'onglet **Compte de service** et vérifiez que les paramètres correspondent au graphique suivant.</span><span class="sxs-lookup"><span data-stu-id="f9130-109">Click the **Service Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="f9130-110">[![Onglet Compte de service](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span><span class="sxs-lookup"><span data-stu-id="f9130-110">[![Service account tab](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span></span>

5. <span data-ttu-id="f9130-111">Cliquez sur l'onglet **URL de service Web** et vérifiez que les paramètres correspondent au graphique suivant.</span><span class="sxs-lookup"><span data-stu-id="f9130-111">Click the **Web Service URL** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="f9130-112">[![Onglet URL de service Web](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span><span class="sxs-lookup"><span data-stu-id="f9130-112">[![Web service URL tab](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span></span>

6. <span data-ttu-id="f9130-113">Cliquez sur l'onglet **Base de donnés** et vérifiez que **Nom de la base de données** et **Paramètres des informations d'identification** correspondent au graphique suivant.</span><span class="sxs-lookup"><span data-stu-id="f9130-113">Click the **Database** tab and verify that the **Database Name** and **Credential settings** match the following graphic.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f9130-114">Vous devez créer une base de données.</span><span class="sxs-lookup"><span data-stu-id="f9130-114">You will need to create a new database.</span></span> <span data-ttu-id="f9130-115">Pour ce faire, cliquez sur **Modifier la base de données**, puis vérifiez que le nom de la nouvelle base de données est : **DynamicsAxReportServer**.</span><span class="sxs-lookup"><span data-stu-id="f9130-115">To do this, click **Change Database**, and then verify that the new database name is: **DynamicsAxReportServer**.</span></span>

    <span data-ttu-id="f9130-116">[![Onglet Base de données](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span><span class="sxs-lookup"><span data-stu-id="f9130-116">[![database tab](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span></span>

7. <span data-ttu-id="f9130-117">Cliquez sur l'onglet **URL du portail Web** et vérifiez que les paramètres correspondent au graphique suivant.</span><span class="sxs-lookup"><span data-stu-id="f9130-117">Click the **Web Portal URL** tab and verify that the settings match the following graphic.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f9130-118">Vous devez cliquer sur **Appliquer** pour créer et configurer correctement le portail.</span><span class="sxs-lookup"><span data-stu-id="f9130-118">You must click **Apply** to create and properly configure the Portal.</span></span>

    <span data-ttu-id="f9130-119">[![Onglet URL du portail Web](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span><span class="sxs-lookup"><span data-stu-id="f9130-119">[![web portal url tab](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span></span>

    <span data-ttu-id="f9130-120">Une fois le portail configuré, l'onglet **Portail Web** correspondra au graphique suivant.</span><span class="sxs-lookup"><span data-stu-id="f9130-120">After the Portal is configured, the **Web Portal** tab will match the following graphic.</span></span>

    <span data-ttu-id="f9130-121">[![Onglet Portail Web](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span><span class="sxs-lookup"><span data-stu-id="f9130-121">[![web portal tab](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span></span>

8. <span data-ttu-id="f9130-122">Cliquez sur l'URL des états pour afficher le portail Web SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="f9130-122">Click the reports URL to view the SQL Server Reporting Services web portal.</span></span>
9. <span data-ttu-id="f9130-123">Lorsque vous êtes dans le portail, créez un dossier nommé **Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="f9130-123">When you are in the portal, create a new folder named **Dynamics**.</span></span>

    <span data-ttu-id="f9130-124">[![Dossier Dynamics](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span><span class="sxs-lookup"><span data-stu-id="f9130-124">[![dynamics folder](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span></span>

10. <span data-ttu-id="f9130-125">Dans **Gestionnaire de configuration Reporting Services**, cliquez sur l'onglet **Paramètres d'e-mail** et vérifiez que les paramètres correspondent au graphique suivant.</span><span class="sxs-lookup"><span data-stu-id="f9130-125">In the **Reporting Services Configuration Manager**, click the **E-mail Settings** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="f9130-126">[![Onglet Paramètres d'e-mail](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span><span class="sxs-lookup"><span data-stu-id="f9130-126">[![email settings tab](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span></span>

11. <span data-ttu-id="f9130-127">Cliquez sur l'onglet **Compte d'exécution** et vérifiez que les paramètres correspondent au graphique suivant.</span><span class="sxs-lookup"><span data-stu-id="f9130-127">Click the **Execution Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="f9130-128">[![Onglet Compte d'exécution](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span><span class="sxs-lookup"><span data-stu-id="f9130-128">[![execution account tab](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span></span>

    <span data-ttu-id="f9130-129">Ne modifiez pas les paramètres par défaut de l'onglet **Clés de chiffrement**.</span><span class="sxs-lookup"><span data-stu-id="f9130-129">Don't change the default settings on the **Encryption Keys** tab.</span></span>

    <span data-ttu-id="f9130-130">[![Onglet Clés de chiffrement](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span><span class="sxs-lookup"><span data-stu-id="f9130-130">[![encryption keys tab](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span></span>

12. <span data-ttu-id="f9130-131">Cliquez sur l'onglet **Paramètres d'abonnement** et vérifiez que les paramètres correspondent au graphique suivant.</span><span class="sxs-lookup"><span data-stu-id="f9130-131">Click the **Subscription Settings** tab, and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="f9130-132">[![Onglet Paramètres d'abonnement](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span><span class="sxs-lookup"><span data-stu-id="f9130-132">[![subscription settings tab](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span></span>

    <span data-ttu-id="f9130-133">Ne modifiez pas les paramètres par défaut de l'onglet **Déploiement avec montée en puissance parallèle**.</span><span class="sxs-lookup"><span data-stu-id="f9130-133">Don't change the default settings on the **Scale-out Deployment** tab.</span></span>

    <span data-ttu-id="f9130-134">[![Onglet Environnement de déploiement avec montée en puissance parallèle](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span><span class="sxs-lookup"><span data-stu-id="f9130-134">[![scale-out deployment tab](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span></span>

    <span data-ttu-id="f9130-135">Ne modifiez pas les paramètres par défaut de l'onglet **Intégration Power BI**. </span><span class="sxs-lookup"><span data-stu-id="f9130-135">Don't change the default settings on the **Power BI Integration** tab.</span></span>

    <span data-ttu-id="f9130-136">[![Onglet Intégration Power BI](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span><span class="sxs-lookup"><span data-stu-id="f9130-136">[![power bi integration tab](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span></span>

13. <span data-ttu-id="f9130-137">Cliquez sur **Quitter** pour fermer le **Gestionnaire de configuration de Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="f9130-137">Click **Exit** to close the **Reporting Services Configuration Manager**.</span></span>

    <span data-ttu-id="f9130-138">[![Fermer le Gestionnaire de configuration de Reporting Services](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span><span class="sxs-lookup"><span data-stu-id="f9130-138">[![close reporting services configuration manager](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span></span>
