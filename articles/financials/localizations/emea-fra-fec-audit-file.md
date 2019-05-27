---
title: Génération du fichier d'audit standard pour la France (FEC)
description: Cette rubrique décrit le processus de génération du fichier d'audit standard pour la France (FEC) dans Microsoft Dynamics 365 for Finance and Operations.
author: ShylaThompson
manager: AnnBe
ms.date: 11/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: France
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b5376923ed5e4c9acafd6a0f2d7af3cdc1a0a9e
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1537941"
---
# <a name="create-standard-audit-file-for-france-fec"></a><span data-ttu-id="6b3b3-103">Créer un fichier d'audit standard pour la France (FEC)</span><span class="sxs-lookup"><span data-stu-id="6b3b3-103">Create Standard Audit File for France (FEC)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6b3b3-104">Cette procédure vous montre comment générer le fichier d'audit standard (FEC) pour la France dans le format de fichier électronique.</span><span class="sxs-lookup"><span data-stu-id="6b3b3-104">This procedure walks you through generating the Standard Audit File (FEC) for France in the electronic file format.</span></span> <span data-ttu-id="6b3b3-105">L'administration fiscale française a besoin de fichiers d'audit générés au format FEC.</span><span class="sxs-lookup"><span data-stu-id="6b3b3-105">French tax authorities require audit files that are generated in the FEC format.</span></span>

<span data-ttu-id="6b3b3-106">Avant de pouvoir générer un fichier FEC, vous devez importer la version la plus récente de la Configuration de la gestion des états électroniques **Importer le fichier XML des données de comptabilité FEC de configuration (FR)**.</span><span class="sxs-lookup"><span data-stu-id="6b3b3-106">Before you can generate an FEC file, you must import the latest version of the Electronic reporting configuration **Import configuration FEC Accounting data XML (FR)**.</span></span> <span data-ttu-id="6b3b3-107">Pour plus d'informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)</span><span class="sxs-lookup"><span data-stu-id="6b3b3-107">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)</span></span>

## <a name="generate-the-standard-audit-file-for-france"></a><span data-ttu-id="6b3b3-108">Génération du fichier d'audit standard pour la France</span><span class="sxs-lookup"><span data-stu-id="6b3b3-108">Generate the Standard Audit File for France</span></span>
1.  <span data-ttu-id="6b3b3-109">Accédez à **Comptabilité** > **Recherches et états** > **États de Comptabilité** > **Exportation de données comptables FEC** pour ouvrir la page **Paramètres des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="6b3b3-109">Go to **General Ledger** > **Inquires and reports** > **Ledger reports** > **FEC Accounting data export** to open the **Electronic report parameters** page.</span></span>
2.  <span data-ttu-id="6b3b3-110">Entrez la plage de dates du fichier.</span><span class="sxs-lookup"><span data-stu-id="6b3b3-110">Enter the date range for the file.</span></span>
3.  <span data-ttu-id="6b3b3-111">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b3b3-111">Click **OK**.</span></span>
