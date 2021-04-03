---
title: Configurer les règles de répartition des tâches
description: Vous pouvez configurer des règles sur des tâches séparées qui doivent être effectuées par les utilisateurs.
author: peakerbl
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1c1521d6bbbe12964fef0942fcc4943f12a4360a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562495"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="ae797-103">Configurer les règles de répartition des tâches</span><span class="sxs-lookup"><span data-stu-id="ae797-103">Set up segregation of duties</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ae797-104">Vous pouvez configurer des règles sur des tâches séparées qui doivent être effectuées par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ae797-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="ae797-105">Ce concept est appelé répartition des tâches.</span><span class="sxs-lookup"><span data-stu-id="ae797-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="ae797-106">Par exemple, vous ne souhaitez peut-être pas que cela soit la même personne qui accuse réception des marchandises et qui traite le paiement au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="ae797-106">For example, you might not want the same person to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="ae797-107">La répartition des tâches vous aide à réduire le risque de fraude et également à détecter des erreurs ou des irrégularités.</span><span class="sxs-lookup"><span data-stu-id="ae797-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="ae797-108">Vous pouvez également utiliser la répartition des tâches pour appliquer des stratégies de contrôle internes.</span><span class="sxs-lookup"><span data-stu-id="ae797-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="ae797-109">Appliquez la procédure suivante pour créer une règle.</span><span class="sxs-lookup"><span data-stu-id="ae797-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="ae797-110">Vous devez être administrateur système pour exécuter la procédure.</span><span class="sxs-lookup"><span data-stu-id="ae797-110">You must be a system administrator to complete the procedure.</span></span>

1. <span data-ttu-id="ae797-111">Accédez à **Administration système** > **Sécurité** > **Répartition des tâches** > **Règles de répartition des tâches**.</span><span class="sxs-lookup"><span data-stu-id="ae797-111">Go to **System administration** > **Security** > **Segregation of duties** > **Segregation of duties rules**.</span></span>
2. <span data-ttu-id="ae797-112">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ae797-112">Click **New**.</span></span>
3. <span data-ttu-id="ae797-113">Dans le champ **Nom**, saisissez une valeur pour la règle.</span><span class="sxs-lookup"><span data-stu-id="ae797-113">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="ae797-114">Dans le champ **Première responsabilité**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ae797-114">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="ae797-115">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="ae797-115">In the list, find and select the desired record.</span></span> <span data-ttu-id="ae797-116">Sélectionnez la première tâche qui est contrôlée par la règle.</span><span class="sxs-lookup"><span data-stu-id="ae797-116">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="ae797-117">Dans le champ **Deuxième responsabilité**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ae797-117">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="ae797-118">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="ae797-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="ae797-119">Sélectionnez la deuxième tâche qui est contrôlée par la règle.</span><span class="sxs-lookup"><span data-stu-id="ae797-119">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="ae797-120">Dans le champ **Gravité**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="ae797-120">In the **Severity** field, select an option.</span></span> <span data-ttu-id="ae797-121">Sélectionnez la gravité du risque qui se produit lorsqu’un même utilisateur ou rôle réalise les deux tâches.</span><span class="sxs-lookup"><span data-stu-id="ae797-121">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="ae797-122">Dans le champ **Risque de sécurité**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ae797-122">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="ae797-123">Entrez une description du risque de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ae797-123">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="ae797-124">Dans le champ **Atténuation de sécurité**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ae797-124">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="ae797-125">Entrez une description des actions que vous prenez pour atténuer le risque de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ae797-125">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="ae797-126">Par exemple, vous pouvez atténuer le risque en conduisant des examens plus détaillés du processus, en conduisant une révision décisionnelle mensuelle, ou en partageant des ressources avec d’autres départements.</span><span class="sxs-lookup"><span data-stu-id="ae797-126">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="ae797-127">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ae797-127">Click **Save**.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="ae797-128">La conformité avec les règles de séparation des tâches n'est pas vérifié lorsque vous créez une règle.</span><span class="sxs-lookup"><span data-stu-id="ae797-128">Compliance with the rules for segregation of duties is not verified when you create a rule.</span></span> <span data-ttu-id="ae797-129">Vous pouvez créer une règle qui crée un conflit pour les rôles existants.</span><span class="sxs-lookup"><span data-stu-id="ae797-129">You can create a rule that creates a conflict for existing roles.</span></span> <span data-ttu-id="ae797-130">Les attributions de rôle utilisateur existantes peuvent également être en conflit avec la nouvelle règle.</span><span class="sxs-lookup"><span data-stu-id="ae797-130">Existing user role assignments can also be in conflict with the new rule.</span></span> <span data-ttu-id="ae797-131">Vous devez valider la conformité une fois que vous avez créé ou modifié une règle.</span><span class="sxs-lookup"><span data-stu-id="ae797-131">You must validate compliance after you create or modify a rule.</span></span> <span data-ttu-id="ae797-132">Pour plus d'informations, voir [Identifier et résoudre les conflits de séparation des tâches](identify-resolve-conflicts-segregation-duties.md)</span><span class="sxs-lookup"><span data-stu-id="ae797-132">For more information, see [Identify and resolve conflicts in segregation of duties](identify-resolve-conflicts-segregation-duties.md)</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]