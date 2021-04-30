---
title: Configurer l’intégration Dataverse
description: Vous pouvez activer ou désactiver l’intégration entre Microsoft Dataverse et Dynamics 365 Human Resources. Vous pouvez également afficher les détails de la synchronisation, effacer les données de suivi et resynchroniser une table pour aider à résoudre les problèmes de données entre les deux environnements.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bf406a954f5bb8b49627b58a901d0721cdad407b
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890026"
---
# <a name="configure-dataverse-integration"></a><span data-ttu-id="2aac1-104">Configurer l’intégration Dataverse</span><span class="sxs-lookup"><span data-stu-id="2aac1-104">Configure Dataverse integration</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2aac1-105">Vous pouvez activer ou désactiver l’intégration entre Microsoft Dataverse et Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2aac1-105">You can turn integration between Microsoft Dataverse and Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="2aac1-106">Vous pouvez également afficher les détails de la synchronisation, effacer les données de suivi et resynchroniser une table pour aider à résoudre les problèmes de données entre les deux environnements.</span><span class="sxs-lookup"><span data-stu-id="2aac1-106">You can also view the synchronization details, clear tracking data, and resync a table to help troubleshoot data issues between the two environments.</span></span>

> [!NOTE]
> <span data-ttu-id="2aac1-107">Pour plus d’informations sur Dataverse (auparavant Common Data Service) et les mises à jour terminologiques, voir [Qu’est-ce que Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="2aac1-107">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="2aac1-108">Lorsque vous désactivez l’intégration, les utilisateurs peuvent apporter des modifications à Human Resources ou Dataverse, mais ces modifications ne sont pas synchronisées entre les deux environnements.</span><span class="sxs-lookup"><span data-stu-id="2aac1-108">When you turn off integration, users can make changes in Human Resources or Dataverse, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="2aac1-109">Par défaut, l’intégration des données entre Human Resources et Dataverse est désactivée.</span><span class="sxs-lookup"><span data-stu-id="2aac1-109">By default, integration between Human Resources and Dataverse is turned off.</span></span>

<span data-ttu-id="2aac1-110">Vous souhaiterez peut-être désactiver l’intégration dans ces situations :</span><span class="sxs-lookup"><span data-stu-id="2aac1-110">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="2aac1-111">Vous remplissez des données via le Data Management Framework et devez importer les données plusieurs fois pour les avoir dans un état correct.</span><span class="sxs-lookup"><span data-stu-id="2aac1-111">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="2aac1-112">Il y a des problèmes avec les données Human Resources ou Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2aac1-112">There are issues with data in either Human Resources or Dataverse.</span></span> <span data-ttu-id="2aac1-113">Si vous désactivez l’intégration, vous pouvez supprimer un enregistrement dans un environnement sans le supprimer dans l’autre.</span><span class="sxs-lookup"><span data-stu-id="2aac1-113">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="2aac1-114">Lorsque vous réactivez l’intégration, l’enregistrement dans l’environnement où il n’a pas été supprimé est synchronisé avec l’environnement où il a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="2aac1-114">When you turn integration back on, the record in the environment where it wasn't deleted sync to the environment where it was deleted.</span></span> <span data-ttu-id="2aac1-115">La synchronisation commence la prochaine fois que le traitement par lots **Intégration Dataverse en échec, demande de synchronisation** s’exécute.</span><span class="sxs-lookup"><span data-stu-id="2aac1-115">Synchronization begins the next time the **Dataverse integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="2aac1-116">Lorsque vous désactivez l’intégration des données, assurez-vous de ne pas modifier le même enregistrement dans les deux environnements.</span><span class="sxs-lookup"><span data-stu-id="2aac1-116">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="2aac1-117">Lorsque vous réactivez l’intégration, l’enregistrement que vous avez modifié en dernier sera synchronisé.</span><span class="sxs-lookup"><span data-stu-id="2aac1-117">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="2aac1-118">Par conséquent, si vous n’avez pas apporté les mêmes modifications à l’enregistrement dans les deux environnements, une perte de données peut se produire.</span><span class="sxs-lookup"><span data-stu-id="2aac1-118">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-dataverse-integration-page"></a><span data-ttu-id="2aac1-119">Accéder à la page d’intégration de Dataverse</span><span class="sxs-lookup"><span data-stu-id="2aac1-119">Access the Dataverse integration page</span></span>

1. <span data-ttu-id="2aac1-120">Dans l’instance Human Resources où vous souhaitez afficher ou configurer les paramètres d’intégration avec Dataverse, sélectionnez la vignette **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="2aac1-120">In the Human Resources instance where you want to view or configure settings for the integration with Dataverse, select the **System administration** tile.</span></span>

    <span data-ttu-id="2aac1-121">[![Vignette Administration du système](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="2aac1-121">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="2aac1-122">Sélectionnez l’onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="2aac1-122">Select the **Links** tab.</span></span>

    <span data-ttu-id="2aac1-123">[![Onglet Liens](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="2aac1-123">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="2aac1-124">Sous **Intégrations**, sélectionnez **Configuration Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="2aac1-124">Under **Integrations**, select **Dataverse configuration**.</span></span>

    <span data-ttu-id="2aac1-125">[![Lien Configuration Dataverse](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)</span><span class="sxs-lookup"><span data-stu-id="2aac1-125">[![Dataverse configuration link](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a><span data-ttu-id="2aac1-126">Activer ou désactiver l’intégration des données entre Human Resources et Dataverse</span><span class="sxs-lookup"><span data-stu-id="2aac1-126">Turn data integration between Human Resources and Dataverse on or off</span></span>

- <span data-ttu-id="2aac1-127">Pour activer l’intégration, définissez l’option **Activer l’intégration Dataverse** sur **Oui** sur la page **Intégration Microsoft Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="2aac1-127">To turn on integration, set the **Enable Dataverse integration** option to **Yes** on the **Microsoft Dataverse integration** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2aac1-128">Lorsque vous activez l’intégration, les données seront synchronisées la prochaine fois que le traitement par lots **Intégration Dataverse en échec, demande de synchronisation** s’exécute.</span><span class="sxs-lookup"><span data-stu-id="2aac1-128">When you turn on integration, data will be synced the next time that the **Dataverse integration missed request sync** batch job runs.</span></span> <span data-ttu-id="2aac1-129">Toutes les données doivent être disponibles une fois le travail par lots terminé.</span><span class="sxs-lookup"><span data-stu-id="2aac1-129">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="2aac1-130">Pour désactiver l’intégration, définissez l’option sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="2aac1-130">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="2aac1-131">[![Activer ou désactiver l’intégration Dataverse](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)</span><span class="sxs-lookup"><span data-stu-id="2aac1-131">[![Turning the Dataverse integration on or off](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)</span></span>

> [!WARNING]
> <span data-ttu-id="2aac1-132">Il est vivement recommandé de désactiver l’intégration de Dataverse lors de l’exécution des tâches de migration des données.</span><span class="sxs-lookup"><span data-stu-id="2aac1-132">We strongly recommend turning off Dataverse integration while performing data migration tasks.</span></span> <span data-ttu-id="2aac1-133">Les chargements de données volumineuses peuvent avoir une incidence significative sur les performances.</span><span class="sxs-lookup"><span data-stu-id="2aac1-133">Large data uploads can significantly impact performance.</span></span> <span data-ttu-id="2aac1-134">Par exemple, le chargement de 2 000 collaborateurs peut prendre plusieurs heures lorsque l’intégration est activée et moins d’une heure lorsqu’elle est désactivée.</span><span class="sxs-lookup"><span data-stu-id="2aac1-134">For example, uploading 2000 workers can take several hours when integration is enabled, and less than one hour when it's disabled.</span></span> <span data-ttu-id="2aac1-135">Les chiffres fournis dans cet exemple ne servent qu’à des fins de démonstration.</span><span class="sxs-lookup"><span data-stu-id="2aac1-135">The numbers provided in this example are for demonstration purposes only.</span></span> <span data-ttu-id="2aac1-136">La durée exacte nécessaire pour importer des enregistrements peut varier considérablement en fonction de nombreux facteurs.</span><span class="sxs-lookup"><span data-stu-id="2aac1-136">The exact amount of time it takes to import records can vary greatly based on many factors.</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="2aac1-137">Afficher les détails de l’intégration de données</span><span class="sxs-lookup"><span data-stu-id="2aac1-137">View data integration details</span></span>

<span data-ttu-id="2aac1-138">Sur l’organisateur **Administration** de la page **Intégration Microsoft Dataverse**, vous pouvez voir comment les lignes sont liées entre Human Resources et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2aac1-138">On the **Administration** FastTab of the **Microsoft Dataverse integration** page, you can see how rows are linked together between Human Resources and Dataverse.</span></span>

- <span data-ttu-id="2aac1-139">Pour afficher les lignes d’un tableau, sélectionnez le tableau dans le champ **Table Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="2aac1-139">To view the rows for a table, select the table in the **Dataverse table** field.</span></span> <span data-ttu-id="2aac1-140">La grille affiche toutes les lignes liées à la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2aac1-140">The grid shows all the rows that are linked to the selected table.</span></span>

> [!NOTE]
> <span data-ttu-id="2aac1-141">Certaines tables Dataverse ne sont pas actuellement répertoriées.</span><span class="sxs-lookup"><span data-stu-id="2aac1-141">Not all Dataverse tables are currently listed.</span></span> <span data-ttu-id="2aac1-142">Seules les tables qui prennent en charge l’utilisation de champs personnalisés apparaissent dans la grille.</span><span class="sxs-lookup"><span data-stu-id="2aac1-142">Only tables that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="2aac1-143">De nouvelles tables seront disponibles grâce dans les prochaines versions de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2aac1-143">New tables become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="2aac1-144">La grille comprend les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="2aac1-144">The grid includes the following fields:</span></span>

- <span data-ttu-id="2aac1-145">**Table Dataverse** – Le nom de la table dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2aac1-145">**Dataverse table** – The name of the table in Dataverse.</span></span>
- <span data-ttu-id="2aac1-146">**Référence de table Dataverse** – L’identifiant qui utilise Dataverse pour identifier un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="2aac1-146">**Dataverse table reference** – The identifier that Dataverse uses to identify a record.</span></span> <span data-ttu-id="2aac1-147">Cette valeur équivaut à la valeur **RecId** dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2aac1-147">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="2aac1-148">Vous pouvez trouver l’identifiant lorsque vous ouvrez la table Dataverse dans Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="2aac1-148">You can find the identifier when you open the Dataverse table in Microsoft Excel.</span></span>
- <span data-ttu-id="2aac1-149">**Nom de l’entité Human Resources** – L’entité Human Resources qui a synchronisé les dernières données avec Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2aac1-149">**Human Resources entity name** – The Human Resources entity that last synced data to Dataverse.</span></span> <span data-ttu-id="2aac1-150">L’entité peut avoir le préfixe Dataverse ou un autre préfixe.</span><span class="sxs-lookup"><span data-stu-id="2aac1-150">The entity can have either the Dataverse prefix or another prefix.</span></span>
- <span data-ttu-id="2aac1-151">**Référence Human Resources** – La valeur **RecId** associée à l’enregistrement dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2aac1-151">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="2aac1-152">**Supprimé de Dataverse** – Une valeur qui indique si la ligne a été supprimée de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2aac1-152">**Deleted from Dataverse** – A value that indicates whether the row was deleted from Dataverse.</span></span>

> [!NOTE]
> <span data-ttu-id="2aac1-153">Les enregistrements dans Human Resources correspondent aux lignes dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2aac1-153">Records in Human Resources correspond to rows in Dataverse.</span></span>

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a><span data-ttu-id="2aac1-154">Supprimer l’association d’un enregistrement dans Human Resources à partir d’une ligne Dataverse</span><span class="sxs-lookup"><span data-stu-id="2aac1-154">Remove the association of a Human Resources record from a Dataverse row</span></span>

<span data-ttu-id="2aac1-155">Si vous rencontrez des problèmes lors de la synchronisation des données entre Human Resources et Dataverse, vous pourrez peut-être les résoudre en effaçant le suivi et en laissant la table de suivi se resynchroniser.</span><span class="sxs-lookup"><span data-stu-id="2aac1-155">If you experience issues during data synchronization between Human Resources and Dataverse, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="2aac1-156">Si vous supprimez l’association, puis modifiez ou supprimez une ligne dans Dataverse, les modifications ne seront pas synchronisées avec Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2aac1-156">If you remove the association, and then change or delete a row in Dataverse, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="2aac1-157">Si vous apportez des modifications à Human Resources, un nouvel enregistrement de suivi est créé et la ligne est mise à jour dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2aac1-157">If you make changes in Human Resources, a new tracking record is created, and the row is updated in Dataverse.</span></span>

- <span data-ttu-id="2aac1-158">Pour supprimer l’association d’un enregistrement Human Resources et une ligne Dataverse, sélectionnez la table dans le champ **Table Dataverse**, puis sélectionnez **Effacer les informations de suivi**.</span><span class="sxs-lookup"><span data-stu-id="2aac1-158">To remove the association of a Human Resources record and a Dataverse row, select the table in the **Dataverse table** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="2aac1-159">[![Effacement des informations de suivi](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="2aac1-159">[![Clearing tracking information](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)</span></span>

<span data-ttu-id="2aac1-160">Pour exécuter une synchronisation complète sur la table après avoir effacé le suivi, consultez la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="2aac1-160">To run a full synchronization on the table after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-a-table-between-human-resources-and-dataverse"></a><span data-ttu-id="2aac1-161">Synchroniser une table entre Human Resources et Dataverse</span><span class="sxs-lookup"><span data-stu-id="2aac1-161">Sync a table between Human Resources and Dataverse</span></span>

<span data-ttu-id="2aac1-162">Utilisez cette procédure lorsque :</span><span class="sxs-lookup"><span data-stu-id="2aac1-162">Use this procedure when:</span></span>

- <span data-ttu-id="2aac1-163">Les modifications depuis Dataverse prennent trop de temps pour apparaître dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2aac1-163">Changes from Dataverse take too long to appear in Human Resources.</span></span>

- <span data-ttu-id="2aac1-164">Vous devez actualiser la table de suivi après avoir effacé le suivi.</span><span class="sxs-lookup"><span data-stu-id="2aac1-164">You must refresh the tracking table after clearing the tracking.</span></span>

<span data-ttu-id="2aac1-165">Pour exécuter une synchronisation complète sur une table entre Human Resources et Dataverse :</span><span class="sxs-lookup"><span data-stu-id="2aac1-165">To run a full synchronization on a table between Human Resources and Dataverse:</span></span>

1. <span data-ttu-id="2aac1-166">Sélectionnez la table dans le champ **Table Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="2aac1-166">Select the table in the **Dataverse table** field.</span></span>

2. <span data-ttu-id="2aac1-167">Sélectionnez **Synchroniser maintenant**.</span><span class="sxs-lookup"><span data-stu-id="2aac1-167">Select **Sync now**.</span></span>

<span data-ttu-id="2aac1-168">[![Exécution d’une synchronisation complète](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="2aac1-168">[![Running a full synchronization](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="2aac1-169">Voir également :</span><span class="sxs-lookup"><span data-stu-id="2aac1-169">See also</span></span>

[<span data-ttu-id="2aac1-170">Tables Dataverse</span><span class="sxs-lookup"><span data-stu-id="2aac1-170">Dataverse tables</span></span>](hr-developer-entities.md)<br>
[<span data-ttu-id="2aac1-171">Configurer des tables virtuelles Dataverse</span><span class="sxs-lookup"><span data-stu-id="2aac1-171">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="2aac1-172">FAQ sur les tables virtuelles Human Resources</span><span class="sxs-lookup"><span data-stu-id="2aac1-172">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="2aac1-173">Qu’est-ce que Microsoft Dataverse ?</span><span class="sxs-lookup"><span data-stu-id="2aac1-173">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="2aac1-174">Mises à jour de la terminologie</span><span class="sxs-lookup"><span data-stu-id="2aac1-174">Terminology updates</span></span>](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]