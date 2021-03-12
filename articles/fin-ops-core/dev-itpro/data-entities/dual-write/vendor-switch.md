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
ms.openlocfilehash: d2c22123d5f05945b34eb107c5b912852aec387a
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744463"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="b3c88-103">Permuter entre les configurations de fournisseur</span><span class="sxs-lookup"><span data-stu-id="b3c88-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="b3c88-104">Flux de données fournisseur</span><span class="sxs-lookup"><span data-stu-id="b3c88-104">Vendor data flow</span></span> 

<span data-ttu-id="b3c88-105">Si vous choisissez d’utiliser la table **Compte** pour stocker les fournisseurs de type **Organisation** et la table **Contact** pour stocker les fournisseurs de type **Personne**, configurez les workflows suivants.</span><span class="sxs-lookup"><span data-stu-id="b3c88-105">If you choose to use the **Account** table to store vendors of the **Organization** type and the **Contact** table to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="b3c88-106">Sinon, cette configuration n’est pas requise.</span><span class="sxs-lookup"><span data-stu-id="b3c88-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="b3c88-107">Utiliser la conception de fournisseur étendue pour les fournisseurs du type Organisation</span><span class="sxs-lookup"><span data-stu-id="b3c88-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="b3c88-108">Le pack de solution **Dynamics365FinanceExtended** contient les modèles de processus de workflow suivants.</span><span class="sxs-lookup"><span data-stu-id="b3c88-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="b3c88-109">Vous allez créer un workflow pour chaque modèle.</span><span class="sxs-lookup"><span data-stu-id="b3c88-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="b3c88-110">Créer des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="b3c88-110">Create Vendors in Accounts Table</span></span>
+ <span data-ttu-id="b3c88-111">Créer des fournisseurs dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="b3c88-111">Create Vendors in Vendors Table</span></span>
+ <span data-ttu-id="b3c88-112">Mettre à jour des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="b3c88-112">Update Vendors in Accounts Table</span></span>
+ <span data-ttu-id="b3c88-113">Mettre à jour des fournisseurs dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="b3c88-113">Update Vendors in Vendors Table</span></span>

<span data-ttu-id="b3c88-114">Pour créer de nouveaux processus de workflow à l’aide des modèles de processus de workflow, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b3c88-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="b3c88-115">Créez un processus de workflow pour la table **Fournisseur** et sélectionnez le modèle de processus de workflow **Créer des fournisseurs dans la table Comptes**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-115">Create a workflow process for the **Vendor** table, and select the **Create Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="b3c88-116">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-116">Then select **OK**.</span></span> <span data-ttu-id="b3c88-117">Ce workflow traite le scénario de création du fournisseur pour la table **Compte**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-117">This workflow handles the vendor creation scenario for the **Account** table.</span></span>

    ![Processus de workflow Créer des fournisseurs dans la table Comptes](media/create_process.png)

2. <span data-ttu-id="b3c88-119">Créez un processus de workflow pour la table **Fournisseur** et sélectionnez le modèle de processus de workflow **Mettre à jour les fournisseurs dans la table Comptes**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-119">Create a workflow process for the **Vendor** table, and select the **Update Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="b3c88-120">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-120">Then select **OK**.</span></span> <span data-ttu-id="b3c88-121">Ce workflow traite le scénario de mise à jour du fournisseur pour la table **Compte**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-121">This workflow handles the vendor update scenario for the **Account** table.</span></span>
3. <span data-ttu-id="b3c88-122">Créez un processus de workflow pour la table **Compte** et sélectionnez le modèle de processus de workflow **Créer des fournisseurs dans la table Fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-122">Create a workflow process for the **Account** table, and select the **Create Vendors in Vendors Table** workflow process template.</span></span>
4. <span data-ttu-id="b3c88-123">Créez un processus de workflow pour la table **Compte** et sélectionnez le modèle de processus de workflow **Mettre à jour les fournisseurs dans la table Fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-123">Create a workflow process for the **Account** table, and select the **Update Vendors in Vendors Table** workflow process template.</span></span>
5. <span data-ttu-id="b3c88-124">Vous pouvez configurer les workflows comme workflows en temps réel ou workflows d’arrière plan selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="b3c88-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="b3c88-125">Pour configurer un workflow en tant que workflow d’arrière-plan, sélectionnez **Convertir en workflow d’arrière-plan**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Bouton Convertir en workflow d’arrière-plan](media/background_workflow.png)

6. <span data-ttu-id="b3c88-127">Activez les workflows que vous avez créés pour les tables **Compte** et **Fournisseur** pour commencer à utiliser la table **Compte** pour enregistrer les informations fournisseur de type **Organisation**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-127">Activate the workflows that you created for the **Account** and **Vendor** tables to start to use the **Account** table to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="b3c88-128">Utiliser la conception de fournisseur étendue pour les fournisseurs du type Personne</span><span class="sxs-lookup"><span data-stu-id="b3c88-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="b3c88-129">Le pack de solution **Dynamics365FinanceExtended** contient les modèles de processus de workflow suivants.</span><span class="sxs-lookup"><span data-stu-id="b3c88-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="b3c88-130">Vous allez créer un workflow pour chaque modèle.</span><span class="sxs-lookup"><span data-stu-id="b3c88-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="b3c88-131">Créer des fournisseurs de type Personne dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="b3c88-131">Create Vendors of type Person in Vendors Table</span></span>
+ <span data-ttu-id="b3c88-132">Créer des fournisseurs de type Personne dans la table Contacts</span><span class="sxs-lookup"><span data-stu-id="b3c88-132">Create Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="b3c88-133">Mettre à jour des fournisseurs de type Personne dans la table Contacts</span><span class="sxs-lookup"><span data-stu-id="b3c88-133">Update Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="b3c88-134">Mettre à jour des fournisseurs de type Personne dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="b3c88-134">Update Vendors of type Person in Vendors Table</span></span>

<span data-ttu-id="b3c88-135">Pour créer de nouveaux processus de workflow à l’aide des modèles de processus de workflow, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b3c88-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="b3c88-136">Créez un processus de workflow pour la table **Fournisseur** et sélectionnez le modèle de processus de workflow **Créer des fournisseurs de type Personne dans la table Contacts**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-136">Create a workflow process for the **Vendor** table, and select the **Create Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="b3c88-137">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-137">Then select **OK**.</span></span> <span data-ttu-id="b3c88-138">Ce workflow traite le scénario de création du fournisseur pour la table **Contact**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-138">This workflow handles the vendor creation scenario for the **Contact** table.</span></span>
2. <span data-ttu-id="b3c88-139">Créez un processus de workflow pour la table **Fournisseur** et sélectionnez le modèle de processus de workflow **Mettre à jour les fournisseurs de type Personne dans la table Contacts**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-139">Create a workflow process for the **Vendor** table, and select the **Update Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="b3c88-140">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-140">Then select **OK**.</span></span> <span data-ttu-id="b3c88-141">Ce workflow traite le scénario de mise à jour du fournisseur pour la table **Contact**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-141">This workflow handles the vendor update scenario for the **Contact** table.</span></span>
3. <span data-ttu-id="b3c88-142">Créez un processus de workflow pour la table **Contact** et sélectionnez le modèle **Créer des fournisseurs de type Personne dans la table Fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-142">Create a workflow process for the **Contact** table, and select the **Create Vendors of type Person in Vendors Table** template.</span></span>
4. <span data-ttu-id="b3c88-143">Créez un processus de workflow pour la table **Contact** et sélectionnez le modèle **Mettre à jour les fournisseurs de type Personne dans la table Fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-143">Create a workflow process for the **Contact** table, and select the **Update Vendors of type Person in Vendors Table** template.</span></span>
5. <span data-ttu-id="b3c88-144">Vous pouvez configurer les workflows comme workflows en temps réel ou workflows d’arrière plan selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="b3c88-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="b3c88-145">Pour configurer un workflow en tant que workflow d’arrière-plan, sélectionnez **Convertir en workflow d’arrière-plan**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="b3c88-146">Activez les workflows que vous avez créés pour les tables **Contact** et **Fournisseur** pour commencer à utiliser la table **Contact** pour enregistrer les informations fournisseur de type **Personne**.</span><span class="sxs-lookup"><span data-stu-id="b3c88-146">Activate the workflows that you created on the **Contact** and **Vendor** tables to start to use the **Contact** table to store information for vendors of the **Person** type.</span></span>
