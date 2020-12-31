---
title: Permuter entre les configurations de fournisseur
description: Cette rubrique décrit comment basculer l’intégration des données fournisseur entre les applications Finance and Operations et Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 731efd3ae841960f3a2c0b9be210c5c68ac835f5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685507"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="90e8f-103">Permuter entre les configurations de fournisseur</span><span class="sxs-lookup"><span data-stu-id="90e8f-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="90e8f-104">Flux de données fournisseur</span><span class="sxs-lookup"><span data-stu-id="90e8f-104">Vendor data flow</span></span> 

<span data-ttu-id="90e8f-105">Si vous choisissez d’utiliser l’entité **Compte** pour stocker les fournisseurs du type **Organisation** et l’entité **Contact** pour stocker les fournisseurs de type **Personne**, configurez les workflows suivants.</span><span class="sxs-lookup"><span data-stu-id="90e8f-105">If you choose to use the **Account** entity to store vendors of the **Organization** type and the **Contact** entity to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="90e8f-106">Sinon, cette configuration n’est pas requise.</span><span class="sxs-lookup"><span data-stu-id="90e8f-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="90e8f-107">Utiliser la conception de fournisseur étendue pour les fournisseurs du type Organisation</span><span class="sxs-lookup"><span data-stu-id="90e8f-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="90e8f-108">Le pack de solution **Dynamics365FinanceExtended** contient les modèles de processus de workflow suivants.</span><span class="sxs-lookup"><span data-stu-id="90e8f-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="90e8f-109">Vous allez créer un workflow pour chaque modèle.</span><span class="sxs-lookup"><span data-stu-id="90e8f-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="90e8f-110">Créer des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="90e8f-110">Create Vendors in Accounts Table</span></span>
+ <span data-ttu-id="90e8f-111">Créer des fournisseurs dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="90e8f-111">Create Vendors in Vendors Table</span></span>
+ <span data-ttu-id="90e8f-112">Mettre à jour des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="90e8f-112">Update Vendors in Accounts Table</span></span>
+ <span data-ttu-id="90e8f-113">Mettre à jour des fournisseurs dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="90e8f-113">Update Vendors in Vendors Table</span></span>

<span data-ttu-id="90e8f-114">Pour créer de nouveaux processus de workflow à l’aide des modèles de processus de workflow, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="90e8f-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="90e8f-115">Créez un processus de workflow pour l’entité **Fournisseur** et sélectionnez **Créer des fournisseurs dans la table Comptes**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-115">Create a workflow process for the **Vendor** entity, and select the **Create Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="90e8f-116">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-116">Then select **OK**.</span></span> <span data-ttu-id="90e8f-117">Ce workflow traite le scénario de création du fournisseur pour l’entité **Compte**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-117">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>

    ![Processus de workflow Créer des fournisseurs dans la table Comptes](media/create_process.png)

2. <span data-ttu-id="90e8f-119">Créez un processus de workflow pour l’entité **Fournisseur** et sélectionnez **Mettre à jour des fournisseurs dans la table Comptes**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-119">Create a workflow process for the **Vendor** entity, and select the **Update Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="90e8f-120">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-120">Then select **OK**.</span></span> <span data-ttu-id="90e8f-121">Ce workflow traite le scénario de mise à jour du fournisseur pour l’entité **Compte**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-121">This workflow handles the vendor update scenario for the **Account** entity.</span></span>
3. <span data-ttu-id="90e8f-122">Créez un processus de workflow pour l’entité **Compte** et sélectionnez **Créer des fournisseurs dans la table Fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-122">Create a workflow process for the **Account** entity, and select the **Create Vendors in Vendors Table** workflow process template.</span></span>
4. <span data-ttu-id="90e8f-123">Créez un processus de workflow pour l’entité **Compte** et sélectionnez **Mettre à jour des fournisseurs dans la table Fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-123">Create a workflow process for the **Account** entity, and select the **Update Vendors in Vendors Table** workflow process template.</span></span>
5. <span data-ttu-id="90e8f-124">Vous pouvez configurer les workflows comme workflows en temps réel ou workflows d’arrière plan selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="90e8f-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="90e8f-125">Pour configurer un workflow en tant que workflow d’arrière-plan, sélectionnez **Convertir en workflow d’arrière-plan**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Bouton Convertir en workflow d’arrière-plan](media/background_workflow.png)

6. <span data-ttu-id="90e8f-127">Activez les workflows que vous avez créés sur les tables **Compte** et **Fournisseur** pour commencer à utiliser l’entité **Compte** pour enregistrer les informations fournisseur de type **Organisation**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-127">Activate the workflows that you created for the **Account** and **Vendor** tables to start to use the **Account** entity to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="90e8f-128">Utiliser la conception de fournisseur étendue pour les fournisseurs du type Personne</span><span class="sxs-lookup"><span data-stu-id="90e8f-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="90e8f-129">Le pack de solution **Dynamics365FinanceExtended** contient les modèles de processus de workflow suivants.</span><span class="sxs-lookup"><span data-stu-id="90e8f-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="90e8f-130">Vous allez créer un workflow pour chaque modèle.</span><span class="sxs-lookup"><span data-stu-id="90e8f-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="90e8f-131">Créer des fournisseurs de type Personne dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="90e8f-131">Create Vendors of type Person in Vendors Table</span></span>
+ <span data-ttu-id="90e8f-132">Créer des fournisseurs de type Personne dans la table Contacts</span><span class="sxs-lookup"><span data-stu-id="90e8f-132">Create Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="90e8f-133">Mettre à jour des fournisseurs de type Personne dans la table Contacts</span><span class="sxs-lookup"><span data-stu-id="90e8f-133">Update Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="90e8f-134">Mettre à jour des fournisseurs de type Personne dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="90e8f-134">Update Vendors of type Person in Vendors Table</span></span>

<span data-ttu-id="90e8f-135">Pour créer de nouveaux processus de workflow à l’aide des modèles de processus de workflow, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="90e8f-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="90e8f-136">Créez un processus de workflow pour l’entité **Fournisseur** et sélectionnez **Créer des fournisseurs de type Personne dans la table Contacts**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-136">Create a workflow process for the **Vendor** entity, and select the **Create Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="90e8f-137">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-137">Then select **OK**.</span></span> <span data-ttu-id="90e8f-138">Ce workflow traite le scénario de création du fournisseur pour l’entité **Contact**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-138">This workflow handles the vendor creation scenario for the **Contact** entity.</span></span>
2. <span data-ttu-id="90e8f-139">Créez un processus de workflow pour l’entité **Fournisseur** et sélectionnez **Mettre à jour des fournisseurs de type Personne dans la table Contacts**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-139">Create a workflow process for the **Vendor** entity, and select the **Update Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="90e8f-140">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-140">Then select **OK**.</span></span> <span data-ttu-id="90e8f-141">Ce workflow traite le scénario de mise à jour du fournisseur pour l’entité **Contact**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-141">This workflow handles the vendor update scenario for the **Contact** entity.</span></span>
3. <span data-ttu-id="90e8f-142">Créez un processus de workflow pour l’entité **Contact** et sélectionnez **Créer des fournisseurs de type Personne dans la table Fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-142">Create a workflow process for the **Contact** entity, and select the **Create Vendors of type Person in Vendors Table** template.</span></span>
4. <span data-ttu-id="90e8f-143">Créez un processus de workflow pour l’entité **Contact** et sélectionnez **Mettre à jour des fournisseurs de type Personne dans la table Fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-143">Create a workflow process for the **Contact** entity, and select the **Update Vendors of type Person in Vendors Table** template.</span></span>
5. <span data-ttu-id="90e8f-144">Vous pouvez configurer les workflows comme workflows en temps réel ou workflows d’arrière plan selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="90e8f-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="90e8f-145">Pour configurer un workflow en tant que workflow d’arrière-plan, sélectionnez **Convertir en workflow d’arrière-plan**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="90e8f-146">Activez les workflows que vous avez créés sur les tables **Contact** et **Fournisseur** pour commencer à utiliser l’entité **Contact** pour enregistrer les informations fournisseur de type **Personne**.</span><span class="sxs-lookup"><span data-stu-id="90e8f-146">Activate the workflows that you created on the **Contact** and **Vendor** tables to start to use the **Contact** entity to store information for vendors of the **Person** type.</span></span>
