--- 
title: "Importer la configuration du débit direct ISO20022"
description: "Cette procédure montre comment importer une configuration de génération d'états électroniques pour un paiement client."
author: mrolecki
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: bb2413e69464068ecde59b5ea7642e102e78e6d8
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="import-iso20022-direct-debit-configuration"></a><span data-ttu-id="a06f0-103">Importer la configuration du débit direct ISO20022</span><span class="sxs-lookup"><span data-stu-id="a06f0-103">Import ISO20022 direct debit configuration</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a06f0-104">Cette procédure montre comment importer une configuration de génération d'états électroniques pour un paiement client.</span><span class="sxs-lookup"><span data-stu-id="a06f0-104">This procedure demonstrates how to import a customer payment electronic reporting configuration.</span></span> <span data-ttu-id="a06f0-105">Cette procédure utilise le format de débit direct ISO 20022 comme exemple.</span><span class="sxs-lookup"><span data-stu-id="a06f0-105">This procedure uses the ISO 20022 direct debit format as an example.</span></span> 



<span data-ttu-id="a06f0-106">Cette procédure a été créée à l'aide de la société fictive DEMF, mais vous pouvez utiliser n'importe quelle société fictive à cet effet.</span><span class="sxs-lookup"><span data-stu-id="a06f0-106">This procedure was created using the demo data company DEMF but you can use any demo data company for this purpose.</span></span>



<span data-ttu-id="a06f0-107">Il s'agit de la première des cinq procédures illustrant le processus de paiement client à l'aide des configurations de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="a06f0-107">This is the first of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="a06f0-108">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="a06f0-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="a06f0-109">Dans la liste des fournisseurs de configuration disponibles, sélectionnez Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a06f0-109">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="a06f0-110">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="a06f0-110">Click Set active.</span></span>
4. <span data-ttu-id="a06f0-111">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="a06f0-111">Click Repositories.</span></span>
5. <span data-ttu-id="a06f0-112">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="a06f0-112">Click Open.</span></span>
6. <span data-ttu-id="a06f0-113">Cliquez sur Afficher les filtres.</span><span class="sxs-lookup"><span data-stu-id="a06f0-113">Click Show filters.</span></span>
7. <span data-ttu-id="a06f0-114">Appliquez les filtres suivants : entrez la valeur de filtre « Débit direct ISO20022 (Allemagne) » dans le champ « Nom de la configuration » à l'aide de l'opérateur de filtre « commence par ».</span><span class="sxs-lookup"><span data-stu-id="a06f0-114">Apply the following filters: Enter a filter value of "ISO20022 Direct debit (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="a06f0-115">Vous pouvez éventuellement rechercher la configuration dans la liste, la sélectionner et ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="a06f0-115">Optionally, you can find the configuration in the list, select it, and skip this step.</span></span>  
8. <span data-ttu-id="a06f0-116">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="a06f0-116">Click Import.</span></span>
    * <span data-ttu-id="a06f0-117">Si le bouton Importer n'est pas disponible, cela signifie que la configuration a déjà été importée.</span><span class="sxs-lookup"><span data-stu-id="a06f0-117">If the Import button is not available, it means that the configuration has been imported already.</span></span>  
9. <span data-ttu-id="a06f0-118">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="a06f0-118">Click Yes.</span></span>


