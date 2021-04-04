---
title: Créer un modèle d’enregistrement pour faciliter la saisie des données
description: Cette rubrique montre comment créer un modèle d’enregistrement pour ne pas avoir à saisir explicitement les valeurs de champ utilisées régulièrement pour chaque nouvel enregistrement.
author: margoc
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, SysRecordInfo, SysRecordTemplatePromptOnCreate
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3d50dbb161fca0b0bfda18a258e5cef03e43fbeb
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561096"
---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="11ee8-103">Créer un modèle d’enregistrement pour faciliter la saisie des données</span><span class="sxs-lookup"><span data-stu-id="11ee8-103">Create a record template to facilitate data entry</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="11ee8-104">Cette rubrique montre comment créer un modèle d’enregistrement pour ne pas avoir à saisir explicitement les valeurs de champ utilisées régulièrement pour chaque nouvel enregistrement.</span><span class="sxs-lookup"><span data-stu-id="11ee8-104">This topic demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="11ee8-105">Dans cette procédure, vous allez créer un enregistrement pour de nouveaux ordinateurs portables qui doivent être ajoutés à vos immobilisations.</span><span class="sxs-lookup"><span data-stu-id="11ee8-105">In this procedure, you'll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="11ee8-106">La société fictive USMF sert d’exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="11ee8-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="11ee8-107">Dans le volet de navigation, accédez à **Modules > Immobilisations > Immobilisations > Immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-107">In the navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="11ee8-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-108">Select **New**.</span></span>
3. <span data-ttu-id="11ee8-109">Entrez ou sélectionnez une valeur dans le champ **Groupe d’immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-109">In the **Fixed asset group** field, enter or select a value.</span></span>
4. <span data-ttu-id="11ee8-110">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-110">In the **Name** field, type a value.</span></span> <span data-ttu-id="11ee8-111">Par exemple, entrez **Ordinateur portable entreprise de prospect**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-111">For example, enter **Corporate lead laptop**.</span></span>  
5. <span data-ttu-id="11ee8-112">Tapez une valeur dans le champ **Nom de recherche**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-112">In the **Search name** field, type a value.</span></span> <span data-ttu-id="11ee8-113">Par exemple, entrez **ordinateur portable**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-113">For example, enter **laptop**.</span></span>  
6. <span data-ttu-id="11ee8-114">Développez la section **Informations techniques**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-114">Expand the **Technical information** section.</span></span>
7. <span data-ttu-id="11ee8-115">Entrez des valeurs dans les champs **Fabrication**, **Modèle** et **Année du modèle**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-115">In the **Make**, **Model**, and **Model year** fields, type values.</span></span>
8. <span data-ttu-id="11ee8-116">Dans le volet Actions, sélectionnez **Options**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-116">On the Action Pane, select **Options**.</span></span>
9. <span data-ttu-id="11ee8-117">Sélectionnez **Infos sur l’enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-117">Select **Record info**.</span></span>
10. <span data-ttu-id="11ee8-118">Sélectionnez **Modèle utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-118">Select **User template**.</span></span>
11. <span data-ttu-id="11ee8-119">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-119">In the **Name** field, type a value.</span></span>
12. <span data-ttu-id="11ee8-120">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-120">In the **Description** field, type a value.</span></span>
13. <span data-ttu-id="11ee8-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-121">Select **OK**.</span></span>
14. <span data-ttu-id="11ee8-122">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="11ee8-122">Select **Close**.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]