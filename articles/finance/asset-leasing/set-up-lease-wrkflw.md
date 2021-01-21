---
title: Configurer les workflows d’approbation de bail
description: La rubrique explique comment configurer un workflow d’approbation qui s’exécutera lors de la création d’un bail.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 58c0fd781710b7ab8efeaa7a6874f412279a5924
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4443360"
---
# <a name="set-up-lease-approval-workflows"></a><span data-ttu-id="918fd-103">Configurer les workflows d’approbation de bail</span><span class="sxs-lookup"><span data-stu-id="918fd-103">Set up lease approval workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="918fd-104">La rubrique explique comment configurer un workflow d’approbation qui s’exécutera lors de la création d’un bail.</span><span class="sxs-lookup"><span data-stu-id="918fd-104">The topic explains how to set up an approval workflow that will run when a new lease is created.</span></span> <span data-ttu-id="918fd-105">Pour plus d’informations sur l’utilisation d’un workflow, voir [Utiliser des workflows d’approbation de bail](use-create-lease-wrkflw.md).</span><span class="sxs-lookup"><span data-stu-id="918fd-105">For information about how to use the workflow, see [Use lease approval workflows](use-create-lease-wrkflw.md).</span></span> 

1. <span data-ttu-id="918fd-106">Accédez à **Location d’actifs \> Configuration \> workflow de bail**.</span><span class="sxs-lookup"><span data-stu-id="918fd-106">Go to **Asset leasing \> Setup \> Lease workflow**.</span></span>
2. <span data-ttu-id="918fd-107">Dans la page **workflow de bail**, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="918fd-107">On the **Lease workflow** page, select **New**.</span></span>
3. <span data-ttu-id="918fd-108">Dans la boîte de dialogue qui apparaît, sous **Type de workflow**, sélectionnez le lien **Workflow de bail**.</span><span class="sxs-lookup"><span data-stu-id="918fd-108">In the dialog box that appears, under **Workflow type**, select the **Lease workflow** link.</span></span>

    <span data-ttu-id="918fd-109">L’application est ouverte.</span><span class="sxs-lookup"><span data-stu-id="918fd-109">The application is opened.</span></span> <span data-ttu-id="918fd-110">Après son exécution, connectez-vous à Azure Active Directory (Azure AD) pour être redirigé vers l’application de workflow.</span><span class="sxs-lookup"><span data-stu-id="918fd-110">After it runs, sign in to Azure Active Directory (Azure AD) to be redirected to the workflow application.</span></span>

4. <span data-ttu-id="918fd-111">Faites glisser l’élément **Approbation du workflow de location** sur le workflow.</span><span class="sxs-lookup"><span data-stu-id="918fd-111">Drag the **Lease workflow approval** element onto the workflow.</span></span>
5. <span data-ttu-id="918fd-112">Connectez un nœud depuis **Début** à **Approbation du workflow de location**.</span><span class="sxs-lookup"><span data-stu-id="918fd-112">Connect one node from **Start** to **Lease workflow approval**.</span></span> <span data-ttu-id="918fd-113">Puis connectez **Approbation du workflow de location** à **Fin**.</span><span class="sxs-lookup"><span data-stu-id="918fd-113">Then connect **Lease workflow approval** to **End**.</span></span>
6. <span data-ttu-id="918fd-114">Double-cliquez sur **Approbation du workflow de location**.</span><span class="sxs-lookup"><span data-stu-id="918fd-114">Double-click **Lease workflow approval**.</span></span>
7. <span data-ttu-id="918fd-115">Sélectionnez **Propriétés**, puis, sous **Paramètres de base**, entrez un nom pour le workflow.</span><span class="sxs-lookup"><span data-stu-id="918fd-115">Select **Properties**, and then, under **Basic settings**, enter a name for the workflow.</span></span>

    <span data-ttu-id="918fd-116">Sur cette page, vous pouvez également définir plus de paramètres pour le workflow.</span><span class="sxs-lookup"><span data-stu-id="918fd-116">On this page, you can also set more parameters for the workflow.</span></span> <span data-ttu-id="918fd-117">Si vous avez activé **Actions automatiques**, le système entreprendra automatiquement une action spécifique.</span><span class="sxs-lookup"><span data-stu-id="918fd-117">If you've turned on **Automatic actions**, the system will automatically take a specific action.</span></span> <span data-ttu-id="918fd-118">Les notifications peuvent être envoyées si elles sont spécifiées sur l’onglet **Notifications**. Sur l’onglet **Paramètres avancés**, vous pouvez spécifier un approbateur final, définir une limite de temps et désigner des actions spécifiques qui doivent être effectuées.</span><span class="sxs-lookup"><span data-stu-id="918fd-118">Notifications can be sent if they are specified on the **Notifications** tab. On the **Advanced settings** tab, you can specify a final approver, set a time limit, and designate specific actions that must be completed.</span></span>

8. <span data-ttu-id="918fd-119">Lorsque vous avez terminé de définir les paramètres du workflow, sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="918fd-119">When you've finished setting the workflow parameters, select **Close**.</span></span>
9. <span data-ttu-id="918fd-120">Sélectionnez **Étape 1**, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="918fd-120">Select **Step 1**, and then select **Properties**.</span></span>
10. <span data-ttu-id="918fd-121">Sous **Paramètres de base**, entrez un nom pour l’étape, créez une ligne d’objet pour l’approbation et spécifiez les instructions pour l’approbation.</span><span class="sxs-lookup"><span data-stu-id="918fd-121">Under **Basic settings**, enter a name for the step, create a subject line for the approval, and specify instructions for the approval.</span></span>
11. <span data-ttu-id="918fd-122">Sur la page **Affectation**, sélectionnez le type d’affectation.</span><span class="sxs-lookup"><span data-stu-id="918fd-122">On the **Assignment** page, select the assignment type.</span></span>
12. <span data-ttu-id="918fd-123">Pour affecter des utilisateurs spécifiques à l’approbation, sélectionnez **Utilisateur**, sélectionnez les utilisateurs qui approuvent les baux, puis sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="918fd-123">To assign specific users to the approval, select **User**, select the users who approve leases, and then select **Close**.</span></span>
13. <span data-ttu-id="918fd-124">Cliquez sur **Enregistrer et fermer** pour créer le workflow.</span><span class="sxs-lookup"><span data-stu-id="918fd-124">Select **Save and close** to create the workflow.</span></span> <span data-ttu-id="918fd-125">Ensuite, lorsque vous y êtes invité, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="918fd-125">Then, when you're prompted, select **OK**.</span></span>
14. <span data-ttu-id="918fd-126">Sur la page **Créer le workflow**, sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="918fd-126">On the **Create workflow** page, select **Close**.</span></span>
14. <span data-ttu-id="918fd-127">Sélectionnez le nouveau workflow, puis sélectionnez **Versions**.</span><span class="sxs-lookup"><span data-stu-id="918fd-127">Select the new workflow, and then select **Versions**.</span></span> <span data-ttu-id="918fd-128">Puis sélectionnez **Rendre actif** pour vous assurer que le workflow est actif.</span><span class="sxs-lookup"><span data-stu-id="918fd-128">Then select **Make active** to ensure that the workflow is active.</span></span>
15. <span data-ttu-id="918fd-129">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="918fd-129">Select **Close**.</span></span> <span data-ttu-id="918fd-130">La nouvelle version active apparaît.</span><span class="sxs-lookup"><span data-stu-id="918fd-130">The new active version appears.</span></span>