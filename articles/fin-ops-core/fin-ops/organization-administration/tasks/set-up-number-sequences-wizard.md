---
title: Configurer les souches de numéros à l'aide d'un assistant
description: Cette rubrique explique comment définir toutes les souches de numéros requises en même temps à l'aide d'un Assistant.
author: sericks007
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f97c4cd6cdb117ebdd67a155478bb6f8d1703541
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177805"
---
# <a name="set-up-number-sequences-using-a-wizard"></a><span data-ttu-id="36fa5-103">Configurer les souches de numéros à l'aide d'un assistant</span><span class="sxs-lookup"><span data-stu-id="36fa5-103">Set up number sequences using a wizard</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="36fa5-104">Les souches de numéros permettent de générer des identificateurs uniques et consultables pour les enregistrements de données principales et de transaction qui en ont besoin.</span><span class="sxs-lookup"><span data-stu-id="36fa5-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require them.</span></span> <span data-ttu-id="36fa5-105">Un enregistrement de données principales ou de transaction nécessitant un identificateur est également appelé référence.</span><span class="sxs-lookup"><span data-stu-id="36fa5-105">A master data or transaction record that requires an identifier is referred to as a reference.</span></span> <span data-ttu-id="36fa5-106">Avant de pouvoir créer des enregistrements pour une référence, vous devez paramétrer une souche de numéros et l'associer à la référence.</span><span class="sxs-lookup"><span data-stu-id="36fa5-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="36fa5-107">Cette rubrique explique comment définir toutes les souches de numéros requises en même temps à l'aide d'un Assistant.</span><span class="sxs-lookup"><span data-stu-id="36fa5-107">This topic explains how to set up all required number sequences at the same time by using a wizard.</span></span> <span data-ttu-id="36fa5-108">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="36fa5-108">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="36fa5-109">Accédez à **Navigation > Modules > Administration d'organisation > Souches de numéros > Souches de numéros**.</span><span class="sxs-lookup"><span data-stu-id="36fa5-109">Go to **Navigation > Modules > Organization administration > Number sequences > Number sequences**.</span></span>
2. <span data-ttu-id="36fa5-110">Sélectionnez **Générer**.</span><span class="sxs-lookup"><span data-stu-id="36fa5-110">Select **Generate**.</span></span>
3. <span data-ttu-id="36fa5-111">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="36fa5-111">Select **Next**.</span></span>

   - <span data-ttu-id="36fa5-112">Dans cette page, vous pouvez modifier le code d'identification, la valeur la plus faible et la valeur la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="36fa5-112">On this page, you can modify the identification code, the lowest value, and the highest value.</span></span> <span data-ttu-id="36fa5-113">De plus, vous pouvez indiquer si la souche de numéros doit être continue.</span><span class="sxs-lookup"><span data-stu-id="36fa5-113">In addition, you can indicate whether the number sequence must be continuous.</span></span>   
   - <span data-ttu-id="36fa5-114">Ne sélectionnez pas l'option **Continue** si vous devez préalablement affecter des numéros pour la souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="36fa5-114">Do not select the **Continuous** option if you must preallocate numbers for the number sequence.</span></span> <span data-ttu-id="36fa5-115">Pour ajouter un segment de portée au format d'une souche de numéros, sélectionnez le format dans la liste, puis sélectionnez **Inclure la portée dans le format**.</span><span class="sxs-lookup"><span data-stu-id="36fa5-115">To add a scope segment to the format of a number sequence, select the format in the list, and then select **Include scope in format**.</span></span> <span data-ttu-id="36fa5-116">Pour supprimer un segment de portée du format d'une souche de numéros, sélectionnez le format dans la liste, puis sélectionnez **Supprimer la portée du format**.</span><span class="sxs-lookup"><span data-stu-id="36fa5-116">To remove a scope segment from the format of a number sequence, select the format in the list, and then select **Remove scope from format**.</span></span> <span data-ttu-id="36fa5-117">Pour exclure une souche de numéros du processus de génération automatique, sélectionnez la souche de numéros dans la liste, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="36fa5-117">To exclude a number sequence from automatic generation, select the number sequence in the list, and then select **Delete**.</span></span>  

4. <span data-ttu-id="36fa5-118">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="36fa5-118">Select **Next**.</span></span>
5. <span data-ttu-id="36fa5-119">Sélectionnez **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="36fa5-119">Select **Finish**.</span></span>

