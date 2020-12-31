---
title: Configurer les règles de répartition des tâches
description: Vous pouvez configurer des règles sur des tâches séparées qui doivent être effectuées par les utilisateurs.
author: peakerbl
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 57c7c436c91ab11404cac3ea056b028023a0617a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688171"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="bc381-103">Configurer les règles de répartition des tâches</span><span class="sxs-lookup"><span data-stu-id="bc381-103">Set up segregation of duties</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bc381-104">Vous pouvez configurer des règles sur des tâches séparées qui doivent être effectuées par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bc381-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="bc381-105">Ce concept est appelé répartition des tâches.</span><span class="sxs-lookup"><span data-stu-id="bc381-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="bc381-106">Par exemple, vous ne souhaitez peut-être pas que cela soit la même personne qui accuse réception des marchandises et qui traite le paiement au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="bc381-106">For example, you might not want the same person both to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="bc381-107">La répartition des tâches vous aide à réduire le risque de fraude et également à détecter des erreurs ou des irrégularités.</span><span class="sxs-lookup"><span data-stu-id="bc381-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="bc381-108">Vous pouvez également utiliser la répartition des tâches pour appliquer des stratégies de contrôle internes.</span><span class="sxs-lookup"><span data-stu-id="bc381-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="bc381-109">Appliquez la procédure suivante pour créer une règle.</span><span class="sxs-lookup"><span data-stu-id="bc381-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="bc381-110">Vous devez être administrateur système pour exécuter la procédure.</span><span class="sxs-lookup"><span data-stu-id="bc381-110">You must be a system administrator to complete the procedure.</span></span> <span data-ttu-id="bc381-111">La société fictive de démonstration utilisée pour créer cette procédure est DAT.</span><span class="sxs-lookup"><span data-stu-id="bc381-111">The demo data company used to create this procedure is DAT.</span></span> 

1. <span data-ttu-id="bc381-112">Accédez à **Volet de navigation > Modules > Administration système > Sécurité > Répartition des tâches > Règles de répartition des tâches**.</span><span class="sxs-lookup"><span data-stu-id="bc381-112">Go to **Navigation pane > Modules > System administration > Security > Segregation of duties > Segregation of duties rules**.</span></span>
2. <span data-ttu-id="bc381-113">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="bc381-113">Click **New**.</span></span>
3. <span data-ttu-id="bc381-114">Dans le champ **Nom**, saisissez une valeur pour la règle.</span><span class="sxs-lookup"><span data-stu-id="bc381-114">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="bc381-115">Dans le champ **Première responsabilité**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="bc381-115">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="bc381-116">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="bc381-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="bc381-117">Sélectionnez la première tâche qui est contrôlée par la règle.</span><span class="sxs-lookup"><span data-stu-id="bc381-117">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="bc381-118">Dans le champ **Deuxième responsabilité**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="bc381-118">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="bc381-119">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="bc381-119">In the list, find and select the desired record.</span></span> <span data-ttu-id="bc381-120">Sélectionnez la deuxième tâche qui est contrôlée par la règle.</span><span class="sxs-lookup"><span data-stu-id="bc381-120">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="bc381-121">Dans le champ **Gravité**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="bc381-121">In the **Severity** field, select an option.</span></span> <span data-ttu-id="bc381-122">Sélectionnez la gravité du risque qui se produit lorsqu’un même utilisateur ou rôle réalise les deux tâches.</span><span class="sxs-lookup"><span data-stu-id="bc381-122">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="bc381-123">Dans le champ **Risque de sécurité**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bc381-123">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="bc381-124">Entrez une description du risque de sécurité.</span><span class="sxs-lookup"><span data-stu-id="bc381-124">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="bc381-125">Dans le champ **Atténuation de sécurité**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bc381-125">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="bc381-126">Entrez une description des actions que vous prenez pour atténuer le risque de sécurité.</span><span class="sxs-lookup"><span data-stu-id="bc381-126">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="bc381-127">Par exemple, vous pouvez atténuer le risque en conduisant des examens plus détaillés du processus, en conduisant une révision décisionnelle mensuelle, ou en partageant des ressources avec d’autres départements.</span><span class="sxs-lookup"><span data-stu-id="bc381-127">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="bc381-128">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="bc381-128">Click **Save**.</span></span>

