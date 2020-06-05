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
# <a name="scenario-setup-for-iot-intelligence"></a>Configuration d'un scénario pour l'intelligence IoT

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment configurer un scénario dans Supply Chain Management pour l'intelligence IoT. Avant de pouvoir configurer des scénarios, vous devez [configurer LCS](iot-lcs-setup.md).

Dans cette rubrique, vous allez configurer le scénario **Temps d'arrêt de l'équipement** pour générer une notification dans Supply Chain Management lorsqu'une machine tombe en panne.

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>Configurer le scénario **Temps d'arrêt de l'équipement** dans Supply Chain Management

Le scénario **Temps d'arrêt de l'équipement** mappe un signal de sortie de pièce à un seuil d'alerte machine. La machine est surveillée uniquement lorsqu'elle est sélectionnée pour le scénario et est configurée pour s'exécuter dans Supply Chain Management. Si le temps écoulé depuis le dernier signal PartOut reçu par la machine est supérieur au seuil d'alerte, la notification **Machine en panne** est déclenchée. Si la machine est toujours en marche, lorsque le signal **PartOut** suivant est envoyé, la notification **Machine en marche** est déclenchée. Si une machine s'arrête pendant 30 minutes, une nouvelle notification **Machine en panne** est déclenchée.

Le scénario **Temps d'arrêt de l'équipement** a les dépendances suivantes :

+ Un ordre de fabrication doit être exécuté sur une machine mappée pour qu'une alerte soit déclenchée.
+ Un signal représentant le signal de sortie de pièce d'une machine mappée doit être envoyé au hub IoT avec un nom de propriété unique.
+ Une propriété d'horodatage Unix millisecondes doit être présente dans le message du hub IoT.

Procédez comme suit pour configurer le scénario :

1. Connectez-vous à Supply Chain Management.
2. Activez l'indicateur de fonctionnalité Intelligence IoT. Pour plus d'informations, voir [Vue d'ensemble de la gestion des fonctionnalités](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
3. Configurez les mesures. Pour plus d'informations, voir [Comment configurer les mesures](iot-metrics-setup.md#configure-metrics).
4. Accédez à **Contrôle de production**.
5. Accédez à **Configuration \> Intelligence IoT \> Gestion des scénarios**.
6. Cliquez sur **Configurer** sur l'onglet **Temps d'arrêt de l'équipement**. L'assistant de configuration commence par la page **Définition du schéma du capteur d'équipement**. L'objectif ici est de configurer le schéma dans Supply Chain Management pour qu'il corresponde au format JSON des messages IoT. Plusieurs schémas de message peuvent être définis. Pour plus d'informations, voir [Formats de schémas de message pour hub IoT](iot-schema-format.md). Dans cet exemple, la charge utile du message contient un lot de messages avec ce format :

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

7. Ajoutez une ligne au tableau.

    1. Définissez le **Nom du schéma** sur **ID**.
    2. Définissez le **Chemin d'accès du schéma** sur **/charge utile[\*]/id**.
    3. Définissez la **Description** sur **ID du message**.

8. Ajoutez une ligne au tableau.

    1. Définissez le **Nom du schéma** sur **Horodatage**.
    2. Définissez le **Chemin d'accès du schéma** sur **/charge utile[\*]/horodatage**.
    3. Définissez la **Description** sur **Horodatage du message**.

9. Ajoutez une ligne au tableau.

    1. Définissez le **Nom du schéma** sur **Valeur**.
    2. Définissez le **Chemin d'accès du schéma** sur **/charge utile[\*]/valeur**.
    3. Définissez la **Description** sur **Valeur du message**.

    Vous n'avez pas besoin de définir toutes les propriétés du message, uniquement celles dont vous avez besoin. Dans cet exemple, vous n'avez pas créé de ligne pour **Horodatage racine**. Le chemin pour **Horodatage racine** serait **/horodatage**.
  
10. Cliquez sur **Suivant** pour accéder à la page **Carte du schéma du capteur d'équipement**.
11. Dans la ligne pour **ID de ressource d'équipement** définissez le **Nom du schéma** sur **ID**. Les valeurs valides sont affichées dans un tableau déroulant.
12. Dans la ligne pour **Heure UTC** définissez le **Nom du schéma** sur **Horodatage**. Les valeurs valides sont affichées dans un tableau déroulant.
13. Dans la ligne pour **Signal produit par la pièce**, définissez le **Nom du schéma** sur **Valeur**. Les valeurs valides sont affichées dans un tableau déroulant.
14. Cliquez sur **Suivant** pour accéder à la page **Configuration de l'ID de ressource d'équipement**.
15. Dans cette étape, vous devez mapper les valeurs de message hub IoT aux ressources de Supply Chain Management.

    1. Dans la table **Valeurs des données du signal**, ajoutez une nouvelle ligne et entrez **IoTInt.Machine1225.PartOut** dans la colonne **Valeur**. La valeur **IoTInt.Machine1225.PartOut** provient de la propriété **id** du JSON dans le message du hub IoT.
    2. Cliquez sur **Enregistrer**.
    3. Dans le tableau **Mise en correspondance des enregistrements commerciaux**, cliquez sur **Nouveau**. La valeur par défaut pour le **Type d'enregistrement commercial** est renseignée automatiquement et vous n'avez pas besoin de la modifier.
    4. Dans la colonne **Enregistrement commercial**, sélectionnez la ressource de la machine Supply Chain Management à partir de laquelle cette valeur de signal est envoyée.
    5. Cliquez sur **Enregistrer**.
    6. Répétez ces étapes en ajoutant une nouvelle mise en correspondance d'enregistrement commercial pour **Machine1226**. Vous pouvez mapper plusieurs valeurs de données de signal à un seul enregistrement dans Supply Chain Management.

16. Utilisez la colonne **Sélectionné** pour choisir les machines à traiter. Vous n'avez pas à définir toutes les valeurs de signal et vous n'avez pas à sélectionner toutes les machines.
17. Cliquez sur **Suivant** pour accéder à la page **Configuration du signal produit par la pièce**.
18. Dans le tableau **Valeurs des données du signal**, ajoutez une ligne et définissez **Valeur** sur **True**. La valeur **True** provient de la propriété **valeur** de JSON dans le message du hub IoT. Vous pouvez ajouter autant de valeurs que nécessaire pour votre scénario.
19. Cliquez sur **Enregistrer**.
20. Cliquez sur **Suivant** pour accéder à la page **Seuil de temps d'arrêt de l'équipement**. Les machines répertoriées sont celles précédemment mappées aux valeurs du signal. Dans cette étape, vous devez définir un seuil pour déterminer si une machine est en panne. Par exemple, si vous définissez le seuil sur 10, Supply Chain Management génère une notification s'il n'y a pas de message de sortie de pièce d'une machine pendant 10 minutes.
21. Cliquez sur **Suivant** pour accéder à la page **Activer le scénario**. Basculez le curseur pour activer le scénario.
22. Cliquez sur **Terminer**.

La configuration du scénario est terminée. L'intelligence IoT commencera automatiquement le traitement des messages de l'hub IoT.

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>Configurer le scénario **Qualité des produits** dans Supply Chain Management

Le scénario **Qualité des produits** génère une notification si un attribut d'un article est en dehors d'une plage spécifiée. Par exemple, un capteur pourrait envoyer le poids de chaque article au hub IoT. Dans Supply Chain Management, une notification serait générée si l'article est trop lourd ou trop léger.

Le scénario a les dépendances suivantes :

+ Un ordre de fabrication doit être exécuté sur une machine mappée et produire un produit avec un attribut de lot mappé pour qu'une alerte soit déclenchée.
+ Un signal représentant l'attribut de lot doit être envoyé au hub IoT avec un nom de propriété unique.
+ Une propriété d'horodatage Unix millisecondes doit être présente dans le message du hub IoT.

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>Configurer le scénario **Retards de fabrication** dans Supply Chain Management

Le scénario **Retards de fabrication** génère une notification si la cadence de production tombe en dessous d'une valeur seuil. Dans ce scénario, un signal **PartOut** est envoyé au hub IoT pour chaque article produit. Dans Supply Chain Management, le retard de commande est calculé en fonction de la durée prévue de l'exécution de l'ordre de fabrication, du nombre d'articles à produire, de la durée d'exécution du travail et du nombre de signaux **PartOut** reçus. Une notification de retard serait générée si le nombre de signaux **PartOut** pour le travail tombent en dessous de la valeur seuil de la valeur attendue.

Le scénario a les dépendances suivantes :

+ Un ordre de fabrication doit être exécuté sur une machine mappée pour qu'une alerte soit déclenchée.
+ Un signal représentant le signal de sortie de pièce d'une machine mappée doit être envoyé au hub IoT avec un nom de propriété unique.
+ Une propriété d'horodatage Unix millisecondes doit être présente dans le message du hub IoT.

## <a name="how-to-disable-a-scenario"></a>Comment désactiver un scénario

Pour désactiver un scénario, procédez comme suit :

1. Dans Supply Chain Management, accédez à **Contrôle de la production \> Configuration \> Intelligence IoT \> Gestion des scénarios**.
2. Cliquez sur **Configurer** sur le scénario.
3. Cliquez sur **Suivant** pour accéder au dernier onglet de l'assistant.
4. Basculez le curseur pour désactiver le scénario.
