---
title: Créer des dimensions financières pour les caisses de PDV et configurer les valeurs de dimension dans les registres
description: Cette procédure illustre la création des dimensions financières des caisses enregistreuses des points de vente (PDV), et montre comment configurer les valeurs de dimension financière des caisses enregistreuses.
author: jashanno
manager: AnnBe
ms.date: 11/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4042fb9da0fe38de50ad7e0c8e64b98925ea1188
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5265957"
---
# <a name="create-financial-dimensions-for-pos-registers-and-configure-dimension-values-on-registers"></a><span data-ttu-id="b347c-103">Créer des dimensions financières pour les caisses de PDV et configurer les valeurs de dimension dans les registres</span><span class="sxs-lookup"><span data-stu-id="b347c-103">Create financial dimensions for POS registers and configure dimension values on registers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b347c-104">Cette procédure illustre la création des dimensions financières des caisses enregistreuses des points de vente (PDV), et montre comment configurer les valeurs de dimension financière des caisses enregistreuses.</span><span class="sxs-lookup"><span data-stu-id="b347c-104">This procedure walks through creating financial dimensions for point of sale (POS) registers, and demonstrates how to configure financial dimension values on registers.</span></span> <span data-ttu-id="b347c-105">Cette procédure n'inclut pas d'autres étapes associées, telles que la création d'ensembles de dimensions et de structures de compte.</span><span class="sxs-lookup"><span data-stu-id="b347c-105">This procedure doesn't include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="b347c-106">Ces tâches sont traitées dans d'autres rubriques.</span><span class="sxs-lookup"><span data-stu-id="b347c-106">Those tasks can be found in other topics.</span></span> <span data-ttu-id="b347c-107">La société fictive USRT sert d'exemple dans cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="b347c-107">This recording uses USRT demo company.</span></span>

1. <span data-ttu-id="b347c-108">Accédez à Comptabilité > Plan de comptes > Dimensions > Dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="b347c-108">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="b347c-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="b347c-109">Click New.</span></span>
3. <span data-ttu-id="b347c-110">Dans le champ Utiliser les valeurs à partir de, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="b347c-110">In the Use values from field, select an option.</span></span>
4. <span data-ttu-id="b347c-111">Dans le champ Nom de la dimension, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b347c-111">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="b347c-112">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="b347c-112">Click Activate.</span></span>
6. <span data-ttu-id="b347c-113">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="b347c-113">Click Close.</span></span>
7. <span data-ttu-id="b347c-114">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="b347c-114">Click Activate.</span></span>
8. <span data-ttu-id="b347c-115">Cliquez sur les valeurs de dimension.</span><span class="sxs-lookup"><span data-stu-id="b347c-115">Click Dimension values.</span></span>
9. <span data-ttu-id="b347c-116">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b347c-116">Close the page.</span></span>
10. <span data-ttu-id="b347c-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="b347c-117">Click Save.</span></span>
11. <span data-ttu-id="b347c-118">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b347c-118">Close the page.</span></span>
12. <span data-ttu-id="b347c-119">Accédez à Commerce et vente au détail > Paramétrage du canal > Paramétrage du PD > Caisses enregistreuses.</span><span class="sxs-lookup"><span data-stu-id="b347c-119">Go to Retail and Commerce > Channel setup > POS setup > Registers.</span></span>
13. <span data-ttu-id="b347c-120">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b347c-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="b347c-121">Activez ou désactivez l'extension de la section Dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="b347c-121">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="b347c-122">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="b347c-122">Click Edit.</span></span>
16. <span data-ttu-id="b347c-123">Dans le champ Terminal, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="b347c-123">In the Terminal field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="b347c-124">Dans la liste, recherchez et sélectionnez la valeur de dimension correspondant à la caisse enregistreuse en cours de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="b347c-124">In the list, find and select the dimension value for the register being updated.</span></span>
18. <span data-ttu-id="b347c-125">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="b347c-125">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]