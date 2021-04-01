---
title: Créer un paiement de taxe
description: La procédure de la tâche Régler et valider la taxe permet de régler les soldes de taxe dans les comptes de taxe et de les compenser dans le compte de règlement de la taxe pour une période donnée.
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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9523ef75953bdca36f509f596c51c08b12b3fdb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254461"
---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="5a70a-103">Créer un paiement de taxe</span><span class="sxs-lookup"><span data-stu-id="5a70a-103">Create a sales tax payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5a70a-104">La procédure de la tâche Régler et valider la taxe permet de régler les soldes de taxe dans les comptes de taxe, et de les compenser dans le compte de règlement de la taxe pour une période donnée.</span><span class="sxs-lookup"><span data-stu-id="5a70a-104">The settle and post sales tax job procedure settles sales tax balances on the sales tax accounts, and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="5a70a-105">Allez dans **Taxe > Déclarations > Taxe > Régler et valider la taxe**.</span><span class="sxs-lookup"><span data-stu-id="5a70a-105">Go to **Tax > Declarations > Sales tax > Settle and post sales tax**.</span></span>
2. <span data-ttu-id="5a70a-106">Dans le champ **Période de règlement**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="5a70a-106">In the **Settlement period** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="5a70a-107">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5a70a-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="5a70a-108">Entrez une date dans le champ **Date de début**.</span><span class="sxs-lookup"><span data-stu-id="5a70a-108">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="5a70a-109">Si vous ne sélectionnez pas m’option **Inclure les corrections** sur la page **Paramètres de comptabilité**, le règlement peut être traité pour différentes versions.</span><span class="sxs-lookup"><span data-stu-id="5a70a-109">If you don't select the **Include corrections** option on the **General ledger parameters** page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="5a70a-110">L’original est le premier règlement pour un intervalle de périodes et peut uniquement être traité une fois pour un intervalle de périodes.</span><span class="sxs-lookup"><span data-stu-id="5a70a-110">Original is the first settlement for a period interval and can be processed only once for a period interval.</span></span> <span data-ttu-id="5a70a-111">Les corrections les plus récentes permettent de régler les transactions de taxe validées après la création de la version d’origine.</span><span class="sxs-lookup"><span data-stu-id="5a70a-111">The latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="5a70a-112">Entrez une date dans le champ **Date de transaction**.</span><span class="sxs-lookup"><span data-stu-id="5a70a-112">In the **Transaction date** field, enter a date.</span></span>
6. <span data-ttu-id="5a70a-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a70a-113">Click **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]