---
title: Créer un modèle d'enregistrement pour faciliter la saisie des données
description: Cette procédure montre comment créer un modèle d'enregistrement pour ne pas avoir à saisir explicitement les valeurs de champ utilisées régulièrement pour chaque nouvel enregistrement.
author: margoc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, SysRecordInfo, SysRecordTemplatePromptOnCreate
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3b2ba56b6146f2495fb6a53c3cef9f549b1ad837
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848205"
---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="22189-103">Créer un modèle d'enregistrement pour faciliter la saisie des données</span><span class="sxs-lookup"><span data-stu-id="22189-103">Create a record template to facilitate data entry</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="22189-104">Cette procédure montre comment créer un modèle d'enregistrement pour ne pas avoir à saisir explicitement les valeurs de champ utilisées régulièrement pour chaque nouvel enregistrement.</span><span class="sxs-lookup"><span data-stu-id="22189-104">This procedure demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="22189-105">Dans cette procédure, vous allez créer un enregistrement pour de nouveaux ordinateurs portables qui doivent être ajoutés à vos immobilisations.</span><span class="sxs-lookup"><span data-stu-id="22189-105">In this procedure, you’ll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="22189-106">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="22189-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="22189-107">Accédez à Immobilisations > Immobilisations > Immobilisations.</span><span class="sxs-lookup"><span data-stu-id="22189-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="22189-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="22189-108">Click New.</span></span>
3. <span data-ttu-id="22189-109">Saisissez ou sélectionnez une valeur dans le champ Groupe d'immobilisations.</span><span class="sxs-lookup"><span data-stu-id="22189-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="22189-110">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="22189-110">In the Name field, type a value.</span></span>
    * <span data-ttu-id="22189-111">Par exemple, entrez « Ordinateur portable entreprise de prospect ».</span><span class="sxs-lookup"><span data-stu-id="22189-111">For example, enter 'Corporate lead laptop'.</span></span>  
5. <span data-ttu-id="22189-112">Dans le champ Rechercher, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="22189-112">In the Search name field, type a value.</span></span>
    * <span data-ttu-id="22189-113">Par exemple, entrez « ordinateur portable ».</span><span class="sxs-lookup"><span data-stu-id="22189-113">For example, enter 'laptop.'</span></span>  
6. <span data-ttu-id="22189-114">Développez la section Informations techniques.</span><span class="sxs-lookup"><span data-stu-id="22189-114">Expand the Technical information section.</span></span>
7. <span data-ttu-id="22189-115">Dans le champ Faire, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="22189-115">In the Make field, type a value.</span></span>
8. <span data-ttu-id="22189-116">Dans le champ Modèle, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="22189-116">In the Model field, type a value.</span></span>
9. <span data-ttu-id="22189-117">Dans le champ Année du modèle, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="22189-117">In the Model year field, type a value.</span></span>
10. <span data-ttu-id="22189-118">Dans le volet Actions, cliquez sur Options.</span><span class="sxs-lookup"><span data-stu-id="22189-118">On the Action Pane, click Options.</span></span>
11. <span data-ttu-id="22189-119">Cliquez sur Infos sur l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="22189-119">Click Record info.</span></span>
12. <span data-ttu-id="22189-120">Cliquez sur Modèle d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="22189-120">Click User template.</span></span>
13. <span data-ttu-id="22189-121">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="22189-121">In the Name field, type a value.</span></span>
    * <span data-ttu-id="22189-122">Par exemple, entrez « Ordinateur portable entreprise ».</span><span class="sxs-lookup"><span data-stu-id="22189-122">For example, enter 'Corporate laptop.'</span></span>  
14. <span data-ttu-id="22189-123">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="22189-123">In the Description field, type a value.</span></span>
    * <span data-ttu-id="22189-124">Par exemple, entrez « Ordinateur portable entreprise ».</span><span class="sxs-lookup"><span data-stu-id="22189-124">For example, enter 'Corporate laptop'.</span></span>  
15. <span data-ttu-id="22189-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="22189-125">Click OK.</span></span>
16. <span data-ttu-id="22189-126">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="22189-126">Click Close.</span></span>

