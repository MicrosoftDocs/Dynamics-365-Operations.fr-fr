---
title: Configurer les règles de répartition des tâches
description: Vous pouvez configurer des règles sur des tâches séparées qui doivent être effectuées par les utilisateurs.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e3682dbcb72588633fb6b3fe4cbda99f422163a3
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851260"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="e830d-103">Configurer les règles de répartition des tâches</span><span class="sxs-lookup"><span data-stu-id="e830d-103">Set up segregation of duties</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e830d-104">Vous pouvez configurer des règles sur des tâches séparées qui doivent être effectuées par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e830d-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="e830d-105">Ce concept est appelé répartition des tâches.</span><span class="sxs-lookup"><span data-stu-id="e830d-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="e830d-106">Par exemple, vous ne souhaitez peut-être pas que cela soit la même personne qui accuse réception des marchandises et qui traite le paiement au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e830d-106">For example, you might not want the same person both to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="e830d-107">La répartition des tâches vous aide à réduire le risque de fraude et également à détecter des erreurs ou des irrégularités.</span><span class="sxs-lookup"><span data-stu-id="e830d-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="e830d-108">Vous pouvez également utiliser la répartition des tâches pour appliquer des stratégies de contrôle internes.</span><span class="sxs-lookup"><span data-stu-id="e830d-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="e830d-109">Appliquez la procédure suivante pour créer une règle.</span><span class="sxs-lookup"><span data-stu-id="e830d-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="e830d-110">Vous devez être administrateur système pour exécuter la procédure.</span><span class="sxs-lookup"><span data-stu-id="e830d-110">You must be a system administrator to complete the procedure.</span></span> <span data-ttu-id="e830d-111">La société fictive de démonstration utilisée pour créer cette procédure est DAT.</span><span class="sxs-lookup"><span data-stu-id="e830d-111">The demo data company used to create this procedure is DAT.</span></span> 

1. <span data-ttu-id="e830d-112">Accédez à Administration système > Sécurité > Répartition des tâches > Règles de répartition des tâches.</span><span class="sxs-lookup"><span data-stu-id="e830d-112">Go to System administration > Security > Segregation of duties > Segregation of duties rules.</span></span>
2. <span data-ttu-id="e830d-113">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e830d-113">Click New.</span></span>
3. <span data-ttu-id="e830d-114">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e830d-114">In the Name field, type a value.</span></span>
    * <span data-ttu-id="e830d-115">Entrer un nom pour la règle.</span><span class="sxs-lookup"><span data-stu-id="e830d-115">Enter a name for the rule.</span></span>  
4. <span data-ttu-id="e830d-116">Dans le champ Première responsabilité, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e830d-116">In the First duty field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="e830d-117">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e830d-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e830d-118">Sélectionnez la première tâche qui est contrôlée par la règle.</span><span class="sxs-lookup"><span data-stu-id="e830d-118">Select the first duty that is controlled by the rule.</span></span>  
6. <span data-ttu-id="e830d-119">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e830d-119">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="e830d-120">Dans le champ Deuxième responsabilité, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e830d-120">In the Second duty field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="e830d-121">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e830d-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e830d-122">Sélectionnez la deuxième tâche qui est contrôlée par la règle.</span><span class="sxs-lookup"><span data-stu-id="e830d-122">Select the second duty that is controlled by the rule.</span></span>  
9. <span data-ttu-id="e830d-123">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e830d-123">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="e830d-124">Dans le champ Gravité, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="e830d-124">In the Severity field, select an option.</span></span>
    * <span data-ttu-id="e830d-125">Sélectionnez la gravité du risque qui se produit lorsqu'un même utilisateur ou rôle réalise les deux tâches.</span><span class="sxs-lookup"><span data-stu-id="e830d-125">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="e830d-126">Dans le champ Risque de sécurité, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e830d-126">In the Security risk field, type a value.</span></span>
    * <span data-ttu-id="e830d-127">Entrez une description du risque de sécurité.</span><span class="sxs-lookup"><span data-stu-id="e830d-127">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="e830d-128">Dans le champ Atténuation de sécurité, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e830d-128">In the Security mitigation field, type a value.</span></span>
    * <span data-ttu-id="e830d-129">Entrez une description des actions que vous prenez pour atténuer le risque de sécurité.</span><span class="sxs-lookup"><span data-stu-id="e830d-129">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="e830d-130">Par exemple, vous pouvez atténuer le risque en conduisant des examens plus détaillés du processus, en conduisant une révision décisionnelle mensuelle, ou en partageant des ressources avec d'autres départements.</span><span class="sxs-lookup"><span data-stu-id="e830d-130">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>  
13. <span data-ttu-id="e830d-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e830d-131">Click Save.</span></span>

