---
title: Paramétrage des administrations fiscales
description: Les administrations fiscales sont des entités auprès desquelles les taxes doivent être déclarées et payées.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 160b2507b7ca14ebab54b4775f29615c4aa5f8e0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815090"
---
# <a name="set-up-sales-tax-authorities"></a><span data-ttu-id="5d59e-103">Paramétrage des administrations fiscales</span><span class="sxs-lookup"><span data-stu-id="5d59e-103">Set up sales tax authorities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5d59e-104">Les administrations fiscales sont des entités auprès desquelles les taxes doivent être déclarées et payées.</span><span class="sxs-lookup"><span data-stu-id="5d59e-104">Sales tax authorities are entities to which collected sales tax needs to be reported and paid.</span></span> <span data-ttu-id="5d59e-105">Vous pouvez payer des taxes à l’administration directement ou via un compte fournisseur que vous créez pour l’administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="5d59e-105">You can pay sales taxes to the authority directly or through a vendor account that you create for the sales tax authority.</span></span> <span data-ttu-id="5d59e-106">Dans ce cas, la société peut utiliser ses routines de paiement habituelles pour payer l’administration fiscale à temps.</span><span class="sxs-lookup"><span data-stu-id="5d59e-106">If you do this, the company can use its usual payment routines to pay the sales tax authority on time.</span></span> <span data-ttu-id="5d59e-107">Si vous ne paramétrez pas l’administration fiscale comme fournisseur, un paiement manuel doit être préparé, à remettre à l’administration fiscale à la date d’échéance appropriée.</span><span class="sxs-lookup"><span data-stu-id="5d59e-107">If you do not set up the tax authority as a vendor, someone must prepare a manual payment to the tax authority on the appropriate due date.</span></span> <span data-ttu-id="5d59e-108">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="5d59e-108">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="5d59e-109">Accédez à Taxe > Taxes indirectes > Taxes > Administrations fiscales.</span><span class="sxs-lookup"><span data-stu-id="5d59e-109">Go to Tax > Indirect taxes > Sales tax > Sales tax authorities.</span></span>
2. <span data-ttu-id="5d59e-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="5d59e-110">Click New.</span></span>
3. <span data-ttu-id="5d59e-111">Tapez une valeur dans le champ Administration.</span><span class="sxs-lookup"><span data-stu-id="5d59e-111">In the Authority field, type a value.</span></span>
4. <span data-ttu-id="5d59e-112">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="5d59e-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="5d59e-113">Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="5d59e-113">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="5d59e-114">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="5d59e-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="5d59e-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5d59e-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="5d59e-116">Sélectionnez la présentation d’état pour votre pays/région, si elle est disponible.</span><span class="sxs-lookup"><span data-stu-id="5d59e-116">Select the report layout for your country/region, if one is available.</span></span> <span data-ttu-id="5d59e-117">Si les états de valeur ne correspondent pas aux exigences de l’administration fiscale, utilisez la structure par défaut.</span><span class="sxs-lookup"><span data-stu-id="5d59e-117">If the report layouts do not correspond to the requirements of the sales tax authority, use default layout.</span></span>
9. <span data-ttu-id="5d59e-118">Entrez des valeurs dans les champs Type d’arrondi et Arrondi pour spécifier la manière dont le montant total de la taxe à payer doit être arrondi.</span><span class="sxs-lookup"><span data-stu-id="5d59e-118">Enter values in the Rounding form and the Round-off fields to specify how the tax total amount to be paid should be rounded.</span></span> <span data-ttu-id="5d59e-119">Les différences d’arrondi seront validées sur les comptes pour les transactions automatiques paramétrées dans Comptabilité.</span><span class="sxs-lookup"><span data-stu-id="5d59e-119">Any rounding differences will be posted to Accounts for automatic transactions set up in General ledger.</span></span>
10. <span data-ttu-id="5d59e-120">Entrez un nombre dans le champ Arrondi.</span><span class="sxs-lookup"><span data-stu-id="5d59e-120">In the Round-off field, enter a number.</span></span>
11. <span data-ttu-id="5d59e-121">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="5d59e-121">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]