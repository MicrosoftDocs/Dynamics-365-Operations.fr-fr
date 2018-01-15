---
title: "Modèles d'enregistrement"
description: "Cet article présente le concept des modèles d'enregistrement et explique comment ils permettent de créer des enregistrements partageant des informations."
author: pvillads
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ef5e95d9d6beed10cd6c80aa131c5cbef85c07a8
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="record-templates"></a><span data-ttu-id="c0e17-103">Modèles d'enregistrement</span><span class="sxs-lookup"><span data-stu-id="c0e17-103">Record templates</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c0e17-104">Cet article présente le concept des modèles d'enregistrement et explique comment ils permettent de créer des enregistrements partageant des informations.</span><span class="sxs-lookup"><span data-stu-id="c0e17-104">This article introduces the concept of record templates and explains how they can be used to create records that share information.</span></span>

<span data-ttu-id="c0e17-105">Les modèles d'enregistrement vous aident à créer des enregistrements plus rapidement dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c0e17-105">Record templates can help you to create records more quickly in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="c0e17-106">Vous pouvez créer des modèles d'enregistrement pour seulement certains types d'enregistrements dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c0e17-106">You can create record templates for only some of the record types in Microsoft Dynamics 365 for Finance and Operations.</span></span> 

<span data-ttu-id="c0e17-107">Imaginez par exemple que vous entrez des informations relatives à la location pour une agence de location de voitures située à San Francisco.</span><span class="sxs-lookup"><span data-stu-id="c0e17-107">For example, imagine you are entering rental information for a car rental business that is located in San Francisco.</span></span> <span data-ttu-id="c0e17-108">Comme la plupart des clients sont susceptibles d'être de la région de San Francisco, il serait judicieux de remplir automatiquement les valeurs des champs **État**, **Pays** et **Ville** dans le formulaire de location.</span><span class="sxs-lookup"><span data-stu-id="c0e17-108">Since most of the customers are likely to be from the San Francisco area, it would be nice if you could automatically fill in the values for the **State**, **Country**, and **City** fields on the rental form.</span></span> 

> [!Note]
> <span data-ttu-id="c0e17-109">Vous pouvez uniquement appliquer des modèles pour les zones de Finance and Operations auxquelles vous avez accès.</span><span class="sxs-lookup"><span data-stu-id="c0e17-109">You can apply templates only for the areas of Finance and Operations that you have access to.</span></span> <span data-ttu-id="c0e17-110">Toutefois, tous les titres de modèle sont visibles par vous lorsque vous créez un enregistrement et par tous les autres utilisateurs également, si vous créez des modèles disponibles pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c0e17-110">However all template titles are visible to you when you create a new record, and to other users as well, if you are creating templates that will be available for all users.</span></span> <span data-ttu-id="c0e17-111">Prenez cela en considération lorsque vous donnez un nom aux modèles.</span><span class="sxs-lookup"><span data-stu-id="c0e17-111">Be sure to consider this when naming templates.</span></span> <span data-ttu-id="c0e17-112">Par exemple, évitez d'utiliser des noms comportant des mots tels que « commission » si tous les utilisateurs ne sont pas supposés savoir que certains employés de la société sont rémunérés à la commission.</span><span class="sxs-lookup"><span data-stu-id="c0e17-112">For example, avoid using names that include words, such as "commission," if is confidential that some employees in the company have commission-based salaries.</span></span> 

<span data-ttu-id="c0e17-113">Lorsqu'un ou plusieurs modèles auxquels vous avez accès existent pour un écran spécifique et que vous tentez de créer un enregistrement dans l'écran, la page **Sélectionner un modèle pour** est affichée.</span><span class="sxs-lookup"><span data-stu-id="c0e17-113">When one or more templates that you have access to exist for a specific form and you attempt to create a new record in the form, the **Select a template for** page is displayed.</span></span> <span data-ttu-id="c0e17-114">Lorsque vous sélectionnez un modèle dans la liste, le nouvel enregistrement créé contient les informations par défaut basées sur le modèle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c0e17-114">When you select a template from the list, the new record is created and contains default information that is based on the template that you selected.</span></span> <span data-ttu-id="c0e17-115">Si vous ne souhaitez pas utiliser de modèles lorsque vous créez des enregistrements, activez la case à cocher **Ne plus demander** dans l'écran **Sélectionner un modèle pour**.</span><span class="sxs-lookup"><span data-stu-id="c0e17-115">If you do not want to use templates when you create new records, select the **Do not ask again** check box in the **Select a template for** page.</span></span> <span data-ttu-id="c0e17-116">Pour afficher de nouveau la boîte de dialogue de sélection du modèle, cliquez avec le bouton droit sur un enregistrement quelconque, cliquez sur **Infos sur l'enregistrement**, puis sur **Afficher la sélection de modèle**.</span><span class="sxs-lookup"><span data-stu-id="c0e17-116">To display the template selection dialog box again, right-click any record, click **Record info**, and then click **Show template selection**.</span></span>



