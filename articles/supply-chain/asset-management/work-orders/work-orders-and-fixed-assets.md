---
title: Ordres de travail et immobilisations
description: Cette rubrique explique les ordres de travail et les immobilisations dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4eadbdc452a5b7d28adfa0f102a9a727faad3c07
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016701"
---
# <a name="work-orders-and-fixed-assets"></a><span data-ttu-id="a706c-103">Ordres de travail et immobilisations</span><span class="sxs-lookup"><span data-stu-id="a706c-103">Work orders and fixed assets</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="a706c-104">Dans le module Gestion des actifs, les actifs peuvent être associés aux immobilisations, et vous pouvez créer des ordres de travail pour ces actifs.</span><span class="sxs-lookup"><span data-stu-id="a706c-104">In Asset Management, assets can be related to fixed assets, and you can create work orders for those assets.</span></span> <span data-ttu-id="a706c-105">Si vous utilisez cette fonction, vous pouvez obtenir une vue d'ensemble complète des immobilisations, des projets d'investissement associés et des coûts enregistrés sur les projets d'investissement dans les modules **Gestion de projets et comptabilité** et **Immobilisations** dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a706c-105">If you use this functionality, you can get a complete overview of fixed assets, related investment projects, and the costs that are registered on the investment projects in the **Project management and accounting** and **Fixed assets** modules in Microsoft Dynamics 365 for Finance and Operations.</span></span>

>[!NOTE]
><span data-ttu-id="a706c-106">Le champ **Numéro d'immobilisation** dans le projet de tâche de l'ordre de travail est renseigné uniquement si le type **Investissement** est sélectionné comme type de projet sur le projet de tâche de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="a706c-106">The **Fixed asset number** field on the work order job project is set only if **Investment** is selected as the project type on the work order job project.</span></span>

<span data-ttu-id="a706c-107">L'illustration ci-dessous montre la relation entre un projet d'investissement dans le module **Gestion de projets et comptabilité** et un projet de tâche d'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="a706c-107">The illustration below shows the relation between an investment project in the **Project management and accounting** module and a work order job project.</span></span>

![Figure 1](media/24-work-orders.png)

<span data-ttu-id="a706c-109">La procédure suivante décrit la relation entre les actifs, les bons de travail, les projets de tâche de l'ordre de travail, et les immobilisations.</span><span class="sxs-lookup"><span data-stu-id="a706c-109">The following procedure describes the relation between assets, work orders, work order job projects, and fixed assets.</span></span>

1. <span data-ttu-id="a706c-110">Vous créez un actif que vous associez à une immobilisation.</span><span class="sxs-lookup"><span data-stu-id="a706c-110">You create an asset that you relate to a fixed asset.</span></span>

![Figure 2](media/25-work-orders.png)

2. <span data-ttu-id="a706c-112">Lorsque vous paramétrez des types d'ordre de travail sur la page **Types d'ordres de travail** (**Gestion des actifs** > **Paramétrage** > **Ordres de travail** > **Types d'ordre de travail**), vous créez un type d'ordre de travail pour gérer les investissements.</span><span class="sxs-lookup"><span data-stu-id="a706c-112">When you set up work order types on the **Work order types** page (**Asset management** > **Setup** > **Work orders** > **Work order types**), you create a work order type for handling investments.</span></span> <span data-ttu-id="a706c-113">Voir également [Types d'ordres de travail](../setup-for-work-orders/work-order-types.md).</span><span class="sxs-lookup"><span data-stu-id="a706c-113">See also [Work order types](../setup-for-work-orders/work-order-types.md).</span></span>

![Figure 3](media/26-work-orders.png)

3. <span data-ttu-id="a706c-115">Lorsque vous configurez les groupes de projet de l'ordre de travail sur l'onglet **Groupe de projets** de la page **Configuration du projet de l'ordre de travail** (**Gestion des actifs** > **Paramétrage** > **Ordres de travail** > **Paramétrage de projet**), vous créez une relation entre le type d'ordre de travail utilisé pour les investissements et le groupe de projets créé pour les investissements sur la page **Groupes de projets** dans le module **Gestion de projets et comptabilité** (**Gestion de projets et comptabilité** > **Paramétrage** > **Validation** > **Groupes de projets**).</span><span class="sxs-lookup"><span data-stu-id="a706c-115">When you set up work order project groups on the **Project group** tab of the **Work order project setup** page (**Asset management** > **Setup** > **Work orders** > **Project setup**), you create a relation between the work order type that is used for investments and the project group that was created for investments on the **Project groups** page in the **Project management and accounting** module (**Project management and accounting** > **Setup** > **Posting** > **Project groups**).</span></span>

![Figure 4](media/27-work-orders.png)

4. <span data-ttu-id="a706c-117">Lorsque vous créez un ordre de travail qui est lié à une immobilisation, vous sélectionnez le type d'ordre de travail utilisé pour traiter les investissements, par exemple, **Investissement**.</span><span class="sxs-lookup"><span data-stu-id="a706c-117">When you create a work order that is related to a fixed asset, you select the work order type that is used to handle investments, such as **Investment**.</span></span>

5. <span data-ttu-id="a706c-118">Lorsque l'ordre de travail est créé, le type d'ordre de travail associé est affiché sur la page **Tous les ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="a706c-118">When the work order is created, the related work order type is shown on the **All work orders** page.</span></span>

![Figure 5](media/28-work-orders.png)

6. <span data-ttu-id="a706c-120">Lorsque l'ordre de travail est créé, le projet lié à l'ordre de travail est créé dans la page **Tous les projets** dans le module **Gestion de projets et comptabilité** (**Gestion de projets et comptabilité** > **Projets** > **Tous les projets**).</span><span class="sxs-lookup"><span data-stu-id="a706c-120">When the work order is created, the project that is related to the work order is created on the **All projects** page in the **Project management and accounting** module (**Project management and accounting** > **Projects** > **All projects**).</span></span> <span data-ttu-id="a706c-121">Pour afficher les informations liées au projet, sélectionnez le lien dans le champ **ID projet** sur l'onglet **Général** sur l'organisateur **Détails de ligne** dans la vue détaillée de la page **Tous les ordres de travail** dans le module **Gestion des actifs** (**Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail**).</span><span class="sxs-lookup"><span data-stu-id="a706c-121">To view project-related information, select the link in the **Project ID** field on the **General** tab on the **Line details** FastTab in the details view of the **All work orders** page in the **Asset management** module (**Asset management** > **Commom** > **Work orders** > **All work orders**).</span></span>

![Figure 6](media/29-work-orders.png)

7. <span data-ttu-id="a706c-123">Pour afficher une vue d'ensemble des projets associés à une immobilisation, sélectionnez **Immobilisations** > **Immobilisations** > **Immobilisations**, puis, dans le champ **Numéro d'immobilisation**, sélectionnez le lien pour l'immobilisation pour ouvrir la vue détaillée.</span><span class="sxs-lookup"><span data-stu-id="a706c-123">To see an overview of the projects associated with a fixed asset, select **Fixed assets** > **Fixed assets** > **Fixed assets**, and then, in the **Fixed asset number** field, select the link for the fixed asset to open the details view.</span></span> <span data-ttu-id="a706c-124">Développez le volet **Informations associées** à droite de la page, puis sélectionnez l'organisateur **Projets associés**.</span><span class="sxs-lookup"><span data-stu-id="a706c-124">Expand the **Related information** pane on the right side of the page, and select the **Associated projects** FastTab.</span></span>

