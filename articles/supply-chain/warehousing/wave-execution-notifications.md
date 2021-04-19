---
title: Notifications d’exécution de vague
description: Cette rubrique décrit les notifications d’exécution de vague et explique comment les configurer.
author: mirzaab
ms.date: 04/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2022-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 0a61aff10234f40f14d603852be30fec3ba83647
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838080"
---
# <a name="wave-execution-notifications"></a><span data-ttu-id="f7ecd-103">Notifications d’exécution de vague</span><span class="sxs-lookup"><span data-stu-id="f7ecd-103">Wave execution notifications</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="f7ecd-104">La fonctionnalité *Notifications d’exécution de vague* utilise des événements commerciaux et le centre de notifications pour envoyer des notifications liées à l’exécution de la vague.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-104">The *Wave execution notifications* feature uses business events and the Action center to deliver notifications that are related to wave execution.</span></span> <span data-ttu-id="f7ecd-105">Elle vous permet de spécifier les types d’événements qui génèrent des notifications, les entrepôts qui les génèrent et les utilisateurs qui les reçoivent.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-105">It lets you specify the types of events that generate notifications, the warehouses that generate them, and the users who receive them.</span></span>

<span data-ttu-id="f7ecd-106">Le bouton **Afficher les messages** (symbole de la cloche) sur le côté droit de la barre de navigation indique quand un message du centre d’action est disponible pour l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-106">The **Show messages** button (bell symbol) on the right side of the navigation bar indicates when an Action center message is available for the current user.</span></span> <span data-ttu-id="f7ecd-107">L’utilisateur peut sélectionner le bouton **Afficher les messages** pour ouvrir le centre de notifications et consulter les messages.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-107">The user can select the **Show messages** button to open the Action center and review the messages.</span></span>

<span data-ttu-id="f7ecd-108">Les événements commerciaux se produisent lors de l’exécution des processus métier.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-108">Business events occur when business processes are run.</span></span> <span data-ttu-id="f7ecd-109">Les processus métier sont constitués de tâches.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-109">Business processes are made up of tasks.</span></span> <span data-ttu-id="f7ecd-110">Au cours d’un processus métier, les utilisateurs qui y participent exécutent des actions métier pour effectuer ces tâches.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-110">During a business process, the users who participate in it perform business actions to complete those tasks.</span></span> <span data-ttu-id="f7ecd-111">Les événements commerciaux fournissent un mécanisme permettant aux systèmes externes de recevoir des notifications de la part des applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-111">Business events provide a mechanism that lets external systems receive notifications from Finance and Operations applications.</span></span> <span data-ttu-id="f7ecd-112">De cette manière, les systèmes peuvent effectuer des actions métier en réponse aux événements commerciaux.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-112">In this way, the systems can perform business actions in response to the business events.</span></span> <span data-ttu-id="f7ecd-113">Pour plus d’informations, consultez [Présentation des événements commerciaux](../../fin-ops-core/dev-itpro/business-events/home-page.md).</span><span class="sxs-lookup"><span data-stu-id="f7ecd-113">For more information, see [Business events overview](../../fin-ops-core/dev-itpro/business-events/home-page.md).</span></span>

## <a name="turn-on-the-wave-execution-notifications-feature"></a><span data-ttu-id="f7ecd-114">Activer la fonctionnalité de notifications d’exécution de vague</span><span class="sxs-lookup"><span data-stu-id="f7ecd-114">Turn on the Wave execution notifications feature</span></span>

<span data-ttu-id="f7ecd-115">Avant de pouvoir utiliser la fonctionnalité *Notifications d’exécution de vague*, celle-ci doit être activée sur votre système.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-115">Before you can use the *Wave execution notifications* feature, it must be turned on in your system.</span></span> <span data-ttu-id="f7ecd-116">Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-116">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="f7ecd-117">Là, la fonctionnalité est répertoriée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="f7ecd-117">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="f7ecd-118">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="f7ecd-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="f7ecd-119">**Nom de la fonctionnalité :** *Notifications d’exécution de vague*</span><span class="sxs-lookup"><span data-stu-id="f7ecd-119">**Feature name:** *Wave execution notifications*</span></span>

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a><span data-ttu-id="f7ecd-120">Scénario : envoyer des notifications d’exécution du traitement par lots d’une vague au centre de notifications</span><span class="sxs-lookup"><span data-stu-id="f7ecd-120">Scenario: Send wave batch execution notifications to the Action center</span></span>

<span data-ttu-id="f7ecd-121">Ce scénario montre le flux de bout en bout pour envoyer des notifications sur les erreurs d’exécution du traitement par lots d’une vague à un rôle spécifique via le centre de notifications.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-121">This scenario shows the end-to-end flow for sending notifications about wave batch execution errors to a specific role via the Action center.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="f7ecd-122">Rendre les données de démonstration disponibles</span><span class="sxs-lookup"><span data-stu-id="f7ecd-122">Make demo data available</span></span>

<span data-ttu-id="f7ecd-123">Pour suivre ce scénario, vous devez avoir des données de démonstration installées, et vous devez sélectionner l’entité juridique **USMF**.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-123">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a><span data-ttu-id="f7ecd-124">Assurez-vous que les vagues sont exécutées en mode de traitement par lots</span><span class="sxs-lookup"><span data-stu-id="f7ecd-124">Make sure that waves are run in batch mode</span></span>

1. <span data-ttu-id="f7ecd-125">Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-125">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="f7ecd-126">Dans le raccourci **Traitement de vague**, définissez l’option **Traiter les vagues par lots** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-126">On the **Wave processing** FastTab, set the **Process waves in batch** option to *Yes*.</span></span>

> [!NOTE]
> <span data-ttu-id="f7ecd-127">Si vous souhaitez désactiver les notifications d’exécution du traitement par lots d’une vague, définissez l’option **Désactiver les notifications du traitement par lots d’une vague** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-127">If you want to disable wave batch execution notifications, set the **Disable wave processing batch notifications** option to *Yes*.</span></span>

### <a name="configure-a-wave-notification-policy"></a><span data-ttu-id="f7ecd-128">Configurer une stratégie de notification de vague</span><span class="sxs-lookup"><span data-stu-id="f7ecd-128">Configure a wave notification policy</span></span>

<span data-ttu-id="f7ecd-129">Les stratégies de notification de vague définissent les types de notifications envoyées et les utilisateurs qui sont notifiés.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-129">Wave notification policies define the types of notifications that are sent and the users who are notified.</span></span>

1. <span data-ttu-id="f7ecd-130">Accédez à **Gestion des entrepôts \> Paramétrage \> Vagues \> Stratégies de notification de vague**.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-130">Go to **Warehouse management \> Setup \> Waves \> Wave notification policies**.</span></span>
1. <span data-ttu-id="f7ecd-131">Créez un enregistrement possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f7ecd-131">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="f7ecd-132">**Stratégie de notification de vague :** *24BatchError*</span><span class="sxs-lookup"><span data-stu-id="f7ecd-132">**Wave notification policy:** *24BatchError*</span></span>
    - <span data-ttu-id="f7ecd-133">**Description :** *Erreur du traitement par lots de la vague de l’entrepôt 24*</span><span class="sxs-lookup"><span data-stu-id="f7ecd-133">**Description:** *Warehouse 24 wave batch error*</span></span>
    - <span data-ttu-id="f7ecd-134">**Envoyer une notification sur :** *Erreur uniquement*</span><span class="sxs-lookup"><span data-stu-id="f7ecd-134">**Send notification on:** *Error only*</span></span>
    - <span data-ttu-id="f7ecd-135">**Rôle de destination :** *Administrateur système*</span><span class="sxs-lookup"><span data-stu-id="f7ecd-135">**To role:** *System administrator*</span></span>

        > [!NOTE]
        > <span data-ttu-id="f7ecd-136">Étant donné que ce scénario utilise des données de démonstration, le rôle *Administrateur système* est choisi par souci de simplicité.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-136">Because this scenario uses demo data, the *System administrator* role is selected for the sake of simplicity.</span></span> <span data-ttu-id="f7ecd-137">Par conséquent, comme vous êtes connecté en tant qu’utilisateur administrateur système, vous recevrez les notifications.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-137">Therefore, because you're signed in as a system administrator user, you will receive the notifications.</span></span> <span data-ttu-id="f7ecd-138">Cependant, en pratique, vous devrez généralement sélectionner un rôle plus spécifique pour notifier les erreurs d’exécution du traitement par lots de vagues, tel que *Gestionnaire d’entrepôt*.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-138">However, in practice, you should usually select a more specific role to notify about wave batch execution errors, such as *Warehouse manager*.</span></span>

1. <span data-ttu-id="f7ecd-139">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-139">On the Action Pane, select **Save**.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="f7ecd-140">Configurer un modèle de vague</span><span class="sxs-lookup"><span data-stu-id="f7ecd-140">Configure a wave template</span></span>

<span data-ttu-id="f7ecd-141">Les modèles de vague vous permettent de lier des instances spécifiques de méthodes de vague à des modèles d’étiquette de vague correspondants.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-141">Wave templates let you link specific instances of wave methods to corresponding wave label templates.</span></span>

1. <span data-ttu-id="f7ecd-142">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-142">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="f7ecd-143">Dans le volet de liste, définissez le champ **Type de modèle de vague** sur *Expédition*, puis sélectionnez le modèle de vague *Livraison par défaut 24* pour l’entrepôt 24.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-143">In the list pane, set the **Wave template type** field to *Shipping*, and then select the *24 Shipping Default* wave template for warehouse 24.</span></span>
1. <span data-ttu-id="f7ecd-144">Dans le raccourci **Général**, définissez le champ **Stratégie de notification de vague** sur *24BatchError*.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-144">On the **General** FastTab, set the **Wave notification policy** field to *24BatchError*.</span></span>

### <a name="configure-a-work-template"></a><span data-ttu-id="f7ecd-145">Configurer un modèle de travail</span><span class="sxs-lookup"><span data-stu-id="f7ecd-145">Configure a work template</span></span>

<span data-ttu-id="f7ecd-146">Les modèles de travail sont utilisés lors de l’exécution de la vague pour générer du travail.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-146">Work templates are used during wave execution to generate work.</span></span> <span data-ttu-id="f7ecd-147">Pour ce scénario, l’exécution de la vague doit déclencher une erreur.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-147">For this scenario, wave execution should trigger an error.</span></span> <span data-ttu-id="f7ecd-148">En définissant la requête de modèle de travail pour utiliser un entrepôt inexistant, vous vous assurez que l’exécution de la vague échouera et enverra donc une notification.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-148">By setting the work template query to use a nonexistent warehouse, you will ensure that wave execution fails and therefore sends a notification.</span></span>

1. <span data-ttu-id="f7ecd-149">Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-149">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="f7ecd-150">Dans le volet de liste, définissez le champ **Type de modèle de travail** sur *Commandes clients*, puis sélectionnez le modèle de travail *Phase CC 24* pour l’entrepôt 24.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-150">In the list pane, set the **Work template type** field to *Sales orders* and then select the *24 SO Stage* work template for warehouse 24.</span></span>
1. <span data-ttu-id="f7ecd-151">Dans le volet Actions, sélectionnez **Modifier une requête**.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-151">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="f7ecd-152">Dans la boîte de dialogue de l’éditeur de requêtes, sur l’onglet **Plage**, modifiez la ligne suivante (ou ajoutez-la si elle n’existe pas) :</span><span class="sxs-lookup"><span data-stu-id="f7ecd-152">In the query editor dialog box, on the **Range** tab, edit the following row (or add it if it doesn't exist):</span></span>

    - <span data-ttu-id="f7ecd-153">**Table :** *Transactions de travail temporaire*</span><span class="sxs-lookup"><span data-stu-id="f7ecd-153">**Table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="f7ecd-154">**Table dérivée :** *Transactions de travail temporaire*</span><span class="sxs-lookup"><span data-stu-id="f7ecd-154">**Derived table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="f7ecd-155">**Champ :** *Entrepôt*</span><span class="sxs-lookup"><span data-stu-id="f7ecd-155">**Field:** *Warehouse*</span></span>
    - <span data-ttu-id="f7ecd-156">**Critères :** Changer la valeur de *24* en *Erreur*.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-156">**Criteria:** Change the value from *24* to *Error*.</span></span>

1. <span data-ttu-id="f7ecd-157">Sélectionnez **OK** et confirmez la modification.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-157">Select **OK**, and confirm the change.</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="f7ecd-158">Créer une commande client et la lancer dans l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="f7ecd-158">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="f7ecd-159">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-159">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="f7ecd-160">Créez une commande client possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f7ecd-160">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="f7ecd-161">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="f7ecd-161">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="f7ecd-162">**Entrepôt :** *24*</span><span class="sxs-lookup"><span data-stu-id="f7ecd-162">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="f7ecd-163">Dans le raccourci **Lignes de commande client**, ajoutez une commande client présentant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f7ecd-163">On the **Sales order lines** FastTab, add a sales order line that has the following settings:</span></span>

    - <span data-ttu-id="f7ecd-164">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="f7ecd-164">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="f7ecd-165">**Quantité :** *10*</span><span class="sxs-lookup"><span data-stu-id="f7ecd-165">**Quantity:** *10*</span></span>

    > [!NOTE]
    > <span data-ttu-id="f7ecd-166">Ces articles et quantités ne sont que des exemples.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-166">These items and quantities are only examples.</span></span> <span data-ttu-id="f7ecd-167">L’entrepôt spécifié doit contenir suffisamment de stock.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-167">The specified warehouse must contain enough stock.</span></span>

1. <span data-ttu-id="f7ecd-168">Alors que la nouvelle ligne de commande est toujours sélectionnée dans le raccourci **Lignes de commande client**, sélectionnez **Stock \> Réservation** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-168">While the new line is still selected on the **Sales order lines** FastTab, select **Inventory \> Reservation** on the toolbar.</span></span>
1. <span data-ttu-id="f7ecd-169">Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot**.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-169">On the **Reservation** page, on the Action Pane, select **Reserve lot**.</span></span> <span data-ttu-id="f7ecd-170">Fermez ensuite la page.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-170">Then close the page.</span></span>
1. <span data-ttu-id="f7ecd-171">Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-171">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

### <a name="notifications-from-wave-batch-job-execution"></a><span data-ttu-id="f7ecd-172">Notifications de l’exécution du traitement par lots d’une vague</span><span class="sxs-lookup"><span data-stu-id="f7ecd-172">Notifications from wave batch job execution</span></span>

<span data-ttu-id="f7ecd-173">En fonction de la configuration de vos événements commerciaux, vous recevrez éventuellement une notification d’échec de l’exécution de la vague.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-173">Depending on the setup of your business events, you will eventually receive a notification about wave execution failure.</span></span> <span data-ttu-id="f7ecd-174">Le message du centre de notifications ressemblera à l’exemple suivant et inclura un lien vers la vague qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-174">The Action center message will resemble the following example and will include a link to the wave that failed.</span></span>

> <span data-ttu-id="f7ecd-175">**Erreur lors de l’exécution de la vague**</span><span class="sxs-lookup"><span data-stu-id="f7ecd-175">**Error during wave execution**</span></span>  
> <span data-ttu-id="f7ecd-176">Une erreur s’est produite lors de l’exécution de la vague USMF-000000001.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-176">An error occurred while executing wave USMF-000000001.</span></span>  
> <span data-ttu-id="f7ecd-177">Derniers messages : Aucun travail n’a été créé pour la vague USMF-000000001.</span><span class="sxs-lookup"><span data-stu-id="f7ecd-177">Last messages: No Work was created for Wave USMF-000000001.</span></span>
>
> <span data-ttu-id="f7ecd-178">**STATUT**</span><span class="sxs-lookup"><span data-stu-id="f7ecd-178">**STATUS**</span></span>  
> <span data-ttu-id="f7ecd-179">Actif.ve</span><span class="sxs-lookup"><span data-stu-id="f7ecd-179">Active</span></span>
>
> <span data-ttu-id="f7ecd-180">Ouvrir les détails de la vague</span><span class="sxs-lookup"><span data-stu-id="f7ecd-180">Open wave details</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
