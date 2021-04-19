---
title: Créer une commande client pour un produit configurable
description: Cette procédure explique comment appliquer un modèle de configuration à un produit dans une commande client.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 81e573593fbbb0bf87e53c5cbd985b38a8db89ac
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841597"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a><span data-ttu-id="3ff0f-103">Créer une commande client pour un produit configurable</span><span class="sxs-lookup"><span data-stu-id="3ff0f-103">Create a sales order for a configurable product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3ff0f-104">Cette procédure explique comment appliquer un modèle de configuration à un produit dans une commande client.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-104">This procedure shows how to apply a configuration template to a product on a sales order.</span></span> <span data-ttu-id="3ff0f-105">Cet exemple utilise le modèle de haut-parleur D0006 dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-105">This example uses the D0006 speaker model in the USMF demo data company.</span></span> <span data-ttu-id="3ff0f-106">Généralement, un processeur de commande client utilise cette procédure.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-106">Typically, a sales order processor uses this procedure.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="3ff0f-107">Créer une commande client</span><span class="sxs-lookup"><span data-stu-id="3ff0f-107">Create a sales order</span></span>
1. <span data-ttu-id="3ff0f-108">Cliquez sur Traitement et recherche de commande client.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-108">Click Sales order processing and inquiry.</span></span>
2. <span data-ttu-id="3ff0f-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-109">Click New.</span></span>
3. <span data-ttu-id="3ff0f-110">Cliquez sur Commande client.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-110">Click Sales order.</span></span>
4. <span data-ttu-id="3ff0f-111">Dans le champ Compte client, sélectionnez US-001.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-111">In the Customer account field, select US-001.</span></span> 
5. <span data-ttu-id="3ff0f-112">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-112">Click OK.</span></span>
6. <span data-ttu-id="3ff0f-113">Sélectionnez D0006 dans le champ Numéro d’article.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-113">In the Item number field, select D0006.</span></span>
    * <span data-ttu-id="3ff0f-114">Pour cette tâche, vous devez sélectionner un produit configurable.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-114">For this task, you must select a configurable product.</span></span>  
7. <span data-ttu-id="3ff0f-115">Cliquez sur Produit et approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-115">Click Product and supply.</span></span>
8. <span data-ttu-id="3ff0f-116">Cliquez sur Configurer la ligne.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-116">Click Configure line.</span></span>
    * <span data-ttu-id="3ff0f-117">Notez que le prix a été modifié sur la base de la configuration sélectionnée et que le champ Inclure le câble est désormais défini sur True.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-117">Note that the price has changed, based on the configuration that was selected, and that the Include cable field is now set to True.</span></span>  
    * <span data-ttu-id="3ff0f-118">Notez le prix par défaut et les paramètres sélectionnés pour le câble.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-118">Note the default price and the settings that are selected for the cable.</span></span>  
9. <span data-ttu-id="3ff0f-119">Cliquez sur Charger un modèle.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-119">Click Load template.</span></span>
    * <span data-ttu-id="3ff0f-120">Cet exemple décrit comment appliquer un modèle pour sélectionner une configuration prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-120">This example shows how you can apply a template to select a predefined configuration.</span></span> <span data-ttu-id="3ff0f-121">Si vous utilisez cette procédure comme guide de tâche et souhaitez afficher les autres valeurs d’attribut disponibles, vous devez cliquer sur le bouton Déverrouiller.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-121">If you're using this procedure as a task guide and want to see the other attribute values that are available, you must click the Unlock button.</span></span>  
10. <span data-ttu-id="3ff0f-122">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-122">Click OK.</span></span>
11. <span data-ttu-id="3ff0f-123">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-123">Click OK.</span></span>
12. <span data-ttu-id="3ff0f-124">Développez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-124">Expand the Line details section.</span></span>
13. <span data-ttu-id="3ff0f-125">Cliquez sur l’onglet Produit.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-125">Click the Product tab.</span></span>
    * <span data-ttu-id="3ff0f-126">La configuration de l’article est maintenant répertoriée sous les dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-126">The configuration of the item is now listed under the product dimensions.</span></span>  
14. <span data-ttu-id="3ff0f-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3ff0f-127">Close the page.</span></span>

## <a name="select-the-product-configuration"></a><span data-ttu-id="3ff0f-128">Sélectionner la configuration du produit</span><span class="sxs-lookup"><span data-stu-id="3ff0f-128">Select the product configuration</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]