---
title: Paramétrer des contraintes de transport pour un article
description: Cette procédure paramètrera une contrainte de transport pour empêcher un article sélectionné d’être transporté via un concentrateur sélectionné.
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
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e2ff8458a9821e1aa2ae8d2dc93cc89cfc318d70
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233557"
---
# <a name="set-up-transportation-constraints-for-an-item"></a><span data-ttu-id="f7d3f-103">Paramétrer des contraintes de transport pour un article</span><span class="sxs-lookup"><span data-stu-id="f7d3f-103">Set up transportation constraints for an item</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f7d3f-104">Cette procédure paramètrera une contrainte de transport pour empêcher un article sélectionné d’être transporté via un concentrateur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f7d3f-104">This procedure will set up a transportation constraint to prevent a selected item from being transported through a selected hub.</span></span> <span data-ttu-id="f7d3f-105">Cette tâche est généralement effectuée par un coordinateur de transport.</span><span class="sxs-lookup"><span data-stu-id="f7d3f-105">This task would typically be carried out by a Transportation coordinator.</span></span> <span data-ttu-id="f7d3f-106">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="f7d3f-106">You can use this procedure in the USMF demo data company or on your own data.</span></span>


## <a name="create-an-item-constaint"></a><span data-ttu-id="f7d3f-107">Créer une contrainte d’article</span><span class="sxs-lookup"><span data-stu-id="f7d3f-107">Create an item constaint</span></span>
1. <span data-ttu-id="f7d3f-108">Allez dans Contraintes.</span><span class="sxs-lookup"><span data-stu-id="f7d3f-108">Go to Constraints.</span></span>
2. <span data-ttu-id="f7d3f-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f7d3f-109">Click New.</span></span>
3. <span data-ttu-id="f7d3f-110">Tapez une valeur dans le champ Contrainte d’article.</span><span class="sxs-lookup"><span data-stu-id="f7d3f-110">In the Item constraint field, type a value.</span></span>
4. <span data-ttu-id="f7d3f-111">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="f7d3f-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="f7d3f-112">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="f7d3f-112">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="f7d3f-113">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f7d3f-113">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="f7d3f-114">Entrez ou sélectionnez une valeur dans le champ Numéro d’article.</span><span class="sxs-lookup"><span data-stu-id="f7d3f-114">In the Item number field, enter or select a value.</span></span>
8. <span data-ttu-id="f7d3f-115">Saisissez ou sélectionnez une valeur dans le champ Point de transbordement.</span><span class="sxs-lookup"><span data-stu-id="f7d3f-115">In the Hub field, enter or select a value.</span></span>
9. <span data-ttu-id="f7d3f-116">Sélectionnez une option dans le champ Action de contrainte.</span><span class="sxs-lookup"><span data-stu-id="f7d3f-116">In the Constraint action field, select an option.</span></span>
10. <span data-ttu-id="f7d3f-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f7d3f-117">Click Save.</span></span>
11. <span data-ttu-id="f7d3f-118">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f7d3f-118">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]