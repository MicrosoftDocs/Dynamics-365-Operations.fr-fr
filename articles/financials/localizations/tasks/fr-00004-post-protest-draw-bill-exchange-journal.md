---
title: FR-00004 Valider le journal de création et de contestation des lettres de change
description: Cette procédure vous guide au cours des étapes des contestation d'une lettre de change impayée.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustBillOfExchange, CustOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a00c5422e0a7671a76345bb1652e99faaca11109
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556597"
---
# <a name="fr-00004-post-protest-draw-bill-of-exchange-journal"></a><span data-ttu-id="87e38-103">FR-00004 Valider le journal de création et de contestation des lettres de change</span><span class="sxs-lookup"><span data-stu-id="87e38-103">FR-00004 Post protest draw bill of exchange journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="87e38-104">Cette procédure vous guide au cours des étapes des contestation d'une lettre de change impayée.</span><span class="sxs-lookup"><span data-stu-id="87e38-104">This procedure walks you through the steps of protesting bill of exchange.</span></span>

<span data-ttu-id="87e38-105">Cette procédure a été créée à l'aide des données fictives de la société FRSI.</span><span class="sxs-lookup"><span data-stu-id="87e38-105">This procedure was created using the demo data company FRSI.</span></span> 

<span data-ttu-id="87e38-106">Cette fonctionnalité est disponible pour les entités juridiques dont l'adresse principale est en France.</span><span class="sxs-lookup"><span data-stu-id="87e38-106">This functionality is available for legal entities whose primary address is in France.</span></span>

<span data-ttu-id="87e38-107">Pour effectuer cette procédure, vous devez avoir le rôle de commis à la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="87e38-107">You should have a role of Accounts receivables clerk to complete this procedure.</span></span>



1. <span data-ttu-id="87e38-108">Accédez à Comptabilité client > Paiements > Lettre de change > Journal des lettres de change impayées.</span><span class="sxs-lookup"><span data-stu-id="87e38-108">Go to Accounts receivable > Payments > Bill of exchange > Protest bill of exchange journal.</span></span>
2. <span data-ttu-id="87e38-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="87e38-109">Click New.</span></span>
3. <span data-ttu-id="87e38-110">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="87e38-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="87e38-111">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="87e38-111">In the Name field, enter or select a value.</span></span>
5. <span data-ttu-id="87e38-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="87e38-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="87e38-113">Sélectionnez « LitigeEAR »</span><span class="sxs-lookup"><span data-stu-id="87e38-113">Select "LitigeEAR"</span></span>  
6. <span data-ttu-id="87e38-114">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="87e38-114">Click Lines.</span></span>
7. <span data-ttu-id="87e38-115">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="87e38-115">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="87e38-116">Dans le champ Compte, spécifiez les valeurs « FR_SI_0001 ».</span><span class="sxs-lookup"><span data-stu-id="87e38-116">In the Account field, specify the values 'FR_SI_0001'.</span></span>
9. <span data-ttu-id="87e38-117">Cliquez sur Régler les transactions.</span><span class="sxs-lookup"><span data-stu-id="87e38-117">Click Settle transactions.</span></span>
10. <span data-ttu-id="87e38-118">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="87e38-118">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="87e38-119">Marquer le journal de création de lettres de change le plus récemment validé</span><span class="sxs-lookup"><span data-stu-id="87e38-119">Mark the most recently posted draw bill of exchange journal</span></span>  
11. <span data-ttu-id="87e38-120">Cochez la case Marquer.</span><span class="sxs-lookup"><span data-stu-id="87e38-120">Select the Mark check box.</span></span>
12. <span data-ttu-id="87e38-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="87e38-121">Click OK.</span></span>
13. <span data-ttu-id="87e38-122">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="87e38-122">Click Post.</span></span>
14. <span data-ttu-id="87e38-123">Accédez à Comptabilité client > Recherches et états > Paiements > Journal des lettres de change.</span><span class="sxs-lookup"><span data-stu-id="87e38-123">Go to Accounts receivable > Inquiries and reports > Payments > Bill of exchange journal.</span></span>
    * <span data-ttu-id="87e38-124">Vérifiez que le statut du journal récemment validé est Impayés.</span><span class="sxs-lookup"><span data-stu-id="87e38-124">Verify that Status for the newly posted journal should be Protested.</span></span> <span data-ttu-id="87e38-125">Si c'est le cas, le processus est terminé.</span><span class="sxs-lookup"><span data-stu-id="87e38-125">If yes, the process is complete</span></span>  

