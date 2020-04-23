---
title: Paramétrer des contraintes de transport pour un article
description: Cette procédure paramètrera une contrainte de transport pour empêcher un article sélectionné d'être transporté via un concentrateur sélectionné.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSConstraint, InventLocationIdLookup, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8eb9873f0ad6f404dc88d27ed5feedfc71fd62b5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201408"
---
# <a name="set-up-transportation-constraints-for-an-item"></a><span data-ttu-id="767cf-103">Paramétrer des contraintes de transport pour un article</span><span class="sxs-lookup"><span data-stu-id="767cf-103">Set up transportation constraints for an item</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="767cf-104">Cette procédure paramètrera une contrainte de transport pour empêcher un article sélectionné d'être transporté via un concentrateur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="767cf-104">This procedure will set up a transportation constraint to prevent a selected item from being transported through a selected hub.</span></span> <span data-ttu-id="767cf-105">Cette tâche est généralement effectuée par un coordinateur de transport.</span><span class="sxs-lookup"><span data-stu-id="767cf-105">This task would typically be carried out by a Transportation coordinator.</span></span> <span data-ttu-id="767cf-106">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="767cf-106">You can use this procedure in the USMF demo data company or on your own data.</span></span>


## <a name="create-an-item-constaint"></a><span data-ttu-id="767cf-107">Créer une contrainte d'article</span><span class="sxs-lookup"><span data-stu-id="767cf-107">Create an item constaint</span></span>
1. <span data-ttu-id="767cf-108">Allez dans Contraintes.</span><span class="sxs-lookup"><span data-stu-id="767cf-108">Go to Constraints.</span></span>
2. <span data-ttu-id="767cf-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="767cf-109">Click New.</span></span>
3. <span data-ttu-id="767cf-110">Tapez une valeur dans le champ Contrainte d'article.</span><span class="sxs-lookup"><span data-stu-id="767cf-110">In the Item constraint field, type a value.</span></span>
4. <span data-ttu-id="767cf-111">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="767cf-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="767cf-112">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="767cf-112">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="767cf-113">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="767cf-113">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="767cf-114">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="767cf-114">In the Item number field, enter or select a value.</span></span>
8. <span data-ttu-id="767cf-115">Saisissez ou sélectionnez une valeur dans le champ Point de transbordement.</span><span class="sxs-lookup"><span data-stu-id="767cf-115">In the Hub field, enter or select a value.</span></span>
9. <span data-ttu-id="767cf-116">Sélectionnez une option dans le champ Action de contrainte.</span><span class="sxs-lookup"><span data-stu-id="767cf-116">In the Constraint action field, select an option.</span></span>
10. <span data-ttu-id="767cf-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="767cf-117">Click Save.</span></span>
11. <span data-ttu-id="767cf-118">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="767cf-118">Close the page.</span></span>

