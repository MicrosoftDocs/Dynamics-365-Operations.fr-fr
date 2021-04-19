---
title: Lancement automatique de l’expédition pour le cross-docking
description: Cette rubrique décrit une stratégie de cross-docking qui vous permet de lancer automatiquement un ordre de demande à l’entrepôt lorsque l’ordre de fabrication qui fournit la quantité de la demande est déclaré terminé, de sorte que la quantité soit déplacée directement depuis l’emplacement de sortie de production à l’emplacement sortant.
author: omulvad
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 1c831030659b38b52932e504f744d24d999958a5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831432"
---
# <a name="auto-release-shipment-for-cross-docking"></a>Lancement automatique de l’expédition pour le cross-docking

[!include [banner](../includes/banner.md)]

Cette rubrique décrit une stratégie de cross-docking qui vous permet de lancer automatiquement un ordre de demande à l’entrepôt lorsque l’ordre de fabrication qui fournit la quantité de la demande est déclaré terminé. De cette manière, la quantité requise pour l’achèvement de l’ordre de demande est déplacée directement entre l’emplacement de sortie de production et l’emplacement sortant.

Le cross-docking est un flux de gestion de l’entrepôt de gestion dans lequel la quantité requise pour achever un ordre de sortie est dirigée vers la zone du quai de débarquement ou de l’échelonnement de l’ordre de l’emplacement où l’ordre entrant a été reçu. (L’ordre entrant peut être une commande fournisseur, un ordre de transfert, ou un ordre de fabrication.) Bien que la fonctionnalité de cross-docking avancé prenne en charge toutes commandes d’approvisionnement et de demande, ce qui nécessite que la demande sortante soit lancée avant que l’opportunité de cross-docking soit identifiée, la fonctionnalité de lancement d’expédition automatique a les spécifications suivantes :

- Elle ne prend en charge que les ordres de fabrication comme approvisionnement, ainsi que seuls les commandes client et les ordres de transfert en tant que demande.
- L’opération de cross-docking peut être démarrée même si l’ordre de demande n’a pas été transmis à l’entrepôt avant que la réception d’approvisionnement soit enregistrée (c’est-à-dire, avant que la fabrication ait été déclarée terminée).

Cette fonctionnalité de cross-docking a deux avantages :

- Les opérations d’entrepôt peuvent ignorer l’étape de rangement de quantités de produits finis dans la zone de stockage habituelle de l’entrepôt si ces quantités seront simplement prélevées de nouveau pour accomplir l’ordre de sortie. Au lieu de cela, les quantités peuvent être déplacées une fois, entre l’emplacement sortant et un lieu d’emballage et d’expédition. Ainsi, la fonctionnalité permet de réduire le nombre de fois où le stock est manipulé et, finalement, permet d’optimiser les gains de temps et d’espace dans l’atelier de l’entrepôt.
- Les opérations d’entrepôt peuvent retarder le lancement des commandes client et des ordres de transfert vers l’entrepôt tant que la sortie des produits finis de l’ordre de fabrication associé n’est pas déclarée terminée. Cet avantage peut être particulièrement pertinent dans des environnements de production de fabrication à la commande, où les délais de fabrication tendent à être plus longs que les délais des environnements de fabrication au stock.

## <a name="prerequisites"></a>Conditions préalables

| Logiciel requis | Description |
|---|---|
| Article | L’article doit être activé pour les processus de gestion des entrepôts.<p>**Remarque :** les articles en poids variable ne peuvent pas être inclus dans les processus de cross-docking.</p> |
| Entrepôt | L’entrepôt doit être activé pour les processus de gestion des entrepôts. |
| Modèles de cross-docking | Au moins un modèle de cross-docking qui utilise la stratégie de lancement de demande **À la réception d’approvisionnement** doit être défini pour un entrepôt donné. |
| Classe de travail | Un ID classe de travail de cross-docking doit être créé pour le type d’ordre de travail **Cross-docking**. |
| Modèles de travail | Les modèles de travail du type d’ordre de travail **Cross-docking** sont requis pour créer du travail de prélèvement et de placement cross-docking. |
| Instructions d’emplacement | Les instructions de l’emplacement du type de bons de travail **Cross-docking** sont requises pour guider le travail de rangement aux emplacements où les quantités de commande client seront emballées et expédiées. |
| Marquage entre un ordre de demande et un ordre de fabrication | Le système d’entrepôt peut déclencher le lancement automatique de l’expédition d’ordre sortant et créer le travail de cross-docking à partir de l’emplacement de sortie au moment de l’action Signaler comme terminé uniquement si des commandes client et des ordres de transfert sont réservés et marqués en fonction d’un ordre de fabrication. |

## <a name="example-cross-docking-flow"></a>Exemple de flux de cross-docking

Un flux de cross-docking standard comprend les opérations principales suivantes.

1. Un preneur de commande client crée une commande client pour un produit fabriqué à la commande. Généralement, la quantité demandée n’est pas disponible et doit d’abord être produite.
2. Le preneur de commande client crée un ordre de fabrication directement à partir de la ligne de commande client. Ainsi, le preneur de commande client réserve et marque la quantité de la commande client par rapport à la quantité de l’ordre de fabrication. 

    Sinon, un gestionnaire de production spécifie que le marquage doit être mis à jour lorsque les ordres prévisionnels sont confirmés.

3. L’ordre de fabrication passe par les étapes suivantes :

    1. Un gestionnaire de production estime et lance l’ordre de fabrication. (L’estimation inclut la réservation de matières premières, et le lancement inclut le lancement à un entrepôt.)
    2. Un collaborateur de l’entrepôt commence et termine le prélèvement de matières premières entre l’emplacement de stockage et l’emplacement d’entrée en production, en fonction du travail de prélèvement de production.
    3. Un opérateur de l’atelier commence l’ordre de fabrication.
    4. Lors de la dernière opération, un opérateur utilise l’appareil mobile pour déclarer l’ordre de fabrication comme terminé.

4. Le système utilise le paramétrage pour identifier l’événement de cross-docking des deux ordres associés puis effectue les tâches suivantes :

    1. Envoi automatique de la commande client associée à un entrepôt pour créer une expédition.
    2. Création automatique du travail de cross-docking avec des instructions de prélèvement du produit fini à l’emplacement de sortie et son déplacement vers l’emplacement sortant auquel les instructions d’emplacement de cross-docking ont affecté à la commande client.
    3. Invitation d’un opérateur à terminer les travaux de cross-docking immédiatement après que l’ordre de fabrication est déclaré terminé.

5. Une fois le travail de cross-docking terminé et les quantités sont chargées sur le véhicule, un gestionnaire d’entrepôt sortant confirme l’expédition de la vente.

## <a name="example-scenario"></a>Exemple de scénario

Pour ce scénario, vous devez avoir des données de démonstration installées, et vous devez utiliser l’entreprise de données de démonstration **USMF**.

### <a name="set-up-cross-docking-that-uses-the-auto-release-shipment-feature"></a>Paramétrer le cross-docking qui utilise la fonctionnalité d’expédition de lancement automatique

#### <a name="cross-docking-template"></a>Modèle de cross-docking

1. Allez dans **Gestion des entrepôts** \> **Configuration** \> **Travail** \> **Modèles cross-docking**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Souche de N°**, saisissez **1**.
4. Dans le champ **ID du modèle de cross-docking**, entrez un nom, tel que **XDock\_RAF**.
5. Dans le champ **Stratégie de lancement de demande**, sélectionnez **À la réception d’approvisionnement**.
6. Dans le champ **Entrepôt**, entrez le numéro de l’entrepôt dans lequel vous souhaitez paramétrer le processus de cross-docking. Pour cet exemple, sélectionnez **51**.

    > [!NOTE]
    > Dès que vous sélectionnez **À la réception d’approvisionnement** comme la stratégie de lancement de demande pour le modèle, tous les autres champs de la page deviennent non disponibles. De même, vous ne pouvez pas définir de sources d’approvisionnement. Ceci se produit car le cross-docking utilisant la fonction d’expédition de lancement automatique prend en charge uniquement les ordres de fabrication comme source d’approvisionnement, et requiert qu’un marquage existent entre les commandes client et les ordres de fabrication. Si vous sélectionnez **Avant la réception d’approvisionnement** comme stratégie de lancement de la demande, les champs sous les onglets **Planification** et **Sources d’approvisionnement** sont disponibles et peuvent être modifiés.

#### <a name="work-classes"></a>Classes de travail

1. Accédez à **Gestion des entrepôts** \> **Configuration** \> **Travail** \> **Classes de travail**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **ID classe de travail**, entrez un nom, tel que **CrossDock**.
4. Dans le champ **Type d’ordre de travail**, sélectionnez **Cross-docking**.

Pour limiter les types d’emplacements où les produits finis ayant fait l’objet d’un cross-docking peut être rangés, vous pouvez spécifier un ou plusieurs types d’emplacements valides.

#### <a name="work-templates"></a>Modèles de travail

1. Allez dans **Gestion des entrepôts** \> **Configuration** \> **Travail** \> **Modèles de travail**.
2. Dans le champ **Type d’ordre de travail**, sélectionnez **Cross-docking**.
3. Sélectionnez **Nouveau**.
4. Dans le champ **Souche de N°**, saisissez **1**.
5. Dans le champ **Modèle de travail**, entrez un nom, tel que **CrossDock\_51**.
6. Sélectionnez **Enregistrer**.
7. Dans la section **Détails du modèle de travail**, sélectionnez **Nouveau**.
8. Pour la nouvelle ligne, dans le champ **Type de travail**, sélectionnez **Prélever**. Dans le champ **ID classe de travail**, sélectionnez **CrossDock**.
9. Sélectionnez **Nouveau**.
10. Pour la nouvelle ligne, dans le champ **Type de travail**, sélectionnez **Ranger**. Dans le champ **ID classe de travail**, sélectionnez **CrossDock**.

#### <a name="location-directives"></a>Instructions d’emplacement

Un processus de rangement standard pour les produits finis requiert une instruction d’emplacement de **Rangement** pour guider le mouvement des quantités de production prélevées à un espace de stockage normal. De même, vous devez paramétrer une instruction d’emplacement de **Rangement** cross-docking pour guider le travail de rangement de la quantité terminée à un emplacement de sortie désigné qui dessert l’expédition de la commande client associée.

Pour le cross-docking, comme le rangement régulier des produits finis, vous ne devez pas créer de directive d’emplacement pour l’action de travail de prélèvement, car l’emplacement de sortie est fourni. En outre, cet emplacement de sortie doit être paramétré comme l’emplacement par défaut de sortie sur l’un des enregistrements associés à une ressource (c’est-à-dire, la ressource, la relation de groupe de ressources, ou le groupe de ressources) ou comme l’emplacement de produits finis de production par défaut pour un entrepôt.

1. Allez dans **Gestion des entrepôts** \> **Configuration** \> **Instructions d’emplacements**.
2. Dans le champ **Type d’ordre de travail**, sélectionnez **Cross-docking**.
3. Sélectionnez **Nouveau**.
4. Dans le champ **Souche de N°**, saisissez **1**.
5. Dans le champ **Nom**, entrez un nom, tel que **Baydoor**.
6. Dans le champ **Type de travail**, sélectionnez **Put**.
7. Dans le champ **Site**, sélectionnez **5**.
8. Dans le champ **Entrepôt**, sélectionnez **51**.
9. Dans l’organisateur **Lignes**, sélectionnez **Nouveau**.
10. Dans le champ **Quantité d’arrivée**, entrez la quantité maximale de la plage, comme **1000000**.
11. Sélectionnez **Enregistrer**.
12. Dans l’organisateur **Actions d’instructions d’emplacement**, sélectionnez **Nouveau**.
13. Dans le champ **Nom**, entrez un nom, tel que **Baydoor**.
14. Sélectionnez **Enregistrer**.
15. Vous pouvez utiliser l’installation de requête standard pour limiter les emplacements de rangement à un ou plusieurs emplacements spécifiques. Sélectionnez **Modifier la requête**, puis sélectionnez **51** comme critère pour le champ **Entrepôt** dans la table **Emplacements**.

### <a name="cross-dock-finished-goods-to-the-outbound-location"></a>Cross-docking des produits finis avec l’emplacement sortant

Pour que la quantité de produits finis fasse l’objet d’un cross-docking à l’emplacement sortant de la commande client associée, procédez comme suit.

1. Accédez à **Ventes et marketing** \> **Commandes client** \> **Toutes les commandes client**.
2. Sélectionnez **Nouveau**.
3. Pour l’en-tête de commande client, sélectionnez le compte client **US-001** et un entrepôt qui est défini pour le cross-docking et utilise la fonctionnalité d’expédition de lancement automatique.
4. Ajoutez une ligne pour un produit fini, puis entrez **10** comme quantité.
5. Dans la section **Lignes de commande client**, sélectionnez **Produit et approvisionnement** \> **Ordre de fabrication**.
6. Dans la boîte de dialogue **Créer un ordre de fabrication**, examinez les valeurs par défaut, puis sélectionnez **Créer**. Un nouvel ordre de fabrication est créé et lié à la commande client (c’est-à-dire, il est réservé et marqué).
7. Facultatif : Modifiez la valeur du champ **Quantité** afin qu’il soit supérieur à la valeur requise pour honorer la commande client. Lorsque la quantité de production est déclarée terminée, le système crée le travail de cross-docking pour la quantité et le travail de rangement marqués pour la quantité restante, selon la procédure habituelle de gestion du rangement du produit fini.

    Comme indiqué précédemment, un marquage doit exister entre la commande client et l’ordre de fabrication. Sinon, le cross-docking ne fonctionne pas. Un marquage peut être créé de plusieurs manières :

    - Le système peut créer automatiquement le marquage dans les situations suivantes :

        - L’"ordre de fabrication est créé manuellement directement à partir de la ligne de commande client (voir étape 6).
        - Les ordres de fabrication prévisionnels sont confirmés, et le champ **Mettre à jour le marquage** est défini sur **Standard**.

    - L’utilisateur peut créer manuellement le marquage en ouvrant la page **Marquage** de la ligne de commande de la demande.

    > [!NOTE]
    > Un marquage ne peut pas être créé manuellement pour les articles paramétrés pour utiliser des moyennes standard et pondérées comme modèles de stock.

8. Dans la page **Ordre de fabrication**, dans le volet Actions, sous l’onglet **Ordre de fabrication**, dans le groupe **Traitement**, sélectionnez **Estimer**, puis **OK**. La commande est estimé, et la quantité de matières premières est réservée pour la production.
9. Dans le volet Actions, sous l’onglet **Ordre de fabrication**, dans le groupe **Traitement**, sélectionnez **Lancer**, puis **OK**. Le travail de prélèvement à l’entrepôt est créé pour les matières premières.
10. Ouvrez et vérifiez le travail. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Général**, cliquez sur **Détails du travail**. Prenez note de l’ID du travail.
11. Connectez-vous à l’application mobile Gestion des entrepôts pour exécuter le travail dans l’entrepôt 51.
12. Accédez à **Production** \> **Prélèvement de la production**.
13. Entrez l’ID travail pour commencer et effectuer le prélèvement de matières premières. 

    Une fois le travail déclaré comme terminé, la quantité de matières premières est disponible à l’emplacement d’entrée en production (**005** dans les données de démonstration USMF), et l’exécution de l’ordre de fabrication peut démarrer.

14. Dans la page **Ordre de fabrication**, dans le volet Actions, sous l’onglet **Ordre de fabrication**, dans le groupe **Traitement**, sélectionnez **Démarrer**, puis **OK**.
15. Dans l’application, accédez à **Production** \> **Déclaré comme terminé et rangé**.
16. Dans le champ **ID prod**, entrez le numéro d’ordre de fabrication et d’autres détails obligatoires, puis sélectionnez **OK**.

Notez que les événements suivants surviennent :

- Le lancement vers un entrepôt est déclenché pour la commande client liée.
- Selon le lancement, le travail d’expédition et de cross-docking est créé. Ce travail guide l’opérateur pour prélever les quantités requises pour exécuter la ligne de commande client et pour les mettre à l’emplacement sortant spécifié dans l’instruction de l’entrepôt de cross-docking.
- Si la quantité de l’ordre de fabrication est supérieure à la quantité requise par la commande client, un travail de rangement normal est créé. Ce travail guide l’opérateur à prélever la quantité de produits finis restant après cross-docking et la déplace vers le stockage habituel, en fonction de l’instruction sur l’emplacement.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]