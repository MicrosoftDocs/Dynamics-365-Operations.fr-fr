---
title: "Générer des documents électroniques et mettre à jour les données d'application à l'aide de l'outil de gestion des états électroniques"
description: "Vous pouvez concevoir des formats d'états électroniques (ER) qui peuvent être utilisés dans l'application Finance and Operations pour générer des documents électroniques sortants. Vous pouvez également concevoir les formats ER qui analysent les documents électroniques entrants et utilisent le contenu de ces documents pour mettre à jour des données d'application."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7378c1d205b9a9cd61044dc33fc52ff75c6b94b7
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="generate-electronic-documents-and-update-application-data-using-the-electronic-reporting-tool"></a><span data-ttu-id="5704c-104">Générer des documents électroniques et mettre à jour les données d'application à l'aide de l'outil de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="5704c-104">Generate electronic documents and update application data using the Electronic reporting tool</span></span>

<span data-ttu-id="5704c-105">Vous pouvez concevoir des formats d'états électroniques (ER) qui peuvent être utilisés dans l'application Finance and Operations pour générer des documents électroniques sortants.</span><span class="sxs-lookup"><span data-stu-id="5704c-105">You can design Electronic reporting (ER) formats that can be used in the Finance and Operations application to generate outgoing electronic documents.</span></span> <span data-ttu-id="5704c-106">Vous pouvez également concevoir les formats ER qui analysent les documents électroniques entrants et utilisent le contenu de ces documents pour mettre à jour des données d'application.</span><span class="sxs-lookup"><span data-stu-id="5704c-106">You can also design ER formats that parse incoming electronic documents and use the content in those documents to update application data.</span></span> 

<span data-ttu-id="5704c-107">Avec cette fonctionnalité, un format ER simple peut être utilisé pour générer les documents électroniques sortants, puis de mettre à jour les données de l'application.</span><span class="sxs-lookup"><span data-stu-id="5704c-107">With this functionality, a single ER format can be used to generate outgoing electronic documents and then update the application data.</span></span> <span data-ttu-id="5704c-108">Cette fonction peut être utilisée dans les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="5704c-108">This feature can be used in the following scenarios:</span></span>

- <span data-ttu-id="5704c-109">Pour empêcher toute utilisation répétée des données d'application dans les processus suivants, vous pouvez marquer les données d'une application immédiatement après la génération des documents électroniques.</span><span class="sxs-lookup"><span data-stu-id="5704c-109">To prevent repeated usage of application data in subsequent processes you can mark an application’s data immediately after it is used to generate electronic documents.</span></span> <span data-ttu-id="5704c-110">Par exemple, vous pouvez marquer les transactions de paiement comme effectué immédiatement après leur ajout à un message de paiement généré.</span><span class="sxs-lookup"><span data-stu-id="5704c-110">For example, you can mark payment transactions as already processed immediately after they have been included in a generated payment message.</span></span>
- <span data-ttu-id="5704c-111">Pour enregistrer les détails de traitement des documents électroniques générés à l'aide de la logique ER.</span><span class="sxs-lookup"><span data-stu-id="5704c-111">To store the processing details of electronic documents that have been generated using ER logic.</span></span> <span data-ttu-id="5704c-112">Par exemple, une identification de message de paiement qui est générée avec l'expression ER.</span><span class="sxs-lookup"><span data-stu-id="5704c-112">For example, a unique payment message identification that is generated using the ER expression.</span></span> <span data-ttu-id="5704c-113">L'expression est basée sur les informations entrées dans la boîte de dialogue ER lorsque le format ER est exécuté pour générer des documents.</span><span class="sxs-lookup"><span data-stu-id="5704c-113">The expression is based on information entered in the ER dialog box when the ER format is run to generate documents.</span></span>

<span data-ttu-id="5704c-114">Pour en savoir plus sur cette fonction, consultez l'ensemble ER Générer des documents avec la mise à jour des données d'application - Guides de tâches (qui fait partie du processus d'entreprise 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)) qui vous guidera dans les détails de la génération et l'archivage d'états de déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="5704c-114">To learn more about this feature, play the set of ER Generate documents with application data update Task guides (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process), which walk you through the details of Intrastat reporting and archiving.</span></span> <span data-ttu-id="5704c-115">Les fichiers suivants sont nécessaires pour exécuter certaines étapes de ces guides de tâche.</span><span class="sxs-lookup"><span data-stu-id="5704c-115">The following files are required to complete certain steps in these Task guides.</span></span> <span data-ttu-id="5704c-116">Téléchargez et enregistrez ces fichiers sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="5704c-116">Download and save these files to your local machine.</span></span>

- [<span data-ttu-id="5704c-117">Configuration du modèle de données ER : Déclaration d'échanges de biens (modèle)</span><span class="sxs-lookup"><span data-stu-id="5704c-117">ER data model configuration: Intrastat (model)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="5704c-118">Configuration du mappage de modèle ER : Déclaration d'échanges de biens (mappage)</span><span class="sxs-lookup"><span data-stu-id="5704c-118">ER model mapping configuration: Intrastat (mapping)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="5704c-119">Configuration du format ER : Déclaration d'échanges de biens (format)</span><span class="sxs-lookup"><span data-stu-id="5704c-119">ER format configuration: Intrastat (format)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
