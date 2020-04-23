---
title: Agents de maintenance responsables
description: Cette rubrique explique comment paramétrer des agents de maintenance responsables dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b5f83474e56c996a40bdbdf7d3a7c8d495429c6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208936"
---
# <a name="responsible-maintenance-workers"></a><span data-ttu-id="4ba03-103">Agents de maintenance responsables</span><span class="sxs-lookup"><span data-stu-id="4ba03-103">Responsible maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="4ba03-104">Les agents de maintenance responsables peuvent être associés aux types d'actif, aux actifs, aux postes techniques, aux catégories de type de tâche de maintenance, aux types de tâche de maintenance, aux variantes de type de tâche de maintenance et aux transactions.</span><span class="sxs-lookup"><span data-stu-id="4ba03-104">Responsible maintenance workers can be related to asset types, assets, functional locations, maintenance job type categories, maintenance job types, maintenance job type variants, and trades.</span></span> <span data-ttu-id="4ba03-105">Ils peuvent être utilisés dans des ordres de travail et des demandes de maintenance pour indiquer une préférence concernant les agents de maintenance qui doivent être responsables d'un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="4ba03-105">They can be used on work orders and maintenance requests to indicate a preference about the maintenance workers who should be responsible for a work order.</span></span> <span data-ttu-id="4ba03-106">(Toutefois, ces agents de maintenance ne sont pas nécessairement les mêmes que ceux planifiés pour exécuter l'ordre de travail). L'utilisation de cette fonctionnalité est facultative.</span><span class="sxs-lookup"><span data-stu-id="4ba03-106">(However, those maintenance workers aren't necessarily the same workers who are scheduled to carry out the work order.) Use of this functionality is optional.</span></span> <span data-ttu-id="4ba03-107">Par exemple, elle peut être utilisée pour sélectionner des agents responsables ou des groupes d'agents pour des types de travail ou des domaines de travail spécifiques.</span><span class="sxs-lookup"><span data-stu-id="4ba03-107">For example, it can be used to select responsible workers or worker groups for specific work types or work areas.</span></span>

<span data-ttu-id="4ba03-108">Durant le cycle de vie d'un ordre de travail ou le cycle de vie d'une demande de maintenance, les agents de maintenance responsables peuvent être modifiés ou mis à jour.</span><span class="sxs-lookup"><span data-stu-id="4ba03-108">During a work order lifecycle or a maintenance request lifecycle, responsible maintenance workers can be changed or updated.</span></span> <span data-ttu-id="4ba03-109">Cette modification ou mise à jour peut être associée à, par exemple, un changement de l'état du cycle de vie de la demande de maintenance ou de l'état du cycle de vie de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="4ba03-109">This change or update might be related to, for example, a change in the maintenance request lifecycle state or the work order lifecycle state.</span></span>

<span data-ttu-id="4ba03-110">Le paramétrage dans la page **Agents de maintenance responsables** *n'est pas* utilisé lors de la planification des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="4ba03-110">The setup on the **Responsible maintenance workers** page is *not* used during work order scheduling.</span></span>

> [!NOTE]
> <span data-ttu-id="4ba03-111">Dans le module Gestion des actifs, vous pouvez également paramétrer des agents de maintenance *préférés* qui peuvent être affectés aux ordres de travail lors de la planification des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="4ba03-111">In Asset Management, you can also set up *preferred* maintenance workers who might be allocated to work orders during work order scheduling.</span></span>

<span data-ttu-id="4ba03-112">Avant de paramétrer des agents de maintenance responsables, vous devez paramétrer les agents et les groupes d'agents de maintenance qui doivent être disponibles pour sélection.</span><span class="sxs-lookup"><span data-stu-id="4ba03-112">Before you can set up responsible maintenance workers, you must set up the workers and maintenance worker groups that should be available for selection.</span></span> <span data-ttu-id="4ba03-113">Pour plus d'informations sur le paramétrage des agents et des groupes d'agents de maintenance, voir [Agents de maintenance et groupes d'agents](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="4ba03-113">For information about how to set up workers and maintenance worker groups, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

## <a name="set-up-responsible-maintenance-workers"></a><span data-ttu-id="4ba03-114">Définir des agents de maintenance responsables</span><span class="sxs-lookup"><span data-stu-id="4ba03-114">Set up responsible maintenance workers</span></span>

1. <span data-ttu-id="4ba03-115">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Collaborateurs** \> **Agents de maintenance responsables**.</span><span class="sxs-lookup"><span data-stu-id="4ba03-115">Select **Asset management** \> **Setup** \> **Workers** \> **Responsible maintenance workers**.</span></span>
2. <span data-ttu-id="4ba03-116">Sélectionnez **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="4ba03-116">Select **New** to create a record.</span></span>
3. <span data-ttu-id="4ba03-117">Créez d'abord un paramétrage d'agent de maintenance responsable ou de groupe d'agents de maintenance responsables par défaut, où vous définissez uniquement le champ **Groupe d'agents de maintenance responsables** et/ou le champ **Collaborateur responsable**.</span><span class="sxs-lookup"><span data-stu-id="4ba03-117">First create a default responsible maintenance worker or responsible maintenance worker group setup, where you set only the **Responsible maintenance worker group** field and/or the **Responsible worker** field.</span></span> <span data-ttu-id="4ba03-118">Laissez les autres champs vides.</span><span class="sxs-lookup"><span data-stu-id="4ba03-118">Leave the remaining fields blank.</span></span> <span data-ttu-id="4ba03-119">Ce paramétrage par défaut sera utilisé lors de la planification des ordres de travail si aucune autre combinaison plus spécifique ne correspond au contenu de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="4ba03-119">This default setup will be used during work order scheduling if no other, more specific combination matches the contents of the work order.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ba03-120">Lors de la création d'une demande de maintenance, lorsqu'un agent de maintenance responsable ou un groupe d'agents de maintenance responsables est disponible pour sélection dans la page **Toutes les demandes de maintenance**, le module Gestion des actifs recherche une correspondance possible dans tous les enregistrements d'agent de maintenance responsable.</span><span class="sxs-lookup"><span data-stu-id="4ba03-120">During creation of a maintenance request, when a responsible maintenance worker or responsible maintenance worker group is made available for selection on the **All maintenance requests** page, Asset Management goes through all responsible maintenance worker records to check for a possible match.</span></span> <span data-ttu-id="4ba03-121">Il vérifie toujours la combinaison la plus spécifique en premier.</span><span class="sxs-lookup"><span data-stu-id="4ba03-121">It always checks the most specific combination first.</span></span> <span data-ttu-id="4ba03-122">En d'autres termes, le module Gestion des actifs recherche d'abord une correspondance pour le champ **Transaction**.</span><span class="sxs-lookup"><span data-stu-id="4ba03-122">In other words, Asset Management first checks for a match for the **Trade** field.</span></span> <span data-ttu-id="4ba03-123">Si aucune correspondance n'est trouvée, il recherche une correspondance pour le champ **Variante du type de tâche de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="4ba03-123">If no match is found, it checks for a match for the **Maintenance job type variant** field.</span></span> <span data-ttu-id="4ba03-124">Si aucune correspondance n'est trouvée, il recherche une correspondance pour le champ **Type de tâche de maintenance**, etc.</span><span class="sxs-lookup"><span data-stu-id="4ba03-124">If no match is found, it checks for a match for the **Maintenance job type** field, and so on.</span></span> <span data-ttu-id="4ba03-125">Comme vous pouvez voir dans la disposition de la page, ce comportement signifie que, pour trouver la combinaison la plus spécifique, le module Gestion des actifs recherche une correspondance dans chaque enregistrement en allant de la droite vers la gauche (d'abord **Transaction**, puis **Variante du type de tâche de maintenance**, puis **Type de tâche de maintenance**, puis **Catégorie de type de tâche de maintenance**, puis **Poste technique**, puis **Actif** et enfin **Type d'actif**).</span><span class="sxs-lookup"><span data-stu-id="4ba03-125">As you can see in the layout of the page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match (first **Trade**, then **Maintenance job type variant**, then **Maintenance job type**, then **Maintenance job type category**, then **Functional location**, then **Asset**, and finally **Asset type**).</span></span> <span data-ttu-id="4ba03-126">Si aucune correspondance n'est trouvée, l'enregistrement par défaut qui ne comporte aucune sélection dans ces sept champs est utilisé.</span><span class="sxs-lookup"><span data-stu-id="4ba03-126">If no match is found, the default record that has no selections in those seven fields is used.</span></span>

<span data-ttu-id="4ba03-127">L'illustration suivante présente un exemple de la page **Agents de maintenance responsables**.</span><span class="sxs-lookup"><span data-stu-id="4ba03-127">The following illustration shows an example of the **Responsible maintenance workers** page.</span></span>

![Page Collaborateurs responsables de la maintenance](media/08-setup-for-requests.png)
