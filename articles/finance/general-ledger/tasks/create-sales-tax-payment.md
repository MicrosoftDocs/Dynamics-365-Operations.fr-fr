---
title: Créer un paiement de taxe
description: La tâche Régler et valider la taxe permet de régler les soldes de taxe dans les comptes de taxe et de les compenser dans le compte de règlement de la taxe pour une période donnée.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 99059a8e5d6f4bf125266ad2a98cb73751529e6b
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139920"
---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="9e08c-103">Créer un paiement de taxe</span><span class="sxs-lookup"><span data-stu-id="9e08c-103">Create a sales tax payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9e08c-104">La tâche Régler et valider la taxe permet de régler les soldes de taxe dans les comptes de taxe et de les compenser dans le compte de règlement de la taxe pour une période donnée.</span><span class="sxs-lookup"><span data-stu-id="9e08c-104">The settle and post sales tax job settles sales tax balances on the sales tax accounts and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="9e08c-105">Allez dans Taxe > Déclarations > Taxe > Régler et valider la taxe.</span><span class="sxs-lookup"><span data-stu-id="9e08c-105">Go to Tax > Declarations > Sales tax > Settle and post sales tax.</span></span>
2. <span data-ttu-id="9e08c-106">Dans le champ Période de règlement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9e08c-106">In the Settlement period field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="9e08c-107">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9e08c-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="9e08c-108">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="9e08c-108">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="9e08c-109">Si l'option Inclure les corrections n'est pas sélectionnée dans la page Paramètres de comptabilité, le règlement peut être traité pour différentes versions.</span><span class="sxs-lookup"><span data-stu-id="9e08c-109">If the Include corrections option is not selected on the General ledger parameters page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="9e08c-110">L'original est le premier règlement pour un intervalle de périodes et peut seulement être traité une fois pour un intervalle de périodes.</span><span class="sxs-lookup"><span data-stu-id="9e08c-110">Original is the first settlement for a period interval and can only processed once for a period interval.</span></span> <span data-ttu-id="9e08c-111">Les dernières corrections permettent de régler les transactions de taxe validées après la création de la version d'origine.</span><span class="sxs-lookup"><span data-stu-id="9e08c-111">Latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="9e08c-112">Entrez une date dans le champ Date de transaction.</span><span class="sxs-lookup"><span data-stu-id="9e08c-112">In the Transaction date field, enter a date.</span></span>
6. <span data-ttu-id="9e08c-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9e08c-113">Click OK.</span></span>

