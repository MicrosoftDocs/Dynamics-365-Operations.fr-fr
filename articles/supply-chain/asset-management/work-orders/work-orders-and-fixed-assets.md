---
title: Ordres de travail et immobilisations
description: Cette rubrique explique les ordres de travail et les immobilisations dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f03b7fa073c4e5338b7b5681ba7b8c9fe00a657b
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875645"
---
# <a name="work-orders-and-fixed-assets"></a><span data-ttu-id="2208d-103">Ordres de travail et immobilisations</span><span class="sxs-lookup"><span data-stu-id="2208d-103">Work orders and fixed assets</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="2208d-104">Dans le module Gestion des actifs, les actifs peuvent être associés aux immobilisations, et vous pouvez créer des ordres de travail pour ces actifs.</span><span class="sxs-lookup"><span data-stu-id="2208d-104">In Asset Management, assets can be related to fixed assets, and you can create work orders for those assets.</span></span> <span data-ttu-id="2208d-105">Si vous utilisez cette fonction, vous pouvez obtenir une vue d'ensemble complète des immobilisations, des projets d'investissement associés et des coûts enregistrés sur les projets d'investissement dans le module **Gestion de projets et comptabilité** et le module **Immobilisations** dans Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2208d-105">If you use this functionality, you can get a complete overview of fixed assets, related investment projects, and the costs registered on the investment projects in the **Project management and accounting** module and the **Fixed assets** module in Dynamics 365 for Finance and Operations.</span></span>

>[!NOTE]
><span data-ttu-id="2208d-106">Le champ **Numéro d'immobilisation** est renseigné uniquement dans le projet de tâche de l'ordre de travail si le type « Investissement » est sélectionné comme type de projet sur le projet de tâche de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="2208d-106">The **Fixed asset number** field is only filled out on the work order job project if type "Investment" is selected as the project type on the work order job project.</span></span>

![Figure 1](media/24-work-orders.png)

<span data-ttu-id="2208d-108">La procédure suivante décrit la relation entre les actifs, les bons de travail, les projets de tâche de l'ordre de travail, et les immobilisations.</span><span class="sxs-lookup"><span data-stu-id="2208d-108">The following procedure describes the relation between assets, work orders, work order job projects, and fixed assets.</span></span>

1. <span data-ttu-id="2208d-109">Vous créez un actif que vous associez à une immobilisation, comme illustré dans le graphique ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="2208d-109">You create an asset that you relate to a fixed asset, as shown in the figure below.</span></span>

![Figure 2](media/25-work-orders.png)

2. <span data-ttu-id="2208d-111">Lorsque vous paramétrez des types d'ordre de travail (**Gestion des actifs** > **Paramétrage** > **Ordres de travail** > **Types d'ordre de travail**), vous créez un type d'ordre de travail pour gérer les investissements.</span><span class="sxs-lookup"><span data-stu-id="2208d-111">When you set up work order types (**Asset management** > **Setup** > **Work orders** > **Work order types**), you create a work order type for handling investments.</span></span> <span data-ttu-id="2208d-112">Voir également [Types d'ordres de travail](../setup-for-work-orders/work-order-types.md).</span><span class="sxs-lookup"><span data-stu-id="2208d-112">See also [Work order types](../setup-for-work-orders/work-order-types.md).</span></span>

![Figure 3](media/26-work-orders.png)

3. <span data-ttu-id="2208d-114">Lorsque vous configurez les groupes de projet de l'ordre de travail (**Gestion des actifs** > **Paramétrage** > **Ordres de travail** > **Paramétrage de projet** > **Groupe de projets**), vous créez une relation entre le type d'ordre de travail utilisé pour les investissements et le groupe de projets créé pour les investissements dans le module **Gestion de projets et comptabilité** (**Gestion de projets et comptabilité** > **Paramétrage** > **Validation** > **Groupes de projets**).</span><span class="sxs-lookup"><span data-stu-id="2208d-114">When you set up work order project groups (**Asset management** > **Setup** > **Work orders** > **Project setup** > **Project group** link), you create a relation between the work order type used for investments and the project group created for investments in the **Project management and accounting** module (**Project management and accounting** > **Setup** > **Posting** > **Project groups**).</span></span>

![Figure 4](media/27-work-orders.png)

4. <span data-ttu-id="2208d-116">Lorsque vous créez un ordre de travail qui est lié à un objet d'immobilisation, vous sélectionnez le type d'ordre de travail utilisé pour traiter les investissements, par exemple, « Investissement ».</span><span class="sxs-lookup"><span data-stu-id="2208d-116">When you create a work order that relates to a fixed asset object, you select the work order type used for handling investments, for example, "Investment".</span></span>

5. <span data-ttu-id="2208d-117">Lorsque l'ordre de travail est créé, le type d'ordre de travail associé est affiché dans champ **Tous les ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="2208d-117">When the work order is created, the related work order type is shown in **All work orders**.</span></span>

![Figure 5](media/28-work-orders.png)

6. <span data-ttu-id="2208d-119">Lorsque l'ordre de travail est créé, le projet lié à l'ordre de travail est créé dans **Gestion de projets et comptabilité** > **Tous les projets**.</span><span class="sxs-lookup"><span data-stu-id="2208d-119">When the work order is created, the project related to the work order is created in **Project management and accounting** > **All projects**.</span></span> <span data-ttu-id="2208d-120">Vous pouvez consulter les informations relatives aux projets en cliquant sur le lien **ID projet** sur l'ordre de travail (dans **Gestion des actifs**, ouvrez l'ordre de travail dans la vue Détails > organisateur **Détails de ligne** > onglet **Général** > champ **ID projet**).</span><span class="sxs-lookup"><span data-stu-id="2208d-120">You can see project-related information by clicking the **Project ID** link on the work order (in **Asset management**, open the work order in Details view > **Line details** FastTab > **General** tab > **Project ID** field).</span></span>

![Figure 6](media/29-work-orders.png)

7. <span data-ttu-id="2208d-122">Dans **Immobilisations**, vous pouvez afficher une vue d'ensemble des projets associés à une immobilisation (**Immobilisations** > **Immobilisations** > **Immobilisations** > cliquez sur l'immobilisation dans le champ **Numéro d'immobilisation** > affichez le contenu dans le volet **Informations associées** > section **Projets associés** ).</span><span class="sxs-lookup"><span data-stu-id="2208d-122">In **Fixed assets**, you are able to see an overview of the projects associated with a fixed asset (**Fixed assets** > **Fixed assets** > **Fixed assets** > click on the fixed asset in the **Fixed asset number** field > view the contents in the **Related information** pane > **Associated projects** section).</span></span>

