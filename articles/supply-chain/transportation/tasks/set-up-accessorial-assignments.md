---
title: Paramétrer les affectations d'élément accessoire
description: Cette procédure décrit comment paramétrer une affectation d'élément accessoire.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSAccessorialAssignment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28562772c52d06fbb2004bd3a01a7bfa32f58a4e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974033"
---
# <a name="set-up-accessorial-assignments"></a><span data-ttu-id="406d4-103">Paramétrer les affectations d'élément accessoire</span><span class="sxs-lookup"><span data-stu-id="406d4-103">Set up accessorial assignments</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="406d4-104">Cette procédure décrit comment paramétrer une affectation d'élément accessoire.</span><span class="sxs-lookup"><span data-stu-id="406d4-104">This procedure shows how to set up an accessorial assignment.</span></span> <span data-ttu-id="406d4-105">Cette opération est généralement réalisée par un coordinateur transport.</span><span class="sxs-lookup"><span data-stu-id="406d4-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="406d4-106">Avant d'utiliser ce guide, vous devez suivre le guide « Configurer les frais annexes de terminal et les données principales annexes ».</span><span class="sxs-lookup"><span data-stu-id="406d4-106">Before you use this guide you need to run the "Set up hub accessorial charges and accessorial masters" guide.</span></span>


## <a name="set-up-accessorial-assignment"></a><span data-ttu-id="406d4-107">Paramétrer l'affectation d'élément accessoire</span><span class="sxs-lookup"><span data-stu-id="406d4-107">Set up Accessorial assignment</span></span>
1. <span data-ttu-id="406d4-108">Allez dans Gestion du transport > Configurer > Classement > Affectations d'élément accessoire.</span><span class="sxs-lookup"><span data-stu-id="406d4-108">Go to Transportation management > Setup > Rating > Accessorial assignments.</span></span>
2. <span data-ttu-id="406d4-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="406d4-109">Click New.</span></span>
3. <span data-ttu-id="406d4-110">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="406d4-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="406d4-111">Activez ou désactivez l'extension de la section Détails.</span><span class="sxs-lookup"><span data-stu-id="406d4-111">Toggle the expansion of the Details section.</span></span>
5. <span data-ttu-id="406d4-112">Dans le champ Point de transbordement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="406d4-112">In the Hub field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="406d4-113">Dans la liste, sélectionnez le concentrateur pour lequel vous avez créé une table maître d'éléments accessoires lorsque vous avez suivi le guide « Configurer les frais annexes de terminal et les données principales annexes ».</span><span class="sxs-lookup"><span data-stu-id="406d4-113">In the list, select the Hub that you created an accessorial master for when you ran the "Set up hub accessorial charges and accessorial masters" guide.</span></span> 
7. <span data-ttu-id="406d4-114">Dans le champ ID élément accessoire de point de transbordement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="406d4-114">In the Hub accessorial ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="406d4-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="406d4-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="406d4-116">Activez ou désactivez l'extension de la section Critères.</span><span class="sxs-lookup"><span data-stu-id="406d4-116">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="406d4-117">Dans la section Critère vous pouvez choisir les critères exacts pour l'application des frais, selon les différentes valeurs offertes ici.</span><span class="sxs-lookup"><span data-stu-id="406d4-117">In the Criteria section you can choose the exact criteria for when the charge should apply, based on the different values offered here.</span></span>  
10. <span data-ttu-id="406d4-118">Définissez l'option Toujours appliquer sur Oui.</span><span class="sxs-lookup"><span data-stu-id="406d4-118">Set the Always apply option to Yes.</span></span>
11. <span data-ttu-id="406d4-119">Sélectionnez une option dans le champ Niveau d'affectation d'élément accessoire.</span><span class="sxs-lookup"><span data-stu-id="406d4-119">In the Accessorial assignment level field, select an option.</span></span>
12. <span data-ttu-id="406d4-120">Activez ou désactivez l'extension de la section Calcul.</span><span class="sxs-lookup"><span data-stu-id="406d4-120">Toggle the expansion of the Calculation section.</span></span>
13. <span data-ttu-id="406d4-121">Sélectionnez « Fixe » dans le champ Type de frais accessoires.</span><span class="sxs-lookup"><span data-stu-id="406d4-121">In the Accessorial fee type field, select 'Flat'.</span></span>
    * <span data-ttu-id="406d4-122">Le type Frais accessoires détermine comment calculer les frais réels.</span><span class="sxs-lookup"><span data-stu-id="406d4-122">The Accessorial fee type determines how to calculate the actual charge.</span></span> <span data-ttu-id="406d4-123">Dans cet exemple il s'agit de frais fixes.</span><span class="sxs-lookup"><span data-stu-id="406d4-123">In this example it's a flat charge.</span></span>  
14. <span data-ttu-id="406d4-124">Entrez un nombre dans le champ Frais accessoires.</span><span class="sxs-lookup"><span data-stu-id="406d4-124">In the Accessorial fee field, enter a number.</span></span>
15. <span data-ttu-id="406d4-125">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="406d4-125">Click Save.</span></span>

