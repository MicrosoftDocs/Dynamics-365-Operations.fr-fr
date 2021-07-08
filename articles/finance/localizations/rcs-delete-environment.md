---
title: Regulatory Configuration Service (RCS) – Supprimer un environnement RCS
description: Cette rubrique explique comment un administrateur système de Regulatory Configuration Service (RCS) peut supprimer un environnement RCS et les données associées.
author: JaneA07
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
audience: Application User, System Admin
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 637962cf63bfd8c2330726f33545f939ec91d58d
ms.sourcegitcommit: dbffde1944b9d037124415c28053036c9ef1ecb7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2021
ms.locfileid: "6295816"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a><span data-ttu-id="38eb3-103">Regulatory Configuration Service (RCS) – Supprimer un environnement RCS</span><span class="sxs-lookup"><span data-stu-id="38eb3-103">Regulatory Configuration Service (RCS) - Delete an RCS environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="38eb3-104">Cette rubrique explique comment un administrateur système de Regulatory Configuration Service (RCS) peut supprimer un environnement RCS et les données associées.</span><span class="sxs-lookup"><span data-stu-id="38eb3-104">This topic explains how a Regulatory Configuration Service (RCS) system administrator can delete an RCS environment and related data.</span></span>

<span data-ttu-id="38eb3-105">Avant de pouvoir effectuer la procédure de cette rubrique, les conditions préalables suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="38eb3-105">Before you can complete the procedure in this topic, the following prerequisites must be met:</span></span>

- <span data-ttu-id="38eb3-106">Vous devez disposer du rôle **Administrateur système** pour l’environnement RCS.</span><span class="sxs-lookup"><span data-stu-id="38eb3-106">You must have the **System Admin** role assigned to you for the RCS environment.</span></span>
- <span data-ttu-id="38eb3-107">Le rôle **Administrateur système** doit disposer du rôle **RCSDeleteEnvironmentDuty**.</span><span class="sxs-lookup"><span data-stu-id="38eb3-107">The **System Admin** role must have the **RCSDeleteEnvironmentDuty** role assigned to it.</span></span>

## <a name="delete-an-rcs-environment"></a><span data-ttu-id="38eb3-108">Supprimer un environnement RCS</span><span class="sxs-lookup"><span data-stu-id="38eb3-108">Delete an RCS environment</span></span>

1. <span data-ttu-id="38eb3-109">Ouvrez RCS et sélectionnez la vignette de l’espace de travail **Gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="38eb3-109">Open RCS, and select the **Electronic reporting** workspace tile.</span></span>
2. <span data-ttu-id="38eb3-110">Dans la section **Liens connexes**, sélectionnez **Supprimer l’environnement RCS**.</span><span class="sxs-lookup"><span data-stu-id="38eb3-110">In the **Related links** section, select **Delete RCS environment**.</span></span>

    ![Lien Supprimer l’environnement RCS dans la section Liens connexes](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. <span data-ttu-id="38eb3-112">Dans la boîte de dialogue qui s’affiche, passez en revue les messages concernant l’étendue de la suppression de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="38eb3-112">In the dialog box that appears, review the messages about the scope of environment deletion.</span></span>

    ![Messages dans la boîte de dialogue Supprimer l’environnement RCS](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > <span data-ttu-id="38eb3-114">La suppression d’un environnement RCS est irréversible.</span><span class="sxs-lookup"><span data-stu-id="38eb3-114">Deletion of an RCS environment can't be reversed.</span></span>
    >
    > <span data-ttu-id="38eb3-115">L’opération supprime l’environnement RCS sélectionné et toutes les données associées, y compris les fonctionnalités et les configurations qui sont stockées dans le référentiel global.</span><span class="sxs-lookup"><span data-stu-id="38eb3-115">The operation deletes the selected RCS environment and any related data, including features and configurations that are stored in the Global repository.</span></span> <span data-ttu-id="38eb3-116">Les fonctionnalités et configurations partagées avec d’autres organisations ne seront plus partagées et seront supprimées si elles n’ont pas de dépendances.</span><span class="sxs-lookup"><span data-stu-id="38eb3-116">Features and configurations that are shared with other organizations will be unshared and deleted if they have no dependencies.</span></span> <span data-ttu-id="38eb3-117">Les fonctionnalités et configurations qui ont des dépendances seront marquées comme abandonnées.</span><span class="sxs-lookup"><span data-stu-id="38eb3-117">Features and configurations that have dependencies will be marked as discontinued.</span></span>

4. <span data-ttu-id="38eb3-118">Dans le champ indiqué, saisissez l’identifiant global unique (GUID) de l’environnement RCS pour confirmer que vous souhaitez le supprimer.</span><span class="sxs-lookup"><span data-stu-id="38eb3-118">In the field that is provided, enter the globally unique identifier (GUID) of the RCS environment to confirm that you want to delete it.</span></span> <span data-ttu-id="38eb3-119">Le GUID de l’environnement est inclus dans le message de suppression.</span><span class="sxs-lookup"><span data-stu-id="38eb3-119">The environment's GUID is included in the deletion message.</span></span>
5. <span data-ttu-id="38eb3-120">Sélectionnez **Supprimer l’environnement**.</span><span class="sxs-lookup"><span data-stu-id="38eb3-120">Select **Delete environment**.</span></span>
    
<span data-ttu-id="38eb3-121">Votre environnement RCS et toutes les données associées sont désormais supprimés.</span><span class="sxs-lookup"><span data-stu-id="38eb3-121">Your RCS environment and any related data are now deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38eb3-122">Après avoir supprimé un environnement RCS, il n’y a aucun moyen de récupérer les données.</span><span class="sxs-lookup"><span data-stu-id="38eb3-122">After you delete an RCS environment, there is no way to recover the data.</span></span> <span data-ttu-id="38eb3-123">Un nouvel environnement RCS peut être créé dans n’importe quelle région RCS disponible.</span><span class="sxs-lookup"><span data-stu-id="38eb3-123">A new RCS environment can be created in any available RCS region.</span></span>
