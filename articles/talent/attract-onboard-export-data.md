---
title: Exporter des données depuis Attract et Onboard
description: Exporter des données depuis Dynamics 365 Talent - Attract et Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 01/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Talent October 2019 update
ms.openlocfilehash: eb97a16c15476c2f34ec581a32a677fa6fee8739
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461107"
---
# <a name="export-data-from-attract-and-onboard"></a><span data-ttu-id="3cfcf-103">Exporter des données depuis Attract et Onboard</span><span class="sxs-lookup"><span data-stu-id="3cfcf-103">Export data from Attract and Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3cfcf-104">Comme annoncé dans [Suppression des applications Dynamics 365 Talent: Attract et Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), nous supprimerons Dynamics 365 Talent: Attract et Dynamics 365 Talent: Onboard le 1 février 2022.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-104">As announced in [Retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard Apps](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), we're retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard on February 1, 2022.</span></span> <span data-ttu-id="3cfcf-105">Pour faciliter votre migration vers un autre produit, les deux applications offrent désormais des capacités d'exportation de données.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-105">To help with your migration to another product, both apps now provide data export capabilities.</span></span>

## <a name="export-data-from-attract"></a><span data-ttu-id="3cfcf-106">Exporter des données depuis Attract</span><span class="sxs-lookup"><span data-stu-id="3cfcf-106">Export data from Attract</span></span>

<span data-ttu-id="3cfcf-107">Vous pouvez exporter vos données sans restreindre l'accès à votre environnement.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-107">You can export your data without restricting access to your environment.</span></span> <span data-ttu-id="3cfcf-108">Vous pouvez le faire à des fins de test ou pour comprendre notre structure de données.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-108">You might want to do this for testing purposes or to understand our data structure.</span></span> <span data-ttu-id="3cfcf-109">Lorsque vous êtes prêt à migrer, limitez l'accès à votre environnement Attract en suivant les instructions après cette procédure.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-109">When you're ready to migrate, restrict access to your Attract environment using the instructions after this procedure.</span></span> <span data-ttu-id="3cfcf-110">Assurez-vous d'exporter à nouveau vos données.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-110">Be sure to export your data again.</span></span> 

1. <span data-ttu-id="3cfcf-111">Atteindre [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span><span class="sxs-lookup"><span data-stu-id="3cfcf-111">Go to [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span></span>

2. <span data-ttu-id="3cfcf-112">Sous **Exportation de données**, sélectionnez **Demander une exportation de données**.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-112">Under **Data export**, select **Request a data export**.</span></span>

   ![[<span data-ttu-id="3cfcf-113">Demander une exportation de données depuis Attract</span><span class="sxs-lookup"><span data-stu-id="3cfcf-113">Request a data export from Attract</span></span>](./media/attract-onboard-export-data-attract-request.png)](./media/attract-onboard-export-data-attract-request.png)

3. <span data-ttu-id="3cfcf-114">Quand la boîte de message **Votre demande est en cours de traitement** s'affiche, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-114">When the **Your request is being processed** message box appears, select **OK**.</span></span> <span data-ttu-id="3cfcf-115">L'exportation de données peut prendre jusqu'à 20 minutes, selon la taille de votre exportation.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-115">The data export can take up to 20 minutes, depending on the size of your export.</span></span>

4. <span data-ttu-id="3cfcf-116">Une fois votre exportation terminée, sélectionnez le bouton **Télécharger** à côté.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-116">When your export completes, select the **Download** button next to it.</span></span> 

   >[!NOTE]
   ><span data-ttu-id="3cfcf-117">Toutes les exportations de données sont disponibles pendant sept jours, moment auquel le lien **Télécharger** expire.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-117">All data exports are available for seven days, at which point the **Download** link expires.</span></span></br>
   
<span data-ttu-id="3cfcf-118">Le téléchargement contient un fichier .zip avec vos données Attract, y compris les dossiers suivants :</span><span class="sxs-lookup"><span data-stu-id="3cfcf-118">The download contains a .zip file with your Attract data, including the following folders:</span></span>

| <span data-ttu-id="3cfcf-119">Nom de dossier</span><span class="sxs-lookup"><span data-stu-id="3cfcf-119">Folder name</span></span> | <span data-ttu-id="3cfcf-120">Description</span><span class="sxs-lookup"><span data-stu-id="3cfcf-120">Description</span></span> |
| --- | --- |
| <span data-ttu-id="3cfcf-121">Paramètres d'administration</span><span class="sxs-lookup"><span data-stu-id="3cfcf-121">Admin settings</span></span> | <span data-ttu-id="3cfcf-122">Configurations du centre d'administration Attract.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-122">Attract admin center configurations.</span></span> |
| <span data-ttu-id="3cfcf-123">Candidats</span><span class="sxs-lookup"><span data-stu-id="3cfcf-123">Candidates</span></span> | <span data-ttu-id="3cfcf-124">Tous les candidats qui ont été ajoutés à des emplois ou à des viviers de talents.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-124">All candidates that were added to jobs or talent pools.</span></span> |
| <span data-ttu-id="3cfcf-125">Modèles d'e-mail</span><span class="sxs-lookup"><span data-stu-id="3cfcf-125">Email templates</span></span> | <span data-ttu-id="3cfcf-126">Tous les modèles d'e-mail configurés pour l'environnement.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-126">All email templates that were configured for the environment.</span></span> |
| <span data-ttu-id="3cfcf-127">Modèles de packages d'offre d'emploi</span><span class="sxs-lookup"><span data-stu-id="3cfcf-127">Job offer package templates</span></span> | <span data-ttu-id="3cfcf-128">Tous les modèles de packages d'offres d'emploi créés, ainsi que leurs configurations associées.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-128">All job offer package templates that were created, plus their associated configurations.</span></span> |
| <span data-ttu-id="3cfcf-129">Ensembles de règles d'offre d'emploi</span><span class="sxs-lookup"><span data-stu-id="3cfcf-129">Job offer rule sets</span></span> |  <span data-ttu-id="3cfcf-130">Tous les fichiers d'ensemble de règles qui ont été téléchargés pour la gestion des offres.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-130">All rule set files that were uploaded for offer management.</span></span> |
| <span data-ttu-id="3cfcf-131">Modèles d'offre d'emploi</span><span class="sxs-lookup"><span data-stu-id="3cfcf-131">Job offer templates</span></span> | <span data-ttu-id="3cfcf-132">Tous les modèles de documents d'offre d'emploi créés pour l'environnement.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-132">All job offer document templates created for the environment.</span></span> |
| <span data-ttu-id="3cfcf-133">Offres d'emploi</span><span class="sxs-lookup"><span data-stu-id="3cfcf-133">Job openings</span></span> | <span data-ttu-id="3cfcf-134">Tous les emplois créés.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-134">All created jobs.</span></span> <span data-ttu-id="3cfcf-135">Les emplois supprimés ne sont pas exportés.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-135">Deleted jobs aren't exported.</span></span> <span data-ttu-id="3cfcf-136">Les sous-dossiers contiennent des candidatures, avec des sous-dossiers pour les pièces jointes des candidatures et les packages d'offres, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-136">The sub-folders contain candidate applications, with sub-folders for candidate application attachments and offer packages, where applicable.</span></span> |
| <span data-ttu-id="3cfcf-137">Modèles d'offres d'emploi</span><span class="sxs-lookup"><span data-stu-id="3cfcf-137">Job opening templates</span></span> | <span data-ttu-id="3cfcf-138">Les modèles de traitement des emplois configurés dans l'environnement.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-138">Job process templates that were configured in the environment.</span></span> |
| <span data-ttu-id="3cfcf-139">Viviers de talents</span><span class="sxs-lookup"><span data-stu-id="3cfcf-139">Talent pools</span></span> | <span data-ttu-id="3cfcf-140">Tous les viviers de talents créés, leurs listes de contributeurs et les listes de candidats pour les viviers de talents.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-140">All created talent pools, their contributors lists, and the candidates lists for the talent pools.</span></span> |
| <span data-ttu-id="3cfcf-141">Collaborateurs</span><span class="sxs-lookup"><span data-stu-id="3cfcf-141">Workers</span></span> | <span data-ttu-id="3cfcf-142">Liste de tous les collaborateurs présents dans l'environnement, ainsi que leurs rôles.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-142">List of all the workers who are present in the environment, plus their roles.</span></span> |
| <span data-ttu-id="3cfcf-143">(dossier racine)</span><span class="sxs-lookup"><span data-stu-id="3cfcf-143">(root folder)</span></span> | <span data-ttu-id="3cfcf-144">Un fichier de schéma JSON qui décrit les champs de structure de données.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-144">A JSON schema file that describes the data structure fields.</span></span> |

### <a name="restrict-access-to-attract"></a><span data-ttu-id="3cfcf-145">Restreindre l'accès à Attract</span><span class="sxs-lookup"><span data-stu-id="3cfcf-145">Restrict access to Attract</span></span>

<span data-ttu-id="3cfcf-146">Lorsque vous êtes prêt à migrer, empêchez les non-administrateurs d'accéder à votre environnement Attract et d'exporter vos données.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-146">When you're ready to migrate, restrict non-admins from accessing your Attract environment and export your data.</span></span>

>[!IMPORTANT]
><span data-ttu-id="3cfcf-147">La restriction de l'accès à votre environnement Attract est permanente et ne peut pas être annulée.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-147">Restricting access to your Attract environment is permanent and can't be undone.</span></span> <span data-ttu-id="3cfcf-148">Si vous souhaitez que les utilisateurs non administrateurs continuent d'accéder à votre environnement, ignorez cette étape.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-148">If you want non-admin users to continue accessing your environment, skip this step.</span></span>

1. <span data-ttu-id="3cfcf-149">Atteindre [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span><span class="sxs-lookup"><span data-stu-id="3cfcf-149">Go to [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span></span>

2. <span data-ttu-id="3cfcf-150">Pour empêcher les non-administrateurs d'accéder à votre environnement Attract, sous **Restreindre l'accès à cette application**, sélectionnez **Restreindre l'accès maintenant**.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-150">To restrict non-admins from accessing your Attract environment, under **Restrict access to this app**, select **Restrict access now**.</span></span> <span data-ttu-id="3cfcf-151">Restreindre l'accès supprime également tous les emplois actifs qui ont été publiés.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-151">Restricting access also unposts any active jobs that have been posted.</span></span>

   ![[<span data-ttu-id="3cfcf-152">Restreindre l'accès non-administrateur à Attract</span><span class="sxs-lookup"><span data-stu-id="3cfcf-152">Restrict non-admin access to Attract</span></span>](./media/attract-onboard-export-data-attract-restrict-access.png)](./media/attract-onboard-export-data-attract-restrict-access.png)

3. <span data-ttu-id="3cfcf-153">Lorsque vous voyez l'avertissement **Ceci est un changement permanent**, sélectionnez **Restreindre l’accès** pour interdire définitivement l'accès des utilisateurs non-administrateurs à cet environnement.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-153">When you see the warning **This is a permanent change**, select **Restrict access** to permanently restrict non-admin users from this environment.</span></span> <span data-ttu-id="3cfcf-154">Si vous n'êtes pas prêt à terminer cette étape, sélectionnez **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-154">If you're not ready to complete this step, select **Cancel**.</span></span>

   ![[<span data-ttu-id="3cfcf-155">Avertissement que restreindre l'accès est un changement permanent</span><span class="sxs-lookup"><span data-stu-id="3cfcf-155">Warning that restricting access is a permanent change</span></span>](./media/attract-onboard-export-data-attract-warning.png)](./media/attract-onboard-export-data-attract-warning.png)

   >[!NOTE]
   ><span data-ttu-id="3cfcf-156">Les administrateurs peuvent continuer d'accéder aux pages d'exportation de données et d'état sur les personnes après que vous avez restreint l'accès à l'environnement Attract.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-156">Admins can continue to access the data export and person report pages after you restrict access to the Attract environment.</span></span>

## <a name="export-data-from-onboard"></a><span data-ttu-id="3cfcf-157">Exporter des données depuis Onboard</span><span class="sxs-lookup"><span data-stu-id="3cfcf-157">Export data from Onboard</span></span>

<span data-ttu-id="3cfcf-158">Lorsque vous êtes prêt, vous pouvez télécharger des modèles, des guides et des données de candidats depuis Onboard.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-158">When you're ready, you can download templates, guides, and candidate data from Onboard.</span></span>

1. <span data-ttu-id="3cfcf-159">Atteindre [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).</span><span class="sxs-lookup"><span data-stu-id="3cfcf-159">Go to [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).</span></span>

2. <span data-ttu-id="3cfcf-160">Sous **Exportation de données**, sélectionnez **Demander une exportation de données**.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-160">Under **Data export**, select **Request a data export**.</span></span> 

   ![[<span data-ttu-id="3cfcf-161">Demander une exportation de données depuis Onboard</span><span class="sxs-lookup"><span data-stu-id="3cfcf-161">Request a data export from Onboard</span></span>](./media/attract-onboard-export-data-onboard-request.png)](./media/attract-onboard-export-data-onboard-request.png)

3. <span data-ttu-id="3cfcf-162">Quand la boîte de message **Votre demande est en cours de traitement** s'affiche, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-162">When the **Your request is being processed** message box appears, select **OK**.</span></span> <span data-ttu-id="3cfcf-163">L'exportation de données peut prendre jusqu'à 20 minutes, selon la taille de votre exportation.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-163">The data export can take up to 20 minutes, depending on the size of your export.</span></span>

4. <span data-ttu-id="3cfcf-164">Une fois votre exportation terminée, sélectionnez le bouton **Télécharger** à côté.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-164">When your export completes, select the **Download** button next to it.</span></span> 

   ![[<span data-ttu-id="3cfcf-165">Télécharger une exportation de données depuis Onboard</span><span class="sxs-lookup"><span data-stu-id="3cfcf-165">Download data export from Onboard</span></span>](./media/attract-onboard-export-data-onboard-download.png)](./media/attract-onboard-export-data-onboard-download.png)

   >[!NOTE]
   ><span data-ttu-id="3cfcf-166">L'exportation de vos données est disponible pendant sept jours.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-166">Your data export is available for seven days.</span></span> <span data-ttu-id="3cfcf-167">Après sept jours, le lien **Télécharger** expire et vous devez demander une nouvelle exportation si vous devez télécharger à nouveau vos données.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-167">After seven days, the **Download** link expires, and you must request a new export if you need to download your data again.</span></span> <span data-ttu-id="3cfcf-168">Lorsque vous démarrez une nouvelle exportation de données, tous les téléchargements existants expirent une fois la nouvelle exportation réussie.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-168">When you start a new data export, any existing downloads will expire after the new export succeeds.</span></span>

<span data-ttu-id="3cfcf-169">Le téléchargement est un fichier .zip qui contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="3cfcf-169">The download is a .zip file that contains:</span></span>

- <span data-ttu-id="3cfcf-170">Un dossier **Modèles** contenant vos modèles Onboard au format de document Word.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-170">A **Templates** folder that contains your Onboard templates in Word document format.</span></span>

- <span data-ttu-id="3cfcf-171">Un dossier **Guides** contenant vos guides Onboard au format de document Word.</span><span class="sxs-lookup"><span data-stu-id="3cfcf-171">A **Guides** folder that contains your Onboard guides in Word document format.</span></span>

## <a name="see-also"></a><span data-ttu-id="3cfcf-172">Voir également :</span><span class="sxs-lookup"><span data-stu-id="3cfcf-172">See also</span></span>

[<span data-ttu-id="3cfcf-173">Suppression des applications Dynamics 365 Talent: Attract et Dynamics 365 Talent: Onboard</span><span class="sxs-lookup"><span data-stu-id="3cfcf-173">Retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard Apps</span></span>](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)