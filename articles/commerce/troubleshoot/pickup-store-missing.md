---
title: Le magasin de vente au détail n’apparaît pas dans la liste des magasins disponibles pour le retrait
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un magasin de vente au détail n’apparaît pas dans la liste des magasins où les articles peuvent être retirés.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9974b3e10bbdcd2e8a8723a3be4b70401bb9e546
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801601"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a><span data-ttu-id="c88b9-103">Le magasin de vente au détail n’apparaît pas dans la liste des magasins disponibles pour le retrait</span><span class="sxs-lookup"><span data-stu-id="c88b9-103">Retail store doesn't appear in the list of stores to pick up from</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c88b9-104">Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un magasin de vente au détail n’apparaît pas dans la liste des magasins où les articles peuvent être retirés.</span><span class="sxs-lookup"><span data-stu-id="c88b9-104">This topic provides troubleshooting guidance that can help when a retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="description"></a><span data-ttu-id="c88b9-105">Description</span><span class="sxs-lookup"><span data-stu-id="c88b9-105">Description</span></span>

<span data-ttu-id="c88b9-106">Un magasin de détail n’apparaît pas dans la liste des magasins où les articles peuvent être retirés.</span><span class="sxs-lookup"><span data-stu-id="c88b9-106">A retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="resolution"></a><span data-ttu-id="c88b9-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="c88b9-107">Resolution</span></span>

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a><span data-ttu-id="c88b9-108">Configurer la longitude et la latitude de l’adresse du magasin dans Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="c88b9-108">Configure the longitude and latitude for the store address in Commerce headquarters</span></span>

<span data-ttu-id="c88b9-109">Pour configurer la longitude et la latitude de l’adresse du magasin dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c88b9-109">To configure the longitude and latitude for the store address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="c88b9-110">Accédez à **Retail et Commerce \> Canaux \> Magasins \> Tous les magasins**.</span><span class="sxs-lookup"><span data-stu-id="c88b9-110">Go to **Retail and Commerce \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="c88b9-111">Trouvez le magasin que vous souhaitez voir apparaître parmi les options de retrait sur le site d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="c88b9-111">Find the store that you want to appear among the pickup options on the e-commerce site.</span></span> <span data-ttu-id="c88b9-112">Notez la valeur du champ **Numéro d’unité opérationnelle**.</span><span class="sxs-lookup"><span data-stu-id="c88b9-112">Make a note of its **Operating unit number** value.</span></span>
1. <span data-ttu-id="c88b9-113">Accédez à **Administration d’organisation \> Organisations \> Unités opérationnelles**.</span><span class="sxs-lookup"><span data-stu-id="c88b9-113">Go to **Organization administration \> Organizations \> Operating units**.</span></span>
1. <span data-ttu-id="c88b9-114">Recherchez le numéro d’unité opérationnelle que vous avez noté précédemment, puis sélectionnez l’unité opérationnelle dans les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="c88b9-114">Search for the operating unit number that you noted earlier, and then select the operating unit in the search results.</span></span>
1. <span data-ttu-id="c88b9-115">Sur le raccourci **Adresses**, sélectionnez **Plus d’options**, puis sélectionnez **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="c88b9-115">On the **Addresses** FastTab, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="c88b9-116">Sur le raccourci **Général**, assurez-vous que les champs **Longitude** et **Latitude** sont correctement définis.</span><span class="sxs-lookup"><span data-stu-id="c88b9-116">On the **General** FastTab, make sure that the **Longitude** and **Latitude** fields are correctly set.</span></span> <span data-ttu-id="c88b9-117">Dans le cadre de cette étape, assurez-vous que les valeurs sont correctement spécifiées sous forme de nombres positifs ou négatifs.</span><span class="sxs-lookup"><span data-stu-id="c88b9-117">As part of this step, make sure that the values are correctly specified as positive or negative numbers.</span></span>

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a><span data-ttu-id="c88b9-118">Configurer les groupes d’exécution dans Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="c88b9-118">Configure fulfillment groups in Commerce headquarters</span></span>

<span data-ttu-id="c88b9-119">Pour configurer les groupes d’exécution dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c88b9-119">To configure fulfillment groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="c88b9-120">Accédez à **Commerce et vente au détail \> Canaux \> Magasins en ligne**.</span><span class="sxs-lookup"><span data-stu-id="c88b9-120">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="c88b9-121">Sélectionnez le magasin en ligne à configurer.</span><span class="sxs-lookup"><span data-stu-id="c88b9-121">Select the online store to configure.</span></span>
1. <span data-ttu-id="c88b9-122">Dans le volet Actions, sélectionnez **Paramétrer**, puis **Affectation du groupe d’exécution**.</span><span class="sxs-lookup"><span data-stu-id="c88b9-122">On the Action Pane, select **Set up**, and then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="c88b9-123">Sur la page **Affectation du groupe d’exécution**, sélectionnez le groupe d’exécution pour le magasin en ligne.</span><span class="sxs-lookup"><span data-stu-id="c88b9-123">On the **Fulfillment group assignment** page, select the fulfillment group for the online store.</span></span>
1. <span data-ttu-id="c88b9-124">Sous **Paramétrer**, assurez-vous que le magasin de vente au détail est correctement configuré pour le groupe d’exécution.</span><span class="sxs-lookup"><span data-stu-id="c88b9-124">Under **Setup**, make sure that the retail store is correctly configured for the fulfillment group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c88b9-125">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c88b9-125">Additional resources</span></span> 

[<span data-ttu-id="c88b9-126">Créer une unité opérationnelle</span><span class="sxs-lookup"><span data-stu-id="c88b9-126">Create an operating unit</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit)

[<span data-ttu-id="c88b9-127">Paramétrer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="c88b9-127">Set up an online channel</span></span>](../channel-setup-online.md)
