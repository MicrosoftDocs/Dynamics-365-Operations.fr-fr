---
title: Utiliser l'importation/exportation rapide
description: "Le but de l’exportation/importation rapide est de vous permettre d’importer et d'exporter avec moins d’étapes."
author: margoc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: dynamics-ax-2012
ms.service: 
ms.technology: 
audience: Application User
ms.reviewer: margoc
ms.search.scope: AX 2012
ms.custom: 89041
ms.assetid: 990d64e6-d436-4c79-9bb5-bf8c5c5a048f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 
ms.dyn365.ops.version: AX 2012 R3 CU8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 14b4a56a229a2e1eb15c29eb7a89a89ac31e58db
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="run-the-test-data-transfer-tool-beta-for-dynamics-ax-ax-2012"></a><span data-ttu-id="7aa8d-103">Exécuter l'Outil de transfert de données de test (bêta) dans Dynamics AX (AX 2012)</span><span class="sxs-lookup"><span data-stu-id="7aa8d-103">Run the Test Data Transfer Tool (beta) for Dynamics AX (AX 2012)</span></span>

[!include[banner](../../includes/banner.md)]


<span data-ttu-id="7aa8d-104">Le but de l’exportation/importation rapide est de vous permettre d’importer et d'exporter avec moins d’étapes.</span><span class="sxs-lookup"><span data-stu-id="7aa8d-104">The purpose of Quick import export is to let you import and export with fewer steps.</span></span>

<span data-ttu-id="7aa8d-105">Nous avons ajouté la fonctionnalité d'importation/exportation rapide pour permettre aux utilisateurs d’importer ou d’exporter des tâches simples qu’ils souhaitent exécuter rapidement.</span><span class="sxs-lookup"><span data-stu-id="7aa8d-105">We added the Quick Import Export feature to let users import or export simple jobs that they want to execute quickly.</span></span> <span data-ttu-id="7aa8d-106">Dans l’idéal, cette fonctionnalité est utilisée dans des scénarios dans lesquels un fichier est mappé automatiquement au système et où l'utilisateur n’a pas besoin de passer par les tâches de mappage ni créer des tâches dd’importation ou d'exportation répétées.</span><span class="sxs-lookup"><span data-stu-id="7aa8d-106">Ideally this feature is used in scenarios in which a file automatically maps to the system and user does not need to go through advanced mapping or create repeated import or export jobs.</span></span>

-   <span data-ttu-id="7aa8d-107">Cette fonctionnalité prend en charge l’utilisation d'entités personnalisées et prêtes à l’emploi.</span><span class="sxs-lookup"><span data-stu-id="7aa8d-107">This feature supports working with both out-of-the-box and custom entities.</span></span>
-   <span data-ttu-id="7aa8d-108">Vous pouvez importer des fichiers, et si vous utilisez une source de données ODBC, vous pouvez sélectionner une requête à utiliser pour définir votre importation.</span><span class="sxs-lookup"><span data-stu-id="7aa8d-108">You can import from files, and if you are using an ODBC data source, you can select a query to use to define your import.</span></span>
-   <span data-ttu-id="7aa8d-109">Vous devez d’abord définir les formats des données sources pour AX ou un fichier et savoir où ils se trouvent.</span><span class="sxs-lookup"><span data-stu-id="7aa8d-109">You must have previously defined source data formats for either AX or File, and know where they are located.</span></span>
-   <span data-ttu-id="7aa8d-110">Vous n’avez pas besoin de créer un groupe de traitement pour utiliser l’importation/exportation rapide, il sera automatiquement créé par le système lors de l’exécution de la tâche d’importation ou d’exportation.</span><span class="sxs-lookup"><span data-stu-id="7aa8d-110">You do not need to create a processing group to use quick import/export, one will be automatically created by the system when executing the import or export job.</span></span> <span data-ttu-id="7aa8d-111">Vous pouvez également choisir de conserver l’historique des données importées par l’importation/exportation rapide.</span><span class="sxs-lookup"><span data-stu-id="7aa8d-111">You can also choose keep the history of the data imported by the quick import/export.</span></span>

  <span data-ttu-id="7aa8d-112">Notez que l’importation/exportation rapide suppose que vous soyez familiarisé avec les concepts de DIXF.</span><span class="sxs-lookup"><span data-stu-id="7aa8d-112">Note that Quick import export assumes that you are familiar with the concepts of DIXF.</span></span>



