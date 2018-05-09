--- 
title: "Configurer les souches de numéros à l'aide d'un assistant"
description: "Les souches de numéros permettent de générer des identificateurs uniques et consultables pour les enregistrements de données principales et de transaction qui en ont besoin."
author: sericks007
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e8f3227f231ffc287bd6ea6204ed50f8b684e5fb
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-number-sequences-by-using-a-wizard"></a><span data-ttu-id="dcaeb-103">Configurer les souches de numéros à l'aide d'un assistant</span><span class="sxs-lookup"><span data-stu-id="dcaeb-103">Set up number sequences by using a wizard</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dcaeb-104">Les souches de numéros permettent de générer des identificateurs uniques et consultables pour les enregistrements de données principales et de transaction qui en ont besoin.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require them.</span></span> <span data-ttu-id="dcaeb-105">Un enregistrement de données principales ou de transaction nécessitant un identificateur est également appelé référence.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-105">A master data or transaction record that requires an identifier is referred to as a reference.</span></span> <span data-ttu-id="dcaeb-106">Avant de pouvoir créer des enregistrements pour une référence, vous devez paramétrer une souche de numéros et l'associer à la référence.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="dcaeb-107">Cette procédure explique comment définir toutes les souches de numéros requises en même temps à l'aide d'un Assistant.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-107">This procedure explains how to set up all required number sequences at the same time by using a wizard.</span></span> <span data-ttu-id="dcaeb-108">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-108">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="dcaeb-109">Accédez à Administration d'organisation > Séquences de nombres > Séquences de nombres.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-109">Go to Organization administration > Number sequences > Number sequences.</span></span>
2. <span data-ttu-id="dcaeb-110">Cliquez sur Générer.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-110">Click Generate.</span></span>
3. <span data-ttu-id="dcaeb-111">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-111">Click Next.</span></span>
    * <span data-ttu-id="dcaeb-112">Dans cette page, vous pouvez modifier le code d'identification, la valeur la plus faible et la valeur la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-112">On this page, you can modify the identification code, the lowest value, and the highest value.</span></span> <span data-ttu-id="dcaeb-113">De plus, vous pouvez indiquer si la souche de numéros doit être continue.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-113">In addition, you can indicate whether the number sequence must be continuous.</span></span>   
    * <span data-ttu-id="dcaeb-114">Ne sélectionnez pas l'option Continue si vous devez préalablement affecter des numéros pour la souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-114">Do not select the Continuous option if you must preallocate numbers for the number sequence.</span></span>     <span data-ttu-id="dcaeb-115">Pour ajouter un segment de portée au format d'une souche de numéros, sélectionnez le format dans la liste, puis cliquez sur Inclure la portée dans le format.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-115">To add a scope segment to the format of a number sequence, select the format in the list, and then click Include scope in format.</span></span>     <span data-ttu-id="dcaeb-116">Pour supprimer un segment de portée du format d'une souche de numéros, sélectionnez le format dans la liste, puis cliquez sur Supprimer la portée du format.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-116">To remove a scope segment from the format of a number sequence, select the format in the list, and then click Remove scope from format.</span></span>     <span data-ttu-id="dcaeb-117">Pour exclure une souche de numéros du processus de génération automatique, sélectionnez la souche de numéros dans la liste, puis cliquez sur Supprimer.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-117">To exclude a number sequence from automatic generation, select the number sequence in the list, and then click Delete.</span></span>  
4. <span data-ttu-id="dcaeb-118">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-118">Click Next.</span></span>
5. <span data-ttu-id="dcaeb-119">Cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="dcaeb-119">Click Finish.</span></span>


