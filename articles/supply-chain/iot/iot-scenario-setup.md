---
title: Configuration d'un scénario pour l'intelligence IoT
description: Cette rubrique décrit comment configurer un scénario dans Supply Chain Management pour l'intelligence IoT.
author: robinarh
manager: AnnBe
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b87a9b73f49e73fe13b98fb11da939c9b30e0f6e
ms.sourcegitcommit: 261b70ea358b2c231e20f320ed8bd6adc1e7d715
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2020
ms.locfileid: "3386514"
---
# <a name="scenario-setup-for-iot-intelligence"></a><span data-ttu-id="ddae1-103">Configuration d'un scénario pour l'intelligence IoT</span><span class="sxs-lookup"><span data-stu-id="ddae1-103">Scenario setup for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ddae1-104">Cette rubrique décrit comment configurer un scénario dans Supply Chain Management pour l'intelligence IoT.</span><span class="sxs-lookup"><span data-stu-id="ddae1-104">This topic describes how to configure a scenario in Supply Chain Management for IoT Intelligence.</span></span> <span data-ttu-id="ddae1-105">Avant de pouvoir configurer des scénarios, vous devez [configurer LCS](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="ddae1-105">Before you can setup the scenarios, you must [setup LCS](iot-lcs-setup.md).</span></span>

<span data-ttu-id="ddae1-106">Dans cette rubrique, vous allez configurer le scénario **Temps d'arrêt de l'équipement** pour générer une notification dans Supply Chain Management lorsqu'une machine tombe en panne.</span><span class="sxs-lookup"><span data-stu-id="ddae1-106">In this topic, you will configure the **Equipment downtime** scenario to generate a notification in Supply Chain Management when a machine goes down.</span></span>

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a><span data-ttu-id="ddae1-107">Configurer le scénario **Temps d'arrêt de l'équipement** dans Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ddae1-107">Configure the **Equipment downtime** scenario in Supply Chain Management</span></span>

<span data-ttu-id="ddae1-108">Le scénario **Temps d'arrêt de l'équipement** mappe un signal de sortie de pièce à un seuil d'alerte machine.</span><span class="sxs-lookup"><span data-stu-id="ddae1-108">The **Equipment downtime** scenario maps a part out signal to a machine alert threshold.</span></span> <span data-ttu-id="ddae1-109">La machine est surveillée uniquement lorsqu'elle est sélectionnée pour le scénario et est configurée pour s'exécuter dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ddae1-109">The machine is monitored only when the machine is selected for the scenario and is set to running in Supply Chain Management.</span></span> <span data-ttu-id="ddae1-110">Si le temps écoulé depuis le dernier signal PartOut reçu par la machine est supérieur au seuil d'alerte, la notification **Machine en panne** est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="ddae1-110">If the time since the machine’s last received Part Out signal is greater than the alert threshold, then a **Machine down** notification is triggered.</span></span> <span data-ttu-id="ddae1-111">Si la machine est toujours en marche, lorsque le signal **PartOut** suivant est envoyé, la notification **Machine en marche** est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="ddae1-111">If the machine is still running, when the next **PartOut** signal is received a **Machine up** notification is triggered.</span></span> <span data-ttu-id="ddae1-112">Si une machine s'arrête pendant 30 minutes, une nouvelle notification **Machine en panne** est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="ddae1-112">If a machine stays down for 30 mins a new **Machine down** notification is triggered.</span></span>

<span data-ttu-id="ddae1-113">Le scénario **Temps d'arrêt de l'équipement** a les dépendances suivantes :</span><span class="sxs-lookup"><span data-stu-id="ddae1-113">The **Equipment downtime** scenario has these dependencies:</span></span>

+ <span data-ttu-id="ddae1-114">Un ordre de fabrication doit être exécuté sur une machine mappée pour qu'une alerte soit déclenchée.</span><span class="sxs-lookup"><span data-stu-id="ddae1-114">A production order must be running on a mapped machine for an alert to be triggered.</span></span>
+ <span data-ttu-id="ddae1-115">Un signal représentant le signal de sortie de pièce d'une machine mappée doit être envoyé au hub IoT avec un nom de propriété unique.</span><span class="sxs-lookup"><span data-stu-id="ddae1-115">A signal representing a mapped machine's part out signal must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="ddae1-116">Une propriété d'horodatage Unix millisecondes doit être présente dans le message du hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ddae1-116">A Unix milliseconds timestamp property must be present in the IoT hub message.</span></span>

<span data-ttu-id="ddae1-117">Procédez comme suit pour configurer le scénario :</span><span class="sxs-lookup"><span data-stu-id="ddae1-117">To configure the scenario, follow these steps:</span></span>

1. <span data-ttu-id="ddae1-118">Connectez-vous à Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ddae1-118">Log into Supply Chain Management.</span></span>
2. <span data-ttu-id="ddae1-119">Activez l'indicateur de fonctionnalité Intelligence IoT.</span><span class="sxs-lookup"><span data-stu-id="ddae1-119">Enable the IoT Intelligence feature flag.</span></span> <span data-ttu-id="ddae1-120">Pour plus d'informations, voir [Vue d'ensemble de la gestion des fonctionnalités](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ddae1-120">For more information, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
3. <span data-ttu-id="ddae1-121">Configurez les mesures.</span><span class="sxs-lookup"><span data-stu-id="ddae1-121">Configure the metrics.</span></span> <span data-ttu-id="ddae1-122">Pour plus d'informations, voir [Comment configurer les mesures](iot-metrics-setup.md#configure-metrics).</span><span class="sxs-lookup"><span data-stu-id="ddae1-122">For more information, see [How to configure metrics](iot-metrics-setup.md#configure-metrics).</span></span>
4. <span data-ttu-id="ddae1-123">Accédez à **Contrôle de production**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-123">Navigate to **Production control**.</span></span>
5. <span data-ttu-id="ddae1-124">Accédez à **Configuration \> Intelligence IoT \> Gestion des scénarios**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-124">Navigate to **Setup \> IoT Intelligence \> Scenario management**.</span></span>
6. <span data-ttu-id="ddae1-125">Cliquez sur **Configurer** sur l'onglet **Temps d'arrêt de l'équipement**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-125">Click **Configure** on the **Equipment downtime** tile.</span></span> <span data-ttu-id="ddae1-126">L'assistant de configuration commence par la page **Définition du schéma du capteur d'équipement**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-126">The configuration wizard starts with the **Equipment sensor schema definition** page.</span></span> <span data-ttu-id="ddae1-127">L'objectif ici est de configurer le schéma dans Supply Chain Management pour qu'il corresponde au format JSON des messages IoT.</span><span class="sxs-lookup"><span data-stu-id="ddae1-127">The goal here is to setup the schema in Supply Chain Management to match the JSON format of the IoT messages.</span></span> <span data-ttu-id="ddae1-128">Plusieurs schémas de message peuvent être définis.</span><span class="sxs-lookup"><span data-stu-id="ddae1-128">Multiple message schemas can be defined.</span></span> <span data-ttu-id="ddae1-129">Pour plus d'informations, voir [Formats de schémas de message pour hub IoT](iot-schema-format.md).</span><span class="sxs-lookup"><span data-stu-id="ddae1-129">For more information, see [Message schema formats for IoT Hub](iot-schema-format.md).</span></span> <span data-ttu-id="ddae1-130">Dans cet exemple, la charge utile du message contient un lot de messages avec ce format :</span><span class="sxs-lookup"><span data-stu-id="ddae1-130">In this example, the message payload contains a batch of messages with this format:</span></span>

    ```json
    {
        "timestamp": 1576016821614,
        "payload": [
            {
                "id": "IoTInt.Machine1225.PartOut",
                "timestamp": 1576016821614,
                "value": True
            },
            {
                "id": "IoTInt.Machine1226.PartOut",
                "timestamp": 1576016991616,
                "value": True
            }
        ]
    }
    ```

7. <span data-ttu-id="ddae1-131">Ajoutez une ligne au tableau.</span><span class="sxs-lookup"><span data-stu-id="ddae1-131">Add a row to the table.</span></span>

    1. <span data-ttu-id="ddae1-132">Définissez le **Nom du schéma** sur **ID**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-132">Set the **Schema name** to **ID**.</span></span>
    2. <span data-ttu-id="ddae1-133">Définissez le **Chemin d'accès du schéma** sur **/charge utile[\*]/id**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-133">Set the **Schema path** to **/payload[\*]/id**.</span></span>
    3. <span data-ttu-id="ddae1-134">Définissez la **Description** sur **ID du message**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-134">Set the **Description** to **Message ID**.</span></span>

8. <span data-ttu-id="ddae1-135">Ajoutez une ligne au tableau.</span><span class="sxs-lookup"><span data-stu-id="ddae1-135">Add a row to the table.</span></span>

    1. <span data-ttu-id="ddae1-136">Définissez le **Nom du schéma** sur **Horodatage**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-136">Set the **Schema name** to **Timestamp**.</span></span>
    2. <span data-ttu-id="ddae1-137">Définissez le **Chemin d'accès du schéma** sur **/charge utile[\*]/horodatage**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-137">Set the **Schema path** to **/payload[\*]/timestamp**.</span></span>
    3. <span data-ttu-id="ddae1-138">Définissez la **Description** sur **Horodatage du message**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-138">Set the **Description** to **Message timestamp**.</span></span>

9. <span data-ttu-id="ddae1-139">Ajoutez une ligne au tableau.</span><span class="sxs-lookup"><span data-stu-id="ddae1-139">Add a row to the table.</span></span>

    1. <span data-ttu-id="ddae1-140">Définissez le **Nom du schéma** sur **Valeur**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-140">Set the **Schema name** to **Value**.</span></span>
    2. <span data-ttu-id="ddae1-141">Définissez le **Chemin d'accès du schéma** sur **/charge utile[\*]/valeur**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-141">Set the **Schema path** to **/payload[\*]/value**.</span></span>
    3. <span data-ttu-id="ddae1-142">Définissez la **Description** sur **Valeur du message**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-142">Set the **Description** to **Message value**.</span></span>

    <span data-ttu-id="ddae1-143">Vous n'avez pas besoin de définir toutes les propriétés du message, uniquement celles dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="ddae1-143">You don't need to define all the properties in the message, only the ones that you need.</span></span> <span data-ttu-id="ddae1-144">Dans cet exemple, vous n'avez pas créé de ligne pour **Horodatage racine**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-144">In this example, you did not create a row for **Root timestamp**.</span></span> <span data-ttu-id="ddae1-145">Le chemin pour **Horodatage racine** serait **/horodatage**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-145">The path for **Root timestamp** would be **/timestamp**.</span></span>
  
10. <span data-ttu-id="ddae1-146">Cliquez sur **Suivant** pour accéder à la page **Carte du schéma du capteur d'équipement**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-146">Click **Next** to go to the **Equipment sensor schema map** page.</span></span>
11. <span data-ttu-id="ddae1-147">Dans la ligne pour **ID de ressource d'équipement** définissez le **Nom du schéma** sur **ID**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-147">In the row for **Equipment resource ID** set the **Schema name** to **ID**.</span></span> <span data-ttu-id="ddae1-148">Les valeurs valides sont affichées dans un tableau déroulant.</span><span class="sxs-lookup"><span data-stu-id="ddae1-148">The valid values are displayed in a dropdown table.</span></span>
12. <span data-ttu-id="ddae1-149">Dans la ligne pour **Heure UTC** définissez le **Nom du schéma** sur **Horodatage**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-149">In the row for **UTC time** set the **Schema name** to **Timestamp**.</span></span> <span data-ttu-id="ddae1-150">Les valeurs valides sont affichées dans un tableau déroulant.</span><span class="sxs-lookup"><span data-stu-id="ddae1-150">The valid values are displayed in a dropdown table.</span></span>
13. <span data-ttu-id="ddae1-151">Dans la ligne pour **Signal produit par la pièce**, définissez le **Nom du schéma** sur **Valeur**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-151">In the row for **Part produced signal** set the **Schema name** to **Value**.</span></span> <span data-ttu-id="ddae1-152">Les valeurs valides sont affichées dans un tableau déroulant.</span><span class="sxs-lookup"><span data-stu-id="ddae1-152">The valid values are displayed in a dropdown table.</span></span>
14. <span data-ttu-id="ddae1-153">Cliquez sur **Suivant** pour accéder à la page **Configuration de l'ID de ressource d'équipement**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-153">Click **Next** for the **Equipment resource ID configuration** page.</span></span>
15. <span data-ttu-id="ddae1-154">Dans cette étape, vous devez mapper les valeurs de message hub IoT aux ressources de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ddae1-154">In this step, you map the IoT Hub message values to the Supply Chain Management resources.</span></span>

    1. <span data-ttu-id="ddae1-155">Dans la table **Valeurs des données du signal**, ajoutez une nouvelle ligne et entrez **IoTInt.Machine1225.PartOut** dans la colonne **Valeur**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-155">In the **Signal Data Values** table, add a new row, and enter **IoTInt.Machine1225.PartOut** in the **Value** column.</span></span> <span data-ttu-id="ddae1-156">La valeur **IoTInt.Machine1225.PartOut** provient de la propriété **id** du JSON dans le message du hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ddae1-156">The value **IoTInt.Machine1225.PartOut** comes from the JSON **id** property in the IoT hub message.</span></span>
    2. <span data-ttu-id="ddae1-157">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-157">Click **Save**.</span></span>
    3. <span data-ttu-id="ddae1-158">Dans le tableau **Mise en correspondance des enregistrements commerciaux**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-158">In the **Business Record Mapping** table, click **New**.</span></span> <span data-ttu-id="ddae1-159">La valeur par défaut pour le **Type d'enregistrement commercial** est renseignée automatiquement et vous n'avez pas besoin de la modifier.</span><span class="sxs-lookup"><span data-stu-id="ddae1-159">The default value for the **Business record type** is autopopulated, and you don't need to change it.</span></span>
    4. <span data-ttu-id="ddae1-160">Dans la colonne **Enregistrement commercial**, sélectionnez la ressource de la machine Supply Chain Management à partir de laquelle cette valeur de signal est envoyée.</span><span class="sxs-lookup"><span data-stu-id="ddae1-160">In the **Business record** column, select the Supple Chain Management machine resource this signal value is being sent from.</span></span>
    5. <span data-ttu-id="ddae1-161">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-161">Click **Save**.</span></span>
    6. <span data-ttu-id="ddae1-162">Répétez ces étapes en ajoutant une nouvelle mise en correspondance d'enregistrement commercial pour **Machine1226**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-162">Repeat these steps, adding a new business record mapping for **Machine1226**.</span></span> <span data-ttu-id="ddae1-163">Vous pouvez mapper plusieurs valeurs de données de signal à un seul enregistrement dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ddae1-163">You can map multiple signal data values to a single record in Supply Chain Management.</span></span>

16. <span data-ttu-id="ddae1-164">Utilisez la colonne **Sélectionné** pour choisir les machines à traiter.</span><span class="sxs-lookup"><span data-stu-id="ddae1-164">Use the **Selected** column to choose which machines you want to process.</span></span> <span data-ttu-id="ddae1-165">Vous n'avez pas à définir toutes les valeurs de signal et vous n'avez pas à sélectionner toutes les machines.</span><span class="sxs-lookup"><span data-stu-id="ddae1-165">You do not have to define all signal values and you do not have to select all machines.</span></span>
17. <span data-ttu-id="ddae1-166">Cliquez sur **Suivant** pour accéder à la page **Configuration du signal produit par la pièce**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-166">Click **Next** to go to the **Part produced signal configuration** page.</span></span>
18. <span data-ttu-id="ddae1-167">Dans le tableau **Valeurs des données du signal**, ajoutez une ligne et définissez **Valeur** sur **True**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-167">In the **Signal Data Values** table, add a row, and set **Value** to **True**.</span></span> <span data-ttu-id="ddae1-168">La valeur **True** provient de la propriété **valeur** de JSON dans le message du hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ddae1-168">The value **True** comes from the JSON **value** property in the IoT hub message.</span></span> <span data-ttu-id="ddae1-169">Vous pouvez ajouter autant de valeurs que nécessaire pour votre scénario.</span><span class="sxs-lookup"><span data-stu-id="ddae1-169">You can add as many values as you need for your scenario.</span></span>
19. <span data-ttu-id="ddae1-170">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-170">Click **Save**.</span></span>
20. <span data-ttu-id="ddae1-171">Cliquez sur **Suivant** pour accéder à la page **Seuil de temps d'arrêt de l'équipement**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-171">Click **Next** to go to the **Equipment downtime threshold** page.</span></span> <span data-ttu-id="ddae1-172">Les machines répertoriées sont celles précédemment mappées aux valeurs du signal.</span><span class="sxs-lookup"><span data-stu-id="ddae1-172">The machines listed are the machines previously mapped to signal values.</span></span> <span data-ttu-id="ddae1-173">Dans cette étape, vous devez définir un seuil pour déterminer si une machine est en panne.</span><span class="sxs-lookup"><span data-stu-id="ddae1-173">In this step, you define a threshold to determine if a machine is down.</span></span> <span data-ttu-id="ddae1-174">Par exemple, si vous définissez le seuil sur 10, Supply Chain Management génère une notification s'il n'y a pas de message de sortie de pièce d'une machine pendant 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="ddae1-174">For example, if you set the threshold to 10, Supply Chain Management generates a notification if there is no part out message from a machine for 10 minutes.</span></span>
21. <span data-ttu-id="ddae1-175">Cliquez sur **Suivant** pour accéder à la page **Activer le scénario**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-175">Click **Next** to go to the **Enable scenario** page.</span></span> <span data-ttu-id="ddae1-176">Basculez le curseur pour activer le scénario.</span><span class="sxs-lookup"><span data-stu-id="ddae1-176">Toggle the slider to enable the scenario.</span></span>
22. <span data-ttu-id="ddae1-177">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-177">Click **Finish**.</span></span>

<span data-ttu-id="ddae1-178">La configuration du scénario est terminée.</span><span class="sxs-lookup"><span data-stu-id="ddae1-178">The scenario setup is complete.</span></span> <span data-ttu-id="ddae1-179">L'intelligence IoT commencera automatiquement le traitement des messages de l'hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ddae1-179">IoT Intelligence will automatically start processing the IoT Hub messages.</span></span>

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a><span data-ttu-id="ddae1-180">Configurer le scénario **Qualité des produits** dans Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ddae1-180">Configure the **Product quality** scenario in Supply Chain Management</span></span>

<span data-ttu-id="ddae1-181">Le scénario **Qualité des produits** génère une notification si un attribut d'un article est en dehors d'une plage spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ddae1-181">The **Product quality** scenario generates a notification if an attribute of an item is outside a specified range.</span></span> <span data-ttu-id="ddae1-182">Par exemple, un capteur pourrait envoyer le poids de chaque article au hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ddae1-182">For example, a sensor could send the weight of each item to IoT Hub.</span></span> <span data-ttu-id="ddae1-183">Dans Supply Chain Management, une notification serait générée si l'article est trop lourd ou trop léger.</span><span class="sxs-lookup"><span data-stu-id="ddae1-183">In Supply Chain Management, a notification would be generated if the item was too heavy or too light.</span></span>

<span data-ttu-id="ddae1-184">Le scénario a les dépendances suivantes :</span><span class="sxs-lookup"><span data-stu-id="ddae1-184">The scenario has these dependencies:</span></span>

+ <span data-ttu-id="ddae1-185">Un ordre de fabrication doit être exécuté sur une machine mappée et produire un produit avec un attribut de lot mappé pour qu'une alerte soit déclenchée.</span><span class="sxs-lookup"><span data-stu-id="ddae1-185">A Production Order must be running on a mapped machine and producing a product with a mapped batch attribute for an alert to be triggered.</span></span>
+ <span data-ttu-id="ddae1-186">Un signal représentant l'attribut de lot doit être envoyé au hub IoT avec un nom de propriété unique.</span><span class="sxs-lookup"><span data-stu-id="ddae1-186">A signal representing the batch attribute must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="ddae1-187">Une propriété d'horodatage Unix millisecondes doit être présente dans le message du hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ddae1-187">A Unix milliseconds timestamp property must be present in the IoT Hub message.</span></span>

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a><span data-ttu-id="ddae1-188">Configurer le scénario **Retards de fabrication** dans Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ddae1-188">Configure the **Production delays** scenario in Supply Chain Management</span></span>

<span data-ttu-id="ddae1-189">Le scénario **Retards de fabrication** génère une notification si la cadence de production tombe en dessous d'une valeur seuil.</span><span class="sxs-lookup"><span data-stu-id="ddae1-189">The **Production delays** scenario generates a notification if the production throughput falls below a threshold value.</span></span> <span data-ttu-id="ddae1-190">Dans ce scénario, un signal **PartOut** est envoyé au hub IoT pour chaque article produit.</span><span class="sxs-lookup"><span data-stu-id="ddae1-190">In this scenario, a **PartOut** signal is sent to IoT Hub for each item produced.</span></span> <span data-ttu-id="ddae1-191">Dans Supply Chain Management, le retard de commande est calculé en fonction de la durée prévue de l'exécution de l'ordre de fabrication, du nombre d'articles à produire, de la durée d'exécution du travail et du nombre de signaux **PartOut** reçus.</span><span class="sxs-lookup"><span data-stu-id="ddae1-191">In Supply Chain Management, the order delay is calculated based on how long the production order is scheduled to run, how many items should be produced, how long the job has been running, and how many **PartOut** signals are received.</span></span> <span data-ttu-id="ddae1-192">Une notification de retard serait générée si le nombre de signaux **PartOut** pour le travail tombent en dessous de la valeur seuil de la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="ddae1-192">A delay notification would be generated if the number of the **PartOut** signals for the job falls below the threshold value of the expected value.</span></span>

<span data-ttu-id="ddae1-193">Le scénario a les dépendances suivantes :</span><span class="sxs-lookup"><span data-stu-id="ddae1-193">The scenario has these dependencies:</span></span>

+ <span data-ttu-id="ddae1-194">Un ordre de fabrication doit être exécuté sur une machine mappée pour qu'une alerte soit déclenchée.</span><span class="sxs-lookup"><span data-stu-id="ddae1-194">A Production Order must be running on a mapped machine for an alert to be triggered.</span></span>
+ <span data-ttu-id="ddae1-195">Un signal représentant le signal de sortie de pièce d'une machine mappée doit être envoyé au hub IoT avec un nom de propriété unique.</span><span class="sxs-lookup"><span data-stu-id="ddae1-195">A signal representing a mapped machine's part out signal must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="ddae1-196">Une propriété d'horodatage Unix millisecondes doit être présente dans le message du hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ddae1-196">A Unix milliseconds timestamp property must be present in the IoT Hub message.</span></span>

## <a name="how-to-disable-a-scenario"></a><span data-ttu-id="ddae1-197">Comment désactiver un scénario</span><span class="sxs-lookup"><span data-stu-id="ddae1-197">How to disable a scenario</span></span>

<span data-ttu-id="ddae1-198">Pour désactiver un scénario, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ddae1-198">To disable a scenario, follow these steps:</span></span>

1. <span data-ttu-id="ddae1-199">Dans Supply Chain Management, accédez à **Contrôle de la production \> Configuration \> Intelligence IoT \> Gestion des scénarios**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-199">In Supply Chain Management, navigate to **Production control \> Setup \> IoT Intelligence \> Scenario management**.</span></span>
2. <span data-ttu-id="ddae1-200">Cliquez sur **Configurer** sur le scénario.</span><span class="sxs-lookup"><span data-stu-id="ddae1-200">Click **Configure** on the scenario.</span></span>
3. <span data-ttu-id="ddae1-201">Cliquez sur **Suivant** pour accéder au dernier onglet de l'assistant.</span><span class="sxs-lookup"><span data-stu-id="ddae1-201">Click **Next** to get to the last wizard tab.</span></span>
4. <span data-ttu-id="ddae1-202">Basculez le curseur pour désactiver le scénario.</span><span class="sxs-lookup"><span data-stu-id="ddae1-202">Toggle the slider to disable the scenario.</span></span>
