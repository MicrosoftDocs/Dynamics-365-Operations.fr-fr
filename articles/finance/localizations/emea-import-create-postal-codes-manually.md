---
title: Importer ou créer manuellement des codes postaux
description: Cette rubrique décrit la procédure d’importation et de création manuelle de codes postaux au format approprié.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LogisticsAddressSetup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 29901
ms.search.region: Belgium, Netherlands, Sweden
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9663c956ed51b862b86e44094a60d0907d3a1647
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408002"
---
# <a name="import-or-manually-create-postal-codes"></a><span data-ttu-id="bea68-103">Importer ou créer manuellement des codes postaux</span><span class="sxs-lookup"><span data-stu-id="bea68-103">Import or manually create postal codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bea68-104">Cette rubrique décrit la procédure d’importation et de création manuelle de codes postaux au format approprié.</span><span class="sxs-lookup"><span data-stu-id="bea68-104">This topic explains how to import and manually create postal codes in the correct format.</span></span> 

<span data-ttu-id="bea68-105">Le processus d’importation permet de mettre à jour les codes postaux d’un pays ou d’une région spécifique.</span><span class="sxs-lookup"><span data-stu-id="bea68-105">The import process lets you update the ZIP/postal codes for a specific country/region.</span></span> <span data-ttu-id="bea68-106">Vous pouvez également créer les codes postaux manuellement.</span><span class="sxs-lookup"><span data-stu-id="bea68-106">You can also create postal codes manually.</span></span>

## <a name="import-zippostal-codes"></a><span data-ttu-id="bea68-107">Importer des codes postaux</span><span class="sxs-lookup"><span data-stu-id="bea68-107">Import ZIP/postal codes</span></span>
<span data-ttu-id="bea68-108">Vous pouvez utiliser la page **Importer des codes postaux** pour importer de nouveaux codes postaux dans Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="bea68-108">You can use the **Import ZIP/postal codes** page to import new postal codes into Dynamics 365 Finance.</span></span> <span data-ttu-id="bea68-109">Lorsque vous importez les codes, les codes postaux existants sont remplacés par le nouveau format, et les nouveaux codes sont ajoutés.</span><span class="sxs-lookup"><span data-stu-id="bea68-109">When you import the codes, the existing ZIP or postal codes are replaced with the new format, and any new codes are added.</span></span>

<span data-ttu-id="bea68-110">Pour certains pays, vous devez utiliser l’infrastructure de gestion des données pour importer des codes, tandis que pour d’autres pays, seul un fichier doit être téléchargé.</span><span class="sxs-lookup"><span data-stu-id="bea68-110">For some countries, you must use the Data management framework to import codes, while for other countries only an upload file is required.</span></span> <span data-ttu-id="bea68-111">Un fichier doit être téléchargé pour la Belgique, les Pays-Bas et la Suède.</span><span class="sxs-lookup"><span data-stu-id="bea68-111">Belgium, Netherlands, and Sweden require a file to upload.</span></span>

> [!NOTE]
> -   <span data-ttu-id="bea68-112">Pour la Belgique, la page Web officielle de la poste belge fournit la liste officielle des codes postaux et les noms de ville correspondants.</span><span class="sxs-lookup"><span data-stu-id="bea68-112">For Belgium, the official webpage from the Belgian Post provides an official list of the postcodes and the corresponding city names.</span></span> <span data-ttu-id="bea68-113">L’importation prend en charge le format de fichier HTML.</span><span class="sxs-lookup"><span data-stu-id="bea68-113">The import supports html file format.</span></span>
> -   <span data-ttu-id="bea68-114">Pour les Pays-Bas, une organisation tierce fournit le fichier contenant les codes postaux.</span><span class="sxs-lookup"><span data-stu-id="bea68-114">For Netherlands, a third-party organization provides the file that contains postal codes.</span></span> <span data-ttu-id="bea68-115">Une fois l’importation terminée, tous les codes postaux s’affichent au format (NNNN AA.)</span><span class="sxs-lookup"><span data-stu-id="bea68-115">After the import is completed, all postal codes will appear in the format (NNNN AA).</span></span>
> -   <span data-ttu-id="bea68-116">Pour la Suède, Postnummerservice.se propose deux types de fichiers : les codes postaux suédois et les adresses suédoises.</span><span class="sxs-lookup"><span data-stu-id="bea68-116">For Sweden, Postnummerservice.se provides two types of files: Swedish postal codes and Swedish addresses.</span></span> <span data-ttu-id="bea68-117">L’importation prend en charge le format de fichier texte pour les deux types.</span><span class="sxs-lookup"><span data-stu-id="bea68-117">The import supports text file format for both types.</span></span>


## <a name="create-zippostal-codes-manually"></a><span data-ttu-id="bea68-118">Création manuelle des codes postaux</span><span class="sxs-lookup"><span data-stu-id="bea68-118">Create ZIP/postal codes manually</span></span>
<span data-ttu-id="bea68-119">Au lieu d’importer les codes, vous pouvez utiliser la page **Configuration de l’adresse** pour ajouter manuellement de nouveaux codes postaux.</span><span class="sxs-lookup"><span data-stu-id="bea68-119">Instead of importing codes, you can use the **Address setup** page to manually add new ZIP/postal codes.</span></span>


