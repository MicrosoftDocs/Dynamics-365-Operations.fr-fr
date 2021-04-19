---
title: Générer des documents électroniques et mettre à jour des données de l’application à l’aide de la gestion des états électroniques (ER)
description: Vous pouvez concevoir des formats d’états électroniques (ER) qui peuvent être utilisés dans l’application pour générer des documents électroniques sortants.
author: NickSelin
ms.date: 11/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 863c69446e9a7d447847483ec129788e85a8fd58
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750032"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a><span data-ttu-id="c777f-103">Générer des documents électroniques et mettre à jour les données d’application à l’aide des états électroniques</span><span class="sxs-lookup"><span data-stu-id="c777f-103">Generate electronic documents and update application data by using ER</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c777f-104">Vous pouvez concevoir des formats d’états électroniques (ER) qui peuvent être utilisés dans l’application pour générer des documents électroniques sortants.</span><span class="sxs-lookup"><span data-stu-id="c777f-104">You can design Electronic reporting (ER) formats that can be used in the application to generate outgoing electronic documents.</span></span> <span data-ttu-id="c777f-105">Vous pouvez également concevoir les formats ER qui analysent les documents électroniques entrants et utilisent le contenu de ces documents pour mettre à jour des données d’application.</span><span class="sxs-lookup"><span data-stu-id="c777f-105">You can also design ER formats that parse incoming electronic documents and use the content in those documents to update application data.</span></span>

<span data-ttu-id="c777f-106">Avec cette fonctionnalité, un format ER simple peut être utilisé pour générer les documents électroniques sortants, puis de mettre à jour les données de l’application.</span><span class="sxs-lookup"><span data-stu-id="c777f-106">With this functionality, a single ER format can be used to generate outgoing electronic documents and then update the application data.</span></span> <span data-ttu-id="c777f-107">Cette fonction peut être utilisée dans les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="c777f-107">This feature can be used in the following scenarios:</span></span>

- <span data-ttu-id="c777f-108">Pour empêcher toute utilisation répétée des données d’application dans les processus suivants, vous pouvez marquer les données d’une application immédiatement après la génération des documents électroniques.</span><span class="sxs-lookup"><span data-stu-id="c777f-108">To prevent repeated usage of application data in subsequent processes you can mark an application’s data immediately after it is used to generate electronic documents.</span></span> <span data-ttu-id="c777f-109">Par exemple, vous pouvez marquer les transactions de paiement comme effectué immédiatement après leur ajout à un message de paiement généré.</span><span class="sxs-lookup"><span data-stu-id="c777f-109">For example, you can mark payment transactions as already processed immediately after they have been included in a generated payment message.</span></span>
- <span data-ttu-id="c777f-110">Pour enregistrer les détails de traitement des documents électroniques générés à l’aide de la logique ER.</span><span class="sxs-lookup"><span data-stu-id="c777f-110">To store the processing details of electronic documents that have been generated using ER logic.</span></span> <span data-ttu-id="c777f-111">Par exemple, une identification de message de paiement qui est générée avec l’expression ER.</span><span class="sxs-lookup"><span data-stu-id="c777f-111">For example, a unique payment message identification that is generated using the ER expression.</span></span> <span data-ttu-id="c777f-112">L’expression est basée sur les informations entrées dans la boîte de dialogue ER lorsque le format ER est exécuté pour générer des documents.</span><span class="sxs-lookup"><span data-stu-id="c777f-112">The expression is based on information entered in the ER dialog box when the ER format is run to generate documents.</span></span>

<span data-ttu-id="c777f-113">Pour en savoir plus sur cette fonction, consultez l’ensemble ER Générer des documents avec la mise à jour des données d’application – Guides de tâches (qui fait partie du processus d’entreprise 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)) qui vous guidera dans les détails de la génération et l’archivage d’états de déclaration d’échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="c777f-113">To learn more about this feature, play the set of ER Generate documents with application data update Task guides (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process), which walk you through the details of Intrastat reporting and archiving.</span></span> <span data-ttu-id="c777f-114">Les fichiers suivants sont nécessaires pour exécuter certaines étapes de ces guides de tâche.</span><span class="sxs-lookup"><span data-stu-id="c777f-114">The following files are required to complete certain steps in these Task guides.</span></span> <span data-ttu-id="c777f-115">Téléchargez et enregistrez ces fichiers sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="c777f-115">Download and save these files to your local machine.</span></span>

- [<span data-ttu-id="c777f-116">Configuration du modèle de données ER : Déclaration d’échanges de biens (modèle)</span><span class="sxs-lookup"><span data-stu-id="c777f-116">ER data model configuration: Intrastat (model)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="c777f-117">Configuration du mappage de modèle ER : Déclaration d’échanges de biens (mappage)</span><span class="sxs-lookup"><span data-stu-id="c777f-117">ER model mapping configuration: Intrastat (mapping)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="c777f-118">Configuration du format ER : Déclaration d’échanges de biens (format)</span><span class="sxs-lookup"><span data-stu-id="c777f-118">ER format configuration: Intrastat (format)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]