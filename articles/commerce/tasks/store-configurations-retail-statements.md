---
title: " Enregistrer les configurations pour les relevés de vente au détail"
description: Cette procédure détaille les configurations du magasin qui affectent la création et la validation des relevés de commerce.
author: jashanno
manager: AnnBe
ms.date: 08/08/2019
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
ms.openlocfilehash: 4b73282abd2df92b3f466f7c1c6c210173001fd7
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022497"
---
# <a name="store-configurations-for-retail-statements"></a><span data-ttu-id="942ef-103"> Enregistrer les configurations pour les relevés de vente au détail</span><span class="sxs-lookup"><span data-stu-id="942ef-103">Store configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="942ef-104">Cette procédure détaille les configurations du magasin qui affectent la création et la validation des relevés de commerce.</span><span class="sxs-lookup"><span data-stu-id="942ef-104">This procedure walks through configurations for the store that affect how Commerce statements get created and posted.</span></span> <span data-ttu-id="942ef-105">Les dimensions financières pour les magasins sont traitées dans une autre procédure.</span><span class="sxs-lookup"><span data-stu-id="942ef-105">Financial dimensions on stores are covered in another procedure.</span></span> <span data-ttu-id="942ef-106">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="942ef-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="942ef-107">Dans le **volet de navigation**, accédez à **Modules > Retail et Commerce > Canaux > Magasins > Tous les magasins**.</span><span class="sxs-lookup"><span data-stu-id="942ef-107">In the **Navgiation pane**, go to **Modules > Retail and Commerce > Channels > Stores > All stores**.</span></span>
2. <span data-ttu-id="942ef-108">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="942ef-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="942ef-109">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="942ef-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="942ef-110">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="942ef-110">Click **Edit**.</span></span>
5. <span data-ttu-id="942ef-111">Les paramètres de l'organisateur **Relevé/clôture** affectent la création, le contrôle et, la validation de relevés pour le magasin.</span><span class="sxs-lookup"><span data-stu-id="942ef-111">The settings in the **Statement/closing** fastTab affect the statement creation, validation, and posting for the store.</span></span> <span data-ttu-id="942ef-112">Développez l'organisateur **Relevé/clôture**.</span><span class="sxs-lookup"><span data-stu-id="942ef-112">Expand the **Statement/closing** fastTab.</span></span>  
6. <span data-ttu-id="942ef-113">Dans le champ **Mode de relevé**, sélectionnez la méthode à utiliser pour regrouper les lignes de relevé.</span><span class="sxs-lookup"><span data-stu-id="942ef-113">In the **Statement method** field, select the method you want to use to to group the statement lines by.</span></span>  
7. <span data-ttu-id="942ef-114">Sélectionnez « Oui » dans **Un relevé par jour** si un seul relevé doit être créé par jour lors de la création de relevés à partir du traitement par lots de la création de relevés.</span><span class="sxs-lookup"><span data-stu-id="942ef-114">Select "Yes" in **One statement per day** if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
8. <span data-ttu-id="942ef-115">Le champ **Calcul de comptage de caisse** définit si les comptages de caisse doivent être ajoutés ensemble ou si c'est le dernier qui doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="942ef-115">The **Tender declaration calculation** field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
9. <span data-ttu-id="942ef-116">Dans le champ **Arrondi**, sélectionnez le compte général dans lequel valider les différences d'arrondi.</span><span class="sxs-lookup"><span data-stu-id="942ef-116">In the **Rounding** field, select the ledger account to post rounding differences into.</span></span>  
10. <span data-ttu-id="942ef-117">Dans le champ **Différence d'arrondi maximale**, spécifiez la différence d'arrondi maximale autorisée.</span><span class="sxs-lookup"><span data-stu-id="942ef-117">In the **Maximum rounding difference** field, enter the maximum rounding difference allowed.</span></span>
11. <span data-ttu-id="942ef-118">Dans le champ **Validation**, vous pouvez spécifier la différence de validation totale maximale autorisée pour un relevé.</span><span class="sxs-lookup"><span data-stu-id="942ef-118">In the **Posting** field, enter the maximum total posting difference allowed for a statement.</span></span>
12. <span data-ttu-id="942ef-119">Dans le champ **Équipe**, vous pouvez spécifier la différence totale maximale au sein d'une équipe dans un relevé.</span><span class="sxs-lookup"><span data-stu-id="942ef-119">In the **Shift** field, enter the maximum total difference within a shift in a statement.</span></span>  
13. <span data-ttu-id="942ef-120">Dans le champ **Transaction**, vous pouvez spécifier la différence totale maximale dans une ligne de relevé.</span><span class="sxs-lookup"><span data-stu-id="942ef-120">In the **Transaction** field, enter the maximum total difference in a statement line.</span></span>  
14. <span data-ttu-id="942ef-121">Dans le champ **Méthode de clôture**, définissez si les transactions à inclure dans un relevé doivent faire partie d'une équipe de travail clôturée ou s'il peut s'agir de toute transaction comprise dans la période définie.</span><span class="sxs-lookup"><span data-stu-id="942ef-121">In the **Closing method** field, define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
15. <span data-ttu-id="942ef-122">Dans le champ **Fin du jour ouvrable**, spécifiez une heure si les transactions qui surviennent après minuit doivent être validées dans le cadre du jour précédent.</span><span class="sxs-lookup"><span data-stu-id="942ef-122">In the **End of business day** field, enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
16. <span data-ttu-id="942ef-123">Sélectionnez « Oui » dans **Valider comme jour ouvrable** si les transactions qui surviennent après minuit doivent être validées dans le cadre du jour précédent.</span><span class="sxs-lookup"><span data-stu-id="942ef-123">Select "Yes" in **Post as business day** if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
17. <span data-ttu-id="942ef-124">Sélectionnez « Oui » dans **Fractionner par mode de relevé** pour que des relevés soient créés pour chaque méthode de relevé définie.</span><span class="sxs-lookup"><span data-stu-id="942ef-124">Select "Yes" in **Split by Statement method** to get statements created for each statement method defined.</span></span> <span data-ttu-id="942ef-125">Cela peut s'avérer utile si les performances de la validation doit être améliorée pour les magasins affichant des volumes élevé de transactions, car cela créera de nombreux relevés plus petits qui peuvent être traités en parallèle.</span><span class="sxs-lookup"><span data-stu-id="942ef-125">This can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
18. <span data-ttu-id="942ef-126">Dans l'organisateur **Général**, dans le champ **Client par défaut**, vous pouvez sélectionner le compte client à utiliser pour les ventes aux clients qui se rendent dans le magasin.</span><span class="sxs-lookup"><span data-stu-id="942ef-126">In the **General** fastTab, in the **Default customer** field, you can select the customer account to use for sales to walk-in customers.</span></span>  

