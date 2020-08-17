---
title: Configurer l’intégration Common Data Service
description: Vous pouvez activer ou désactiver l’intégration entre Common Data Service et Dynamics 365 Human Resources. Vous pouvez également afficher les détails de la synchronisation, effacer les données de suivi et resynchroniser une entité pour aider à résoudre les problèmes de données entre les deux environnements.
author: andreabichsel
manager: AnnBe
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 8cbead2961c4576a5394080aae2fec109bce3f10
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621302"
---
# <a name="configure-common-data-service-integration"></a><span data-ttu-id="d205d-104">Configurer l’intégration Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d205d-104">Configure Common Data Service integration</span></span>

<span data-ttu-id="d205d-105">Vous pouvez activer ou désactiver l’intégration entre Common Data Service et Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d205d-105">You can turn integration between Common Data Service and Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="d205d-106">Vous pouvez également afficher les détails de la synchronisation, effacer les données de suivi et resynchroniser une entité pour aider à résoudre les problèmes de données entre les deux environnements.</span><span class="sxs-lookup"><span data-stu-id="d205d-106">You can also view the synchronization details, clear tracking data, and resync an entity to help troubleshoot data issues between the two environments.</span></span>

<span data-ttu-id="d205d-107">Lorsque vous désactivez l’intégration, les utilisateurs peuvent apporter des modifications à Human Resources ou Common Data Service, mais ces modifications ne sont pas synchronisées entre les deux environnements.</span><span class="sxs-lookup"><span data-stu-id="d205d-107">When you turn off integration, users can make changes in Human Resources or Common Data Service, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="d205d-108">Par défaut, l’intégration des données entre Human Resources et Common Data Service est désactivée.</span><span class="sxs-lookup"><span data-stu-id="d205d-108">By default, integration between Human Resources and Common Data Service is turned off.</span></span>

<span data-ttu-id="d205d-109">Vous souhaiterez peut-être désactiver l’intégration dans ces situations :</span><span class="sxs-lookup"><span data-stu-id="d205d-109">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="d205d-110">Vous remplissez des données via le Data Management Framework et devez importer les données plusieurs fois pour les avoir dans un état correct.</span><span class="sxs-lookup"><span data-stu-id="d205d-110">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="d205d-111">Il y a des problèmes avec les données Human Resources ou Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d205d-111">There are issues with data in either Human Resources or Common Data Service.</span></span> <span data-ttu-id="d205d-112">Si vous désactivez l’intégration, vous pouvez supprimer un enregistrement dans un environnement sans le supprimer dans l’autre.</span><span class="sxs-lookup"><span data-stu-id="d205d-112">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="d205d-113">Lorsque vous réactivez l’intégration, l’enregistrement dans l’environnement où il n’a pas été supprimé est synchronisé avec l’environnement où il a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="d205d-113">When you turn integration back on, the record in the environment where it wasn't deleted sync to the environment where it was deleted.</span></span> <span data-ttu-id="d205d-114">La synchronisation commence la prochaine fois que le traitement par lots **Intégration Common Data Service en échec, demande de synchronisation** s’exécute.</span><span class="sxs-lookup"><span data-stu-id="d205d-114">Synchronization begins the next time the **Common Data Service integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="d205d-115">Lorsque vous désactivez l’intégration des données, assurez-vous de ne pas modifier le même enregistrement dans les deux environnements.</span><span class="sxs-lookup"><span data-stu-id="d205d-115">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="d205d-116">Lorsque vous réactivez l’intégration, l’enregistrement que vous avez modifié en dernier sera synchronisé.</span><span class="sxs-lookup"><span data-stu-id="d205d-116">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="d205d-117">Par conséquent, si vous n’avez pas apporté les mêmes modifications à l’enregistrement dans les deux environnements, une perte de données peut se produire.</span><span class="sxs-lookup"><span data-stu-id="d205d-117">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-common-data-service-integration-page"></a><span data-ttu-id="d205d-118">Accéder à la page d’intégration de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d205d-118">Access the Common Data Service integration page</span></span>

1. <span data-ttu-id="d205d-119">Dans l’instance Human Resources où vous souhaitez afficher ou configurer les paramètres d’intégration avec Common Data Service, sélectionnez la vignette **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="d205d-119">In the Human Resources instance where you want to view or configure settings for the integration with Common Data Service, select the **System administration** tile.</span></span>

    <span data-ttu-id="d205d-120">[![Vignette Administration du système](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="d205d-120">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="d205d-121">Sélectionnez l’onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="d205d-121">Select the **Links** tab.</span></span>

    <span data-ttu-id="d205d-122">[![Onglet Liens](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="d205d-122">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="d205d-123">Sous **Intégrations**, sélectionnez **Configuration Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="d205d-123">Under **Integrations**, select **Common Data Service configuration**.</span></span>

    <span data-ttu-id="d205d-124">[![Lien Configuration Common Data Service](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="d205d-124">[![Common Data Service configuration link](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a><span data-ttu-id="d205d-125">Activer ou désactiver l’intégration des données entre Human Resources et Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d205d-125">Turn data integration between Human Resources and Common Data Service on or off</span></span>

- <span data-ttu-id="d205d-126">Pour activer l’intégration, définissez l’option **Activer l’intégration à Common Data Service** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="d205d-126">To turn on integration, set the **Enable the integration to the Common Data Service** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d205d-127">Lorsque vous activez l’intégration, les données seront synchronisées la prochaine fois que le traitement par lots **Intégration Common Data Service en échec, demande de synchronisation** s’exécute.</span><span class="sxs-lookup"><span data-stu-id="d205d-127">When you turn on integration, data will be synced the next time that the **Common Data Service integration missed request sync** batch job runs.</span></span> <span data-ttu-id="d205d-128">Toutes les données doivent être disponibles une fois le travail par lots terminé.</span><span class="sxs-lookup"><span data-stu-id="d205d-128">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="d205d-129">Pour désactiver l’intégration, définissez l’option sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="d205d-129">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="d205d-130">[![Activer ou désactiver l’intégration Common Data Service](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="d205d-130">[![Turning the Common Data Service integration on or off](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span></span>

> [!WARNING]
> <span data-ttu-id="d205d-131">Il est vivement recommandé de désactiver l’intégration de Common Data Service lors de l’exécution des tâches de migration des données.</span><span class="sxs-lookup"><span data-stu-id="d205d-131">We strongly recommend turning off Common Data Service integration while performing data migration tasks.</span></span> <span data-ttu-id="d205d-132">Les chargements de données volumineuses peuvent avoir une incidence significative sur les performances.</span><span class="sxs-lookup"><span data-stu-id="d205d-132">Large data uploads can significantly impact performance.</span></span> <span data-ttu-id="d205d-133">Par exemple, le chargement de 2 000 collaborateurs peut prendre plusieurs heures lorsque l’intégration est activée et moins d’une heure lorsqu’elle est désactivée.</span><span class="sxs-lookup"><span data-stu-id="d205d-133">For example, uploading 2000 workers can take several hours when integration is enabled, and less than one hour when it's disabled.</span></span> <span data-ttu-id="d205d-134">Les chiffres fournis dans cet exemple ne servent qu’à des fins de démonstration.</span><span class="sxs-lookup"><span data-stu-id="d205d-134">The numbers provided in this example are for demonstration purposes only.</span></span> <span data-ttu-id="d205d-135">La durée exacte nécessaire pour importer des enregistrements peut varier considérablement en fonction de nombreux facteurs.</span><span class="sxs-lookup"><span data-stu-id="d205d-135">The exact amount of time it takes to import records can vary greatly based on many factors.</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="d205d-136">Afficher les détails de l’intégration de données</span><span class="sxs-lookup"><span data-stu-id="d205d-136">View data integration details</span></span>

<span data-ttu-id="d205d-137">Sur l’organisateur **Administration** de la page **Intégration Common Data Service**, vous pouvez voir comment les enregistrements sont liés entre Human Resources et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d205d-137">On the **Administration** FastTab of the **Common Data Service integration** page, you can see how records are linked together between Human Resources and Common Data Service.</span></span>

- <span data-ttu-id="d205d-138">Pour afficher les enregistrements d’une entité, sélectionnez l’entité dans le champ **Nom d’entité CDS**.</span><span class="sxs-lookup"><span data-stu-id="d205d-138">To view the records for an entity, select the entity in the **CDS entity name** field.</span></span> <span data-ttu-id="d205d-139">La grille affiche tous les enregistrements liés à l’entité sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d205d-139">The grid shows all the records that are linked to the selected entity.</span></span>

<span data-ttu-id="d205d-140">[![Affichage des enregistrements d’une entité](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span><span class="sxs-lookup"><span data-stu-id="d205d-140">[![Viewing the records for an entity](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span></span>

> [!NOTE]
> <span data-ttu-id="d205d-141">Certaines entités Common Data Service ne sont pas actuellement répertoriées.</span><span class="sxs-lookup"><span data-stu-id="d205d-141">Not all Common Data Service entities are currently listed.</span></span> <span data-ttu-id="d205d-142">Seules les entités qui prennent en charge l’utilisation de champs personnalisés apparaissent dans la grille.</span><span class="sxs-lookup"><span data-stu-id="d205d-142">Only entities that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="d205d-143">De nouvelles entités seront disponibles grâce dans les prochaines versions de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d205d-143">New entities become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="d205d-144">La grille comprend les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="d205d-144">The grid includes the following fields:</span></span>

- <span data-ttu-id="d205d-145">**Nom de l’entité CDS** – Le nom de l’entité dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d205d-145">**CDS entity name** – The name of the entity in Common Data Service.</span></span>
- <span data-ttu-id="d205d-146">**Référence d’entité CDS** - L’identifiant qui utilise Common Data Service pour identifier un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="d205d-146">**CDS entity reference** – The identifier that Common Data Service uses to identify a record.</span></span> <span data-ttu-id="d205d-147">Cette valeur équivaut à la valeur **RecId** dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d205d-147">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="d205d-148">Vous pouvez trouver l’identifiant lorsque vous ouvrez l’entité Common Data Service dans Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="d205d-148">You can find the identifier when you open the Common Data Service entity in Microsoft Excel.</span></span>
- <span data-ttu-id="d205d-149">**Nom de l’entité Human Resources** - L’entité qui a synchronisé les dernières données avec Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d205d-149">**Human Resources entity name** – The entity that last synced data to Common Data Service.</span></span> <span data-ttu-id="d205d-150">L’entité peut avoir le préfixe Common Data Service ou un autre préfixe.</span><span class="sxs-lookup"><span data-stu-id="d205d-150">The entity can have either the Common Data Service prefix or another prefix.</span></span>
- <span data-ttu-id="d205d-151">**Référence Human Resources** - La valeur **RecId** associée à l’enregistrement dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d205d-151">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="d205d-152">**A été supprimé de CDS** - Une valeur qui indique si l’enregistrement a été supprimé de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d205d-152">**Was deleted from CDS** – A value that indicates whether the record was deleted from Common Data Service.</span></span>

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a><span data-ttu-id="d205d-153">Supprimer l’association d’un enregistrement dans Human Resources depuis Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d205d-153">Remove the association of a record in Human Resources from Common Data Service</span></span>

<span data-ttu-id="d205d-154">Si vous rencontrez des problèmes lors de la synchronisation des données entre Human Resources et Common Data Service, vous pourrez peut-être les résoudre en effaçant le suivi et en laissant la table de suivi se resynchroniser.</span><span class="sxs-lookup"><span data-stu-id="d205d-154">If you experience issues during data synchronization between Human Resources and Common Data Service, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="d205d-155">Si vous supprimez l’association, puis modifiez ou supprimez un enregistrement dans Common Data Service, les modifications ne seront pas synchronisées avec Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d205d-155">If you remove the association, and then change or delete a record in Common Data Service, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="d205d-156">Si vous apportez des modifications à Human Resources, un nouvel enregistrement de suivi est créé et l’enregistrement est mis à jour dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d205d-156">If you make changes in Human Resources, a new tracking record is created, and the record is updated in Common Data Service.</span></span>

- <span data-ttu-id="d205d-157">Pour supprimer l’association d’un enregistrement entre Human Resources et Common Data Service, sélectionnez l’entité dans le champ **Nom d’entité CDS**, puis sélectionnez **Effacer les informations de suivi**.</span><span class="sxs-lookup"><span data-stu-id="d205d-157">To remove the association of a record between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="d205d-158">[![Effacement des informations de suivi](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="d205d-158">[![Clearing tracking information](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span></span>

<span data-ttu-id="d205d-159">Pour exécuter une synchronisation complète sur l’entité après avoir effacé le suivi, consultez la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="d205d-159">To run a full synchronization on the entity after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a><span data-ttu-id="d205d-160">Synchroniser une entité entre Human Resources et Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d205d-160">Sync an entity between Human Resources and Common Data Service</span></span>

<span data-ttu-id="d205d-161">Utilisez cette procédure lorsque :</span><span class="sxs-lookup"><span data-stu-id="d205d-161">Use this procedure when:</span></span>

- <span data-ttu-id="d205d-162">Les modifications depuis Common Data Service prennent trop de temps pour apparaître dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d205d-162">Changes from Common Data Service take too long to appear in Human Resources.</span></span>

- <span data-ttu-id="d205d-163">Vous devez actualiser la table de suivi après avoir effacé le suivi.</span><span class="sxs-lookup"><span data-stu-id="d205d-163">You must refresh the tracking table after clearing the tracking.</span></span>

<span data-ttu-id="d205d-164">Pour exécuter une synchronisation complète sur une entité entre Human Resources et Common Data Service :</span><span class="sxs-lookup"><span data-stu-id="d205d-164">To run a full synchronization on an entity between Human Resources and Common Data Service:</span></span>

1. <span data-ttu-id="d205d-165">Sélectionnez l’entité dans le champ **Nom de l’entité CDS**.</span><span class="sxs-lookup"><span data-stu-id="d205d-165">Select the entity in the **CDS entity name** field.</span></span>

2. <span data-ttu-id="d205d-166">Sélectionnez **Synchroniser maintenant**.</span><span class="sxs-lookup"><span data-stu-id="d205d-166">Select **Sync now**.</span></span>

<span data-ttu-id="d205d-167">[![Exécution d’une synchronisation complète](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="d205d-167">[![Running a full synchronization](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span></span>


