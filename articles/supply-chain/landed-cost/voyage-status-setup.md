---
title: Configuration du statut du voyage
description: Cette rubrique décrit comment établir les valeurs de statut que les utilisateurs peuvent attribuer aux voyages.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMStatusTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: e19a54fc9de166c93fd68408ca8c8c692dc96cab
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022106"
---
# <a name="voyage-status-setup"></a><span data-ttu-id="f28d6-103">Configuration du statut du voyage</span><span class="sxs-lookup"><span data-stu-id="f28d6-103">Voyage status setup</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f28d6-104">Sur la page **Statuts de voyage**, vous définissez l’ensemble des valeurs de statut que les utilisateurs peuvent attribuer aux voyages.</span><span class="sxs-lookup"><span data-stu-id="f28d6-104">On the **Voyage statuses** page, you establish the set of status values that users can assign to voyages.</span></span> <span data-ttu-id="f28d6-105">Les utilisateurs peuvent attribuer des valeurs de statut de voyage à tous les niveaux d’un voyage : voyage, conteneur d’expédition, folio, commande fournisseur et article (lignes d’achat et lignes d’ordre de transfert).</span><span class="sxs-lookup"><span data-stu-id="f28d6-105">Users can assign voyage status values to all levels of a voyage: voyage, shipping container, folio, purchase order, and item (purchase lines and transfer order lines).</span></span> <span data-ttu-id="f28d6-106">Ils sont utilisés à deux fins :</span><span class="sxs-lookup"><span data-stu-id="f28d6-106">They are used for two purposes:</span></span>

- <span data-ttu-id="f28d6-107">Informez l’utilisateur du statut du voyage, du conteneur d’expédition, du folio, de la commande fournisseur ou de l’article (lignes d’achat et lignes d’ordre de transfert).</span><span class="sxs-lookup"><span data-stu-id="f28d6-107">Inform the user about the status of the voyage, shipping container, folio, purchase order, or item (purchase lines and transfer order lines).</span></span>
- <span data-ttu-id="f28d6-108">Limitez l’utilisation de la zone de coûts en empêchant la modification ou la suppression.</span><span class="sxs-lookup"><span data-stu-id="f28d6-108">Limit the use of the cost area by preventing modification or deletion.</span></span>

<span data-ttu-id="f28d6-109">Pour configurer vos statuts de voyage, accédez à **Coût au débarquement \> Installer \> Statuts de voyage**.</span><span class="sxs-lookup"><span data-stu-id="f28d6-109">To set up your voyage statuses, go to **Landed cost \> Setup \> Voyage statuses**.</span></span> <span data-ttu-id="f28d6-110">Vous pouvez ajouter, supprimer et modifier des statuts avec les boutons du volet Actions.</span><span class="sxs-lookup"><span data-stu-id="f28d6-110">There, you can add, remove, and edit statuses by using the buttons on the Action Pane.</span></span>

<span data-ttu-id="f28d6-111">Chaque zone de coût a son propre ensemble et sa propre hiérarchie de statuts de voyage.</span><span class="sxs-lookup"><span data-stu-id="f28d6-111">Each cost area has its own set and hierarchy of voyage statuses.</span></span> <span data-ttu-id="f28d6-112">Par conséquent, sur la page **Statuts de voyage**, dans la **Zone de coût**, vous devez d’abord sélectionner la zone de coûts pour laquelle vous souhaitez afficher ou créer des statuts de voyage.</span><span class="sxs-lookup"><span data-stu-id="f28d6-112">Therefore, on the **Voyage statuses** page, in the **Cost area** field, you must first select the cost area that you want to view or create voyage statuses for.</span></span> <span data-ttu-id="f28d6-113">Ensuite, pour chaque statut de voyage, définissez les champs décrits dans le tableau suivant, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="f28d6-113">Then, for each voyage status, set the fields that are described in the following table, as required.</span></span> <span data-ttu-id="f28d6-114">Notez que le statut d’un voyage peut également être automatiquement modifié par des événements système, tels que des règles qui ont été établies à l’aide du centre de contrôle de suivi.</span><span class="sxs-lookup"><span data-stu-id="f28d6-114">Note that the status of a voyage can also be automatically changed by system events, such as rules that have been established by using the tracking control center.</span></span>

| <span data-ttu-id="f28d6-115">Champ</span><span class="sxs-lookup"><span data-stu-id="f28d6-115">Field</span></span> | <span data-ttu-id="f28d6-116">Description</span><span class="sxs-lookup"><span data-stu-id="f28d6-116">Description</span></span> |
|---|---|
| <span data-ttu-id="f28d6-117">Statut du voyage</span><span class="sxs-lookup"><span data-stu-id="f28d6-117">Voyage status</span></span> | <span data-ttu-id="f28d6-118">Entrez le nom du statut de voyage.</span><span class="sxs-lookup"><span data-stu-id="f28d6-118">Enter the name of the voyage status.</span></span> |
| <span data-ttu-id="f28d6-119">Description</span><span class="sxs-lookup"><span data-stu-id="f28d6-119">Description</span></span> | <span data-ttu-id="f28d6-120">Entrez une description du statut de voyage.</span><span class="sxs-lookup"><span data-stu-id="f28d6-120">Enter a description of the voyage status.</span></span> |
| <span data-ttu-id="f28d6-121">Modifier</span><span class="sxs-lookup"><span data-stu-id="f28d6-121">Modify</span></span> | <span data-ttu-id="f28d6-122">Cochez cette case si les utilisateurs sont autorisés à modifier les voyages qui ont ce statut.</span><span class="sxs-lookup"><span data-stu-id="f28d6-122">Select this check box if users are allowed to modify voyages that have this status.</span></span> |
| <span data-ttu-id="f28d6-123">Retirer</span><span class="sxs-lookup"><span data-stu-id="f28d6-123">Delete</span></span> | <span data-ttu-id="f28d6-124">Cochez cette case si les utilisateurs sont autorisés à supprimer les voyages qui ont ce statut.</span><span class="sxs-lookup"><span data-stu-id="f28d6-124">Select this check box if users are allowed to delete voyages that have this status.</span></span> |
| <span data-ttu-id="f28d6-125">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="f28d6-125">Mandatory</span></span> | <span data-ttu-id="f28d6-126">Cochez cette case pour rendre le statut du voyage obligatoire, afin qu’il ne puisse pas être ignoré.</span><span class="sxs-lookup"><span data-stu-id="f28d6-126">Select this check box to make the voyage status mandatory, so that it can't be skipped.</span></span> |
| <span data-ttu-id="f28d6-127">Parent</span><span class="sxs-lookup"><span data-stu-id="f28d6-127">Parent</span></span> | <span data-ttu-id="f28d6-128">Utilisez ce champ pour établir une hiérarchie entre les valeurs de statut.</span><span class="sxs-lookup"><span data-stu-id="f28d6-128">Use this field to establish a hierarchy among the status values.</span></span> <span data-ttu-id="f28d6-129">Les statuts de voyage peuvent être modifiés (manuellement ou automatiquement) uniquement vers le bas dans la hiérarchie, d’un statut parent à l’un de ses statuts enfants.</span><span class="sxs-lookup"><span data-stu-id="f28d6-129">Voyage statuses can be changed (either manually or automatically) only downward in the hierarchy, from a parent status to one of its child statuses.</span></span>

> [!NOTE]
> <span data-ttu-id="f28d6-130">Vous devez configurer uniquement les statuts de voyage spécifiques utilisés par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f28d6-130">You have to set up only the specific voyage statuses that your organization uses.</span></span> <span data-ttu-id="f28d6-131">Les statuts de voyage typiques incluent *Confirmé*, *Marchandises en transit*, *Reçu*, *Prêt pour l’évaluation des coûts*, et *Évaluer les coûts*.</span><span class="sxs-lookup"><span data-stu-id="f28d6-131">Typical voyage statuses include *Confirmed*, *Goods in transit*, *Received*, *Ready for costing*, and *Costed*.</span></span> <span data-ttu-id="f28d6-132">Cependant, d’autres statuts peuvent être présents.</span><span class="sxs-lookup"><span data-stu-id="f28d6-132">However, other statuses might be present.</span></span>
