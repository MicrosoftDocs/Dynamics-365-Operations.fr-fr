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
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: France
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 931b34b5a88811e359603c1023217951b05f3b57
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852249"
---
# <a name="create-standard-audit-file-for-france-fec"></a><span data-ttu-id="edf47-103">Créer un fichier d'audit standard pour la France (FEC)</span><span class="sxs-lookup"><span data-stu-id="edf47-103">Create Standard Audit File for France (FEC)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="edf47-104">Cette procédure vous montre comment générer le fichier d'audit standard (FEC) pour la France dans le format de fichier électronique.</span><span class="sxs-lookup"><span data-stu-id="edf47-104">This procedure walks you through generating the Standard Audit File (FEC) for France in the electronic file format.</span></span> <span data-ttu-id="edf47-105">L'administration fiscale française a besoin de fichiers d'audit générés au format FEC.</span><span class="sxs-lookup"><span data-stu-id="edf47-105">French tax authorities require audit files that are generated in the FEC format.</span></span>

<span data-ttu-id="edf47-106">Avant de générer un fichier d'audit FEC, vous devez</span><span class="sxs-lookup"><span data-stu-id="edf47-106">Before you can generate a FEC audit file, you must</span></span> 
1. <span data-ttu-id="edf47-107">Importer la dernière version du **Fichier d'audit FEC français** de la configuration de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="edf47-107">Import the latest version of the Electronic reporting configuration **French FEC audit file**.</span></span> <span data-ttu-id="edf47-108">Pour plus d'informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)</span><span class="sxs-lookup"><span data-stu-id="edf47-108">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)</span></span>
2. <span data-ttu-id="edf47-109">Dans la page **Configurations**, développez **Modèle d'exportation des données**, sélectionnez **Mise en correspondance de modèle FEC français**.</span><span class="sxs-lookup"><span data-stu-id="edf47-109">On the **Configurations** page, expand **Data export model**, select **French FEC model mapping**.</span></span> <span data-ttu-id="edf47-110">Définissez **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**</span><span class="sxs-lookup"><span data-stu-id="edf47-110">Set **Default for model mapping** to **Yes**</span></span>

## <a name="generate-the-standard-audit-file-for-france"></a><span data-ttu-id="edf47-111">Génération du fichier d'audit standard pour la France</span><span class="sxs-lookup"><span data-stu-id="edf47-111">Generate the Standard Audit File for France</span></span>
1. <span data-ttu-id="edf47-112">Accédez à **Comptabilité générale** > **Tâches périodiques** > **Exportation de données** pour ouvrir la page **Exportation de données**.</span><span class="sxs-lookup"><span data-stu-id="edf47-112">Go to **General Ledger** > **Periodic tasks** > **Data export** to open the **Data export** page.</span></span>
2. <span data-ttu-id="edf47-113">Dans le champ **Mise en correspondance des formats**, sélectionnez *Fichier d'audit FEC français*.</span><span class="sxs-lookup"><span data-stu-id="edf47-113">In the **Format mapping** field, select *French FEC audit file*.</span></span>
3. <span data-ttu-id="edf47-114">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="edf47-114">Click **OK**.</span></span>
4. <span data-ttu-id="edf47-115">Dans la page **Paramètres de génération d'états électroniques**, entrez les dates de début et de fin de la période dans les champs **Période - date de début**, **Période - Date de fin** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="edf47-115">On the **Electronic report parameters** page, enter start and end dates of the period in the fields **Period - date from**, **Period - date to** and click **OK**.</span></span>
5. <span data-ttu-id="edf47-116">Examinez le fichier généré.</span><span class="sxs-lookup"><span data-stu-id="edf47-116">Review the generated file.</span></span>
