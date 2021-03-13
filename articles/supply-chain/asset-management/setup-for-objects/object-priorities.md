---
title: Niveaux de service de l'actif
description: Cette rubrique explique les niveaux de service de l'actif dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 83b195add44927d847491e6394e72637323117b3
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021627"
---
# <a name="asset-service-levels"></a><span data-ttu-id="90eb7-103">Niveaux de service de l'actif</span><span class="sxs-lookup"><span data-stu-id="90eb7-103">Asset service levels</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="90eb7-104">Cette rubrique explique les niveaux de service de l'actif dans le module Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="90eb7-104">This topic explains asset service levels in Asset Management.</span></span> <span data-ttu-id="90eb7-105">Les niveaux de service de l'actif sont associés aux actifs, et sont transférés vers les demandes de maintenance et les ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="90eb7-105">Asset service levels are related to assets, and are transferred to maintenance requests and work orders.</span></span> <span data-ttu-id="90eb7-106">Ils sont utilisés pour calculer la priorité des ordres de travail lors de la planification des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="90eb7-106">They are used to calculate the priority of work orders during work order scheduling.</span></span> <span data-ttu-id="90eb7-107">Les niveaux de service de l'actif peuvent être modifiés, si cela est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="90eb7-107">Asset service levels can be changed, if changes are required.</span></span>

<span data-ttu-id="90eb7-108">Pour plus d'informations sur le paramétrage lié au calcul des scores pour la planification des ordres de travail, voir [Paramètres de gestion des actifs](../setup-for-objects/enterprise-asset-management-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="90eb7-108">For more information about the setup that is related to the calculation of rating scores for work order scheduling, see [Asset Management parameters](../setup-for-objects/enterprise-asset-management-parameters.md).</span></span> <span data-ttu-id="90eb7-109">Vous devez paramétrer au moins un enregistrement par défaut pour le niveau de service de l'actif.</span><span class="sxs-lookup"><span data-stu-id="90eb7-109">You must set up at least one default record for the asset service level.</span></span> <span data-ttu-id="90eb7-110">Cet enregistrement par défaut est utilisé si aucune autre correspondance n'est trouvée lors de la planification des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="90eb7-110">This default record is used if no other match is found during work order scheduling.</span></span>

<span data-ttu-id="90eb7-111">**Exemple 1 :** niveau de service par défaut qui est utilisé si aucune autre correspondance n'est trouvée.</span><span class="sxs-lookup"><span data-stu-id="90eb7-111">**Example 1:** The default service level that is used if no other match is found.</span></span> <span data-ttu-id="90eb7-112">Dans cet enregistrement, vous sélectionnez uniquement un niveau de service.</span><span class="sxs-lookup"><span data-stu-id="90eb7-112">In this record, you select only a service level.</span></span>

<span data-ttu-id="90eb7-113">**Exemple 2 :** niveau de service élevé qui est utilisé pour planifier des tâches pour un moteur de camion Volvo.</span><span class="sxs-lookup"><span data-stu-id="90eb7-113">**Example 2:** A high service level that is used to schedule jobs for a Volvo truck engine.</span></span> <span data-ttu-id="90eb7-114">Dans cet enregistrement, vous sélectionnez un type d'actif approprié (par exemple, **Moteur de camion**), un fabricant (**Volvo**) et un niveau de service.</span><span class="sxs-lookup"><span data-stu-id="90eb7-114">In this record, you select a relevant asset type (such as **Truck Engine**), a manufacturer (**Volvo**), and a service level.</span></span>

## <a name="set-up-asset-service-levels"></a><span data-ttu-id="90eb7-115">Paramétrer les niveaux de service de l'actif</span><span class="sxs-lookup"><span data-stu-id="90eb7-115">Set up asset service levels</span></span>

1. <span data-ttu-id="90eb7-116">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Niveaux de service d'actifs**.</span><span class="sxs-lookup"><span data-stu-id="90eb7-116">Select **Asset management** \> **Setup** \> **Asset service levels**.</span></span>
2. <span data-ttu-id="90eb7-117">Sélectionnez **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="90eb7-117">Select **New** to create a record.</span></span>
3. <span data-ttu-id="90eb7-118">En fonction du niveau de détail requis pour le niveau de service de l'actif, effectuez les sélections appropriées dans les champs **Poste technique**, **Type d'actif**, **Fabricant**, **Modèle**, **Actif**, **Type d'ordre de travail** et **Niveau de service**.</span><span class="sxs-lookup"><span data-stu-id="90eb7-118">Depending on the detail level that is required for the asset service level, make relevant selections in the **Functional location**, **Asset type**, **Manufacturer**, **Model**, **Asset**, **Work order type**, and **Service level** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="90eb7-119">Lorsque le niveau de service de l'actif est utilisé pour les demandes de maintenance et les ordres de travail, le module Gestion des actifs recherche une correspondance possible dans tous les enregistrements de niveau de service d'actif.</span><span class="sxs-lookup"><span data-stu-id="90eb7-119">When the asset service level is used for maintenance requests and work orders, Asset Management goes through all asset service level records to check for a possible match.</span></span> <span data-ttu-id="90eb7-120">Il vérifie toujours la combinaison la plus spécifique en premier.</span><span class="sxs-lookup"><span data-stu-id="90eb7-120">It always checks the most specific combination first.</span></span> <span data-ttu-id="90eb7-121">En d'autres termes, le module Gestion des actifs recherche d'abord une correspondance pour le champ **Type d'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="90eb7-121">In other words, Asset Management first checks for a match for the **Work order type** field.</span></span> <span data-ttu-id="90eb7-122">Si aucune correspondance n'est trouvée, il recherche une correspondance pour le champ **Actif**, etc.</span><span class="sxs-lookup"><span data-stu-id="90eb7-122">If no match is found, it checks for a match for the **Asset** field, and so on.</span></span> <span data-ttu-id="90eb7-123">Comme vous pouvez voir dans la disposition de la page **Niveaux de service d'actifs**, ce comportement signifie que, pour trouver la combinaison la plus spécifique, le module Gestion des actifs recherche une correspondance dans chaque enregistrement en allant de la droite vers la gauche.</span><span class="sxs-lookup"><span data-stu-id="90eb7-123">As you can see in the layout of the **Asset service levels** page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="90eb7-124">Si aucune correspondance n'est trouvée, l'enregistrement par défaut qui ne comporte aucune sélection dans ces champs est utilisé.</span><span class="sxs-lookup"><span data-stu-id="90eb7-124">If no match is found, the default record that has no selections in those fields is used.</span></span>

4. <span data-ttu-id="90eb7-125">Dans le champ **Niveau de service**, sélectionnez un nombre qui indique le niveau de service (priorité).</span><span class="sxs-lookup"><span data-stu-id="90eb7-125">In the **Service level** field, select a number that indicates the service level (priority).</span></span>


> [!NOTE]
> <span data-ttu-id="90eb7-126">Si vous modifiez un enregistrement de niveau de service d'actif dans la page **Niveaux de service d'actifs** après l'avoir déjà utilisé sur un ordre de travail, le niveau de service des demandes de maintenance et des ordres de travail n'est pas mis à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="90eb7-126">If you change an asset service level record on the **Asset service levels** page after you've already used it on a work order, the service level on maintenance requests and work orders isn't updated accordingly.</span></span>
