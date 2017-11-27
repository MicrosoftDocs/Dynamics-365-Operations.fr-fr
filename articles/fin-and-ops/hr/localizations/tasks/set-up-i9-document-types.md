--- 
title: "Paramétrer les types de documents I-9"
description: "Cette procédure décrit comment afficher et paramétrer des types de documents utilisés pour la vérification du Formulaire I-9."
author: ShielaSogge
manager: AnnBe
ms.date: 11/01/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 950237499441e7f1d5b9e3355c4bd9513ad3783e
ms.openlocfilehash: b47998eccd7509154ee8863e2e19594cc59ac945
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-i-9-document-types"></a><span data-ttu-id="e5230-103">Paramétrer les types de documents I-9</span><span class="sxs-lookup"><span data-stu-id="e5230-103">Set up I-9 document types</span></span>

[!include[task guide banner](../../../includes/task-guide-banner.md)]

<span data-ttu-id="e5230-104">Cette procédure décrit comment afficher et paramétrer des types de documents utilisés pour la vérification du Formulaire I-9.</span><span class="sxs-lookup"><span data-stu-id="e5230-104">This procedure shows how to view and set up document types that are used for I-9 verification.</span></span> <span data-ttu-id="e5230-105">Avant de paramétrer des types de documents I-9, vous devez également paramétrer les agences et les types d'identification.</span><span class="sxs-lookup"><span data-stu-id="e5230-105">Before you set up I-9 document types, you must also set up the issuing agencies and identification types.</span></span> <span data-ttu-id="e5230-106">La société de données de démonstration utilisée pour créer cette procédure s'appelle USMF. Elle inclut des exemples d'agences et des types d'identification nécessaires pour exécuter la procédure.</span><span class="sxs-lookup"><span data-stu-id="e5230-106">The demo data company used to create this procedure is USMF, which includes examples of the issue agencies and identification types that are needed to complete the procedure.</span></span>

1. <span data-ttu-id="e5230-107">Accédez à Ressources humaines > Collaborateurs > I-9 > Types de documents I-9.</span><span class="sxs-lookup"><span data-stu-id="e5230-107">Go to Human resources > Workers > I-9 > I-9 document types.</span></span>
2. <span data-ttu-id="e5230-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e5230-108">Click New.</span></span>
3. <span data-ttu-id="e5230-109">Dans le champ Type de document I-9, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e5230-109">In the I-9 document type field, type a value.</span></span>
    * <span data-ttu-id="e5230-110">Exemple : ID école.</span><span class="sxs-lookup"><span data-stu-id="e5230-110">Example: School ID.</span></span>  
4. <span data-ttu-id="e5230-111">Sélectionnez le type d'identification.</span><span class="sxs-lookup"><span data-stu-id="e5230-111">Select the identification type.</span></span>  <span data-ttu-id="e5230-112">Exemple : ID école</span><span class="sxs-lookup"><span data-stu-id="e5230-112">Example:  School ID</span></span>
    * <span data-ttu-id="e5230-113">Certains types d'identification comprennent un numéro de sécurité sociale (SSN), un numéro de visa, de passeport ou de permis de conduire.</span><span class="sxs-lookup"><span data-stu-id="e5230-113">Examples of identification types include a Social Security number (SSN), visa number, passport ID, or driver's license.</span></span>  
5. <span data-ttu-id="e5230-114">Sélectionnez la liste de documents I-9 utilisée pour le type de document.</span><span class="sxs-lookup"><span data-stu-id="e5230-114">Select the I-9 document list that is used for the document type.</span></span>
    * <span data-ttu-id="e5230-115">Dans le cadre du processus I-9, les employés doivent présenter la documentation qui indique à l'employeur leur identité et leur permis de travail.</span><span class="sxs-lookup"><span data-stu-id="e5230-115">As part of the I-9 process, employees must present documentation that shows the employer their identity and employment authorization.</span></span> <span data-ttu-id="e5230-116">Le site Web des services de citoyenneté et d'immigration des USA contient des informations sur les documents acceptables et sur la liste à laquelle ils appartiennent.</span><span class="sxs-lookup"><span data-stu-id="e5230-116">The US Citizenship and Immigration Services website contains information about which documents are acceptable, and which list they belong to.</span></span>  <span data-ttu-id="e5230-117">http://www.uscis.gov</span><span class="sxs-lookup"><span data-stu-id="e5230-117">http://www.uscis.gov</span></span>  
6. <span data-ttu-id="e5230-118">Dans le champ Formulaire, entrez le numéro de formulaire officiel du type de document.</span><span class="sxs-lookup"><span data-stu-id="e5230-118">In the Form field, Enter the official form number for the document type.</span></span> <span data-ttu-id="e5230-119">Exemple : ID école.</span><span class="sxs-lookup"><span data-stu-id="e5230-119">Example: School ID.</span></span>
    * <span data-ttu-id="e5230-120">Les numéros de formulaires officiels peuvent être recherchés sur le site Web des services de citoyenneté et d'immigration des USA.</span><span class="sxs-lookup"><span data-stu-id="e5230-120">The official form numbers can be found on the US Citizenship and Immigration Services website.</span></span>  <span data-ttu-id="e5230-121">http://www.uscis.gov</span><span class="sxs-lookup"><span data-stu-id="e5230-121">http://www.uscis.gov</span></span>  
7. <span data-ttu-id="e5230-122">Cochez ou décochez la case Activer.</span><span class="sxs-lookup"><span data-stu-id="e5230-122">Check or uncheck the Active checkbox.</span></span>
8. <span data-ttu-id="e5230-123">Dans le champ Expiration, définissez la date sur « 27-10-2019 ».</span><span class="sxs-lookup"><span data-stu-id="e5230-123">In the Expire field, set the date to '2019-10-27'.</span></span>
    * <span data-ttu-id="e5230-124">La date d'expiration est facultative.</span><span class="sxs-lookup"><span data-stu-id="e5230-124">The expiration date is optional.</span></span>  
9. <span data-ttu-id="e5230-125">Sélectionnez l'agence ayant émis le type de document.</span><span class="sxs-lookup"><span data-stu-id="e5230-125">Select the agency that issued the document type.</span></span> <span data-ttu-id="e5230-126">Exemple : Province/territoire</span><span class="sxs-lookup"><span data-stu-id="e5230-126">Example: Province/territory</span></span>
10. <span data-ttu-id="e5230-127">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e5230-127">Click Save.</span></span>


