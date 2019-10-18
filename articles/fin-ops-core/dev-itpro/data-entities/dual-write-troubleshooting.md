---
title: Guide de résolution des problèmes d'intégration de données
description: Cette rubrique fournit des informations sur le dépannage de l'intégration des données entre les applications Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: c16268338085d414468f17362294fb7e933d1b57
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249107"
---
# <a name="troubleshooting-guide-for-data-integration"></a><span data-ttu-id="6e86a-103">Guide de résolution des problèmes d'intégration de données</span><span class="sxs-lookup"><span data-stu-id="6e86a-103">Troubleshooting guide for data integration</span></span>

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a><span data-ttu-id="6e86a-104">Activer les journaux de suivi des plug-ins dans Common Data Service et vérifier les détails d'erreur de plug-in en double écriture</span><span class="sxs-lookup"><span data-stu-id="6e86a-104">Enable plug-in trace logs in Common Data Service and inspect the dual-write plug-in error details</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="6e86a-105">Si vous rencontrez un problème ou une erreur durant la synchronisation en double écriture, procédez comme suit pour examiner les erreurs dans le journal de suivi.</span><span class="sxs-lookup"><span data-stu-id="6e86a-105">If you experience an issue or error during dual-write synchronization, follow these steps to inspect the errors in the trace log.</span></span>

1. <span data-ttu-id="6e86a-106">Avant de pouvoir examiner les erreurs, vous devez activer les journaux de suivi des plug-ins.</span><span class="sxs-lookup"><span data-stu-id="6e86a-106">Before you can inspect the errors, you must enable plug-in trace logs.</span></span> <span data-ttu-id="6e86a-107">Pour obtenir des instructions, voir la section « Afficher les journaux de suivi » du [Didacticiel : Écrire et enregistrer un plug-in](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).</span><span class="sxs-lookup"><span data-stu-id="6e86a-107">For instructions, see the "View trace logs" section of [Tutorial: Write and register a plug-in](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).</span></span>

    <span data-ttu-id="6e86a-108">Vous pouvez désormais examiner les erreurs.</span><span class="sxs-lookup"><span data-stu-id="6e86a-108">You can now inspect the errors.</span></span>

2. <span data-ttu-id="6e86a-109">Connectez-vous à Microsoft Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="6e86a-109">Sign in to Microsoft Dynamics 365 Sales.</span></span>
3. <span data-ttu-id="6e86a-110">Sélectionnez le bouton **Paramètres** (le symbole d'engrenage), puis sélectionnez **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="6e86a-110">Select the **Settings** button (the gear symbol), and then select **Advanced Settings**.</span></span>
4. <span data-ttu-id="6e86a-111">Dans le menu  **Paramètres**, choisissez **Personnalisation \> Journal de suivi des plug-ins**.</span><span class="sxs-lookup"><span data-stu-id="6e86a-111">On the **Settings** menu, select **Customization \> Plug-In Trace Log**.</span></span>
5. <span data-ttu-id="6e86a-112">Sélectionnez le nom de type **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** pour afficher les détails de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="6e86a-112">Select **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** as the type name to show the error details.</span></span>

## <a name="inspect-dual-write-synchronization-errors"></a><span data-ttu-id="6e86a-113">Contrôler les erreurs de synchronisation en double écriture</span><span class="sxs-lookup"><span data-stu-id="6e86a-113">Inspect dual-write synchronization errors</span></span>

<span data-ttu-id="6e86a-114">Procédez comme suit pour examiner les erreurs au cours des tests.</span><span class="sxs-lookup"><span data-stu-id="6e86a-114">Follow these steps to inspect errors during testing.</span></span>

1. <span data-ttu-id="6e86a-115">Connectez-vous à Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="6e86a-115">Sign in to Microsoft Dynamics Lifecycle Services (LCS).</span></span>
2. <span data-ttu-id="6e86a-116">Ouvrez le projet LCS pour effectuer le test de double écriture.</span><span class="sxs-lookup"><span data-stu-id="6e86a-116">Open the LCS project to do dual-write testing for.</span></span>
3. <span data-ttu-id="6e86a-117">Sélectionnez **Environnements hébergés dans le cloud**.</span><span class="sxs-lookup"><span data-stu-id="6e86a-117">Select **Cloud-hosted environments**.</span></span>
4. <span data-ttu-id="6e86a-118">Établissez une connexion RDP (Remote Desktop Protocol) à l'ordinateur virtuel (VM) de l'application en utilisant le compte local qui s'affiche dans LCS.</span><span class="sxs-lookup"><span data-stu-id="6e86a-118">Make a Remote desktop connection to the application virtual machine (VM) by using local account that is shown in LCS.</span></span>
5. <span data-ttu-id="6e86a-119">Ouvrez l'Observateur d'événements.</span><span class="sxs-lookup"><span data-stu-id="6e86a-119">Open Event Viewer.</span></span> 
6. <span data-ttu-id="6e86a-120">Accédez à **Journaux des applications et des services \> Microsoft \> Dynamics \> AX-DualWriteSync \> Opérationnel**.</span><span class="sxs-lookup"><span data-stu-id="6e86a-120">Go to **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**.</span></span> <span data-ttu-id="6e86a-121">Les erreurs et les détails sont affichés.</span><span class="sxs-lookup"><span data-stu-id="6e86a-121">The errors and details are shown.</span></span>

## <a name="unlink-one-common-data-service-environment-from-the-application-and-link-another-environment"></a><span data-ttu-id="6e86a-122">Supprimer un environnement Common Data Service depuis l'application et lier un autre environnement</span><span class="sxs-lookup"><span data-stu-id="6e86a-122">Unlink one Common Data Service environment from the application and link another environment</span></span>

<span data-ttu-id="6e86a-123">Procédez comme suit pour mettre à jour des liens.</span><span class="sxs-lookup"><span data-stu-id="6e86a-123">Follow these steps to update links.</span></span>

1. <span data-ttu-id="6e86a-124">Accédez à l'environnement d'application.</span><span class="sxs-lookup"><span data-stu-id="6e86a-124">Go to the application environment.</span></span>
2. <span data-ttu-id="6e86a-125">Ouvrez Gestion des données.</span><span class="sxs-lookup"><span data-stu-id="6e86a-125">Open Data Management.</span></span>
3. <span data-ttu-id="6e86a-126">Sélectionnez **Lien vers CDS for Apps**.</span><span class="sxs-lookup"><span data-stu-id="6e86a-126">Select **Link to CDS for apps**.</span></span>
4. <span data-ttu-id="6e86a-127">Sélectionnez toutes les mises en correspondance qui s'exécutent, puis sélectionnez **Arrêter**.</span><span class="sxs-lookup"><span data-stu-id="6e86a-127">Select all the mappings that are running, and then select **Stop**.</span></span>
5. <span data-ttu-id="6e86a-128">Sélectionnez toutes les mises en correspondance et sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="6e86a-128">Select all the mappings, and then select **Delete**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6e86a-129">L'option **Supprimer** n'est pas disponible si le modèle **CustomerV3-Account** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="6e86a-129">The **Delete** option isn't available if the **CustomerV3-Account** template is selected.</span></span> <span data-ttu-id="6e86a-130">Effacez la sélection de ce modèle, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6e86a-130">Clear the selection of this template as required.</span></span> <span data-ttu-id="6e86a-131">**CustomerV3-Account** est un modèle anciennement mis en service et fonctionne avec la solution Prospect en disponibilités.</span><span class="sxs-lookup"><span data-stu-id="6e86a-131">**CustomerV3-Account** is an older provisioned template and works with the Prospect to Cash solution.</span></span> <span data-ttu-id="6e86a-132">Comme il est disponible mondialement, il s'affiche sous tous les modèles.</span><span class="sxs-lookup"><span data-stu-id="6e86a-132">Because it's globally released, it appears under all templates.</span></span>

6. <span data-ttu-id="6e86a-133">Cliquez sur **Supprimer le lien avec l'environnement**.</span><span class="sxs-lookup"><span data-stu-id="6e86a-133">Select **Unlink environment**.</span></span>
7. <span data-ttu-id="6e86a-134">Sélectionnez **Oui** pour confirmer l'opération.</span><span class="sxs-lookup"><span data-stu-id="6e86a-134">Select **Yes** to confirm the operation.</span></span>
8. <span data-ttu-id="6e86a-135">Pour lier le nouvel environnement, suivez les étapes du [guide d'installation](https://aka.ms/dualwrite-docs).</span><span class="sxs-lookup"><span data-stu-id="6e86a-135">To link the new environment, follow the steps in the [installation guide](https://aka.ms/dualwrite-docs).</span></span>
