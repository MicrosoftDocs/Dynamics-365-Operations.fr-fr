---
title: Paramétrage des entrepôts pour les ordres de transfert
description: Cette rubrique décrit la procédure de paramétrage des entrepôts pour les ordres de transfert.
author: Mirzaab
manager: tfehr
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation,CustVendTransportPoint2Point
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 7dfb215683b4ee5d186626492bd90116d1a06a1d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976836"
---
# <a name="set-up-warehouses-for-transfer-orders"></a><span data-ttu-id="40da2-103">Paramétrage des entrepôts pour les ordres de transfert</span><span class="sxs-lookup"><span data-stu-id="40da2-103">Set up warehouses for transfer orders</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="40da2-104">Les niveaux d'entrepôt permettent de créer une hiérarchie prenant en charge les ordres de transfert entre entrepôts.</span><span class="sxs-lookup"><span data-stu-id="40da2-104">You can use warehouse levels to create a hierarchy that supports transfer orders between warehouses.</span></span> <span data-ttu-id="40da2-105">À partir de ce paramétrage, le calcul PDP/MRP calcule les demandes d'articles au niveau d'entrepôt individuel et génère des ordres de transfert prévisionnels à partir d'un entrepôt source affecté pour les exécuter.</span><span class="sxs-lookup"><span data-stu-id="40da2-105">Based on this setup, master scheduling calculates item requirements at the individual warehouse level and generates planned transfer orders from an assigned source warehouse to fulfill them.</span></span>

1.  <span data-ttu-id="40da2-106">Cliquez sur **Gestion des stocks > Paramétrage > Décomposition du stock > Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="40da2-106">Click **Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>

2.  <span data-ttu-id="40da2-107">Sélectionnez l'entrepôt à recharger.</span><span class="sxs-lookup"><span data-stu-id="40da2-107">Select the warehouse that you want to refill.</span></span>

3.  <span data-ttu-id="40da2-108">Dans l'organisateur **Planification**, activez la case à cocher **Rechargement**.</span><span class="sxs-lookup"><span data-stu-id="40da2-108">On the **Master planning** FastTab, select the **Refilling** check box.</span></span>

4.  <span data-ttu-id="40da2-109">Dans le champ **Entrepôt principal**, sélectionnez l'entrepôt à désigner comme entrepôt source du rechargement.</span><span class="sxs-lookup"><span data-stu-id="40da2-109">In the **Main warehouse** field, select the warehouse that you want to assign as the refilling warehouse.</span></span> <span data-ttu-id="40da2-110">Le PDP/MRP calcule une demande de transfert pour l'entrepôt sélectionné et génère un ordre de transfert prévisionnel à partir de l'**Entrepôt principal** assigné.</span><span class="sxs-lookup"><span data-stu-id="40da2-110">Master scheduling calculates a transfer requirement for the selected warehouse and generates a planned transfer order from the assigned **Main warehouse**.</span></span>
   
    > [!NOTE]
    > <P><span data-ttu-id="40da2-111">Si vous ne cochez pas la case <STRONG>Rechargement</STRONG>, l'entrepôt sélectionné se voit attribuer un niveau d'entrepôt lié à <STRONG>Entrepôt principal</STRONG>, mais <STRONG>Entrepôt principal</STRONG> n'est pas paramétré comme entrepôt de rechargement.</span><span class="sxs-lookup"><span data-stu-id="40da2-111">If you clear the <STRONG>Refilling</STRONG> check box, the selected warehouse is assigned a warehouse level in regard to the <STRONG>Main warehouse</STRONG>, but the <STRONG>Main warehouse</STRONG> is not set up as a refilling warehouse.</span></span></P>

5.  <span data-ttu-id="40da2-112">Fermez la page pour appliquer le nouveau paramétrage.</span><span class="sxs-lookup"><span data-stu-id="40da2-112">Close the page to apply the new setup.</span></span>


> [!TIP]
> <P><span data-ttu-id="40da2-113">Si vous souhaitez désigner un entrepôt pour le rechargement, vous devez commencer par définir l'entrepôt comme une dimension de stock sur la page <STRONG>Groupes de dimension de stockage</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="40da2-113">If you want to assign a warehouse for refilling, you must first set up the warehouse as a storage dimension on the <STRONG>Storage dimension groups</STRONG> page.</span></span> <span data-ttu-id="40da2-114">Sur cette page, sélectionnez le champ <STRONG>Actif</STRONG> et le champ <STRONG>Plan de couverture par dimension</STRONG> pour l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="40da2-114">On this page, select the <STRONG>Active</STRONG> field and the <STRONG>Coverage plan by dimension</STRONG> field for the warehouse.</span></span></P>

## <a name="set-up-transport-lead-time"></a><span data-ttu-id="40da2-115">Paramétrer le délai de transport</span><span class="sxs-lookup"><span data-stu-id="40da2-115">Set up transport lead time</span></span>

<span data-ttu-id="40da2-116">Vous devez également paramétrer le délai de transport entre les entrepôts sur la page **Jours de transport**.</span><span class="sxs-lookup"><span data-stu-id="40da2-116">You must also set up the transport lead time between the warehouses on the **Transport days** page.</span></span> 
1. <span data-ttu-id="40da2-117">Accédez à **Gestion des stocks > Paramétrage > Distribution > Jours de transport**.</span><span class="sxs-lookup"><span data-stu-id="40da2-117">Go to **Inventory management > Setup > Distribution > Transport days**.</span></span>
2. <span data-ttu-id="40da2-118">Dans le champ **Point de réception**, sélectionnez **Entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="40da2-118">In the **Receiving point** field, select **warehouse**.</span></span>
3. <span data-ttu-id="40da2-119">Sélectionnez **Entrepôt d'expédition**, **Entrepôt de réception** et **Jours de transport**.</span><span class="sxs-lookup"><span data-stu-id="40da2-119">Select the **Shipping warehouse**, **Receiving warehouse**, and **Transport days**.</span></span> 
4. <span data-ttu-id="40da2-120">(En option) Vous pouvez également définir la durée de transport, en fonction du mode de livraison, sous l'onglet **Jours de transport par mode de livraison**.</span><span class="sxs-lookup"><span data-stu-id="40da2-120">(Optional) You can also set transport time, depending on the mode of delivery, under the **Transport days per mode of delivery** tab.</span></span>
