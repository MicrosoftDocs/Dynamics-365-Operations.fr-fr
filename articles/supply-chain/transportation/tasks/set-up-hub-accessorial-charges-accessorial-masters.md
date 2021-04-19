---
title: Paramétrer des frais annexes de terminal et des données principales annexes
description: Cette procédure décrit la création de données principales annexes pour un terminal et l’utilisation de ces données principales pour créer des frais annexes de terminal.
author: ShylaThompson
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSCarrierAccessorial,TMSAccessorialMaster, TMSHubAccessorial
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8f4c0d3af96e6ef6735b01165a49c1450b3b633b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837560"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a><span data-ttu-id="4e30f-103">Paramétrer des frais annexes de terminal et des données principales annexes</span><span class="sxs-lookup"><span data-stu-id="4e30f-103">Set up hub accessorial charges and accessorial masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4e30f-104">Cette procédure décrit la création de données principales annexes pour un terminal et l’utilisation de ces données principales pour créer des frais annexes de terminal.</span><span class="sxs-lookup"><span data-stu-id="4e30f-104">This procedure shows how to create an accessorial master for a hub and use that master to create a hub accessorial charge.</span></span> <span data-ttu-id="4e30f-105">La procédure utilise le dataset USMF.</span><span class="sxs-lookup"><span data-stu-id="4e30f-105">The procedure uses the USMF dataset.</span></span> <span data-ttu-id="4e30f-106">Cette configuration est généralement réalisée par un coordinateur transport.</span><span class="sxs-lookup"><span data-stu-id="4e30f-106">This set up will typically be done by a transportation coordinator.</span></span>


## <a name="set-up-a-hub-master"></a><span data-ttu-id="4e30f-107">Paramétrer une table maître de transbordement</span><span class="sxs-lookup"><span data-stu-id="4e30f-107">Set up a hub master</span></span>
1. <span data-ttu-id="4e30f-108">Accédez à Gestion du transport > Configurer > Taux > Données principales de l’élément accessoire.</span><span class="sxs-lookup"><span data-stu-id="4e30f-108">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="4e30f-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4e30f-109">Click New.</span></span>
3. <span data-ttu-id="4e30f-110">Dans le champ Données principales annexes, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4e30f-110">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="4e30f-111">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="4e30f-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="4e30f-112">Dans le champ Type d’annexe, sélectionnez « Terminal ».</span><span class="sxs-lookup"><span data-stu-id="4e30f-112">In the Accessorial type field, select 'Hub'.</span></span>
6. <span data-ttu-id="4e30f-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="4e30f-113">Click Save.</span></span>
7. <span data-ttu-id="4e30f-114">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="4e30f-114">Close the page.</span></span>

## <a name="set-up-a-hub-accessorial-charge"></a><span data-ttu-id="4e30f-115">Paramétrer des frais annexes de terminal</span><span class="sxs-lookup"><span data-stu-id="4e30f-115">Set up a hub accessorial charge</span></span>
1. <span data-ttu-id="4e30f-116">Accédez à Gestion du transport > Configurer > Classement > Frais annexes du terminal.</span><span class="sxs-lookup"><span data-stu-id="4e30f-116">Go to Transportation management > Setup > Rating > Hub accessorial charges.</span></span>
2. <span data-ttu-id="4e30f-117">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4e30f-117">Click New.</span></span>
3. <span data-ttu-id="4e30f-118">Dans le champ ID annexe du terminal, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4e30f-118">In the Hub accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="4e30f-119">Dans le champ Point de transbordement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="4e30f-119">In the Hub field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="4e30f-120">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="4e30f-120">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="4e30f-121">Dans le champ Position du terminal, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="4e30f-121">In the Hub position field, select an option.</span></span>
    * <span data-ttu-id="4e30f-122">Vous pouvez créer les frais pour le lieu d’enlèvement ou le lieu de livraison.</span><span class="sxs-lookup"><span data-stu-id="4e30f-122">You can either create the charge as a pickup or drop-off.</span></span> <span data-ttu-id="4e30f-123">En fonction de votre choix, les frais seront appliqués au segment de transport correspondant sur votre route.</span><span class="sxs-lookup"><span data-stu-id="4e30f-123">Depending on your selection the charge will be applied to the corresponding transportation segment on your route.</span></span>  
7. <span data-ttu-id="4e30f-124">Dans le champ Données principales annexes, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="4e30f-124">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="4e30f-125">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4e30f-125">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4e30f-126">Sélectionnez les données principales que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="4e30f-126">Select the master you just created.</span></span>  
9. <span data-ttu-id="4e30f-127">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="4e30f-127">Click Save.</span></span>
10. <span data-ttu-id="4e30f-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="4e30f-128">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]