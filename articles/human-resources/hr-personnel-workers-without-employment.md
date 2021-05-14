---
title: Collaborateurs sans emploi
description: Les collaborateurs sans emploi futur, actuel ou passé au sein de votre organisation apparaissent dans le formulaire Collaborateurs sans emploi.
author: andreabichsel
ms.date: 04/06/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1a137de25924f4c4ec6f6b1fe70f9d21af591c0
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924569"
---
# <a name="workers-without-employment"></a><span data-ttu-id="78739-103">Collaborateurs sans emploi</span><span class="sxs-lookup"><span data-stu-id="78739-103">Workers without employment</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="78739-104">Les collaborateurs sans emploi futur, actuel ou passé au sein de votre organisation apparaissent dans le formulaire **Collaborateurs sans emploi**.</span><span class="sxs-lookup"><span data-stu-id="78739-104">Workers with no future, active, or historical employment with your organization appear in the **Workers without employment** form.</span></span> <span data-ttu-id="78739-105">Les collaborateurs ayant ce statut peuvent apparaître lorsque vous importez des collaborateurs sans dossier ou lorsque vous supprimez l'emploi d'un collaborateur via **Collaborateur > Historique des emplois**.</span><span class="sxs-lookup"><span data-stu-id="78739-105">Workers with this status can appear when you import workers without an employment record, or when you delete a worker's employment via **Workers > Employment history**.</span></span>

<span data-ttu-id="78739-106">Par défaut, le formulaire **Collaborateurs sans emploi** est disponible pour les postes suivants :</span><span class="sxs-lookup"><span data-stu-id="78739-106">By default, the **Workers without employment** form is available to the following roles:</span></span>

- <span data-ttu-id="78739-107">Assistant des ressources humaines</span><span class="sxs-lookup"><span data-stu-id="78739-107">Human Resources Assistant</span></span>
- <span data-ttu-id="78739-108">Directeur des ressources humaines</span><span class="sxs-lookup"><span data-stu-id="78739-108">Human Resources Manager</span></span>
- <span data-ttu-id="78739-109">Recruteur</span><span class="sxs-lookup"><span data-stu-id="78739-109">Recruiter</span></span>
- <span data-ttu-id="78739-110">Gestionnaire de rémunération et avantages sociaux</span><span class="sxs-lookup"><span data-stu-id="78739-110">Comp and Benefits Manager</span></span>
- <span data-ttu-id="78739-111">Administrateur de paie</span><span class="sxs-lookup"><span data-stu-id="78739-111">Payroll Administrator</span></span>
- <span data-ttu-id="78739-112">Responsable paie</span><span class="sxs-lookup"><span data-stu-id="78739-112">Payroll Manager</span></span>
- <span data-ttu-id="78739-113">Responsable formation</span><span class="sxs-lookup"><span data-stu-id="78739-113">Training Manager</span></span>

<span data-ttu-id="78739-114">Dans la liste **Collaborateurs sans emploi**, vous pouvez supprimer les individus répertoriés.</span><span class="sxs-lookup"><span data-stu-id="78739-114">In the **Workers without employment** list, you can delete the individuals listed.</span></span> <span data-ttu-id="78739-115">Par défaut, ce privilège est accordé au poste d'Assistant des ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="78739-115">By default, this privilege is given to the Human Resources Assistant role.</span></span> <span data-ttu-id="78739-116">Vous pouvez accorder ce privilège à d'autres postes en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="78739-116">You can give this privilege to other roles with the following steps:</span></span>

1. <span data-ttu-id="78739-117">Sélectionnez **Administration du système**, puis **Configuration de sécurité**.</span><span class="sxs-lookup"><span data-stu-id="78739-117">Select **System administration**, and then select **Security configuration**.</span></span>

2. <span data-ttu-id="78739-118">Dans l'onglet **Privilèges**, filtrez la liste **Privilèges** sur **Tenir à jour les collaborateurs**.</span><span class="sxs-lookup"><span data-stu-id="78739-118">In the **Privileges** tab, filter the **Privileges** list to **Maintain workers**.</span></span>

   <span data-ttu-id="78739-119">[![Liste des privilèges de filtrage](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)</span><span class="sxs-lookup"><span data-stu-id="78739-119">[![Filter Privileges list](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)</span></span>

3. <span data-ttu-id="78739-120">Dans la colonne **Références**, sélectionnez **Options du menu d'affichage**.</span><span class="sxs-lookup"><span data-stu-id="78739-120">In the **References** column, select **Display menu items**.</span></span>

4. <span data-ttu-id="78739-121">Dans **Options du menu d'affichage**, sélectionnez **HcmWorkersWithoutEmployment**.</span><span class="sxs-lookup"><span data-stu-id="78739-121">In **Display menu items**, select **HcmWorkersWithoutEmployment**.</span></span>

   <span data-ttu-id="78739-122">[![Sélectionner l'écran](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)</span><span class="sxs-lookup"><span data-stu-id="78739-122">[![Select form](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)</span></span>

5. <span data-ttu-id="78739-123">Définissez l'autorisation **Supprimer** sur **Accorder**.</span><span class="sxs-lookup"><span data-stu-id="78739-123">Set the **Delete** permission to **Grant**.</span></span>

6. <span data-ttu-id="78739-124">Sélectionnez l'onglet **Objets non publiés**.</span><span class="sxs-lookup"><span data-stu-id="78739-124">Select the **Unpublished objects** tab.</span></span>

7. <span data-ttu-id="78739-125">Sélectionnez **Publier tous**.</span><span class="sxs-lookup"><span data-stu-id="78739-125">Select **Publish all**.</span></span>

   <span data-ttu-id="78739-126">[![Publier les modifications](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)</span><span class="sxs-lookup"><span data-stu-id="78739-126">[![Publish changes](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]