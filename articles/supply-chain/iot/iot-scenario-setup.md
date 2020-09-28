---
title: Configuration d’un scénario pour l’intelligence IoT
description: Cette rubrique explique comment configurer des scénarios pour l’intelligence IoT dans Microsoft Dynamics 365 Supply Chain Management.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d1deaa2130b63272da39a42315c6a1bc4b7ccb8a
ms.sourcegitcommit: 8adc65e26d78e229271eb427659a87ee5f371319
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "3814057"
---
# <a name="scenario-setup-for-iot-intelligence"></a>Configuration d’un scénario pour l’intelligence IoT

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment configurer des scénarios pour l’intelligence IoT dans Microsoft Dynamics 365 Supply Chain Management. Avant de paramétrer les scénarios, vous devez [paramétrer Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).

Dans cette rubrique, vous allez configurer le scénario **Temps d’arrêt de l’équipement** pour générer une notification dans Supply Chain Management lorsqu’une machine tombe en panne. La rubrique montre également comment configurer le scénario **Qualité des produits** afin qu’une notification soit générée si un attribut d’un élément est en dehors d’une plage spécifiée, et comment configurer le scénario **Délais de production** afin qu’une notification soit générée si le débit de production tombe en dessous d’une valeur seuil.

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>Configurer le scénario Temps d’arrêt de l’équipement dans Supply Chain Management

Le scénario **Temps d’arrêt de l’équipement** mappe un signal **PartOut** (sortie de pièce) à un seuil d’alerte machine. La machine est surveillée uniquement lorsqu’elle est sélectionnée pour le scénario et configurée pour **s’exécuter** dans Supply Chain Management. Si le temps écoulé depuis le dernier signal **PartOut** reçu par la machine est supérieur au seuil d’alerte, la notification **Machine en panne** est déclenchée. Si la machine est toujours en marche, une notification **Machine en marche** est déclenchée lorsque le signal **PartOut** suivant est reçu. Si une machine s’arrête pendant 30 minutes, une nouvelle notification **Machine en panne** est déclenchée.

Le scénario **Temps d’arrêt de l’équipement** a les dépendances suivantes :

+ Une alerte peut être déclenchée uniquement si un ordre de production s’exécute sur une machine mappée.
+ Un signal qui représentant le signal **PartOut** d’une machine mappée doit être envoyé au hub IoT et un nom de propriété unique doit être inclus.
+ Une propriété **horodatage** UNIX, où la valeur est exprimée en millisecondes (ms), doit être présente dans le message du hub Azure IoT.

Procédez comme suit pour configurer le scénario.

1. Connectez-vous à Supply Chain Management.
2. Activez l’indicateur de fonctionnalité Intelligence IoT. Pour plus d’informations, voir [Vue d’ensemble de la gestion des fonctionnalités](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
3. Configurez les mesures. Pour plus d’informations, voir [Comment configurer les mesures](iot-metrics-setup.md#configure-metrics).
4. Aller à **Contrôle de production \> Configurer \> Intelligence IoT \> Gestion de scénario**.
6. Sur la vignette **Temps d’arrêt de l’équipement**, sélectionnez **Configurer** pour ouvrir l’assistant de configuration.

   La première page de l’assistant de configuration est la page **Définition du schéma du capteur d’équipement**. Sur cette page, votre objectif est de configurer le schéma dans Supply Chain Management afin qu’il corresponde au format JavaScript Object Notation (JSON) des messages du hub IoT. Plusieurs schémas de message peuvent être définis. Pour plus d’informations, voir [Formats de schémas des messages du hub IoT](iot-schema-format.md). Dans cet exemple, la charge utile du message contient un lot de messages ayant le format suivant.

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

7. Ajoutez une ligne à la table et définissez les valeurs suivantes :

    1. Définissez le champ **Nom du schéma** sur **ID**.
    2. Définissez le champ **Chemin d’accès du schéma** sur **/charge utile\[\*\]/id**.
    3. Définissez le champ **Description** sur **ID du message**.

8. Ajoutez une autre ligne à la table et définissez les valeurs suivantes :

    1. Définissez le champ **Nom du schéma** sur **Horodatage**.
    2. Définissez le champ **Chemin d’accès du schéma** sur **/charge utile\[\*\]/horodatage**.
    3. Définissez le champ **Description** sur **Horodatage du message**.

9. Ajoutez une autre ligne à la table et définissez les valeurs suivantes :

    1. Définissez le champ **Nom du schéma** sur **Valeur**.
    2. Définissez le champ **Chemin d’accès du schéma** sur **/charge utile\[\*\]/valeur**.
    3. Définissez le champ **Description** sur **Valeur du message**.

    > [!NOTE]
    > Il n’est pas nécessaire de définir toutes les propriétés du message. Définissez uniquement les propriétés dont vous avez besoin. Dans les étapes précédentes, vous n’avez pas créé de ligne pour **Horodatage racine**. Le chemin de l’**Horodatage racine** serait **/horodatage**.

10. Cliquez sur **Suivant** pour accéder à la page **Carte du schéma du capteur d’équipement**.
11. Dans la ligne pour **ID de ressource d’équipement**, dans le champ **Nom du schéma**, sélectionnez **ID**.
12. Dans la ligne pour **Heure UTC**, dans le champ **Nom du schéma**, sélectionnez **Horodatage**.
13. Dans la ligne pour **Signal produit par la pièce**, dans le champ le **Nom du schéma**, sélectionnez **Valeur**.
14. Cliquez sur **Suivant** pour accéder à la page **Configuration de l’ID de ressource d’équipement**.
15. Suivez ces étapes pour mapper les valeurs du message du hub IoT aux ressources de Supply Chain Management :

    1. Dans la table **Valeurs des données de signal**, ajoutez une nouvelle ligne. Dans le champ **Valeur**, entrez **IoTInt.Machine1225.PartOut**. Cette valeur provient de la propriété **id** JSON dans le message du hub IoT.
    2. Sélectionnez **Enregistrer**.
    3. Dans le tableau **Mise en correspondance des enregistrements commerciaux**, sélectionnez **Nouveau**. Une valeur par défaut pour le champ **Type d’enregistrement commercial** est renseignée automatiquement et vous n’avez pas besoin de la modifier.
    4. Dans le champ **Enregistrement commercial**, sélectionnez la ressource de la machine Supply Chain Management à partir de laquelle cette valeur de signal est envoyée.
    5. Sélectionnez **Enregistrer**.
    6. Répétez ces étapes pour ajouter une nouvelle mise en correspondance d’enregistrement commercial pour **Machine1226**. Vous pouvez mapper plusieurs valeurs de données de signal à un seul enregistrement dans Supply Chain Management.

16. Utilisez la colonne **Sélectionné** pour sélectionner les machines à traiter. Vous n’avez pas à définir toutes les valeurs de signal et vous n’avez pas à sélectionner toutes les machines.
17. Cliquez sur **Suivant** pour accéder à la page **Configuration du signal produit par la pièce**.
18. Dans la table **Valeurs des données du signal**, ajoutez une ligne et définissez le champ **Valeur** sur **True**. Cette valeur provient de la propriété **valeur** JSON dans le message du hub IoT. Vous pouvez ajouter autant de valeurs que nécessaire pour votre scénario.
19. Sélectionnez **Enregistrer**.
20. Cliquez sur **Suivant** pour accéder à la page **Seuil de temps d’arrêt de l’équipement**. Les machines répertoriées sont celles précédemment mappées aux valeurs du signal. Sur cette étape, vous allez définir un seuil pour déterminer si une machine est en panne. Par exemple, si vous définissez le seuil sur **10**, Supply Chain Management génèrera une notification s’il n’y a pas de signal **PartOut** reçu d’une machine pendant 10 minutes.
21. Cliquez sur **Suivant** pour accéder à la page **Activer le scénario**. Définissez l’option pour activer le scénario.
22. Sélectionnez **Terminer**.

La configuration du scénario est maintenant terminée. L’intelligence IoT commencera automatiquement le traitement des messages du hub IoT.

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>Configurer le scénario Qualité des produits dans Supply Chain Management

Le scénario **Qualité des produits** génère une notification si un attribut d’un article est en dehors d’une plage spécifiée. Par exemple, un capteur envoie le poids de chaque article au hub IoT. Si un article est trop lourd ou trop léger, une notification est générée dans Supply Chain Management.

Le scénario **Qualité du produit** a les dépendances suivantes :

+ Une alerte peut être déclenchée si un ordre de fabrication s’exécute sur une machine mappée et produit un produit avec un attribut de lot mappé.
+ Un signal représentant l’attribut de lot doit être envoyé au hub IoT et un nom de propriété unique doit être inclus.
+ Une propriété **horodatage** UNIX, où la valeur est exprimée en millisecondes (ms), doit être présente dans le message du hub Azure IoT.

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>Configurer le scénario Retards de fabrication dans Supply Chain Management

Le scénario **Retards de fabrication** génère une notification si la cadence de production tombe en dessous d’une valeur seuil. Dans ce scénario, un signal **PartOut** est envoyé au hub IoT pour chaque article qui est produit. Dans Supply Chain Management, le retard de commande est calculé en fonction de la durée prévue de l’exécution de l’ordre de fabrication, du nombre d’articles à produire, de la durée d’exécution du travail et du nombre de signaux **PartOut** reçus. Une notification de retard est générée si le nombre de signaux **PartOut** pour le travail tombent en dessous de la valeur seuil de la valeur attendue.

Le scénario **Retards de fabrication** a les dépendances suivantes :

+ Une alerte peut être déclenchée uniquement si un ordre de production s’exécute sur une machine mappée.
+ Un signal qui représentant le signal **PartOut** d’une machine mappée doit être envoyé au hub Azure IoT et un nom de propriété unique doit être inclus.
+ Une propriété **horodatage** UNIX, où la valeur est exprimée en millisecondes (ms), doit être présente dans le message du hub Azure IoT.

## <a name="disable-a-scenario"></a>Désactiver un scénario

Pour désactiver un scénario, procédez comme suit.

1. Dans Supply Chain Management, accédez à **Contrôle de la production \> Configuration \> Intelligence IoT \> Gestion des scénarios**.
2. Sur la vignette du scénario, sélectionnez **Configurer**.
3. Cliquez sur **Suivant** pour accéder à la dernière page de l’Assistant.
4. Définissez l’option sur désactiver le scénario.
