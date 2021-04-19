---
title: Configuration en double écriture depuis Lifecycle Services
description: Cette rubrique explique comment configurer une connexion de double écriture à partir de Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
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
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: e51b4ef1e309e5f89dc82a3776b88c505dc6593d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748539"
---
# <a name="dual-write-setup-from-lifecycle-services"></a><span data-ttu-id="07a06-103">Configuration en double écriture depuis Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="07a06-103">Dual-write setup from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="07a06-104">Cette rubrique explique comment configurer une connexion en double écriture entre un nouvel environnement Finance and Operations et un nouvel environnement Dataverse de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="07a06-104">This topic explains how to set up a dual-write connection between a new Finance and Operations environment and a new Dataverse environment from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="07a06-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="07a06-105">Prerequisites</span></span>

<span data-ttu-id="07a06-106">Vous devez être administrateur pour configurer une connexion en double écriture.</span><span class="sxs-lookup"><span data-stu-id="07a06-106">You must be an admin to set up a dual-write connection.</span></span>

+ <span data-ttu-id="07a06-107">Vous devez avoir accès au client.</span><span class="sxs-lookup"><span data-stu-id="07a06-107">You must have access to the tenant.</span></span>
+ <span data-ttu-id="07a06-108">Vous devez être administrateur dans les deux environnements Finance and Operations et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="07a06-108">You must be an admin in both Finance and Operations environments and Dataverse environments.</span></span>

## <a name="set-up-a-dual-write-connection"></a><span data-ttu-id="07a06-109">Configurer une connexion en double écriture</span><span class="sxs-lookup"><span data-stu-id="07a06-109">Set up a dual-write connection</span></span>

<span data-ttu-id="07a06-110">Procédez comme suit pour configurer la connexion en double écriture.</span><span class="sxs-lookup"><span data-stu-id="07a06-110">Follow these steps to set up the dual-write connection.</span></span>

1. <span data-ttu-id="07a06-111">Dans LCS, accédez à votre projet.</span><span class="sxs-lookup"><span data-stu-id="07a06-111">In LCS, go to your project.</span></span>
2. <span data-ttu-id="07a06-112">Sélectionnez **Configurer** pour déployer un nouvel environnement.</span><span class="sxs-lookup"><span data-stu-id="07a06-112">Select **Configure** to deploy a new environment.</span></span>
3. <span data-ttu-id="07a06-113">Sélectionnez la version.</span><span class="sxs-lookup"><span data-stu-id="07a06-113">Select the version.</span></span> 
4. <span data-ttu-id="07a06-114">Sélectionnez la topologie.</span><span class="sxs-lookup"><span data-stu-id="07a06-114">Select the topology.</span></span> <span data-ttu-id="07a06-115">Si une seule topologie est disponible, elle est automatiquement sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="07a06-115">If only one topology is available, it's automatically selected.</span></span>
5. <span data-ttu-id="07a06-116">Suivez les premières étapes de l’assistant **Paramètres de déploiement**.</span><span class="sxs-lookup"><span data-stu-id="07a06-116">Complete the first steps in the **Deployment settings** wizard.</span></span>
6. <span data-ttu-id="07a06-117">Sur l’onglet **Dataverse**, suivez une des étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="07a06-117">On the **Dataverse** tab, follow one of these steps:</span></span>

    - <span data-ttu-id="07a06-118">Si un environnement Dataverse est déjà configuré pour votre client, vous pouvez le sélectionner.</span><span class="sxs-lookup"><span data-stu-id="07a06-118">If a Dataverse environment is already provisioned for your tenant, you can select it.</span></span>

        1. <span data-ttu-id="07a06-119">Définissez l’option **Configurer Dataverse** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="07a06-119">Set the **Configure Dataverse** option to **Yes**.</span></span>
        2. <span data-ttu-id="07a06-120">Dans la colonne **Environnements disponibles**, sélectionnez l’environnement à intégrer avec vos données Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="07a06-120">In the **Available environments** column, select the environment to integrate with your Finance and Operations data.</span></span> <span data-ttu-id="07a06-121">La liste comprend tous les environnements dans lesquels vous disposez de privilèges d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="07a06-121">The list includes all environments where you have admin privileges.</span></span>
        3. <span data-ttu-id="07a06-122">Sélectionnez la case à cocher **Accepter** pour indiquer que vous acceptez les termes et conditions.</span><span class="sxs-lookup"><span data-stu-id="07a06-122">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![Onglet Dataverse lorsqu’un environnement Dataverse est déjà configuré pour votre client.](../dual-write/media/lcs_setup_1.png)

    - <span data-ttu-id="07a06-124">Si votre client n’a pas encore d’environnement Dataverse, un nouvel environnement sera mis à disposition.</span><span class="sxs-lookup"><span data-stu-id="07a06-124">If your tenant doesn't already have a Dataverse environment, a new environment will be provisioned.</span></span>

        1. <span data-ttu-id="07a06-125">Définissez l’option **Configurer Dataverse** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="07a06-125">Set the **Configure Dataverse** option to **Yes**.</span></span>
        2. <span data-ttu-id="07a06-126">Entrez un nom pour l’environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="07a06-126">Enter a name for the Dataverse environment.</span></span>
        3. <span data-ttu-id="07a06-127">Sélectionnez la région dans laquelle déployer l’environnement.</span><span class="sxs-lookup"><span data-stu-id="07a06-127">Select the region to deploy the environment in.</span></span>
        4. <span data-ttu-id="07a06-128">Sélectionnez la langue et la devise par défaut pour l’environnement.</span><span class="sxs-lookup"><span data-stu-id="07a06-128">Select the default language and currency for the environment.</span></span>

            > [!NOTE]
            > <span data-ttu-id="07a06-129">Vous ne pouvez pas modifier la langue et la devise ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="07a06-129">You can't change the language and currency later.</span></span>

        5. <span data-ttu-id="07a06-130">Sélectionnez la case à cocher **Accepter** pour indiquer que vous acceptez les termes et conditions.</span><span class="sxs-lookup"><span data-stu-id="07a06-130">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![Onglet Dataverse lorsque votre client n’a pas déjà un environnement Dataverse](../dual-write/media/lcs_setup_2.png)

7. <span data-ttu-id="07a06-132">Suivez les étapes restantes de l’assistant **Paramètres de déploiement**.</span><span class="sxs-lookup"><span data-stu-id="07a06-132">Complete the remaining steps in the **Deployment settings** wizard.</span></span>
8. <span data-ttu-id="07a06-133">Une fois que l’environnement a le statut **Déployé**, ouvrez la page des détails de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="07a06-133">After the environment has a status of **Deployed**, open the environment details page.</span></span> <span data-ttu-id="07a06-134">La section **Intégration de Power Platform** montre les noms de l’environnement Finance and Operations et de l’environnement Dataverse associés.</span><span class="sxs-lookup"><span data-stu-id="07a06-134">The **Power Platform Integration** section shows the names of the Finance and Operations environment and the Dataverse environment that are linked.</span></span>

    ![Section Intégration de Power Platform](../dual-write/media/lcs_setup_3.png)

9. <span data-ttu-id="07a06-136">Un administrateur de l’environnement Finance and Operations doit se connecter à LCS et sélectionner **Lien vers CDS pour les applications** pour compléter le lien.</span><span class="sxs-lookup"><span data-stu-id="07a06-136">An admin of the Finance and Operations environment must sign in to LCS and select **Link to CDS for Apps** to complete the link.</span></span> <span data-ttu-id="07a06-137">La page des détails de l’environnement affiche les informations de contact de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="07a06-137">The environment details page shows the admin's contact information.</span></span>

    <span data-ttu-id="07a06-138">Une fois le lien terminé, le statut est mis à jour vers **Association à l’environnement terminée avec succès**.</span><span class="sxs-lookup"><span data-stu-id="07a06-138">After the link is completed, the status is updated to **Environment linking successfully completed**.</span></span>

10. <span data-ttu-id="07a06-139">Pour ouvrir l’espace de travail **Intégration de données** dans l’environnement Finance and Operations et contrôler les modèles disponibles, sélectionnez **Lien vers CDS pour les applications**.</span><span class="sxs-lookup"><span data-stu-id="07a06-139">To open the **Data integration** workspace in the Finance and Operations environment and control the templates that are available, select **Link to CDS for Apps**.</span></span>

    ![Bouton Lien vers CDS for Apps dans la section Intégration de Power Platform](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> <span data-ttu-id="07a06-141">Vous ne pouvez pas dissocier des environnements à l’aide de LCS.</span><span class="sxs-lookup"><span data-stu-id="07a06-141">You can't unlink environments by using LCS.</span></span> <span data-ttu-id="07a06-142">Pour dissocier un environnement, ouvrez l’espace de travail **Intégration des données** dans l’environnement Finance and Operations, puis sélectionnez **Dissocier**.</span><span class="sxs-lookup"><span data-stu-id="07a06-142">To unlink an environment, open the **Data integration** workspace in the Finance and Operations environment, and then select **Unlink**.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]