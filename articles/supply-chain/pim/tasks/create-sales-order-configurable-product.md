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
ms.openlocfilehash: 8607de5705354aa58c985fb536f3e1d52acd1f37
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921287"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a><span data-ttu-id="36e93-103">Créer une commande client pour un produit configurable</span><span class="sxs-lookup"><span data-stu-id="36e93-103">Create a sales order for a configurable product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="36e93-104">Cette procédure explique comment appliquer un modèle de configuration à un produit dans une commande client.</span><span class="sxs-lookup"><span data-stu-id="36e93-104">This procedure shows how to apply a configuration template to a product on a sales order.</span></span> <span data-ttu-id="36e93-105">Cet exemple utilise le modèle de haut-parleur D0006 dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="36e93-105">This example uses the D0006 speaker model in the USMF demo data company.</span></span> <span data-ttu-id="36e93-106">Généralement, un processeur de commande client utilise cette procédure.</span><span class="sxs-lookup"><span data-stu-id="36e93-106">Typically, a sales order processor uses this procedure.</span></span>

## <a name="create-a-sales-order"></a><span data-ttu-id="36e93-107">Créer une commande client</span><span class="sxs-lookup"><span data-stu-id="36e93-107">Create a sales order</span></span>

1. <span data-ttu-id="36e93-108">Accédez à **Ventes et marketing \> Espaces de travail \> Traitement et recherche de commande client**.</span><span class="sxs-lookup"><span data-stu-id="36e93-108">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="36e93-109">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="36e93-109">Select **New**.</span></span>
1. <span data-ttu-id="36e93-110">Sélectionnez **Commandes client**.</span><span class="sxs-lookup"><span data-stu-id="36e93-110">Select **Sales order**.</span></span>
1. <span data-ttu-id="36e93-111">Dans le champ **Compte client**, sélectionnez *US-001*.</span><span class="sxs-lookup"><span data-stu-id="36e93-111">In the **Customer account** field, select *US-001*.</span></span> 
1. <span data-ttu-id="36e93-112">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="36e93-112">Select **OK**.</span></span>
1. <span data-ttu-id="36e93-113">Dans le champ **Numéro d’article**, sélectionnez *D0006*.</span><span class="sxs-lookup"><span data-stu-id="36e93-113">In the **Item number** field, select *D0006*.</span></span>
    * <span data-ttu-id="36e93-114">Pour cette tâche, vous devez sélectionner un produit configurable.</span><span class="sxs-lookup"><span data-stu-id="36e93-114">For this task, you must select a configurable product.</span></span>  
1. <span data-ttu-id="36e93-115">Sélectionnez **Produit et approvisionnement**.</span><span class="sxs-lookup"><span data-stu-id="36e93-115">Select **Product and supply**.</span></span>
1. <span data-ttu-id="36e93-116">Sélectionnez **Configurer la ligne**.</span><span class="sxs-lookup"><span data-stu-id="36e93-116">Select **Configure line**.</span></span>
    * <span data-ttu-id="36e93-117">Notez que le prix a été modifié sur la base de la configuration sélectionnée et que le champ **Inclure le câble** est désormais défini sur *True*.</span><span class="sxs-lookup"><span data-stu-id="36e93-117">Note that the price has changed, based on the configuration that was selected, and that the **Include cable** field is now set to *True*.</span></span>  
    * <span data-ttu-id="36e93-118">Notez le prix par défaut et les paramètres sélectionnés pour le câble.</span><span class="sxs-lookup"><span data-stu-id="36e93-118">Note the default price and the settings that are selected for the cable.</span></span>  
1. <span data-ttu-id="36e93-119">Sélectionnez **Charger un modèle**.</span><span class="sxs-lookup"><span data-stu-id="36e93-119">Select **Load template**.</span></span>
    * <span data-ttu-id="36e93-120">Cet exemple décrit comment appliquer un modèle pour sélectionner une configuration prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="36e93-120">This example shows how you can apply a template to select a predefined configuration.</span></span> <span data-ttu-id="36e93-121">Si vous utilisez cette procédure comme guide de tâche et souhaitez afficher les autres valeurs d’attribut disponibles, vous devez cliquer sur le bouton **Déverrouiller**.</span><span class="sxs-lookup"><span data-stu-id="36e93-121">If you're using this procedure as a task guide and want to see the other attribute values that are available, you must select the **Unlock** button.</span></span>  
1. <span data-ttu-id="36e93-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="36e93-122">Select **OK**.</span></span>
1. <span data-ttu-id="36e93-123">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="36e93-123">Select **OK**.</span></span>
1. <span data-ttu-id="36e93-124">Développez la section **Détails de ligne**.</span><span class="sxs-lookup"><span data-stu-id="36e93-124">Expand the **Line details** section.</span></span>
1. <span data-ttu-id="36e93-125">Sélectionnez l'onglet **Produit**.</span><span class="sxs-lookup"><span data-stu-id="36e93-125">Select the **Product** tab.</span></span>
    * <span data-ttu-id="36e93-126">La configuration de l’article est maintenant répertoriée sous les dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="36e93-126">The configuration of the item is now listed under the product dimensions.</span></span>  
1. <span data-ttu-id="36e93-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="36e93-127">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]