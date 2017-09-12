---
title: "Importer ou créer manuellement des codes postaux"
description: "Cet article décrit la procédure d'importation et de création manuelle de codes postaux au format approprié. Cette rubrique inclut des informations sur les fonctions qui ont été ajoutées pour Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LogisticsAddressSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 29901
ms.search.region: Belgium, Netherlands, Sweden
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 3f7b8cbd5f9c5540142869b748e2f9ee1453d5da
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---

# <a name="import-or-manually-create-postal-codes"></a><span data-ttu-id="72e71-104">Importer ou créer manuellement des codes postaux</span><span class="sxs-lookup"><span data-stu-id="72e71-104">Import or manually create postal codes</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="72e71-105">Cet article décrit la procédure d'importation et de création manuelle de codes postaux au format approprié.</span><span class="sxs-lookup"><span data-stu-id="72e71-105">This article explains how to import and manually create postal codes in the correct format.</span></span> <span data-ttu-id="72e71-106">Cette rubrique inclut des informations sur les fonctions qui ont été ajoutées pour Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span><span class="sxs-lookup"><span data-stu-id="72e71-106">This topic includes information about feature that was added for Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> 

<span data-ttu-id="72e71-107">Le processus d'importation permet de mettre à jour les codes postaux d'un pays ou d'une région spécifique.</span><span class="sxs-lookup"><span data-stu-id="72e71-107">The import process lets you update the ZIP/postal codes for a specific country/region.</span></span> <span data-ttu-id="72e71-108">Vous pouvez également créer les codes postaux manuellement.</span><span class="sxs-lookup"><span data-stu-id="72e71-108">You can also create postal codes manually.</span></span>

## <a name="import-zippostal-codes"></a><span data-ttu-id="72e71-109">Importer des codes postaux</span><span class="sxs-lookup"><span data-stu-id="72e71-109">Import ZIP/postal codes</span></span>
<span data-ttu-id="72e71-110">Vous pouvez utiliser la page **Importer des codes postaux** pour importer de nouveaux codes postaux dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="72e71-110">You can use the **Import ZIP/postal codes** page to import new postal codes into Finance and Operations.</span></span> <span data-ttu-id="72e71-111">Lorsque vous importez les codes, les codes postaux existants sont remplacés par le nouveau format, et les nouveaux codes sont ajoutés.</span><span class="sxs-lookup"><span data-stu-id="72e71-111">When you import the codes, the existing ZIP or postal codes are replaced with the new format, and any new codes are added.</span></span>

<span data-ttu-id="72e71-112">Pour certains pays, vous devez utiliser l'infrastructure de gestion des données pour importer des codes, tandis que pour d'autres pays, seul un fichier doit être téléchargé.</span><span class="sxs-lookup"><span data-stu-id="72e71-112">For some countries, you must use the Data management framework to import codes, while for other countries only a upload file is required.</span></span> <span data-ttu-id="72e71-113">Un fichier doit être téléchargé pour la Belgique, les Pays-Bas et la Suède.</span><span class="sxs-lookup"><span data-stu-id="72e71-113">Belgium, Netherlands, and Sweden require a file to upload.</span></span>

> [!NOTE]
> -   <span data-ttu-id="72e71-114">Pour la Belgique, la page Web officielle de la poste belge fournit la liste officielle des codes postaux et les noms de ville correspondants.</span><span class="sxs-lookup"><span data-stu-id="72e71-114">For Belgium, the official webpage from the Belgian Post provides an official list of the postcodes and the corresponding city names.</span></span> <span data-ttu-id="72e71-115">L'importation prend en charge le format de fichier HTML.</span><span class="sxs-lookup"><span data-stu-id="72e71-115">The import supports html file format.</span></span>
> -   <span data-ttu-id="72e71-116">Pour les Pays-Bas, une organisation tierce fournit le fichier contenant les codes postaux.</span><span class="sxs-lookup"><span data-stu-id="72e71-116">For Netherlands, a third-party organization provides the file that contains postal codes.</span></span> <span data-ttu-id="72e71-117">Une fois l'importation terminée, tous les codes postaux s'affichent au format (NNNN AA.)</span><span class="sxs-lookup"><span data-stu-id="72e71-117">After the import is completed, all postal codes will appear in the format (NNNN AA).</span></span>
> -   <span data-ttu-id="72e71-118">Pour la Suède, Postnummerservice.se propose deux types de fichiers : les codes postaux suédois et les adresses suédoises.</span><span class="sxs-lookup"><span data-stu-id="72e71-118">For Sweden, Postnummerservice.se provides two types of files: Swedish postal codes and Swedish addresses.</span></span> <span data-ttu-id="72e71-119">L'importation prend en charge le format de fichier texte pour les deux types.</span><span class="sxs-lookup"><span data-stu-id="72e71-119">The import supports text file format for both types.</span></span>


## <a name="create-zippostal-codes-manually"></a><span data-ttu-id="72e71-120">Création manuelle des codes postaux</span><span class="sxs-lookup"><span data-stu-id="72e71-120">Create ZIP/postal codes manually</span></span>
<span data-ttu-id="72e71-121">Au lieu d'importer les codes, vous pouvez utiliser la page **Configuration de l'adresse** pour ajouter manuellement de nouveaux codes postaux.</span><span class="sxs-lookup"><span data-stu-id="72e71-121">Instead of importing codes, you can use the **Address setup** page to manually add new ZIP/postal codes.</span></span>



