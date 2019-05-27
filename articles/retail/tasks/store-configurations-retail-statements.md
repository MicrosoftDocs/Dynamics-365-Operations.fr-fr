---
title: " Enregistrer les configurations pour les relevés de vente au détail"
description: Cette procédure illustre les configurations du magasin de vente au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9fddeb8434d916df1613d61da88110dec8fb4465
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563642"
---
# <a name="store-configurations-for-retail-statements"></a><span data-ttu-id="c4bb9-103"> Enregistrer les configurations pour les relevés de vente au détail</span><span class="sxs-lookup"><span data-stu-id="c4bb9-103">Store configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="c4bb9-104">Cette procédure illustre les configurations du magasin de vente au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-104">This procedure walks through configurations for the Retail store that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="c4bb9-105">Les dimensions financières pour les magasins de vente au détail sont traitées dans une autre procédure.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-105">Financial dimensions on Retail stores are covered in another procedure.</span></span> <span data-ttu-id="c4bb9-106">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="c4bb9-107">Accédez à Commerce et vente au détail > Canaux > Magasins de vente au détail > Tous les magasins de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-107">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="c4bb9-108">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c4bb9-109">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c4bb9-110">Les paramètres de la section Relevé/clôture affectent la création, le contrôle et, la validation de relevés pour le magasin.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-110">The settings in the Statement/closing section affect the statement creation, validation, and posting for the store.</span></span>  <span data-ttu-id="c4bb9-111">Ouvrez la section Relevé/clôture</span><span class="sxs-lookup"><span data-stu-id="c4bb9-111">Open the Statement/closing section.</span></span>  
    * <span data-ttu-id="c4bb9-112">Sélectionnez la méthode à utiliser sur pour regrouper les lignes de relevé.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-112">Select the method you want to use to to group the statement lines by.</span></span>  
    * <span data-ttu-id="c4bb9-113">Sélectionnez « Oui » si un seul relevé doit être créé par jour lors de la création de relevés à partir du traitement par lots de la création de relevés.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-113">Select "Yes" if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
    * <span data-ttu-id="c4bb9-114">Le champ Calcul de comptage de caisse définit si les comptages de caisse doivent être ajoutés ensemble ou si c'est le dernier qui doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-114">The Tender declaration calculation field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
    * <span data-ttu-id="c4bb9-115">Sélectionnez le compte général dans lequel valider les différences d'arrondi.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-115">Select the ledger account to post rounding differences into.</span></span>  
    * <span data-ttu-id="c4bb9-116">Dans le champ Différence d'arrondi maximale, vous pouvez spécifier la différence d'arrondi maximale autorisée.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-116">In the Maximum rounding difference field, you can enter the maximum rounding difference allowed.</span></span>  
    * <span data-ttu-id="c4bb9-117">Dans le champ Validation, vous pouvez spécifier la différence de validation totale maximale autorisée pour un relevé.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-117">In the Posting field, you can enter the maximum total posting difference allowed for a statement.</span></span>  
    * <span data-ttu-id="c4bb9-118">Dans le champ Équipe, vous pouvez spécifier la différence totale maximale au sein d'une équipe dans un relevé.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-118">In the Shift field, you can enter the maximum total difference within a shift in a statement.</span></span>  
    * <span data-ttu-id="c4bb9-119">Dans le champ Transaction, vous pouvez spécifier la différence totale maximale dans une ligne de relevé.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-119">In the Transaction field, you can enter the maximum total difference in a statement line.</span></span>  
    * <span data-ttu-id="c4bb9-120">Dans le champ Méthode de clôture, vous pouvez définir si les transactions à inclure dans un relevé doivent faire partie d'une équipe de travail clôturée ou s'il peut s'agir de toute transaction comprise dans la période définie.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-120">In the Closing method field, you can define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
    * <span data-ttu-id="c4bb9-121">Dans le champ Fin du jour ouvrable, vous pouvez spécifier une heure si les transactions qui surviennent après minuit doivent être validées dans le cadre du jour précédent.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-121">In the End of business day field, you can enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
    * <span data-ttu-id="c4bb9-122">Sélectionnez « Oui » si les transactions qui surviennent après minuit doivent être validées dans le cadre du jour précédent.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-122">Select "Yes" if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
    * <span data-ttu-id="c4bb9-123">Sélectionnez « Oui » pour que des relevés soient créés pour chaque méthode de relevé définie.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-123">Select "Yes" to get statements created for each statement method defined.</span></span> <span data-ttu-id="c4bb9-124">Cela peut s'avérer utile si les performances de la validation doit être améliorée pour les magasins affichant des volumes élevé de transactions, car cela créera de nombreux relevés plus petits qui peuvent être traités en parallèle.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-124">This can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
    * <span data-ttu-id="c4bb9-125">Dans le champ Client par défaut, vous pouvez sélectionner le compte client à utiliser pour les ventes aux clients qui se rendent dans le magasin.</span><span class="sxs-lookup"><span data-stu-id="c4bb9-125">In the Default customer field, you can select the customer account to use for sales to walk-in customers.</span></span>  

