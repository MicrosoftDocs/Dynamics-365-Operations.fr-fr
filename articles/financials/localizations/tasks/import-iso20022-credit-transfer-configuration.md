---
title: Importer la configuration du virement ISO20022
description: Cette procédure indique comment importer une configuration de génération d'états électroniques pour un paiement fournisseur.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3fbd2e39f488696ebe8db5579ed88595e246ce97
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1573115"
---
# <a name="import-iso20022-credit-transfer-configuration"></a><span data-ttu-id="4b35f-103">Importer la configuration du virement ISO20022</span><span class="sxs-lookup"><span data-stu-id="4b35f-103">Import ISO20022 credit transfer configuration</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4b35f-104">Cette procédure indique comment importer une configuration de génération d'états électroniques pour un paiement fournisseur.</span><span class="sxs-lookup"><span data-stu-id="4b35f-104">This procedure shows how to import a vendor payment electronic reporting configuration.</span></span> <span data-ttu-id="4b35f-105">Le format du virement ISO 20022 allemand est utilisé comme exemple.</span><span class="sxs-lookup"><span data-stu-id="4b35f-105">The German ISO 20022 credit transfer format is used as an example.</span></span> <span data-ttu-id="4b35f-106">Cette procédure peut être utilisée pour tout autre format de génération d'états électroniques disponible.</span><span class="sxs-lookup"><span data-stu-id="4b35f-106">This procedure can be used for other available electronic reporting format.</span></span> 

<span data-ttu-id="4b35f-107">Cette tâche a été créée à l'aide de la société fictive DEMF, mais vous pouvez utiliser n'importe quelle société fictive pour effectuer cette tâche.</span><span class="sxs-lookup"><span data-stu-id="4b35f-107">This task was created using the demo data company DEMF but you can use any demo data company to complete this task.</span></span>

<span data-ttu-id="4b35f-108">Il s'agit de la première des cinq tâches illustrant le processus de paiement fournisseur à l'aide des configurations de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="4b35f-108">This is the first of five tasks, that together illustrate the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="4b35f-109">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="4b35f-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="4b35f-110">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="4b35f-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="4b35f-111">Dans la liste des fournisseurs de configuration disponibles, sélectionnez Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4b35f-111">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="4b35f-112">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="4b35f-112">Click Set active.</span></span>
4. <span data-ttu-id="4b35f-113">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="4b35f-113">Click Repositories.</span></span>
5. <span data-ttu-id="4b35f-114">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="4b35f-114">Click Open.</span></span>
6. <span data-ttu-id="4b35f-115">Cliquez sur Afficher les filtres.</span><span class="sxs-lookup"><span data-stu-id="4b35f-115">Click Show filters.</span></span>
7. <span data-ttu-id="4b35f-116">Appliquez les filtres suivants : entrez la valeur de filtre « Virement ISO20022 (Allemagne) » dans le champ « Nom de la configuration » à l'aide de l'opérateur de filtre « commence par ».</span><span class="sxs-lookup"><span data-stu-id="4b35f-116">Apply the following filters: Enter a filter value of "ISO20022 Credit transfer (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="4b35f-117">Vous pouvez également rechercher la configuration dans la liste, la sélectionner et la déplacer dans la tâche d'importation.</span><span class="sxs-lookup"><span data-stu-id="4b35f-117">Alternatively, you can find the configuration in the list, select it, and then move it to the Import task.</span></span>  
8. <span data-ttu-id="4b35f-118">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="4b35f-118">Click Import.</span></span>
    * <span data-ttu-id="4b35f-119">Si le bouton Importer n'est pas disponible, cela signifie que la configuration a déjà été importée.</span><span class="sxs-lookup"><span data-stu-id="4b35f-119">If the Import button is not available, it means that the configuration has  already been imported.</span></span>  
9. <span data-ttu-id="4b35f-120">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="4b35f-120">Click Yes.</span></span>

