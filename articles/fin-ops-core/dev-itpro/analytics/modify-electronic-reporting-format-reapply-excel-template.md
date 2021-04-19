---
title: Modifier des formats de gestion des états électroniques en réappliquant des modèles Excel
description: Cette rubrique décrit comment modifier le format des états électroniques (ER) utilisé pour générer des documents commerciaux en réappliquant un modèle Excel modifié.
author: NickSelin
ms.date: 06/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0ab7686ac0aba982fd44195214df878ba3ede446
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748715"
---
# <a name="modify-electronic-reporting-formats-by-reapplying-excel-templates"></a><span data-ttu-id="19c5a-103">Modifier des formats de gestion d’états électroniques en réappliquant des modèles Excel</span><span class="sxs-lookup"><span data-stu-id="19c5a-103">Modify Electronic reporting formats by reapplying Excel templates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="19c5a-104">L’outil d’états électroniques (ER) est utilisé pour générer les documents commerciaux dans un format électronique.</span><span class="sxs-lookup"><span data-stu-id="19c5a-104">The Electronic reporting (ER) tool is used to generate business documents in an electronic format.</span></span> <span data-ttu-id="19c5a-105">Pour générer un document commercial, vous devez créer un format d’ER, puis utilisez le concepteur d’ER pour définir la mise en page du document commercial et spécifier les données à y inclure.</span><span class="sxs-lookup"><span data-stu-id="19c5a-105">To generate a business document, you must create an ER format, and then use the ER designer to define the layout of the business document and specify the data that should be included in it.</span></span> <span data-ttu-id="19c5a-106">Vous pouvez ensuite exécuter le format d’ER pour générer le document commercial.</span><span class="sxs-lookup"><span data-stu-id="19c5a-106">You can then run the ER format to generate the business document.</span></span>

<span data-ttu-id="19c5a-107">L’outil d’ER peut être utilisé pour générer des documents commerciaux en tant que fichiers Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="19c5a-107">The ER tool can be used to generate business documents as Microsoft Excel files.</span></span> <span data-ttu-id="19c5a-108">Vous pouvez utiliser un document Excel comme modèle pour ces documents.</span><span class="sxs-lookup"><span data-stu-id="19c5a-108">You can use an Excel document as a template for these documents.</span></span> <span data-ttu-id="19c5a-109">Pour définir le modèle de document dans le concepteur d’ER, vous pouvez importer le contenu du document Excel que vous souhaitez utiliser comme modèle dans le format défini d’ER.</span><span class="sxs-lookup"><span data-stu-id="19c5a-109">To define the document layout in the ER designer, you can import the contents of the Excel document that you want to use as a template into the defined ER format.</span></span> <span data-ttu-id="19c5a-110">Pour plus d’informations et pour mettre en pratique ce scénario, visionnez le guide de tâche **ER Concevoir une configuration pour générer des états au format OPENXML** (qui fait partie du processus d’entreprise 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)).</span><span class="sxs-lookup"><span data-stu-id="19c5a-110">For more details, and to practice this scenario, play the task guide **ER Design a configuration for generating reports in OPENXML format** (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process).</span></span>

<span data-ttu-id="19c5a-111">Si vous modifiez le document Excel utilisé comme modèle pour un document commercial, la nouvelle fonctionnalité d’ER vous permet de réappliquer le modèle mis à jour dans le format d’ER.</span><span class="sxs-lookup"><span data-stu-id="19c5a-111">If you edit the Excel document that is used as a template for a business document, new ER functionality lets you reapply the updated template to the ER format.</span></span> <span data-ttu-id="19c5a-112">Le format d’ER est alors mis à jour de sorte qu’il s’applique au modèle mis à jour.</span><span class="sxs-lookup"><span data-stu-id="19c5a-112">The ER format is then updated so that it adheres to the updated template.</span></span> <span data-ttu-id="19c5a-113">Pour plus d’informations sur cette fonctionnalité, visionnez le guide de tâche **ER Modifier un format en réappliquant un modèle Excel** (qui fait partie du processus d’entreprise 7.5.5.3 Acquérir/Développer des composants de services/solutions informatiques (10683)).</span><span class="sxs-lookup"><span data-stu-id="19c5a-113">For more details about this functionality, play the task guide **ER Modify a format by reapplying an Excel template** (part of the 7.5.5.3 Acquire/Develop IT service/solution components (10683) business process).</span></span> <span data-ttu-id="19c5a-114">Dans le cadre de l’étape du guide de tâche au cours de laquelle vous importez un modèle mis à jour, utilisez le modèle modifié du fichier Excel d’état de paiement, SampleVendPaymWsReport2, en tant que modèle.</span><span class="sxs-lookup"><span data-stu-id="19c5a-114">In the task guide step where you import an updated template, use the modified template of the Payment Report Excel file, SampleVendPaymWsReport2, as a template.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]