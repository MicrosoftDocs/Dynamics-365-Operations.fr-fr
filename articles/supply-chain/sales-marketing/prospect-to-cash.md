---
title: "Prospect en disponibilités"
description: "Cette rubrique fournit une vue d'ensemble de la solution Prospect en disponibilités entre Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition et Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 02/08/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: e342c67f53828c77f77d99a2c3f909a23ced8989
ms.openlocfilehash: 5d9bc41c92258f9856088b04ec5af123c8e915e5
ms.contentlocale: fr-fr
ms.lasthandoff: 03/13/2018

---

# <a name="prospect-to-cash"></a><span data-ttu-id="ead7b-103">Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="ead7b-103">Prospect to cash</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ead7b-104">La solution Prospect en disponibilités fournit une synchronisation directe entre Dynamics 365 for Finance and Operations, Enterprise Edition et Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="ead7b-104">The Prospect to cash solution provides direct synchronization across Dynamics 365 for Finance and Operations, Enterprise edition, and Dynamics 365 for Sales.</span></span> <span data-ttu-id="ead7b-105">Les modèles Prospect en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données pour les comptes, contacts, produits, devis de vente, commandes client et factures client entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="ead7b-105">The Prospect to cash templates that are available with the Data Integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="ead7b-106">Bien que les données transitent entre Finance and Operations et Sales, vous pouvez effectuer des activités de vente et de marketing dans Sales, et vous pouvez gérer l'exécution de commande à l'aide de la gestion des stocks de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ead7b-106">While data is flowing between Finance and Operations and Sales, you can perform sales and marketing activities in Sales, and you can handle order fulfillment by using inventory management in Finance and Operations.</span></span> 

<span data-ttu-id="ead7b-107">Pour plus d'informations sur l'intégration de la solution Prospect en disponibilités, consultez la courte vidéo YouTube :</span><span class="sxs-lookup"><span data-stu-id="ead7b-107">For more information about the Prospect to cash integration, watch the short YouTube video:</span></span>

> [!Video https://www.youtube.com/embed/AVV9x5x-XCg]

<span data-ttu-id="ead7b-108">Dans la version actuelle, la solution Prospect en disponibilités fournit les types suivants de synchronisation directe :</span><span class="sxs-lookup"><span data-stu-id="ead7b-108">In the current version, the Prospect to cash solution provides the following types of direct synchronization:</span></span>

- [<span data-ttu-id="ead7b-109">Tenir à jour les comptes dans Sales et les synchroniser directement avec Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ead7b-109">Maintain accounts in Sales and sync them directly from Sales to Finance and Operations</span></span>](accounts-template-mapping-direct.md)
- [<span data-ttu-id="ead7b-110">Tenir à jour des produits dans Finance and Operations et les synchroniser directement avec Sales</span><span class="sxs-lookup"><span data-stu-id="ead7b-110">Maintain products in Finance and Operations and sync them directly to Sales</span></span>](products-template-mapping-direct.md)
- [<span data-ttu-id="ead7b-111">Tenir à jour les contacts dans Sales et les synchroniser directement avec les contacts ou les clients dans Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ead7b-111">Maintain contacts in Sales and sync them directly to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)
- [<span data-ttu-id="ead7b-112">Synchroniser le devis de vente directement à partir de Sales sur Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ead7b-112">Synchronize sales quotation directly from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping-sales-fin.md)
- [<span data-ttu-id="ead7b-113">Synchroniser les commandes client directement entre Sales et Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ead7b-113">Synchronize sales orders directly between Sales and Finance and Operations</span></span>](sales-order-template-mapping-direct-two-ways.md)
- [<span data-ttu-id="ead7b-114">Synchroniser les factures client directement à partir de Finance and Operations avec Sales</span><span class="sxs-lookup"><span data-stu-id="ead7b-114">Synchronize sales invoice directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="ead7b-115">Configuration requise pour Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ead7b-115">System requirements for Finance and Operations</span></span>

<span data-ttu-id="ead7b-116">L'intégration de la solution Prospect en disponibilités est prise en charge dans les versions suivantes :</span><span class="sxs-lookup"><span data-stu-id="ead7b-116">Prospect to cash integration is supported on the following versions:</span></span>

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a><span data-ttu-id="ead7b-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 (décembre 2017)</span><span class="sxs-lookup"><span data-stu-id="ead7b-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 (December 2017)</span></span>

- <span data-ttu-id="ead7b-118">Dynamics 365 for Finance and Operations, Enterprise Edition (décembre 2017) - Version d'application 7.3.11971.56116 avec mise à jour 12 de la plateforme (7.0.4709.41129)</span><span class="sxs-lookup"><span data-stu-id="ead7b-118">Dynamics 365 for Finance and Operations, Enterprise edition (December 2017) - Application build 7.3.11971.56116 with Platform Update 12 (7.0.4709.41129)</span></span>

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a><span data-ttu-id="ead7b-119">Dynamics 365 for Finance and Operations, Enterprise Edition (juillet 2017)</span><span class="sxs-lookup"><span data-stu-id="ead7b-119">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017)</span></span>

- <span data-ttu-id="ead7b-120">Dynamics 365 for Finance and Operations, Enterprise Edition (juillet 2017) avec mise à jour 8 de la plateforme (version d'application 7.2.11792.56024 avec version de plateforme 7.0.4565.16212).</span><span class="sxs-lookup"><span data-stu-id="ead7b-120">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) - with platform update 8 (application build 7.2.11792.56024 with platform build 7.0.4565.16212).</span></span>
- <span data-ttu-id="ead7b-121">Les correctifs suivants sont requis :</span><span class="sxs-lookup"><span data-stu-id="ead7b-121">The following hotfixes are required:</span></span>

    - <span data-ttu-id="ead7b-122">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Ce correctif permet la synchronisation des commandes client entre Sales et Finance and Operations via la fonctionnalité d'intégration de données.</span><span class="sxs-lookup"><span data-stu-id="ead7b-122">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – This hotfix enables sales order synchronization from Sales to Finance and Operations via the Data Integration feature.</span></span> <span data-ttu-id="ead7b-123">Il fournit également plusieurs autres améliorations.</span><span class="sxs-lookup"><span data-stu-id="ead7b-123">It also provides several other enhancements.</span></span>
    - <span data-ttu-id="ead7b-124">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ce correctif permet la synchronisation des lignes de commande client entre Finance and Operations et Sales via la fonctionnalité d'intégration de données.</span><span class="sxs-lookup"><span data-stu-id="ead7b-124">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order line synchronization from Finance and Operations to Sales via the Data Integration feature.</span></span>
    - <span data-ttu-id="ead7b-125">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ce correctif permet la synchronisation des commandes client entre Finance and Operations et Sales via la fonctionnalité d'intégration de données.</span><span class="sxs-lookup"><span data-stu-id="ead7b-125">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order synchronization from Finance and Operations to Sales via the Data Integration feature.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ead7b-126">Vous devez uniquement installer KB4045570 car l'installation inclut les modifications issues des autres correctifs.</span><span class="sxs-lookup"><span data-stu-id="ead7b-126">You only have to install KB4045570 because the installation includes the changes from other hotfixes.</span></span> 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a><span data-ttu-id="ead7b-127">Dynamics 365 for Finance and Operations, version 1611 (novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="ead7b-127">Dynamics 365 for Finance and Operations version 1611 (November 2016)</span></span>

- <span data-ttu-id="ead7b-128">Dynamics 365 for Finance and Operations, version 1611 (novembre 2016) avec mise à jour 8 ou plus de la plateforme</span><span class="sxs-lookup"><span data-stu-id="ead7b-128">Dynamics 365 for Finance and Operations version 1611 (November 2016)  with platform update 8 or higher</span></span>

- <span data-ttu-id="ead7b-129">Les correctifs suivants sont requis :</span><span class="sxs-lookup"><span data-stu-id="ead7b-129">The following hotfixes are required:</span></span>

    - <span data-ttu-id="ead7b-130">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Permet la synchronisation des commandes client avec l'intégrateur de données entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="ead7b-130">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Enable sales order synchronization with Data integrator from Finance and Operations to Sales.</span></span> 
    - <span data-ttu-id="ead7b-131">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Permet la synchronisation des en-têtes et lignes de commande client avec l'intégrateur de données entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="ead7b-131">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Enable sales order header and line synchronization with Data integrator from Finance and Operations to Sales.</span></span>
    - <span data-ttu-id="ead7b-132">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - La prise en charge de l'intégration de la solution Prospect en disponibilités via les entités de données est requise.</span><span class="sxs-lookup"><span data-stu-id="ead7b-132">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Support for prospect to cash integration through data entities is required.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ead7b-133">Après avoir installé les correctifs, vous devez déclencher le traitement par lots suivant à partir de l'écran **SalesPopulateProspectToCash**.</span><span class="sxs-lookup"><span data-stu-id="ead7b-133">After you install the hotfixes, you must trigger the following batch job from the **SalesPopulateProspectToCash** form.</span></span> <span data-ttu-id="ead7b-134">Cet écran est masqué, car vous n'en avez besoin qu'une seule fois.</span><span class="sxs-lookup"><span data-stu-id="ead7b-134">This form is hidden because you only need it once.</span></span> <span data-ttu-id="ead7b-135">Pour accéder à l'écran, connectez-vous à l'environnement et ajoutez ce qui suit à l'URL dans le champ d'adresse du navigateur, &mi=action:SalesPopulateProspectToCash, par exemple, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`.</span><span class="sxs-lookup"><span data-stu-id="ead7b-135">To access the form, log in to the environment and add the following to the URL in your browser address: &mi=action:SalesPopulateProspectToCash, for example, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`.</span></span> <span data-ttu-id="ead7b-136">Lorsque l'écran s'ouvre, cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ead7b-136">When the form opens, click OK.</span></span> <span data-ttu-id="ead7b-137">Un nouveau champ **LineCreationSequnceNumber** dans les tables **SalesLine**, **SalesQuotationLine** et **CustInvoiceTrans** est renseigné avec des valeurs uniques et la liste des produits est actualisée.</span><span class="sxs-lookup"><span data-stu-id="ead7b-137">This will populate a new **LineCreationSequnceNumber** field in the **SalesLine**, **SalesQuotationLine**, and **CustInvoiceTrans** tables with unique values, and the product list will be refreshed.</span></span> <span data-ttu-id="ead7b-138">Cela est nécessaire pour assurer l'intégration de la solution Prospect en disponibilités.</span><span class="sxs-lookup"><span data-stu-id="ead7b-138">This is required for the Prospect to cash integration to work.</span></span>


## <a name="system-requirements-for-sales"></a><span data-ttu-id="ead7b-139">Configuration requise pour Sales</span><span class="sxs-lookup"><span data-stu-id="ead7b-139">System requirements for Sales</span></span>

<span data-ttu-id="ead7b-140">Pour utiliser la solution Prospect en disponibilités, vous devez installer les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="ead7b-140">To use the Prospect to cash solution, you must install the following components:</span></span>

- <span data-ttu-id="ead7b-141">Dynamics 365 pour la version de Sales 1612 (8.2.1.207) (DB 8.2.1.207) en ligne ou ultérieure</span><span class="sxs-lookup"><span data-stu-id="ead7b-141">Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online or a later version</span></span>
- <span data-ttu-id="ead7b-142">Solution Prospect en disponibilités pour Dynamics 365 for Sales, version 1.15.0.0 (v15).</span><span class="sxs-lookup"><span data-stu-id="ead7b-142">Prospect to cash solution for Dynamics 365 for Sales, version 1.15.0.0 (v15)</span></span> 

### <a name="install-the-prospect-to-cash-solution-for-sales"></a><span data-ttu-id="ead7b-143">Installer le Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="ead7b-143">Install the Prospect to cash solution for Sales</span></span>

1. <span data-ttu-id="ead7b-144">Téléchargez le [fichier zip du package de la solution Prospect en disponibilités pour Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) à partir de CustomerSource.</span><span class="sxs-lookup"><span data-stu-id="ead7b-144">Download the [Prospect to cash for Dynamics 365 for Sales solution package zip file](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) from CustomerSource.</span></span>
2. <span data-ttu-id="ead7b-145">Vérifiez que le fichier zip est débloqué.</span><span class="sxs-lookup"><span data-stu-id="ead7b-145">Make sure that the zip file is unblocked.</span></span> <span data-ttu-id="ead7b-146">Sinon, lorsque vous tentez d'installer le package de solution, vous pouvez recevoir le message d'erreur suivant : « Aucun package d'importation n'a été trouvé ».</span><span class="sxs-lookup"><span data-stu-id="ead7b-146">Otherwise, when you try to install the solution package, you may receive the following error message, "No import packages were found."</span></span> <span data-ttu-id="ead7b-147">Pour débloquer le fichier zip, cliquez dessus avec le bouton droit, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ead7b-147">To unblock the zip file, right-click it, and select **Properties**.</span></span> <span data-ttu-id="ead7b-148">Sélectionnez **Débloquer**.</span><span class="sxs-lookup"><span data-stu-id="ead7b-148">Select **Unblock**.</span></span>
3. <span data-ttu-id="ead7b-149">Décompressez et exécutez **PackageDeployer.exe**.</span><span class="sxs-lookup"><span data-stu-id="ead7b-149">Unzip and run **PackageDeployer.exe**.</span></span>
4. <span data-ttu-id="ead7b-150">Installez la solution Prospect en disponibilités dans votre instance de Sales :</span><span class="sxs-lookup"><span data-stu-id="ead7b-150">Install the Prospect to cash solution on your Sales instance:</span></span>

    1. <span data-ttu-id="ead7b-151">Sélectionnez **Office 365** comme type de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ead7b-151">Select **Office 365** as the deployment type.</span></span>
    2. <span data-ttu-id="ead7b-152">Sélectionnez **Show advanced**.</span><span class="sxs-lookup"><span data-stu-id="ead7b-152">Select **Show advanced**.</span></span>
    3. <span data-ttu-id="ead7b-153">Pour une installation rapide, sélectionnez une région.</span><span class="sxs-lookup"><span data-stu-id="ead7b-153">For a quick installation, select a region.</span></span> <span data-ttu-id="ead7b-154">Si vous sélectionnez **Don't know**, le système recherchera toutes les régions et le temps d'installation sera plus long.</span><span class="sxs-lookup"><span data-stu-id="ead7b-154">If you select **Don't know**, the system searches for all regions, and the installation will take more time.</span></span>
    4. <span data-ttu-id="ead7b-155">Entrez le nom d'utilisateur et le mot de passe d'un utilisateur administrateur disposant de droits d'installation.</span><span class="sxs-lookup"><span data-stu-id="ead7b-155">Enter the user name and password of an admin user who has installation rights.</span></span>



