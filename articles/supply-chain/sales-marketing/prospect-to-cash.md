---
title: "Prospect en disponibilités"
description: "La rubrique fournit une vue d'ensemble de la solution de prospect en disponibilités entre Dynamics 365 for Finance and Operations, Enterprise edition et Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: a5f1ecd5f8b46287839439a963e571531ae161a7
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="prospect-to-cash"></a><span data-ttu-id="e9d6f-103">Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="e9d6f-103">Prospect to cash</span></span>  

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e9d6f-104">La solution de prospect en disponibilités utilise l'[Intégration de données](/common-data-service/entity-reference/dynamics-365-integration) pour synchroniser les données entre les instances de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition et Dynamics 365 for Sales via Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-104">The Prospect to cash solution uses [Data Integration](/common-data-service/entity-reference/dynamics-365-integration) to synchronize data across Microsoft Dynamics 365 for Finance and Operations, Enterprise edition and Dynamics 365 for Sales instances via the Common Data Service (CDS).</span></span> <span data-ttu-id="e9d6f-105">Les modèles de prospects en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis client, commandes client et factures client entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-105">The Prospect to cash templates available with the Data Integration feature enable the flow of accounts, contacts, products, sales quotes, sales orders, and sales invoices data between Finance and Operations and Sales.</span></span> <span data-ttu-id="e9d6f-106">Bien que les données transitent entre Finance and Operations et Sales, vous pouvez effectuer des ventes et des activités marketing dans Sales et gérer l'exécution de commande avec la gestion des stocks de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-106">While the data is flowing between Finance and Operations and Sales, you can carry out sales and marketing activities in Sales and handle the order fulfillment with inventory management in Finance and Operations.</span></span> 

<span data-ttu-id="e9d6f-107">Cette solution fournit l'intégration dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="e9d6f-107">This solution provides integration in the following areas:</span></span> 

-   [<span data-ttu-id="e9d6f-108">Tenir à jour les comptes dans Sales et les synchroniser avec Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e9d6f-108">Maintain accounts in Sales and sync them to Finance and Operations</span></span>](accounts-template-mapping.md)
-   [<span data-ttu-id="e9d6f-109">Tenir à jour les contacts dans Sales et les synchroniser avec Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e9d6f-109">Maintain contacts in Sales and sync them to Finance and Operations</span></span>](contacts-template-mapping.md)
-   [<span data-ttu-id="e9d6f-110">Tenir à jour des produits dans Finance and Operations et les synchroniser avec Sales</span><span class="sxs-lookup"><span data-stu-id="e9d6f-110">Maintain products in Finance and Operations and sync them to Sales</span></span>](products-template-mapping.md)
-   [<span data-ttu-id="e9d6f-111">Créer des devis dans Sales et les synchroniser avec Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e9d6f-111">Create sales quotes in Sales and sync them to Finance and Operations</span></span>](sales-quotation-template-mapping.md)
-   [<span data-ttu-id="e9d6f-112">Créer des commandes client dans Finance and Operations et les synchroniser avec Sales</span><span class="sxs-lookup"><span data-stu-id="e9d6f-112">Create sales orders in Finance and Operations and sync them to Sales</span></span>](sales-order-template-mapping.md)
-   [<span data-ttu-id="e9d6f-113">Créer des factures client dans Finance and Operations et les synchroniser avec Sales</span><span class="sxs-lookup"><span data-stu-id="e9d6f-113">Create sales invoices in Finance and Operations and sync them to Sales</span></span>](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-dynamics-365-for-finance-and-operations-enterprise-edition"></a><span data-ttu-id="e9d6f-114">Configuration système pour Dynamics 365 for Finance and Operations, Enterprise edition</span><span class="sxs-lookup"><span data-stu-id="e9d6f-114">System requirements for Dynamics 365 for Finance and Operations, Enterprise edition</span></span>

<span data-ttu-id="e9d6f-115">Pour utiliser le prospect pour une solution de disponibilités, vous devez installer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e9d6f-115">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="e9d6f-116">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Juillet 2017) avec Mise à jour 8 de la plateforme (App 7.2.11792.56024 w/ Platform 7.0.4565.16212)</span><span class="sxs-lookup"><span data-stu-id="e9d6f-116">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) with Platform update 8 (App 7.2.11792.56024 w/ Platform 7.0.4565.16212)</span></span>

- <span data-ttu-id="e9d6f-117">Deux correctifs pour Dynamics 365 for Finance and Operations, Enterprise edition (juillet 2017).</span><span class="sxs-lookup"><span data-stu-id="e9d6f-117">Two hotfixes for Dynamics 365 for Finance and Operations, Enterprise edition (July 2017).</span></span>

    -  <span data-ttu-id="e9d6f-118">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Ce correctif permet la synchronisation des lignes de commande client avec la fonctionnalité d'intégration de données de Finance and Operations avec Sales.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-118">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order line synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>
        
    -  <span data-ttu-id="e9d6f-119">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Ce correctif permet la synchronisation des commandes client avec la fonctionnalité d'intégration de données de Finance and Operations avec Sales.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-119">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>
    
<span data-ttu-id="e9d6f-120">**Remarque** : Vous devez uniquement installer KB4036524 car l'installation inclut les modifications issues de KB4036461.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-120">**Note**: You only need to install KB4036524 because the installation includes the changes from KB4036461.</span></span>
 
## <a name="system-requirements-for-dynamics-365-for-sales"></a><span data-ttu-id="e9d6f-121">Configuration requise pour Dynamics 365 pour Sales</span><span class="sxs-lookup"><span data-stu-id="e9d6f-121">System requirements for Dynamics 365 for Sales</span></span>

<span data-ttu-id="e9d6f-122">Pour utiliser le prospect pour une solution de disponibilités, vous devez installer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e9d6f-122">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="e9d6f-123">Dynamics 365 pour la version de Sales 1612 (8.2.1.207) (DB 8.2.1.207) en ligne ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-123">Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online or later.</span></span>
- <span data-ttu-id="e9d6f-124">Prospect pour une solution de disponibilités pour Dynamics 365 for Sales, version 1.14.0.0 (v14) or ultérieure.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-124">Prospect to cash solution for Dynamics 365 for Sales, version 1.14.0.0 (v14) or later.</span></span>

### <a name="install-the-prospect-to-cash-solution-for-sales"></a><span data-ttu-id="e9d6f-125">Installer le Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="e9d6f-125">Install the Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="e9d6f-126">Téléchargez [le fichier zip du package de solution Prospect pour une solution de disponibilités pour Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) depuis le CustomerSource.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-126">Download the [Prospect to cash for Dynamics 365 for Sales solution package zip file](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) on CustomerSource.</span></span>

- <span data-ttu-id="e9d6f-127">Assurez-vous que le fichier zip est débloqué de sorte que vous n'obteniez pas le message d'erreur « No import packages were found » lorsque vous installez le package de solution.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-127">Make sure that the zip file is unblocked so that you do not get the error message "No import packages were found" when you install the solution package.</span></span> <span data-ttu-id="e9d6f-128">Pour débloquer le fichier, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e9d6f-128">To unblock the file, do the following:</span></span>

    -  <span data-ttu-id="e9d6f-129">Cliquez avec le bouton droit sur le fichier zip.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-129">Right-click the zip file.</span></span>
    -  <span data-ttu-id="e9d6f-130">Sélectionnez **Properties**, puis sélectionnez **Unblock**.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-130">Select **Properties** and then select **Unblock**.</span></span> 

- <span data-ttu-id="e9d6f-131">Décompressez et exécutez PackageDeployer.exe.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-131">Unzip and run PackageDeployer.exe.</span></span>

- <span data-ttu-id="e9d6f-132">Installez le Prospect pour une solution de disponibilités dans votre instance de Sales.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-132">Install the Prospect to Cash solution in your Sales instance.</span></span>

    - <span data-ttu-id="e9d6f-133">Sélectionnez le type de déploiement **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-133">Select the **Office 365** Deployment type.</span></span>
    - <span data-ttu-id="e9d6f-134">Sélectionnez **Show advanced**.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-134">Select **Show advanced**.</span></span>
    - <span data-ttu-id="e9d6f-135">Pour une installation rapide, sélectionnez **Region**.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-135">For a quick installation, select a **Region**.</span></span> <span data-ttu-id="e9d6f-136">Si vous sélectionnez **Don’t know**, le système recherchera toutes les régions et le temps d'installation sera plus long.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-136">If you select **Don’t know**, the system searches for all regions and it will take longer to install.</span></span>
    - <span data-ttu-id="e9d6f-137">Entrez un **Nom d'utilisateur** et un **Mot de passe** d'utilisateur Admin disposant des droits d'utilisateur nécessaires pour effectuer l'installation.</span><span class="sxs-lookup"><span data-stu-id="e9d6f-137">Enter **User name** and **Password** for an admin user who has the user rights to install.</span></span>

