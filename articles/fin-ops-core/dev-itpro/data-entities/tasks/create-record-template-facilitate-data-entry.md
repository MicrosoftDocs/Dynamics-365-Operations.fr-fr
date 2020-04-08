---
title: Créer un modèle d'enregistrement pour faciliter la saisie des données
description: Cette rubrique montre comment créer un modèle d'enregistrement pour ne pas avoir à saisir explicitement les valeurs de champ utilisées régulièrement pour chaque nouvel enregistrement.
author: margoc
manager: AnnBe
ms.date: 07/29/2019
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
ms.openlocfilehash: ec21415158ad611d0ad55778e76aa128f53561bd
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143382"
---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="ffe61-103">Créer un modèle d'enregistrement pour faciliter la saisie des données</span><span class="sxs-lookup"><span data-stu-id="ffe61-103">Create a record template to facilitate data entry</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ffe61-104">Cette rubrique montre comment créer un modèle d'enregistrement pour ne pas avoir à saisir explicitement les valeurs de champ utilisées régulièrement pour chaque nouvel enregistrement.</span><span class="sxs-lookup"><span data-stu-id="ffe61-104">This topic demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="ffe61-105">Dans cette procédure, vous allez créer un enregistrement pour de nouveaux ordinateurs portables qui doivent être ajoutés à vos immobilisations.</span><span class="sxs-lookup"><span data-stu-id="ffe61-105">In this procedure, you'll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="ffe61-106">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="ffe61-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="ffe61-107">Dans le volet de navigation, accédez à **Modules > Immobilisations > Immobilisations > Immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-107">In the navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="ffe61-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-108">Select **New**.</span></span>
3. <span data-ttu-id="ffe61-109">Entrez ou sélectionnez une valeur dans le champ **Groupe d'immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-109">In the **Fixed asset group** field, enter or select a value.</span></span>
4. <span data-ttu-id="ffe61-110">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-110">In the **Name** field, type a value.</span></span> <span data-ttu-id="ffe61-111">Par exemple, entrez **Ordinateur portable entreprise de prospect**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-111">For example, enter **Corporate lead laptop**.</span></span>  
5. <span data-ttu-id="ffe61-112">Tapez une valeur dans le champ **Nom de recherche**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-112">In the **Search name** field, type a value.</span></span> <span data-ttu-id="ffe61-113">Par exemple, entrez **ordinateur portable**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-113">For example, enter **laptop**.</span></span>  
6. <span data-ttu-id="ffe61-114">Développez la section **Informations techniques**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-114">Expand the **Technical information** section.</span></span>
7. <span data-ttu-id="ffe61-115">Entrez des valeurs dans les champs **Fabrication**, **Modèle** et **Année du modèle**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-115">In the **Make**, **Model**, and **Model year** fields, type values.</span></span>
8. <span data-ttu-id="ffe61-116">Dans le volet Actions, sélectionnez **Options**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-116">On the Action Pane, select **Options**.</span></span>
9. <span data-ttu-id="ffe61-117">Sélectionnez **Infos sur l'enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-117">Select **Record info**.</span></span>
10. <span data-ttu-id="ffe61-118">Sélectionnez **Modèle utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-118">Select **User template**.</span></span>
11. <span data-ttu-id="ffe61-119">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-119">In the **Name** field, type a value.</span></span>
12. <span data-ttu-id="ffe61-120">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-120">In the **Description** field, type a value.</span></span>
13. <span data-ttu-id="ffe61-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-121">Select **OK**.</span></span>
14. <span data-ttu-id="ffe61-122">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="ffe61-122">Select **Close**.</span></span>

