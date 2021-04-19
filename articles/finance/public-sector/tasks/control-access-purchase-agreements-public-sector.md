---
title: Contrôler l’accès aux contrats d’achat dans le secteur public
description: Vous pouvez vous assurer que seuls les départements approuvés peuvent accéder à un contrat d’achat.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementFinDimensionAccess_PSN
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a05dea1f98e80809361cad519b24457f7458dd6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816826"
---
# <a name="control-access-to-purchase-agreements-in-the-public-sector"></a><span data-ttu-id="8b7fd-103">Contrôler l’accès aux contrats d’achat dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="8b7fd-103">Control access to purchase agreements in the public sector</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8b7fd-104">Vous pouvez vous assurer que seuls les départements approuvés peuvent accéder à un contrat d’achat.</span><span class="sxs-lookup"><span data-stu-id="8b7fd-104">You can make sure that only approved departments can access a purchase agreement.</span></span> <span data-ttu-id="8b7fd-105">Vous pouvez également limiter le montant que chaque département peut dépenser dans le cadre du contrat d’achat.</span><span class="sxs-lookup"><span data-stu-id="8b7fd-105">You can also limit the amount that each department can spend against the purchase agreement.</span></span> <span data-ttu-id="8b7fd-106">Pour ce faire, la structure de compte et les dimensions financières pour l’accès au département doivent être définies dans l’écran Paramètres de la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="8b7fd-106">In order to do this, the account structure and financial dimensions for department access must be set on the Accounts payable parameters form.</span></span> <span data-ttu-id="8b7fd-107">Cette procédure a été créée pour les organisations du secteur public français, en utilisant les données de la société fictive PSUS dans la partition du secteur public.</span><span class="sxs-lookup"><span data-stu-id="8b7fd-107">This procedure was created for French public sector organizations using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="8b7fd-108">Accédez à Comptabilité fournisseur > Commandes fournisseur > Contrats d’achat.</span><span class="sxs-lookup"><span data-stu-id="8b7fd-108">Go to Accounts payable > Purchase orders > Purchase agreements.</span></span>
2. <span data-ttu-id="8b7fd-109">Dans la liste, sélectionnez le contrat d’achat auquel vous souhaitez contrôler l’accès.</span><span class="sxs-lookup"><span data-stu-id="8b7fd-109">In the list, select the purchase agreement that you want to control access to.</span></span>
3. <span data-ttu-id="8b7fd-110">Dans le volet Action, cliquez sur Contrat d’achat.</span><span class="sxs-lookup"><span data-stu-id="8b7fd-110">On the Action Pane, click Purchase agreement.</span></span>
4. <span data-ttu-id="8b7fd-111">Cliquez sur Accès du département.</span><span class="sxs-lookup"><span data-stu-id="8b7fd-111">Click Department access.</span></span>
5. <span data-ttu-id="8b7fd-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8b7fd-112">Click New.</span></span>
6. <span data-ttu-id="8b7fd-113">Cliquez sur le bouton de liste déroulante pour ouvrir la recherche dans le champ Département.</span><span class="sxs-lookup"><span data-stu-id="8b7fd-113">In the Department field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="8b7fd-114">Dans la liste, sélectionnez la dimension financière pour un département qui a accès à ce contrat d’achat.</span><span class="sxs-lookup"><span data-stu-id="8b7fd-114">In the list, select the financial dimension for a department that has access to this purchase agreement.</span></span>
8. <span data-ttu-id="8b7fd-115">Dans le champ Montant autorisé, entrez le montant total que ce département est autorisé à débloquer dans le cadre de ce contrat d’achat.</span><span class="sxs-lookup"><span data-stu-id="8b7fd-115">In the Authorized amount field, enter the total amount that this department is authorized to release from this purchase agreement.</span></span>
    * <span data-ttu-id="8b7fd-116">Ajoutez des départements supplémentaires jusqu’à ce que tous les départements autorisés aient été ajoutés au contrat d’achat.</span><span class="sxs-lookup"><span data-stu-id="8b7fd-116">Add additional departments until all authorized departments have been added to the purchase agreement.</span></span>  
9. <span data-ttu-id="8b7fd-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8b7fd-117">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]