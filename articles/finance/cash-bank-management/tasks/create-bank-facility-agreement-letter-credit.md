---
title: Créer un accord d’établissement bancaire pour une lettre de crédit
description: Cette tâche illustre la création d’un accord d’établissement bancaire pour traiter une lettre de crédit.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankDocumentFacilityAgreement, BankAccountTableLookUp, BankDocumentFacilityAgreementExtension, DefaultDashboard
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 582a41a0a4a3c509eae8a05c57b0910446addb26
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834834"
---
# <a name="create-a-bank-facility-agreement-for-a-letter-of-credit"></a><span data-ttu-id="e4d62-103">Créer un accord d’établissement bancaire pour une lettre de crédit</span><span class="sxs-lookup"><span data-stu-id="e4d62-103">Create a bank facility agreement for a letter of credit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e4d62-104">Cette tâche illustre la création d’un accord d’établissement bancaire pour traiter une lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="e4d62-104">This task walks through the creating a Bank facility agreement to process a Letter of credit.</span></span> <span data-ttu-id="e4d62-105">Vous devrez paramétrer des établissements bancaires et des profils de validation avant cette tâche.</span><span class="sxs-lookup"><span data-stu-id="e4d62-105">You will want to set up bank facilities and posting profiles before this task.</span></span>  <span data-ttu-id="e4d62-106">Cette tâche utilise la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="e4d62-106">This task uses the demo company 'USMF'.</span></span>  


## <a name="create-bank-facility-agreement"></a><span data-ttu-id="e4d62-107">Créer un accord d’établissement bancaire</span><span class="sxs-lookup"><span data-stu-id="e4d62-107">Create Bank facility agreement</span></span>
1. <span data-ttu-id="e4d62-108">Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Accords d’établissement bancaire.</span><span class="sxs-lookup"><span data-stu-id="e4d62-108">Go to Cash and bank management > Letters of credit > Bank facility agreements.</span></span>
2. <span data-ttu-id="e4d62-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e4d62-109">Click New.</span></span>
3. <span data-ttu-id="e4d62-110">Dans le champ Numéro d’accord, entrez le numéro d’accord en fonction de l’accord avec la banque.</span><span class="sxs-lookup"><span data-stu-id="e4d62-110">In the Agreement number field, enter the agreement number according to the agreement with the bank.</span></span>
4. <span data-ttu-id="e4d62-111">Dans le champ Compte en banque, entrez le numéro de compte bancaire de la banque émettrice.</span><span class="sxs-lookup"><span data-stu-id="e4d62-111">In the Bank account field, enter the account number at the issuing bank.</span></span>
5. <span data-ttu-id="e4d62-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e4d62-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e4d62-113">Entrez une date et une heure dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="e4d62-113">In the Start date field, enter a date and time.</span></span>
7. <span data-ttu-id="e4d62-114">Entrez une date et une heure dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="e4d62-114">In the End date field, enter a date and time.</span></span>
8. <span data-ttu-id="e4d62-115">Développez ou réduisez la section Général.</span><span class="sxs-lookup"><span data-stu-id="e4d62-115">Expand or collapse the General section.</span></span>
9. <span data-ttu-id="e4d62-116">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="e4d62-116">Click Add line.</span></span>
10. <span data-ttu-id="e4d62-117">Dans le champ Type d’établissement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e4d62-117">In the Facility type field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="e4d62-118">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e4d62-118">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="e4d62-119">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e4d62-119">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="e4d62-120">Dans le champ Limite, entrez le montant de l’établissement tel que négocié avec la banque.</span><span class="sxs-lookup"><span data-stu-id="e4d62-120">In the Limit field, enter the facility amount that was negotiated with the bank.</span></span>
14. <span data-ttu-id="e4d62-121">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e4d62-121">Click Save.</span></span>
15. <span data-ttu-id="e4d62-122">Cliquez sur Étendre pour ouvrir l’écran de boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e4d62-122">Click Extend to open the drop dialog.</span></span>
16. <span data-ttu-id="e4d62-123">Saisissez une valeur dans le champ Nouveau numéro d’accord.</span><span class="sxs-lookup"><span data-stu-id="e4d62-123">In the New agreement number field, type a value.</span></span>
17. <span data-ttu-id="e4d62-124">Entrez une date et une heure dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="e4d62-124">In the End date field, enter a date and time.</span></span>
18. <span data-ttu-id="e4d62-125">Cliquez sur Étendre.</span><span class="sxs-lookup"><span data-stu-id="e4d62-125">Click Extend.</span></span>
19. <span data-ttu-id="e4d62-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e4d62-126">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]