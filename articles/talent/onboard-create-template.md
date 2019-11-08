---
title: Créer un modèle d'intégration à l'aide de Dynamics 365 Talent - Onboard
description: Cette rubrique vous explique comment utiliser l'application Dynamics 365 Talent - Onboard pour créer un modèle de guide d'intégration pour vos nouvelles recrues. Cette tâche est une première étape essentielle dans la stratégie « De l'embauche à la retraite » de la gestion du capital humain (GCH).
author: andreabichsel
manager: ''
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a1fac239524d4873a782e6a3d177a573a382d0f6
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2552033"
---
# <a name="create-an-onboarding-template-by-using-dynamics-365-talent---onboard"></a><span data-ttu-id="b3a91-104">Créer un modèle d'intégration à l'aide de Dynamics 365 Talent - Onboard</span><span class="sxs-lookup"><span data-stu-id="b3a91-104">Create an onboarding template by using Dynamics 365 Talent - Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b3a91-105">Microsoft Dynamics 365 Talent: Onboard fournit plusieurs modèles qui peuvent vous aider à créer un guide d'intégration le plus rapidement possible.</span><span class="sxs-lookup"><span data-stu-id="b3a91-105">Microsoft Dynamics 365 Talent: Onboard provides various templates that can help you create an onboarding guide as quickly as possible.</span></span> <span data-ttu-id="b3a91-106">Vous pouvez utiliser un ou plusieurs de ces modèles, ou vous pouvez créer vos propres modèles.</span><span class="sxs-lookup"><span data-stu-id="b3a91-106">You can use one or more of these templates, or you can create your own templates.</span></span> <span data-ttu-id="b3a91-107">Onboard fournit un exemple de texte que vous pouvez utiliser lorsque vous créez vos propres modèles.</span><span class="sxs-lookup"><span data-stu-id="b3a91-107">Onboard provides sample text that you can use when you create your own templates.</span></span> <span data-ttu-id="b3a91-108">Par conséquent, le processus est facile même si vous commencez à partir de zéro.</span><span class="sxs-lookup"><span data-stu-id="b3a91-108">Therefore, the process is easy even if you start from scratch.</span></span>

## <a name="create-an-onboarding-template-from-an-existing-template"></a><span data-ttu-id="b3a91-109">Créer un modèle d'intégration à partir d'un modèle existant</span><span class="sxs-lookup"><span data-stu-id="b3a91-109">Create an onboarding template from an existing template</span></span>

1. <span data-ttu-id="b3a91-110">Dans le menu à gauche, sélectionnez **Modèles**.</span><span class="sxs-lookup"><span data-stu-id="b3a91-110">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="b3a91-111">Sous **Modèles populaires de la galerie** ou **Mes modèles**, sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="b3a91-111">Under **Popular templates from the gallery** or **My templates**, select a template.</span></span> <span data-ttu-id="b3a91-112">Pour afficher d'autres modèles, sélectionnez **Autres modèles dans la galerie de modèles**.</span><span class="sxs-lookup"><span data-stu-id="b3a91-112">To view more templates, select **More in template gallery**.</span></span>
3. <span data-ttu-id="b3a91-113">Utilisez l'une des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="b3a91-113">Follow one of these steps:</span></span>

    - <span data-ttu-id="b3a91-114">Si le modèle provient de la galerie, sélectionnez **Enregistrer comme mon modèle**, entrez un nouveau nom pour le modèle, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b3a91-114">If the template is from the gallery, select **Save as my template**, enter a new name for the template, and select **Save**.</span></span>
    - <span data-ttu-id="b3a91-115">Si le modèle provient de **Mes modèles**, sélectionnez **Enregistrer en tant que modèle**, entrez un nouveau nom pour le modèle, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b3a91-115">If the template is from **My templates**, select **Save as template**, enter a new name for the template, and select **Save**.</span></span>

    <span data-ttu-id="b3a91-116">[![Création d'un modèle à partir d'un modèle existant](./media/onboard-save-template.png)](./media/onboard-save-template.png)</span><span class="sxs-lookup"><span data-stu-id="b3a91-116">[![Creating a template from an existing template](./media/onboard-save-template.png)](./media/onboard-save-template.png)</span></span>

## <a name="create-a-new-onboarding-template"></a><span data-ttu-id="b3a91-117">Créer un nouveau modèle d'intégration</span><span class="sxs-lookup"><span data-stu-id="b3a91-117">Create a new onboarding template</span></span>

1. <span data-ttu-id="b3a91-118">Dans le menu à gauche, sélectionnez **Modèles**.</span><span class="sxs-lookup"><span data-stu-id="b3a91-118">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="b3a91-119">Sous **Mes modèles**, sélectionnez la vignette **Ajouter** (signe plus) \[**+**\].</span><span class="sxs-lookup"><span data-stu-id="b3a91-119">Under **My templates**, select the **Add** (plus sign \[**+**\]) tile.</span></span>

    <span data-ttu-id="b3a91-120">[![Création d'un nouveau modèle](./media/onboard-create-new-template.png)](./media/onboard-create-new-template.png)</span><span class="sxs-lookup"><span data-stu-id="b3a91-120">[![Creating a new template](./media/onboard-create-new-template.png)](./media/onboard-create-new-template.png)</span></span>

3. <span data-ttu-id="b3a91-121">Dans la boîte de dialogue **Créer un modèle de guide**, entrez un nom pour le modèle, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b3a91-121">In the **Create a guide template** dialog box, enter a name for the template, and then select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b3a91-122">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="b3a91-122">Next steps</span></span>

- [<span data-ttu-id="b3a91-123">Modifier les guides et les modèles d'intégration</span><span class="sxs-lookup"><span data-stu-id="b3a91-123">Edit onboarding guides and templates</span></span>](./onboard-edit-guides-templates.md)
- [<span data-ttu-id="b3a91-124">Partager du contenu avec d'autres contributeurs</span><span class="sxs-lookup"><span data-stu-id="b3a91-124">Share content with other contributors</span></span>](./onboard-share-template.md)
- [<span data-ttu-id="b3a91-125">Afficher le statut d'intégration des employés et des tâches</span><span class="sxs-lookup"><span data-stu-id="b3a91-125">View the status of tasks and onboarding employees</span></span>](./onboard-view-status.md)
- [<span data-ttu-id="b3a91-126">Créer des équipes de recrutement dans Onboard</span><span class="sxs-lookup"><span data-stu-id="b3a91-126">Create hiring teams in Onboard</span></span>](./onboard-create-team.md)

### <a name="see-also"></a><span data-ttu-id="b3a91-127">Voir également :</span><span class="sxs-lookup"><span data-stu-id="b3a91-127">See also</span></span>

- [<span data-ttu-id="b3a91-128">Essayer ou acheter l'application Onboard</span><span class="sxs-lookup"><span data-stu-id="b3a91-128">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="b3a91-129">Nouveautés</span><span class="sxs-lookup"><span data-stu-id="b3a91-129">What's new</span></span>](./whats-new.md)
- [<span data-ttu-id="b3a91-130">Note de publication</span><span class="sxs-lookup"><span data-stu-id="b3a91-130">Release notes</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="b3a91-131">Obtenir de l'aide</span><span class="sxs-lookup"><span data-stu-id="b3a91-131">Get support</span></span>](./talent-support.md)
