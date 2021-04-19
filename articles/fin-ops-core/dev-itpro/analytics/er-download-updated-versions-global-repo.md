---
title: Importer des versions mises à jour des configurations de gestion des états électroniques
description: Cette rubrique explique comment importer des versions mises à jour des configurations de gestion des états électroniques depuis le référentiel global du service de configuration.
author: NickSelin
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 1e021105c19273db5ded7cb0902eca1d502ced8e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753358"
---
# <a name="import-updated-versions-of-er-configurations"></a><span data-ttu-id="bd044-103">Importer des versions mises à jour des configurations de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="bd044-103">Import updated versions of ER configurations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bd044-104">Les [référentiels](general-electronic-reporting.md#Repository) de gestion des états électroniques sont utilisés pour partager des [configurations de gestion des états électroniques](general-electronic-reporting.md#Configuration).</span><span class="sxs-lookup"><span data-stu-id="bd044-104">Electronic reporting (ER) [repositories](general-electronic-reporting.md#Repository) are used to share [ER configurations](general-electronic-reporting.md#Configuration).</span></span> <span data-ttu-id="bd044-105">Vous pouvez [importer](download-electronic-reporting-configuration-lcs.md) des configurations de gestion des états électroniques depuis différents référentiels vers votre instance de Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="bd044-105">You can [import](download-electronic-reporting-configuration-lcs.md) ER configurations from different repositories into your instance of Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="bd044-106">Lorsque vous importez des configurations de gestion des états électroniques, les [fournisseurs de configuration](general-electronic-reporting.md#Provider) peuvent publier de nouveaux référentiels de [versions](general-electronic-reporting.md#component-versioning) afin de pouvoir les partager.</span><span class="sxs-lookup"><span data-stu-id="bd044-106">When you import ER configurations, [configuration providers](general-electronic-reporting.md#Provider) can publish new [versions](general-electronic-reporting.md#component-versioning) repositories so that they can be shared.</span></span>

<span data-ttu-id="bd044-107">Cette rubrique explique comment importer des versions mises à jour des configurations de gestion des états électroniques depuis le référentiel global du service de configuration.</span><span class="sxs-lookup"><span data-stu-id="bd044-107">This topic explains how to import updated versions of ER configurations from the Global repository of the Configuration service.</span></span> <span data-ttu-id="bd044-108">Pour plus d’informations, voir [Microsoft Dynamics 365 for Finance and Operations – Regulatory Services, service de configuration](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span><span class="sxs-lookup"><span data-stu-id="bd044-108">For more information, see [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span></span>

## <a name="review-the-available-updated-versions"></a><span data-ttu-id="bd044-109">Consulter les versions mises à jour disponibles</span><span class="sxs-lookup"><span data-stu-id="bd044-109">Review the available updated versions</span></span>

1. <span data-ttu-id="bd044-110">Connectez-vous à Finance en utilisant l’un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="bd044-110">Sign in to Finance by using one of the following roles:</span></span>

    - <span data-ttu-id="bd044-111">Développeur de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="bd044-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="bd044-112">Consultant fonctionnel des états électroniques</span><span class="sxs-lookup"><span data-stu-id="bd044-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="bd044-113">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="bd044-113">System administrator</span></span>

2. <span data-ttu-id="bd044-114">Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="bd044-114">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="bd044-115">Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Importer les mises à jour des versions de configurations**.</span><span class="sxs-lookup"><span data-stu-id="bd044-115">On the **Localization configurations** page, in the **Related links** section, select **Import configurations versions updates**.</span></span>

    ![Page Configurations de localisation](./media/er-download-updated-versions-global-repo1.png)

4. <span data-ttu-id="bd044-117">Dans la boîte de dialogue **Importer les mises à jour des versions des configurations de gestion des états électroniques**, dans le champ **Mode d’exécution**, sélectionnez **Afficher uniquement les mises à jour disponibles**.</span><span class="sxs-lookup"><span data-stu-id="bd044-117">In the **Import electronic reporting configurations versions updates** dialog box, in the **Run mode** field, select **Only show available updates**.</span></span> <span data-ttu-id="bd044-118">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd044-118">Then select **OK**.</span></span> 

    ![Champ Mode d’exécution défini sur Afficher uniquement les mises à jour disponibles](./media/er-download-updated-versions-global-repo2.png)

5. <span data-ttu-id="bd044-120">Passez en revue les messages que vous recevez.</span><span class="sxs-lookup"><span data-stu-id="bd044-120">Review the messages that you receive.</span></span> <span data-ttu-id="bd044-121">Ces messages fournissent les informations suivantes sur les configurations de gestion des états électroniques dans l’instance actuelle de Finance et la façon de les comparer au contenu du référentiel global :</span><span class="sxs-lookup"><span data-stu-id="bd044-121">These messages provide the following information about the ER configurations in the current Finance instance and how they compare to the content of the Global repository:</span></span>

    - <span data-ttu-id="bd044-122">Le nombre total de configurations de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="bd044-122">The total number of ER configurations</span></span>
    - <span data-ttu-id="bd044-123">Les configurations de gestion des états électroniques qui ne sont pas présentes dans le référentiel global</span><span class="sxs-lookup"><span data-stu-id="bd044-123">ER configurations that aren't present in the Global repository</span></span>
    - <span data-ttu-id="bd044-124">Les configurations de gestion des états électroniques pour lesquelles la dernière version est déjà disponible dans l’instance actuelle de Finance (Pour afficher la liste complète de ces configurations de gestion des états électroniques, sélectionnez le lien **Détails du message**.)</span><span class="sxs-lookup"><span data-stu-id="bd044-124">ER configurations for which the latest version is already available in the current Finance instance (To view the full list of these ER configurations, select the **Message details** link.)</span></span>

        ![Le message « Les dernières versions des configurations suivantes sont déjà importées » et les détails du message](./media/er-download-updated-versions-global-repo3.png)

    - <span data-ttu-id="bd044-126">Les configurations de gestion des états électroniques pour lesquelles la dernière version est disponible dans le référentiel global et qui peuvent être importées dans l’instance actuelle de Finance (Pour afficher la liste complète de ces configurations de gestion des états électroniques, sélectionnez le lien **Détails du message**.)</span><span class="sxs-lookup"><span data-stu-id="bd044-126">ER configurations for which the latest version is available in the Global repository and can be imported into the current Finance instance (To view the full list of these ER configurations, select the **Message details** link.)</span></span>

        ![Le message « Mises à jour disponibles » et les détails du message](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a><span data-ttu-id="bd044-128">Importer les versions mises à jour disponibles</span><span class="sxs-lookup"><span data-stu-id="bd044-128">Import available updated versions</span></span>

1. <span data-ttu-id="bd044-129">Connectez-vous à Finance en utilisant l’un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="bd044-129">Sign in to Finance by using one of the following roles:</span></span>

    - <span data-ttu-id="bd044-130">Développeur de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="bd044-130">Electronic reporting developer</span></span>
    - <span data-ttu-id="bd044-131">Consultant fonctionnel des états électroniques</span><span class="sxs-lookup"><span data-stu-id="bd044-131">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="bd044-132">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="bd044-132">System administrator</span></span>

2. <span data-ttu-id="bd044-133">Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="bd044-133">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="bd044-134">Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Importer les mises à jour des versions de configurations**.</span><span class="sxs-lookup"><span data-stu-id="bd044-134">On the **Localization configurations** page, in the **Related links** section, select **Import configurations versions updates**.</span></span>
4. <span data-ttu-id="bd044-135">Dans la boîte de dialogue **Importer les mises à jour des versions des configurations de gestion des états électroniques**, dans le champ **Mode d’exécution**, sélectionnez **Importer les dernières mises à jour** pour importer les dernières versions des configurations de gestion des états électroniques depuis le référentiel global vers l’instance actuelle de Finance.</span><span class="sxs-lookup"><span data-stu-id="bd044-135">In the **Import electronic reporting configurations versions updates** dialog box, in the **Run mode** field, select **Import latest updates** to import the latest versions of ER configurations from the Global repository into the current Finance instance.</span></span>
5. <span data-ttu-id="bd044-136">Pour planifier un traitement par lots pour l’importation, sur l’organisateur **Exécuter à l’arrière-plan**, définissez l’option **Traitement par lots** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="bd044-136">To schedule a batch job for the import, on the **Run in the background** FastTab, set the **Batch processing** option to **Yes**.</span></span> <span data-ttu-id="bd044-137">Si vous souhaitez répéter l’importation régulièrement, configurez la périodicité requise.</span><span class="sxs-lookup"><span data-stu-id="bd044-137">If you want to repeat the import periodically, configure the required recurrence.</span></span>

    ![Champ Mode d’exécution défini sur Importer les dernières mises à jour](./media/er-download-updated-versions-global-repo5.png)

6. <span data-ttu-id="bd044-139">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd044-139">Select **OK**.</span></span>
7. <span data-ttu-id="bd044-140">Pour savoir quelles versions de configuration ont été importées, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bd044-140">To learn what configuration versions have been imported, follow one of these steps:</span></span>

    - <span data-ttu-id="bd044-141">Si vous exécutez l’importation de manière interactive au lieu d’utiliser un traitement par lots, consultez les messages que vous recevez.</span><span class="sxs-lookup"><span data-stu-id="bd044-141">If you run the import interactively instead of using a batch job, review the messages that you receive.</span></span>

        ![Messages reçus lors de l’exécution d’une importation interactive](./media/er-download-updated-versions-global-repo6.png)

    - <span data-ttu-id="bd044-143">Si vous exécutez l’importation en mode de traitement par lots, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bd044-143">If you run the import in batch mode, follow these steps:</span></span>

        1. <span data-ttu-id="bd044-144">Allez dans **Commun** \> **Recherches** \> **Traitements par lots** \> **Mes traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="bd044-144">Go to **Common** \> **Inquiries** \> **Batch jobs** \> **My batch jobs**.</span></span>
        2. <span data-ttu-id="bd044-145">Recherchez et sélectionnez le travail **Importer les mises à jour des versions des configurations de gestion des états électroniques**, puis, dans le volet Actions, sous l’onglet **Traitement par lots**, sélectionnez **Historique des traitements par lots** pour afficher l’historique des travaux.</span><span class="sxs-lookup"><span data-stu-id="bd044-145">Find and select the **Import electronic reporting configurations versions updates** job, and then, on the Action Pane, on the **Batch job** tab, select **Batch job history** to view the job history.</span></span>
        3. <span data-ttu-id="bd044-146">Sur la page **Historique des traitements par lots**, sélectionnez **Journal**.</span><span class="sxs-lookup"><span data-stu-id="bd044-146">On the **Batch job history** page, select **Log**.</span></span> <span data-ttu-id="bd044-147">Ensuite, dans le message que vous recevez, sélectionnez le lien **Détails du message** pour afficher le journal des travaux.</span><span class="sxs-lookup"><span data-stu-id="bd044-147">Then, in the message that you receive, select the **Message details** link to view the job log.</span></span>

        ![Journal des travaux](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> <span data-ttu-id="bd044-149">Il n’est pas recommandé de planifier un traitement par lots récurrent pour importer des versions mises à jour des configurations de gestion des états électroniques directement depuis le référentiel global vers un environnement de production, car les versions importées seront immédiatement disponibles pour utilisation.</span><span class="sxs-lookup"><span data-stu-id="bd044-149">We don't recommend that you schedule a recurring batch job to import updated versions of ER configurations directly from the Global repository into a production environment, because the imported versions will immediately be available for use.</span></span> <span data-ttu-id="bd044-150">Utilisez plutôt cette approche pour déployer des versions des configurations de gestion des états électroniques dans un environnement de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="bd044-150">Instead, use this approach to deploy versions of ER configurations to a sandbox environment.</span></span> <span data-ttu-id="bd044-151">Elles peuvent ensuite être évaluées dans l’environnement de bac à sable avant d’être déployées dans un environnement de production.</span><span class="sxs-lookup"><span data-stu-id="bd044-151">They can then be evaluated in the sandbox environment before they are deployed to a production environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bd044-152">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="bd044-152">Additional resources</span></span>

- [<span data-ttu-id="bd044-153">Vue d’ensemble des états électroniques</span><span class="sxs-lookup"><span data-stu-id="bd044-153">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="bd044-154">Télécharger les configurations ER depuis le référentiel global du service de configuration</span><span class="sxs-lookup"><span data-stu-id="bd044-154">Download ER configurations from the Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]