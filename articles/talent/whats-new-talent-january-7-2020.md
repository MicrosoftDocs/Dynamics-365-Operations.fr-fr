---
title: Nouveautés ou modifications dans Dynamics 365 Talent (7 janvier 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-01-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e227c614fdbfe6f3dd410f1a533c593979abf1ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461169"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-7-2020"></a><span data-ttu-id="b1344-103">Nouveautés ou modifications dans Dynamics 365 Talent (7 janvier 2020)</span><span class="sxs-lookup"><span data-stu-id="b1344-103">What's new or changed in Dynamics 365 Talent (January 7, 2020)</span></span>

<span data-ttu-id="b1344-104">Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="b1344-104">This article describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="b1344-105">Modifications apportées dans Attract</span><span class="sxs-lookup"><span data-stu-id="b1344-105">Changes in Attract</span></span>

<span data-ttu-id="b1344-106">Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="b1344-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="b1344-107">Modifications apportées à Onboard</span><span class="sxs-lookup"><span data-stu-id="b1344-107">Changes in Onboard</span></span>

<span data-ttu-id="b1344-108">Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="b1344-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="b1344-109">Modifications apportées à Core HR</span><span class="sxs-lookup"><span data-stu-id="b1344-109">Changes in Core HR</span></span>

<span data-ttu-id="b1344-110">Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2697.</span><span class="sxs-lookup"><span data-stu-id="b1344-110">Changes described in this section apply to build number 8.1.2697.</span></span> <span data-ttu-id="b1344-111">Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="b1344-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

 
### <a name="cant-delete-workers-that-dont-have-employment-records---386157"></a><span data-ttu-id="b1344-112">Impossible de supprimer les collaborateurs sans dossier d'emploi - (386157)</span><span class="sxs-lookup"><span data-stu-id="b1344-112">Can't delete workers that don't have employment records - (386157)</span></span>

<span data-ttu-id="b1344-113">Cette modification ajoute une option de suppression dans le formulaire **Collaborateurs sans emploi**.</span><span class="sxs-lookup"><span data-stu-id="b1344-113">This change adds a delete option in the **Workers without employment** form.</span></span> <span data-ttu-id="b1344-114">Les collaborateurs apparaissent dans ce formulaire lorsqu'ils ne sont associés à aucun emploi futur, actif ou historique.</span><span class="sxs-lookup"><span data-stu-id="b1344-114">Workers appear in this form when no future, active, or historical employments exist for the worker.</span></span> <span data-ttu-id="b1344-115">Dans cette version, la suppression n'est activée que pour les administrateurs système.</span><span class="sxs-lookup"><span data-stu-id="b1344-115">In this release, delete is only enabled for System Administrators.</span></span> <span data-ttu-id="b1344-116">Cependant, dans la version de la semaine prochaine, la sécurité sera mise à jour pour permettre à tous les utilisateurs avec le rôle d'assistant RH de supprimer des employés sans emploi.</span><span class="sxs-lookup"><span data-stu-id="b1344-116">However, in next week's release, security will be updated to allow all users with the HR assistant role to remove employees without employments.</span></span> <span data-ttu-id="b1344-117">Vous pouvez également effectuer ces modifications manuellement en suivant les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="b1344-117">You can also make these changes manually by following the following steps.</span></span>

1. <span data-ttu-id="b1344-118">Accédez à **Configuration de sécurité**.</span><span class="sxs-lookup"><span data-stu-id="b1344-118">Go to **Security configuration**.</span></span>
2. <span data-ttu-id="b1344-119">Dans l'onglet **Privilèges**, filtrez la liste **Privilèges** sur **Tenir à jour les collaborateurs**.</span><span class="sxs-lookup"><span data-stu-id="b1344-119">In the **Privileges** tab, filter the **Privileges** list to **Maintain workers**.</span></span>
3. <span data-ttu-id="b1344-120">Dans la colonne **Références**, sélectionnez **Options du menu d'affichage**.</span><span class="sxs-lookup"><span data-stu-id="b1344-120">In the **References** column, select **Display menu items**.</span></span>
4. <span data-ttu-id="b1344-121">Dans **Options du menu d'affichage**, sélectionnez **HcmWOrkersWithoutEmployment**.</span><span class="sxs-lookup"><span data-stu-id="b1344-121">In **Display menu items**, select **HcmWOrkersWithoutEmployment**.</span></span>
5. <span data-ttu-id="b1344-122">Définissez l'autorisation **Supprimer** sur Accorder.</span><span class="sxs-lookup"><span data-stu-id="b1344-122">Set the **Delete** permission to Grant.</span></span>
6. <span data-ttu-id="b1344-123">Sélectionnez l'onglet **Objets non publiés**.</span><span class="sxs-lookup"><span data-stu-id="b1344-123">Select the **Unpublished objects** tab.</span></span>
7. <span data-ttu-id="b1344-124">Sélectionnez **Publier tous**.</span><span class="sxs-lookup"><span data-stu-id="b1344-124">Select **Publish all**.</span></span>
