---
title: Vue d’ensemble des modèles d’enregistrement
description: Cet article présente le concept des modèles d’enregistrement et explique comment ils permettent de créer des enregistrements partageant des informations.
author: pvillads
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a37b4875fd2bf6e981cbe6ee2cc7e999be7b5f36
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559891"
---
# <a name="record-templates-overview"></a><span data-ttu-id="b60d0-103">Vue d’ensemble des modèles d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="b60d0-103">Record templates overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b60d0-104">Cet article présente le concept des modèles d’enregistrement et explique comment ils permettent de créer des enregistrements partageant des informations.</span><span class="sxs-lookup"><span data-stu-id="b60d0-104">This article introduces the concept of record templates and explains how they can be used to create records that share information.</span></span>

<span data-ttu-id="b60d0-105">Les modèles d’enregistrement vous permettent de créer des enregistrements plus rapidement, mais vous ne pouvez créer des modèles d’enregistrement que pour certains types d’enregistrements.</span><span class="sxs-lookup"><span data-stu-id="b60d0-105">Record templates can help you to create records more quickly, however you can only create record templates for some record types.</span></span>

<span data-ttu-id="b60d0-106">Imaginez par exemple que vous entrez des informations relatives à la location pour une agence de location de voitures située à San Francisco.</span><span class="sxs-lookup"><span data-stu-id="b60d0-106">For example, imagine you are entering rental information for a car rental business that is located in San Francisco.</span></span> <span data-ttu-id="b60d0-107">Comme la plupart des clients sont susceptibles d’être de la région de San Francisco, il serait judicieux de remplir automatiquement les valeurs des champs **État**, **Pays** et **Ville** dans le formulaire de location.</span><span class="sxs-lookup"><span data-stu-id="b60d0-107">Since most of the customers are likely to be from the San Francisco area, it would be nice if you could automatically fill in the values for the **State**, **Country**, and **City** fields on the rental form.</span></span>

> [!NOTE]
> <span data-ttu-id="b60d0-108">Vous pouvez uniquement appliquer des modèles dans les secteurs auxquels vous avez accès.</span><span class="sxs-lookup"><span data-stu-id="b60d0-108">You can apply templates only in areas that you have access to.</span></span> <span data-ttu-id="b60d0-109">Toutefois, tous les titres de modèle sont visibles par vous lorsque vous créez un enregistrement et par tous les autres utilisateurs également, si vous créez des modèles disponibles pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b60d0-109">However all template titles are visible to you when you create a new record, and to other users as well, if you are creating templates that will be available for all users.</span></span> <span data-ttu-id="b60d0-110">Prenez cela en considération lorsque vous donnez un nom aux modèles.</span><span class="sxs-lookup"><span data-stu-id="b60d0-110">Be sure to consider this when naming templates.</span></span> <span data-ttu-id="b60d0-111">Par exemple, évitez d’utiliser des noms comportant des mots tels que « commission » si tous les utilisateurs ne sont pas supposés savoir que certains employés de la société sont rémunérés à la commission.</span><span class="sxs-lookup"><span data-stu-id="b60d0-111">For example, avoid using names that include words, such as "commission," if is confidential that some employees in the company have commission-based salaries.</span></span>

<span data-ttu-id="b60d0-112">Lorsqu’un ou plusieurs modèles auxquels vous avez accès existent pour un écran spécifique et que vous tentez de créer un enregistrement dans l’écran, la page **Sélectionner un modèle pour** est affichée.</span><span class="sxs-lookup"><span data-stu-id="b60d0-112">When one or more templates that you have access to exist for a specific form and you attempt to create a new record in the form, the **Select a template for** page is displayed.</span></span> <span data-ttu-id="b60d0-113">Lorsque vous sélectionnez un modèle dans la liste, le nouvel enregistrement créé contient les informations par défaut basées sur le modèle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b60d0-113">When you select a template from the list, the new record is created and contains default information that is based on the template that you selected.</span></span> <span data-ttu-id="b60d0-114">Si vous ne souhaitez pas utiliser de modèles lorsque vous créez des enregistrements, activez la case à cocher **Ne plus demander** dans l’écran **Sélectionner un modèle pour**.</span><span class="sxs-lookup"><span data-stu-id="b60d0-114">If you do not want to use templates when you create new records, select the **Do not ask again** check box in the **Select a template for** page.</span></span> <span data-ttu-id="b60d0-115">Pour afficher de nouveau la boîte de dialogue de sélection du modèle, cliquez avec le bouton droit sur un enregistrement quelconque, cliquez sur **Infos sur l’enregistrement**, puis sur **Afficher la sélection de modèle**.</span><span class="sxs-lookup"><span data-stu-id="b60d0-115">To display the template selection dialog box again, right-click any record, click **Record info**, and then click **Show template selection**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]