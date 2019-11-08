---
title: Créer des ordres de travail à partir de demandes de maintenance
description: Cette rubrique explique comment créer un ordre de travail à partir d'une demande de maintenance dans Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c42f259a57675c3dbac829d6d671e91982ef9011
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571689"
---
# <a name="create-work-orders-from-maintenance-requests"></a><span data-ttu-id="6d140-103">Créer des ordres de travail à partir de demandes de maintenance</span><span class="sxs-lookup"><span data-stu-id="6d140-103">Create work orders from maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="6d140-104">Après avoir créé des demandes de maintenance, vous pouvez facilement les convertir en ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="6d140-104">After you've created maintenance requests, you can easily convert them to work orders.</span></span> <span data-ttu-id="6d140-105">Cette rubrique décrit le moyen le plus rapide de traiter des demandes de maintenance, de mettre à jour plusieurs demandes de maintenance en même temps, puis de créer un ordre de travail pour plusieurs demandes de maintenance en même temps.</span><span class="sxs-lookup"><span data-stu-id="6d140-105">This topic describes the quickest way to work with maintenance requests, update several maintenance requests at the same time, and then create a work order for several maintenance requests at the same time.</span></span> <span data-ttu-id="6d140-106">Dans la page **Demandes de maintenance actives** ou **Mes demandes de maintenance de poste technique**, vous pouvez également utiliser une demande de maintenance à la fois et convertir une demande de maintenance en ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="6d140-106">On the **Active maintenance requests** or **My functional location maintenance requests** page, you can also work with one maintenance request at a time and convert one maintenance request to a work order.</span></span>

> [!NOTE]
> <span data-ttu-id="6d140-107">Chaque demande de maintenance peut être associée à un seul ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="6d140-107">Every maintenance request can be related to only one work order.</span></span> <span data-ttu-id="6d140-108">Toutefois, plusieurs demandes de maintenance peuvent être incluses dans un même ordre de travail, même si les demandes de maintenance ont des actifs différents.</span><span class="sxs-lookup"><span data-stu-id="6d140-108">However, multiple maintenance requests can be included in one work order, even if the maintenance requests have different assets.</span></span>

1. <span data-ttu-id="6d140-109">Sélectionnez **Gestion des actifs** \> **Commun** \> **Demandes de maintenance** \> **Toutes les demandes de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="6d140-109">Select **Asset management** \> **Common** \> **maintenance requests** \> **All maintenance requests**.</span></span>
2. <span data-ttu-id="6d140-110">Avant de pouvoir créer un ordre de travail à partir de demandes de maintenance, vous devez au minimum sélectionner un type de travail de maintenance pour les demandes de maintenance, ainsi qu'une variante et un échange de type de travail de maintenance, si ces informations sont pertinentes.</span><span class="sxs-lookup"><span data-stu-id="6d140-110">Before you can create a work order from maintenance requests, you must select, at a minimum, a maintenance job type for the maintenance requests, and also a maintenance job type variant and trade, if this information is relevant.</span></span> <span data-ttu-id="6d140-111">Dans la vue Grille, vous pouvez facilement mettre à jour les informations de mise à jour pour une demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="6d140-111">In the grid view, you can easily update information for a maintenance request.</span></span>
3. <span data-ttu-id="6d140-112">Lorsque vous êtes prêt(e) à créer un ordre de travail, sélectionnez les demandes de maintenance à inclure dans celui-ci.</span><span class="sxs-lookup"><span data-stu-id="6d140-112">When you're ready to create a work order, select the maintenance requests to include in it.</span></span>

    - <span data-ttu-id="6d140-113">Si vous sélectionnez plusieurs demandes de maintenance à convertir en ordre de travail, le champ **Actif** et le champ **Type de tâche de maintenance** doivent être définis avant de créer les ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="6d140-113">If you select several maintenance requests to convert to a work order, both the **Asset** field and the **Maintenance job type** field must be set before you create the work order.</span></span>
    - <span data-ttu-id="6d140-114">Si vous sélectionnez une demande de maintenance à convertir en ordre de travail, seul le champ **Actif** doit être défini avant de créer les ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="6d140-114">If you select one maintenance request to convert to a work order, only the **Asset** field must be set before you create the work order.</span></span> <span data-ttu-id="6d140-115">Toutefois, lorsque vous créez l'ordre de travail, vous pouvez sélectionner un type de travail de maintenance (et une variante de type de travail de maintenance et un échange associés, si cette information est pertinente) dans la boîte de dialogue **Créer un ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="6d140-115">However, when you create the work order, you can select a maintenance job type (and a related maintenance job type variant and trade, if this information is relevant) in the **Create work order** dialog box.</span></span>

4. <span data-ttu-id="6d140-116">Sélectionnez **Ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="6d140-116">Select **Work order**.</span></span>
5. <span data-ttu-id="6d140-117">Dans la boîte de dialogue **Créer un ordre de travail**, définissez les champs, puis les sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d140-117">In the **Create work order** dialog box, set the fields, and then select **OK**.</span></span>

    <span data-ttu-id="6d140-118">Une barre de message peut vous informer qu'un ordre de travail récent a été créé.</span><span class="sxs-lookup"><span data-stu-id="6d140-118">A message bar might notify you that a new work order has been created.</span></span>

    <span data-ttu-id="6d140-119">En outre, lorsque vous créez un ordre de travail basé sur une demande de maintenance, si l'actif associé à la demande de maintenance est inclus dans un contrat de garantie, une barre de message vous avertit du contrat de garantie.</span><span class="sxs-lookup"><span data-stu-id="6d140-119">Additionally, when you create a work order that is based on a maintenance request, if the asset that is related to the maintenance request is included in a warranty agreement, a message bar notifies you about the warranty agreement.</span></span>

6. <span data-ttu-id="6d140-120">Sélectionnez **Gestion des actifs** \> **Commun** \> **Ordres de travail** \> **Tous les ordres de travail**, puis ouvrez le nouvel ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="6d140-120">Select **Asset management** \> **Common** \> **Work orders** \> **All work orders**, and open the new work order.</span></span>

    ![Ouvrir le nouvel ordre de travail](media/05-manage-maintenance-requests.png)

