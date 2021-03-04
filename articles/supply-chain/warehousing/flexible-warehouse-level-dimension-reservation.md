---
title: Politique de réservation de dimension flexible au niveau de l’entrepôt
description: Cette rubrique décrit la politique de réservation de stock qui permet aux entreprises qui vendent des produits suivis par lots et exécutent leur logistique en tant qu’opérations activées par WMS de réserver des lots spécifiques pour les commandes client, même si la hiérarchie de réservation associée aux produits interdit la réservation de lots spécifiques.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReservationHierarchy, WHSWorkTrans, WHSWorkInventTrans, WHSInventTableReservationHierarchy, WHSReservationHierarchyCreate, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: b9bd4e67ed64218f9c4ac87bd143f73680af9ac4
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428216"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a>Politique de réservation de dimension flexible au niveau de l’entrepôt

[!include [banner](../includes/banner.md)]

Lorsqu’une hiérarchie de réservation de stock de type « Batch-below\[location\] » est associée aux produits, les entreprises qui vendent des produits suivis par lots et gèrent leur logistique en tant qu’opérations activées pour Microsoft Dynamics 365 Warehouse Management System (WMS) ne peuvent pas réserver des lots spécifiques de ces produits pour les commandes client.

De la même manière, des contenants spécifiques ne peuvent pas être réservés pour des produits sur des commandes client lorsque ces produits sont associés à la hiérarchie de réservation par défaut.

Cette rubrique décrit la politique de réservation de stock qui permet à ces entreprises de réserver des lots ou des contenants spécifiques, même lorsque les produits sont associés à une hiérarchie de réservation « Batch-below\[location\] ».

## <a name="inventory-reservation-hierarchy"></a>Hiérarchie de réservation du stock

Cette section résume la hiérarchie de réservation de stock existante.

La hiérarchie de réservation de stock impose que, en ce qui concerne les dimensions de stockage, l’ordre à la demande porte les dimensions obligatoires du site, de l’entrepôt et du statut du stock, tandis que la logique d’entrepôt est responsable d’affecter un emplacement aux quantités demandées et de réserver l’emplacement. En d’autres termes, lors des interactions entre la commande à la demande et les opérations de l’entrepôt, la commande à la demande devrait indiquer d’où la commande doit être expédiée (c’est-à-dire quel site et quel entrepôt). L’entrepôt s’appuie ensuite sur sa logique pour trouver la quantité requise dans les locaux de l’entrepôt.

Cependant, pour refléter le modèle opérationnel de l’entreprise, les dimensions de suivi (numéros de lot et de série) sont soumises à plus de flexibilité. Une hiérarchie de réservation de stock peut prendre en charge des scénarios dans lesquels les conditions suivantes s’appliquent :

- L’entreprise s’appuie sur ses opérations d’entrepôt pour gérer le prélèvement des quantités qui ont des numéros de lot ou de série, après que les quantités ont été trouvées dans l’espace de stockage de l’entrepôt. Ce modèle est souvent appelé *Batch-below\[location\]*. Il est généralement utilisé lorsque l’identification du lot ou du numéro de série d’un produit n’est pas importante pour les clients qui adressent la demande à l’entreprise vendeuse.
- Si les numéros de lot ou de série font partie de la spécification de commande d’un client et qu’ils sont enregistrés sur la commande à la demande, les opérations d’entrepôt qui trouvent les quantités dans l’entrepôt sont limitées par les numéros spécifiques demandés et ne sont pas autorisées à les modifier. Ce modèle est souvent appelé *Batch-above\[location\]*.

Dans ces scénarios, la difficulté est qu’une seule hiérarchie de réservation de stock peut être affectée à chaque produit lancé. Par conséquent, pour que le WMS gère les articles suivis, une fois que l’affectation de la hiérarchie a déterminé le moment où le numéro de lot ou de série doit être réservé (soit lors de la prise de la commande à la demande, soit pendant le travail de prélèvement en entrepôt), ce délai ne peut pas être modifié sur une base ad hoc.

## <a name="flexible-reservation-for-batch-tracked-items"></a>Réservation flexible pour les articles suivis par lots

### <a name="business-scenario"></a>Scénario d’entreprise

Dans ce scénario, une entreprise utilise une stratégie de stock où les produits finis sont suivis par numéros de lot. Cette entreprise utilise également la charge de travail WMS. Étant donné que cette charge de travail possède une logique bien établie pour la planification et l’exécution des opérations de prélèvement et d’expédition en entrepôt des articles activés par lots, la plupart des articles finis sont associés à une hiérarchie de réservation de stock « Batch-below\[location\] ». L’avantage de ce type de configuration opérationnelle est que les décisions (qui sont en fait des décisions de réservation) concernant les lots à prélever et où les placer dans l’entrepôt sont reportées jusqu’au début des opérations de prélèvement de l’entrepôt. Elles ne sont pas prises lors de la commande du client.

Si la hiérarchie de réservation « Batch-below\[location\] » sert bien les objectifs commerciaux de la société, de nombreux clients établis ont souvent besoin du même lot qu’ils ont précédemment acheté lorsqu’ils commandent des produits. Par conséquent, l’entreprise doit viser la flexibilité dans la façon dont les règles de réservation par lots sont traitées, de sorte que, selon la demande des clients pour le même article, les comportements suivants puissent se produire :

- Un numéro de lot peut être enregistré et réservé lorsque la commande est prise par le processeur de vente, et ne peut pas être modifié pendant les opérations de l’entrepôt et / ou pris par d’autres demandes. Ce comportement garantit que le numéro de lot qui a été commandé est expédié au client.
- Si le numéro de lot n’est pas important pour le client, les opérations de l’entrepôt peuvent déterminer un numéro de lot pendant le travail de prélèvement, après l’enregistrement et la réservation de la commande client.

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a>Permettre la réservation d’un lot spécifique à la commande client

Pour permettre la flexibilité souhaitée dans le comportement de réservation de lots pour les articles associés à une hiérarchie de réservation de stock « Batch-below\[location\] », les gestionnaires de stock doivent sélectionner la case à cocher **Autoriser la réservation à la commande** pour le niveau **Numéro du lot** sur la page **Hiérarchies de réservation du stock**.

![Rendre flexible la hiérarchie de réservation du stock](media/Flexible-inventory-reservation-hierarchy.png)

Quand le niveau **Numéro du lot** dans la hiérarchie est sélectionné, toutes les dimensions au-dessus de ce niveau et jusqu’à l’**Emplacement** seront automatiquement sélectionnées. (Par défaut, toutes les dimensions au-dessus de l’**Emplacement** sont présélectionnés.) Ce comportement reflète la logique selon laquelle toutes les dimensions dans la plage entre le numéro de lot et l’emplacement sont également automatiquement réservées après avoir réservé un numéro de lot spécifique sur la ligne de commande.

> [!NOTE]
> La case à cocher **Autoriser la réservation à la commande** s’applique uniquement aux niveaux de hiérarchie de réservation inférieurs à la dimension d’emplacement de l’entrepôt.
>
> **Numéro du lot** et **Contenant** sont les seuls niveaux de la hiérarchie qui sont ouverts à la politique de réservation flexible. En d’autres termes, vous ne pouvez pas activer la case à cocher **Autoriser la réservation sur ordre de la demande** pour le niveau **Emplacement** ou **Numéro de série**.
>
> Si votre hiérarchie de réservation comprend la dimension du numéro de série (qui doit toujours être inférieure au niveau **Numéro du lot** et si vous avez activé la réservation spécifique au lot pour le numéro de lot), le système continuera à gérer les opérations de réservation et de prélèvement de numéro de série, en fonction des règles qui s’appliquent à la politique de réservation « Serial-below\[location\] ».

À tout moment, vous pouvez autoriser une réservation spécifique au lot pour une hiérarchie de réservation « Batch-below\[location\] » existante dans votre déploiement. Cette modification n’affectera pas les réservations et les travaux d’entrepôt ouverts créés avant la modification. Cependant, la case à cocher **Autoriser la réservation à la commande** ne peut pas être désactivée si des transactions de stock problématiques de type **Commandé réservé**, **Physique réservé**, ou **Commandé** existent pour un ou plusieurs éléments associés à cette hiérarchie de réservation.

> [!NOTE]
> Si la hiérarchie de réservation existante d’un article n’autorise pas la spécification du lot sur la commande, vous pouvez le réaffecter à une hiérarchie de réservation qui autorise la spécification du lot, à condition que la structure de niveau de hiérarchie soit la même dans les deux hiérarchies. Utilisez la foction **Modifier la hiérarchie de réservation pour les articles** pour effectuer la réaffectation. Cette modification peut être pertinente lorsque vous souhaitez empêcher la réservation de lots flexible pour un sous-ensemble d’articles suivis par lots, mais l’autorisez pour le reste du portefeuille de produits.

Que vous ayez sélectionné ou non la case à cocher **Autoriser la réservation à la commande**, si vous ne souhaitez pas réserver un numéro de lot spécifique pour l’article sur une ligne de commande, la logique des opérations d’entrepôt par défaut qui est valide pour une hiérarchie de réservation « Batch-below\[location\] » s’applique toujours.

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a>Réserver un numéro de lot spécifique pour une commande client

Après qu’une hiérarchie de réservation du stock « Batch-below\[location\] » pour un article suivi par lot est configurée pour permettre la réservation de numéros de lot spécifiques sur les commandes client, les processeurs de commande client peuvent prendre des commandes client pour le même article de l’une des manières suivantes, selon la demande du client :

- **Entrez les détails de la commande sans spécifier de numéro de lot** - Cette approche doit être utilisée lorsque la spécification du lot du produit n’est pas importante pour le client. Tous les processus existants associés à la gestion d’une commande de ce type dans le système restent inchangés. Aucune mesure supplémentaire n’est requise de la part des utilisateurs.
- **Entrer les détails de la commande et réserver un numéro de lot spécifique** - Cette approche doit être utilisée lorsque le client demande un lot spécifique. En règle générale, les clients demandent un lot spécifique lorsqu’ils réorganisent un produit qu’ils ont précédemment acheté. Ce type de réservation spécifique au lot est appelé *réservation confirmée par la commande*.

L’ensemble de règles suivant est valide lorsque des quantités sont traitées et qu’un numéro de lot est validé pour une commande spécifique :

- Pour autoriser la réservation d’un numéro de lot spécifique pour un article selon la politique de réservation « Batch-below\[location\] », le système doit réserver toutes les dimensions jusqu’à l’emplacement. Cette plage inclut généralement la dimension du contenant.
- Les directives d’emplacement ne sont pas utilisées lorsque le travail de prélèvement est créé pour une ligne de vente qui utilise la réservation par lots validée par la commande.
- Pendant le traitement en magasin des travaux pour les lots validés par la commande, ni l’utilisateur ni le système ne sont autorisés à modifier le numéro de lot. (Ce traitement inclut la gestion des exceptions.)

L’exemple suivant montre le flux de bout en bout.

## <a name="example-scenario-batch-number-allocation"></a>Exemple de scénario : affectation de numéros de lot

Pour cet exemple, il convient d’avoir des données de démonstration installées, et vous utiliserez l’exemple d’entreprise **USMF**.

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a><a name="Example-batch-allocation"></a>Configurer une hiérarchie de réservation de stock pour autoriser la réservation spécifique au lot

1. Allez à **Gestion des entrepôts** \> **Configuration** \> **Stock \> Hiérarchie de réservation**.
2. Sélectionnez **Nouveau**.
3. Entrez un nom unique dans le champ **Nom** (par exemple **Lot-Flex**).
4. Dans le champ **Description**, entrez une description (par exemple **Lot, moins prioritaire, flexible**).
5. Dans le chanp **Sélectionné(s)**, sélectionnez **Numéro de série** et **Propriétaire**, puis sélectionnez le bouton fléché gauche pour les déplacer vers le champ **Disponible**.
6. Cliquez sur **OK**.
7. Dans la rangée pour le niveau de dimension **Numéro du lot**, sélectionnez la case à cocher **Autoriser la réservation à la commande**. Les niveaux **Contenant** et **Emplacement** sont automatiquement sélectionnés et vous ne pouvez pas les désactiver.
8. Sélectionnez **Enregistrer**.

### <a name="create-a-new-released-product"></a>Créer un produit lancé

1. Définissez les trois paramètres de données de base du produit en utilisant ces valeurs :

    - Dans le champ **Groupe de dimension de stockage**, sélectionnez **Entrepôt**.
    - Dans le champ **Groupe de dimension de suivi**, sélectionnez **Lot-Phy**.
    - Sélectionnez **Lot-Flex** dans le champ **Hiérarchie de réservation**.

2. Créez deux numéros de lot, tels que **B11** et **B22**.
3. Ajoutez les quantités d’articles au stock disponible en utilisant les valeurs suivantes.

    | Entrepôt | Numéro du lot | Emplacement | Contenant | Quantité |
    |-----------|--------------|----------|---------------|----------|
    | 24        | B11          | BULK-001 | Aucune          | 10       |
    | 24        | B11          | FL-001   | LP11          | 10       |
    | 24        | B22          | FL-002   | LP22          | 10       |

### <a name="enter-sales-order-details"></a><a name="sales-order-details"></a>Entrer les détails des commandes client

1. Accédez à **Ventes et marketing** \> **Commandes client** \> **Toutes les commandes client**.
2. Sélectionnez **Nouveau**.
3. Dans l’en-tête de la commande client, dans le champ **Compte client**, entrez **US-003**.
4. Ajoutez une ligne pour le nouvel article, puis entrez **10** comme quantité. Veillez à ce que le champ **Entrepôt** soit défini sur **24**.
5. Dans l’organisateur **Lignes de commande client**, sélectionnez **Stock**, puis, dans le groupe **Mettre à jour**, sélectionnez **Réservation de lot**. La page **Réservation de lot** affiche la liste des lots disponibles à la réservation pour la ligne de commande. Pour cet exemple, elle montre une quantité de **20** pour le numéro de lot **B11** et une quantité de **10** pour le numéro de lot **B22**. Notez que la page **Réservation de lot** n’est pas accessible à partir d’une ligne si l’élément de cette ligne est associé à la hiérarchie de réservation « Batch-below\[location\] », sauf s’il est configuré pour autoriser une réservation spécifique au lot.

    > [!NOTE]
    > Pour réserver un lot spécifique pour une commande client, vous devez utiliser la page **Réservation de lot**.
    >
    > Si vous saisissez le numéro de lot directement sur la ligne de commande client, le système se comportera comme si vous aviez entré une valeur de lot spécifique pour un article soumis à la politique de réservation « Batch-below\[location\] ». Lorsque vous enregistrez la ligne, vous recevrez un message d’avertissement. Si vous confirmez que le numéro de lot doit être spécifié directement sur la ligne de commande, la ligne ne sera pas gérée par la logique de gestion d’entrepôt standard.
    >
    > Si vous réservez la quantité à partir de la page **Réservation**, aucun lot spécifique ne sera réservé et l’exécution des opérations d’entrepôt pour la ligne suivra les règles applicables dans le cadre de la politique de réservation « Batch-below\[location\] ».

    En général, cette page fonctionne et interagit de la même manière qu’elle fonctionne et interagit pour les articles qui ont une hiérarchie de réservation associée de type « Batch-below\[location\] ». Cependant, les exceptions suivantes s’appliquent :

    - L’organisateur **Numéros de lot validés sur la ligne source** affiche les numéros de lot réservés pour la ligne de commande. Les valeurs des lots dans la grille seront affichées tout au long du cycle d’exécution de la ligne de commande, y compris les étapes de traitement de l’entrepôt. En revanche, sur l’organisateur **Vue d’ensemble**, la réservation de ligne de commande normale (c’est-à-dire la réservation effectuée pour les dimensions au-dessus du niveau **Emplacement**) est affichée dans la grille jusqu’au moment où le travail d’entrepôt est créé. L’entité de travail prend alors en charge la réservation de ligne, et la réservation de ligne n’apparaît plus sur la page. L’organisateur **Numéros de lot validés sur la ligne source** permet de garantir que le processeur de commande client peut afficher les numéros de lot qui ont été validés pour la commande du client à tout moment au cours de son cycle de vie, jusqu’à la facturation.
    - En plus de réserver un lot spécifique, un utilisateur peut sélectionner manuellement l’emplacement spécifique et le contenant du lot au lieu de laisser le système les sélectionner automatiquement. Cette capacité est liée à la conception du mécanisme de réservation de lots validé par la commande. Comme mentionné plus haut, lorsqu’un numéro de lot est réservé pour un article selon la politique de réservation « Batch-below\[location\] », le système doit réserver toutes les dimensions jusqu’à l’emplacement. Par conséquent, le travail d’entrepôt comportera les mêmes dimensions de stockage qui ont été réservées par les utilisateurs qui ont travaillé sur les commandes, et parfois cela ne correspond pas à l’emplacement de stockage de l’article le plus pratique, voire ce choix est impossible pour les opérations de prélèvement. Si les processeurs de la commande sont conscients des contraintes de l’entrepôt, ils peuvent sélectionner manuellement les emplacements spécifiques et les contenants lorsqu’ils réservent un lot. Dans ce cas, l’utilisateur doit utiliser la fonction **Afficher les dimensions** sur l’en-tête de la page et doit ajouter l’emplacement et le contenant dans la grille de l’organisateur **Vue d’ensemble**.

6. Sur la page **Réservation de lot**, sélectionnez la ligne pour le lot **B11**, puis sélectionnez **Réserver une ligne**. Il n’y a pas de logique désignée pour attribuer des emplacements et des contenants lors de la réservation automatique. Vous pouvez saisir manuellement la quantité dans le champ **Réservation**. Notez que, sur l’organisateur **Numéros de lot validés sur la ligne source**, le lot **B11** est affiché comme **Validé**.

    ![Validation d’un numéro de lot spécifique sur une ligne de commande client sur la page de réservation de lot](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > La réservation de la quantité sur une ligne de commande client peut être effectuée sur plusieurs lots. De même, la réservation du même lot peut être effectuée sur plusieurs emplacements et contenants (si les contenants sont activés pour les emplacements).
    >
    > La réservation d’un lot spécifique pour la quantité sur une ligne de commande client peut également être partielle. Par exemple, la quantité totale de 100 unités peut être réservée pour qu’un lot spécifique soit validé à 20 unités, tandis que 80 unités sont réservées au niveau du site et de l’entrepôt pour tout lot disponible. Dans ce cas, le WMS gérera les opérations de prélèvement en utilisant deux lignes de travail distinctes.

7. Allez à **Gestion des informations sur les produits** \> **Produits** \> **Produits lancés**. Sélectionnez votre article, puis sélectionnez **Gérer le stock**\>**Vue** \>**Transactions**.

    ![Réservation validée en tant que type de transaction de stock](media/Inventory-transactions-for-order-committed-reservation.png)

8. Vérifiez les transactions de stock de l’article qui sont liées à la réservation de la ligne de commande client.

    - Une transaction où la **Référence** est définie sur **Commande client** et le **Problème** est défini sur **Physique réservé** représente la réservation de la ligne de commande pour les dimensions de stock au-dessus du niveau **Emplacement**. Selon la hiérarchie de réservation de stock de l’article, ces dimensions sont le site, l’entrepôt et l’état du stock.
    - Une transaction où le champ **Référence** est défini sur **Réservation confirmée par la commande** et le champ **Problème** est défini sur **Physique réservé** représente la réservation de la ligne de commande pour le lot spécifique et toutes les dimensions de stock au-dessus. Selon la hiérarchie de réservation de stock de l’article, ces dimensions sont le numéro du lot et l’emplacement. Dans cet exemple, l’emplacement est **Bulk-001**.

9. Dans l’en-tête de la commande client, sélectionnez **Entrepôt** \>**Actions** \>**Libérer dans l’entrepôt**. La ligne de commande est maintenant traité par vagues et une charge et un travail sont créés.

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a>Examiner et traiter le travail en entrepôt dont les numéros de lot sont validés par la commande

1. Sur l’organisateur **Lignes de commande client**, sélectionnez **Entrepôt** \>**Détails du travail**.

    Le travail qui gère l’opération de prélèvement pour les quantités de lots validées sur la ligne de commande client présente les caractéristiques suivantes :

    - Pour créer un travail, le système utilise des modèles de travail mais pas des directives d’emplacement. Tous les paramètres standard définis pour les modèles de travail, tels que le nombre maximal de lignes de sélection ou une unité de mesure spécifique, seront appliqués pour déterminer le moment où un nouveau travail doit être créé. Cependant, les règles associées aux directives d’emplacement pour identifier les emplacements de prélèvement ne sont pas prises en compte, car la réservation validée par la commande spécifie déjà toutes les dimensions du stock. Ces dimensions de stock incluent les dimensions au niveau du stockage en entrepôt. Par conséquent, le travail hérite de ces dimensions sans avoir à consulter les directives d’emplacement.
    - Le numéro de lot n’apparaît pas sur la ligne de prélèvement (comme c’est le cas pour la ligne de travail créée pour un article auquel est associé une hiérarchie de réservation « Batch-above\[location\] ».) Au lieu de cela, le numéro de lot « origine » et toutes les autres dimensions de stockage sont affichés sur la transaction de stock de la ligne de travail qui est référencée à partir des transactions de stock associées.

        ![Transaction de stock d’entrepôt pour les travaux provenant de la réservation validée par la commande](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - Une fois le travail créé, la transaction de stock de l’article où le champ **Référence** est défini sur **Réservation confirmée par la commande** est retirée. La transaction de stock où le champ **Référence** est défini sur **Travail** détient désormais la réservation physique sur toutes les dimensions de stock de la quantité.

        Les opérations d’entrepôt peuvent procéder à l’exécution des travaux de la manière habituelle. Cependant, les instructions sur l’appareil mobile demanderont au collaborateur de choisir un numéro de lot spécifique. Dans les environnements d’entrepôt où les emplacements sont contrôlés par contenant, lorsqu’un collaborateur atteint un emplacement qui stocke le même lot sur plusieurs contenants, il peut choisir n’importe quel contenant qui n’est pas déjà réservé (par exemple, par une autre réservation confirmée par la commande ou un travail provenant d’une réservation de ce type.)

        S’il s’avère impossible de prélever à partir de l’emplacement spécifié sur la ligne de travail, les opérateurs de l’entrepôt peuvent utiliser l’une des actions suivantes pour rediriger le prélèvement du lot spécifique à partir d’un emplacement plus pratique :

        - L’action **Emplacement de remplacement** standard sur un appareil mobile (à condition que le paramètre **Autoriser le remplacement de l’emplacement de prélèvement** soit activé pour le collaborateur de l’entrepôt)
        - L’action **Changer d’emplacement** sur la page **Détails de la liste de travail**. 

2. Sur l’appareil mobile, terminez le prélèvement et le rangement du travail.

    La quantité de **10** pour le numéro de lot **B11** est maintenant sélectionnée pour la ligne de commande client et placée dans l’empalcement **Baydoor**. À ce stade, le lot est prêt à être chargé dans le camion et expédié à l’adresse du client.

## <a name="flexible-license-plate-reservation"></a>Réservation de contenant flexible

### <a name="business-scenario"></a>Scénario d’entreprise

Dans ce scénario, une société utilise la gestion des entrepôts et le traitement du travail, et gère la planification des chargements au niveau des palettes/conteneurs individuels en dehors de Supply Chain Management avant la création du travail. Ces conteneurs sont représentés par des contenants dans les dimensions de stock. Par conséquent, pour cette approche, des contenants spécifiques doivent être pré-affectées aux lignes de commande client avant que le travail de prélèvement ne soit effectué. La société souhaite une certaine flexibilité dans la manière dont les règles de réservation de contenant sont gérées, afin que les comportements suivants se produisent :

- Un contenant peut être enregistré et réservé lorsque la commande est prise par le processeur de vente, et ne peut pas être modifié par d’autres demandes. Ce comportement garantit que le contenant qui a été planifié est expédié au client.
- Si le contenant n’est pas déjà affecté à une ligne de commande client, le personnel de l’entrepôt peut sélectionner un contenant pendant le travail de prélèvement, une fois l’enregistrement et la réservation de la commande client terminés.

### <a name="turn-on-flexible-license-plate-reservation"></a>Activer la réservation de contenant flexible

Avant de pouvoir utiliser la réservation de contenant flexible, deux fonctionnalités doivent être activées dans votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut des fonctionnalités et les activer si nécessaire. Vous devez activer les fonctionnalités dans l’ordre suivant :

1. **Nom de la fonctionnalité :** *Réservation flexible de dimension au niveau de l’entrepôt*
1. **Nom de la fonctionnalité :** *Réservation flexible de contenant validée par commande*

### <a name="reserve-a-specific-license-plate-on-the-sales-order"></a>Réserver un contenant spécifique sur la commande client

Pour activer la réservation de contenant sur une commande, vous devez activer la case à cocher **Autoriser la réservation sur ordre de la demande** pour le niveau **Contenant** sur la page **Hiérarchies de réservation de stock** de la hiérarchie associée à l’article concerné.

![Page Hiérarchies de réservation de stock pour une hiérarchie de réservation de contenant flexible](media/Flexible-LP-reservation-hierarchy.png)

Vous pouvez activer la réservation de contenant sur la commande à n’importe quel moment de votre déploiement. Cette modification n’affectera pas les réservations ou les travaux d’entrepôt en cours créés avant la modification. Cependant, vous ne pouvez pas désactiver la case à cocher **Autoriser la réservation sur ordre de la commande** s’il existe des mouvements de stock sortants en cours présentant le statut de sortie *En commande*, *Commandé réservé* ou *Physique réservé* pour un ou plusieurs articles associés à cette hiérarchie de réservation.

Même si la case à cocher **Autoriser la réservation sur ordre de la demande** est activée pour le niveau **Contenant**, il est toujours possible de *ne pas* réserver un contenant spécifique sur la commande. Dans ce cas, la logique des opérations en entrepôt par défaut valide pour la hiérarchie de réservation s’applique.

Pour réserver un contenant spécifique, vous devez utiliser un processus [Open Data Protocol (OData)](../../fin-ops-core/dev-itpro/data-entities/odata.md). Dans l’application, vous pouvez effectuer cette réservation directement à partir d’une commande client en utilisant l’option **Réservations validées par commande par contenant** de la commande **Ouvrir dans Excel**. Dans les données d’entité ouvertes dans le complément Excel, vous devez entrer les données de réservation suivantes, puis sélectionner **Publier** pour renvoyer les données à Supply Chain Management :

- Référence (Seule la valeur *Commande client* est prise en charge.)
- Numéro de commande (La valeur peut être dérivée du lot.)
- N° de traitement
- Contenant
- Quantité

Si vous devez réserver un contenant spécifique pour un article suivi par lot, utilisez la page **Réservation de lot**, comme décrit dans la section [Entrer les détails de la commande client](#sales-order-details).

Lorsque la ligne de commande client qui utilise une réservation de contenant validée par commande est traitée par les opérations en entrepôt, les instructions d’emplacement ne sont pas utilisées.

Si un élément de travail d’entrepôt se compose de lignes correspondant à une palette complète et dont les quantités sont validées par contenant, vous pouvez optimiser le processus de prélèvement en utilisant un élément de menu de l’appareil mobile où l’option **Traiter par contenant** est définie sur *Oui*. Un magasinier peut ensuite numériser un contenant pour terminer un prélèvement au lieu de numériser les articles du travail individuellement.

![Élément de menu de l’appareil mobile où l’option Traiter par contenant est définie sur Oui](media/Handle-by-LP-menu-item.png)

Comme la fonctionnalité **Traiter par contenant** ne prend pas en charge les travaux couvrant plusieurs palettes, il est préférable d’avoir un élément de travail distinct pour les différents contenants. Pour utiliser cette approche, ajoutez le champ **ID contenant validé par commande** en tant que décomposition de l’en-tête de travail sur la page **Modèle de travail**.

> [!NOTE]
> Pour le processus de création de travaux validés par commande, une valeur « order-committed inventory dimension » sera attribuée aux lignes de travail de prélèvement et il ne sera pas possible d'afficher directement la valeur de la plaque d'immatriculation. Seul le processus *Dirigé par l'utilisateur* est pris en charge lors de la configuration d'un élément de menu d'appareil mobile.

## <a name="example-scenario-set-up-and-process-an-order-committed-license-plate-reservation"></a>Exemple de scénario : configurer et traiter une réservation de contenant validée par commande

Ce scénario montre comment configurer et traiter une réservation de contenant validée par commande.

### <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Ce scénario fait référence à des valeurs et des enregistrements inclus dans les données de démonstration standard fournies pour Supply Chain Management. Si vous souhaitez exécuter le scénario à l’aide des valeurs fournies ici, veillez à utiliser un environnement dans lequel les données de démonstration sont installées. En outre, définissez l’entité juridique sur **USMF** avant de commencer.

### <a name="create-an-inventory-reservation-hierarchy-that-allows-for-license-plate-reservation"></a>Créer une hiérarchie de réservation de stock qui permet la réservation de contenant

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Stock \> Hiérarchie de réservation**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **Nom**, entrez une valeur (par exemple *FlexibleLP*).
1. Dans le champ **Description**, entrez une valeur (par exemple *Réservation de contenant flexible*).
1. Dans la liste **Sélectionné**, sélectionnez **Numéro de lot**, **Numéro de série** et **Propriétaire**.
1. Cliquez sur le bouton **Supprimer** ![flèche vers l’arrière](media/backward-button.png) pour déplacer les enregistrements sélectionnés vers la liste **Disponible**.
1. Cliquez sur **OK**.
1. Dans la ligne du niveau de dimension **Contenant**, activez la case à cocher **Autoriser la réservation sur ordre de la commande**. Le niveau **Emplacement** est automatiquement sélectionné et vous ne pouvez pas le désactiver.
1. Sélectionnez **Enregistrer**.

### <a name="create-two-released-products"></a>Créer deux produits lancés

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Nouveau produit lancé**, définissez les valeurs suivantes :

    - **Numéro de produit :** *Article1*
    - **Numéro d’article :** *Article1*
    - **Groupe de modèles d’article :** *FIFO*
    - **Groupe d’articles :** *Audio*
    - **Groupe de dimension de stockage :** *Entrepôt*
    - **Groupe de dimension de suivi :** *Aucun*
    - **Hiérarchie de réservation :** *FlexibleLP*

1. Cliquez sur **OK** pour créer le produit et fermer la boîte de dialogue.
1. Le nouveau produit est ouvert. Dans l’organisateur **Entrepôt**, définissez le champ **ID groupe de séquences d’unités** sur *ea*.
1. Répétez les étapes précédentes pour créer un deuxième produit avec les mêmes paramètres, mais définissez les champs **Numéro de produit** et **Numéro d’article** sur *Article2*.
1. Dans le volet Actions, dans l’onglet **Gérer le stock**, dans le groupe **Afficher**, sélectionnez **Stock disponible**. Sélectionnez ensuite **Ajustement de la quantité**.
1. Ajustez le stock disponible des nouveaux articles comme indiqué dans le tableau suivant.

    | Article  | Entrepôt | Entrepôt | Contenant | Quantité |
    |-------|-----------|----------|---------------|----------|
    | Article1 | 24        | FL-010   | LP01          | 10       |
    | Article1 | 24        | FL-011   | LP02          | 10       |
    | Article2 | 24        | FL-010   | LP01          | 5        |
    | Article2 | 24        | FL-011   | LP02          | 5        |

    > [!NOTE]
    > Vous devez créer les deux contenants et utiliser des emplacements qui autorisent des articles mixtes, tels que *FL-010* et *FL-011*.

### <a name="create-a-sales-order-and-reserve-a-specific-license-plate"></a>Créer une commande et réserver un contenant spécifique

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Compte client :** *US-001*
    - **Entrepôt :** *24*

1. Cliquez sur **OK** pour fermer la boîte de dialogue **Créer une commande client** et ouvrez la nouvelle commande client.
1. Dans l’organisateur **Lignes de commande client**, ajoutez une ligne présentant les paramètres suivants :

    - **Numéro d’article :** *Article1*
    - **Quantité :** *10*

1. Ajoutez une deuxième ligne de commande client avec les paramètres suivants :

    - **Numéro d’article :** *Article2*
    - **Quantité :** *5*

1. Sélectionnez **Enregistrer**.
1. Dans l’organisateur **Détails de la ligne**, dans l’onglet **Paramétrage**, notez la valeur **N° de lot** pour chaque ligne. Ces valeurs seront requises lors de la réservation de contenants spécifiques.

    > [!NOTE]
    > Pour réserver un contenant spécifique, vous devez utiliser l’entité de données **Réservations validées par commande par contenant**. Pour réserver un article suivi par lot sur un contenant spécifique, vous pouvez également utiliser la page **Réservation de lot**, comme décrit dans la section [Entrer les détails de la commande client](#sales-order-details).
    >
    > Si vous entrez le contenant directement sur la ligne de commande client et le confirmez au système, le traitement de la gestion des entrepôts n’est pas utilisé pour la ligne.

1. Sélectionnez **Ouvrir dans Microsoft Office**, sélectionnez **Réservations validées par commande par contenant** et téléchargez le fichier.
1. Ouvrez le fichier téléchargé dans Excel et sélectionnez **Activer la modification** pour activer l’exécution du complément Excel.
1. Si vous exécutez le module complémentaire Excel pour la première fois, cliquez sur **Faire confiance à ce module complémentaire**.
1. Si vous êtes invité à vous connecter, cliquez sur **Connexion** et connectez-vous à l’aide des mêmes informations d’identification que pour Supply Chain Management.
1. Pour réserver un article sur un contenant spécifique, dans le complément Excel, sélectionnez **Nouveau** pour ajouter une ligne de réservation, puis définissez les valeurs suivantes :

    - **N° de lot :** entrez la valeur **N° de lot** que vous avez trouvée pour la ligne de commande client associée à *Article1*.
    - **Contenant :** *LP02*
    - **ReservedInventoryQuantity :** *10*

1. Sélectionnez **Nouveau** pour ajouter une autre ligne de réservation, puis définissez les valeurs suivantes :

    - **N° de lot :** entrez la valeur **N° de lot** que vous avez trouvée pour la ligne de commande client associée à *Article2*.
    - **Contenant :** *LP02*
    - **ReservedInventoryQuantity :** *5*

1. Dans le complément Excel, sélectionnez **Publier** pour renvoyer les données à Supply Chain Management.

    > [!NOTE]
    > La ligne de réservation ne s’affiche dans le système que si la publication est terminée sans erreurs.

1. Revenez à Supply Chain Management. 
1. Pour consulter la réservation de l’article, dans l’organisateur **Lignes de commande client**, dans le menu **Stock**, sélectionnez **Mettre à jour \> Réservation**. Notez que, pour la ligne de commande client associée à *Article1*, un stock de *10* est réservé, et pour la ligne de commande client associée à *Article2*, un stock de *5* est réservé.
1. Pour consulter les mouvements de stock liés à la réservation de la ligne de commande client, dans l’organisateur **Lignes de commande client**, dans le menu **Stock**, sélectionnez **Afficher \> Transactions**. Notez que deux transactions sont liées à la réservation : une où le champ **Référence** est défini sur *Commande client* et une où le champ **Référence** est défini sur *Réservation validée par commande*.

    > [!NOTE]
    > Une transaction où le champ **Référence** est défini sur *Commande client* représente la réservation de la ligne de commande pour les dimensions de stock situées au-dessus du niveau **Emplacement** (site, entrepôt et statut du stock). Une transaction où le champ **Référence** est défini sur *Réservation validée par commande* représente la réservation de la ligne de commande pour le contenant et l’emplacement spécifiques.

1. Pour libérer la commande client, dans le volet Actions, dans l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.

### <a name="review-and-process-warehouse-work-with-order-committed-license-plates-assigned"></a>Examiner et traiter le travail en entrepôt avec des contenants validés par commande attribués

1. Dans l’organisateur **Lignes de commande client**, dans le menu **Entrepôt**, sélectionnez **Détails du travail**.

    Comme lorsque la réservation est effectuée pour un lot spécifique, le système n’utilise pas d’instructions d’emplacement lorsqu’il crée le travail pour la commande client qui utilise la réservation de contenant. Comme la réservation validée par commande spécifie toutes les dimensions de stock, notamment l’emplacement, il n’est pas nécessaire d’utiliser les instructions d’emplacement, car ces dimensions de stock sont simplement entrées dans le travail. Elles sont affichées dans la section **Des dimensions de stock** de la page **Mouvements de stock des travaux**.

    > [!NOTE]
    > Une fois le travail créé, le mouvement de stock de l’article où le champ **Référence** est défini sur *Réservation validée par commande* est supprimé. Le mouvement de stock où le champ **Référence** est défini sur *Travail* détient désormais la réservation physique pour toutes les dimensions de stock de la quantité.

1. Sur l’appareil mobile, terminez le prélèvement et le placement du travail en utilisant un élément de menu où la case à cocher **Traiter par contenant** est activée.

    > [!NOTE]
    > La fonctionnalité **Traiter par contenant** vous aide à traiter l’ensemble du contenant. Si vous devez traiter une partie du contenant, vous ne pouvez pas utiliser cette fonctionnalité.
    >
    > Nous vous recommandons de générer un travail distinct pour chaque contenant. Pour obtenir ce résultat, utilisez la fonctionnalité **Décompositions de l’en-tête de travail** sur la page **Modèle de travail**.

    Le contenant *LP02* est maintenant prélevé pour les lignes de commande client et placé dans l’emplacement *Porte baie*. À ce stade, il est prêt à être chargé et expédié au client.

## <a name="exception-handling-of-warehouse-work-that-has-order-committed-batch-numbers"></a>Gestion des exceptions pour un travail d’entrepôt dont les numéros de lot sont validés par la commande

Le travail d’entrepôt pour le prélèvement de numéros de lot validés par la commande est soumis à la même gestion et aux mêmes exceptions qu’un travail normal. En général, la ligne ou le travail ouvert peut être annulé, il peut être interrompu car un emplacement utilisateur est plein, il peut être sélectionné et il peut être mis à jour en raison d’un mouvement. De même, la quantité de travail sélectionnée déjà terminée peut être réduite ou le travail peut être inversé.

La règle clé suivante est appliquée à toutes ces actions de gestion des exceptions : le numéro de lot réservé pour le client ne peut jamais être remplacé par un numéro de lot différent, mais ses dimensions de stockage (emplacement et contenant) peuvent être modifiées via une mise à jour manuelle par l’utilisateur ou une mise à jour automatique par le système. La mise à jour automatique est basée sur la même affectation aléatoire des dimensions de stockage qui s’appliquait lorsqu’un lot spécifique était automatiquement réservé mais qu’aucune dimension de stockage n’était spécifiée.

### <a name="example-scenario"></a>Exemple de scénario

Un exemple de ce scénario est une situation où un travail précédemment terminé est modifié à l’aide de la fonction **Réduire la quantité prélevée**. Cet exemple suppose que vous avez déjà réalisé les étapes décrites dans [Exemple de scénario : affectation de numéros de lot](#Example-batch-allocation). Il fait suite à cet exemple.

1. Allez à **Gestion des entrepôts** \> **Charges** \> **Chargements actifs**.
2. Sélectionnez le chargement créé lors de l’expédition de votre commande client.
3. Dans l’organisateur **Charger des lignes de commande**, sélectionnez **Réduire la quantité prélevée**.
4. Sur la page **RRéduire la quantité prélevée**, dans le champ **Déplacer vers l’emplacement**, sélectionnez **FL-001**.
5. Dans le champ **Déplacer vers le contenant**, sélectionnez **LP33**.
6. Dans la grille, dans le champ **Quantité en stock à ne pas prélever**, entrez **10**.
7. Cliquez sur **OK**.

Voici les résultats de l’action de non prélèvement :

- Le statut du travail précédemment clôturé est défini sur **Annulé**.
- Un nouveau travail de type **Mouvement de stock** est créé pour la quantité non prélevée de **10** pour le numéro de lot **B11**. Ce travail représente le mouvement de l’emplacement **Baydoor** vers le contenant **LP33** à l’emplacement **FL-001**. Le statut est défini sur **Clôturé**.
- Le système réserve à nouveau le numéro de lot qui avait été initialement commandé et attribue l’emplacement et les ID de contenant. (Ce processus équivaut à exécuter la fonction **Réserver une ligne** pour la ligne de commande pour un numéro de lot donné). En conséquence, le lot **B11** apparaît comme validé sur l’organisateur **Numéros de lot validés sur la ligne source** de la page **Réservation de lot** et le champ **Réservation** contient une quantité de **10** pour le numéro de lot **B11**. De plus, l’**Emplacement** est défini sur **FL-001**, et le champ **Contenant** est défini sur **LP11**. (Vous pouvez ajouter ces champs à la grille s’ils ne sont pas visibles.)

Les tableaux suivants fournissent une vue d’ensemble qui montre comment le système gère la réservation par lots validée par la commande pour des actions d’entrepôt spécifiques. Pour interpréter le contenu des tableaux, supposez que chaque action d’entrepôt est exécutée dans le contexte d’un travail d’entrepôt existant provenant d’une réservation par lots validée par une commande, ou que l’exécution de chaque action d’entrepôt affecte un travail de ce type.

> [!NOTE]
> Dans ces tableaux, la colonne « La quantité de lot est disponible » indique si une quantité de lot est disponible en plus de la quantité qui est déjà réservée pour les réservations validées par la commande en cours ou déjà réservée par le travail d’entrepôt qui provient de réservations de ce type.

#### <a name="override-the-pick-location-on-the-open-work"></a>Remplacement de l’emplacement de prélèvement sur le travail ouvert

<table>
<thead>
<tr>
<th>Paramètre de configuration clé</th>
<th>La quantité de lot est disponible</th>
<th>Étapes clés pour l’utilisateur</th>
<th>Travail d’entrepôt</th>
<th>Réservation de lots validée par la commande</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>L’option <strong>Autoriser le remplacement de l’emplacement de prélèvement</strong> est activée pour le collaborateur.</td>
<td>Oui</td>
<td>
<ol>
<li>Sélectionnez l’élément de menu <strong>Emplacement de remplacement</strong> sur l’application d’entrepôt lorsque vous commencez le travail de prélèvement.</li>
<li>Sélectionnez <strong>Suggérer</strong>.</li>
<li>Confirmez le nouvel emplacement suggéré en fonction de la disponibilité de la quantité de lots.</li>
</ol>
</td>
<td>Sur le travail en cours, les actions suivantes se produisent :
<ul>
<li>L’emplacement sur la ligne de sélection est mis à jour vers le nouvel emplacement. (Si l’emplacement est contrôlé par le contenant, un contenant aléatoire est affecté à la transaction de stock, et le collaborateur peut choisir parmi n’importe quel contenant qui a une quantité disponible.)</li>
<li>Si la quantité se trouve sur plusieurs contenants dans le nouvel emplacement, la ligne de prélèvement d’origine est divisée en plusieurs lignes pour correspondre à chaque contenant.</li>
</ul>
</td>
<td>Non applicable</td>
</tr>
<tr>
<td>N°</td>
<td>
<ol>
<li>Sélectionnez l’élément de menu <strong>Emplacement de remplacement</strong> sur l’application d’entrepôt lorsque vous commencez le travail de prélèvement.</li>
<li>Entrez manuellement un emplacement.</li>
</ol>
</td>
<td>L’action <strong>Emplacement de remplacement</strong> n’est pas possible. Elle échoue et une erreur est générée.</td>
<td>Non applicable</td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a>Bouton Complet - Fractionner une ligne de travail en raison d’un dépassement sur l’emplacement de l’utilisateur

<table>
<thead>
<tr>
<th>Paramètre de configuration clé</th>
<th>La quantité de lot est disponible</th>
<th>Étapes clés pour l’utilisateur</th>
<th>Travail d’entrepôt</th>
<th>Réservation de lots validée par la commande</th>
</tr>
</thead>
<tbody>
<tr>
<td>L’option <strong>Autoriser le fractionnement du travail </strong> est activée sur l’élément de menu de l’appareil mobile.</td>
<td>Non applicable</td>
<td>
<ol>
<li>Sélectionnez l’élément de menu <strong>Complet</strong> sur l’application d’entrepôt lorsque vous traitez le travail de prélèvement.</li>
<li>Dans le champ <strong>Qté prélevée</strong>, entrez la quantité partielle de prélèvement requise pour indiquer la pleine capacité.</li>
</ol>
</td>
<td>
<ul>
<li>Sur le travail en cours, la quantité est mise à jour avec la quantité restante qui doit être prélevée.</li>
<li>Un nouveau travail pour la quantité prélevée est créé et fermé.</li>
</ul></td>
<td>Non applicable</td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a>Réduisez la quantité prélevée du travail terminé (à partir d’un chargement)

<table>
<thead>
<tr>
<th>Paramètre de configuration clé</th>
<th>La quantité de lot est disponible</th>
<th>Étapes clés pour l’utilisateur</th>
<th>Travail d’entrepôt</th>
<th>Réservation de lots validée par la commande</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>Non applicable</td>
<td>Oui</td>
<td>
<ol>
<li>Ouvrez la page <strong>Réduire la quantité prélevée</strong> à partir de la ligne de chargement.</li>
<li>Entrer la quantité complète à ne pas prélever.</li>
<li>Sélectionnez un emplacement « déplacer vers » / contenant.</li>
</ol>
</td>
<td>
<ul> 
<li>Le travail associé à la ligne de chargement est annulé.</li>
<li>Un nouveau travail pour le mouvement de stock est créé et fermé.</li>
</ul>
</td>
<td>La quantité est réservée de nouveau pour le même lot. Le système attribue au hasard un emplacement et un contenant (si l’emplacement est contrôlé par le contenant) où la quantité est disponible.</td>
</tr>
<tr>
<td>Non</td>
<td>Voir la ligne précédente.</td>
<td>Voir la ligne précédente.</td>
<td>La quantité est réservée pour le même lot et pour le même emplacement et le même contenant (si l’emplacement est contrôlé par le contenant) qui ont été saisis lors du prélèvement.</td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a>Déplacer un article dans un entrepôt

> [!NOTE]
> Cette action d’entrepôt ne s’applique qu’au mouvement de type **Processus de création du travail**, pas au mouvement par modèle.

<table>
<thead>
<tr>
<th>Paramètre de configuration clé</th>
<th>La quantité de lot est disponible</th>
<th>Étapes clés pour l’utilisateur</th>
<th>Travail d’entrepôt</th>
<th>Réservation de lots validée par la commande</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>L’option <strong>Autoriser les mouvements de stock avec le travail associé</strong> est activée sur le collaborateur.</td>
<td>Oui</td>
<td>
<ol>
<li>Démarrez un mouvement sur l’application d’entrepôt.</li>
<li>Entrez les emplacements d’origine et de destination.</li>
</ol></td>
<td>
<ul>
<li>Sur tous les travaux existants affectés par le déplacement, l’emplacement de prélèvement est mis à jour vers le nouvel emplacement de destination.</li>
<li>Un nouveau travail pour le mouvement de stock est créé et fermé.</li>
</ul>
</td>
<td>Toutes les réservations existantes qui sont affectées par le mouvement de quantité à partir de l’emplacement donné sont re-réservées pour le même lot. Le système attribue au hasard un emplacement et un contenant (si l’emplacement est contrôlé par le contenant) où la quantité est disponible.</td>
</tr>
<tr>
<td>Non</td>
<td>Voir la ligne précédente.</td>
<td>Voir la ligne précédente.</td>
<td>Toutes les réservations existantes qui sont affectées par le mouvement de quantité à partir de l’emplacement donné sont réservées de nouveau pour le même lot, ainsi que pour le nouvel emplacement de destination et le nouveau contenant (si l’emplacement est contrôlé par le contenant).</td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a>Contrepasser la quantité prélevée du travail terminé (à partir d’un chargement ou de la vague)

<table>
<thead>
<tr>
<th>Paramètre de configuration clé</th>
<th>La quantité de lot est disponible</th>
<th>Étapes clés pour l’utilisateur</th>
<th>Travail d’entrepôt</th>
<th>Réservation de lots validée par la commande</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'>Non applicable</td>
<td>Oui</td>
<td>
<ol>
<li>Ouvrez la page <strong>Contrepasser le travail</strong>.</li>
<li>Sur la page de demande, sélectionnez l’option <strong>Laisser les articles à l’emplacement actuel</strong>.</li>
</ol>
</td>
<td>Les travaux associés à la ligne de chargement sont annulés.</td>
<td>La quantité est réservée de nouveau pour le même lot. Le système attribue au hasard un emplacement et un contenant (si l’emplacement est contrôlé par le contenant) où la quantité est disponible.</td>
</tr>
<tr>
<td>Non</td>
<td>Voir la ligne précédente.</td>
<td>Voir la ligne précédente.</td>
<td>La quantité est réservée de nouveau pour le même lot, ainsi que pour l’emplacement et le contenant où la quantité a été laissée lors de la contrepassation.</td>
</tr>
<tr>
<td>Oui</td>
<td>
<ol>
<li>Ouvrez la page <strong>Contrepasser le travail</strong>.</li>
<li>Sur la page de demande, sélectionnez l’option <strong>Affecter des articles à cet emplacement</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>Le travail actuel est annulé.</li>
<li>Un nouveau travail pour le mouvement de stock est créé et fermé.</li>
</ul>
</td>
<td>La quantité est réservée de nouveau pour le même lot. Le système attribue au hasard un emplacement et un contenant (si l’emplacement est contrôlé par le contenant) où la quantité est disponible.</td>
</tr>
<tr>
<td>Non</td>
<td>Voir la ligne précédente.</td>
<td>Voir la ligne précédente.</td>
<td>La quantité est réservée de nouveau pour le même lot, ainsi que pour l’emplacement et le contenant auquel la quantité a été affectée lors de la contrepassation.</td>
</tr>
<tr>
<td>Oui/Non</td>
<td>
<ol>
<li>Ouvrez la page <strong>Contrepasser le travail</strong>.</li>
<li>Sur la page de demande, sélectionnez l’option <strong>Déplacer des articles vers cet emplacement</strong>.</li>
</ol>
</td>
<td>La contrepassation n’est pas prise en charge.</td>
<td>Non applicable</td>
</tr>
<tr>
<td>Oui/Non</td>
<td>
<ol>
<li>Ouvrez la page <strong>Contrepasser le travail</strong>.</li>
<li>Sur la page de demande, sélectionnez l’option <strong>Déplacer des articles selon les instructions d’emplacement</strong>.</li>
</ol>
</td>
<td>La contrepassation n’est pas prise en charge. </td>
<td>Non applicable</td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a>Sélection rapide d’une quantité - Enregistrer la quantité comme physiquement introuvable à l’emplacement / dans le contenant pendant que vous effectuez un travail de prélèvement

<table>
<thead>
<tr>
<th>Paramètre de configuration clé</th>
<th>La quantité de lot est disponible</th>
<th>Étapes clés pour l’utilisateur</th>
<th>Travail d’entrepôt</th>
<th>Réservation de lots validée par la commande</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>Une exception du travail de type <strong>Prélèvement partiel</strong> est configurée, où <strong>Réaffectation des articles </strong> = <strong>Aucun</strong>, <strong>Ajuster le stock </strong> = <strong>Oui</strong>, et <strong>Supprimer des réservations </strong> = <strong>Non</strong>.</td>
<td>Oui</td>
<td>
<ol>
<li>Sélectionnez l’élément de menu <strong>Prélèvement partiel</strong> sur l’application d’entrepôt lorsque vous exécutez le travail de prélèvement.</li>
<li>Dans le champ <strong>Prélever une quantité</strong>, entrez <strong>0</strong> (zéro).</li>
<li>Dans le champ <strong>Nom</strong>, entrez <strong>Aucune imposition</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>Le travail en cours est fermé et la quantité prélevée est 0 (zéro).</li>
<li>Une transaction de stock de type <strong>Comptage </strong>et le type de problème <strong>Vendu </strong>sont créés pour représenter l’ajustement.</li>
</ul>
</td>
<td>La quantité est réservée de nouveau pour le même lot. Le système attribue au hasard un emplacement et un contenant (si l’emplacement est contrôlé par le contenant) où la quantité est disponible.</td>
</tr>
<tr>
<td>Non</td>
<td>Voir la ligne précédente.</td>
<td>
<ul>
<li>L’action de sélection rapide échoue et une erreur est générée.</li>
<li>Le travail en cours reste ouvert.</li>
</ul>
</td>
<td>Non applicable</td>
</tr>
<tr>
<td rowspan='2'>Une exception du travail de type <strong>Prélèvement partiel</strong> est configurée, où <strong>Réaffectation des articles </strong> = <strong>Aucun</strong>, <strong>Ajuster le stock </strong> = <strong>Oui</strong>, et <strong>Supprimer des réservations </strong> = <strong>Oui</strong>.</td>
<td>Oui</td>
<td>
<ol>
<li>Sélectionnez l’élément de menu <strong>Prélèvement partiel</strong> sur l’application d’entrepôt lorsque vous exécutez le travail de prélèvement.</li>
<li>Dans le champ <strong>Prélever une quantité</strong>, entrez <strong>0</strong> (zéro).</li>
<li>Dans le champ <strong>Nom</strong>, entrez <strong>Aucune imposition</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>Le travail en cours est fermé et la quantité prélevée est 0 (zéro).</li>
<li>Une transaction de stock de type <strong>Comptage </strong>et le type de problème <strong>Vendu </strong>sont créés pour représenter l’ajustement.</li>
</ul>
</td>
<td>Toutes les réservations existantes qui sont affectées par l’ajustement de quantité dans l’emplacement faisant l’objet d’un prélèvement partiel sont re-réservées pour le même lot. Le système attribue au hasard un emplacement et un contenant (si l’emplacement est contrôlé par le contenant) où la quantité est disponible.</td>
</tr>
<tr>
<td>Non</td>
<td>Voir la ligne précédente.</td>
<td>Voir la ligne précédente.</td>
<td>Toutes les réservations existantes qui sont affectées par l’ajustement de quantité dans l’emplacement faisant l’objet d’un prélèvement partiel supprimées.</td>
</tr>
<tr>
<td>Une exception du travail de type <strong>Prélèvement partiel</strong> est configurée, où <strong>Réaffectation des articles </strong> = <strong>Manuel</strong>, <strong>Ajuster le stock </strong> = <strong>Oui</strong>, et <strong>Supprimer des réservations </strong> = <strong>Non/Oui</strong>. De plus, l’option <strong>Autoriser la réaffectation manuelle des articles </strong>est activée pour le collaborateur.</td>
<td>Oui</td>
<td>
<ol>
<li>Sélectionnez l’élément de menu <strong>Prélèvement partiel</strong> sur l’application d’entrepôt lorsque vous exécutez le travail de prélèvement.</li>
<li>Dans le champ <strong>Prélever partiellemment une quantité</strong>, entrez <strong>0</strong> (zéro).</li>
<li>Dans le champ <strong>Motif</strong>, sélectionnez <strong>Prélèvement partiel avec réallocation manuelle</strong>.</li>
<li>Sélectionnez l’emplacement / le contenant dans la liste.</li>
</ol>
</td>
<td>
<ul>
<li>Sur le travail en cours, les actions suivantes se produisent :
<ul>
<li>La ligne de prélèvement est fermée et la quantité prélevée est 0 (zéro).</li>
<li>La ligne de placement est annulée.</li>
<li>Une nouvelle ligne de prélèvement a été créée. Elle utilise l’emplacement / contenant que l’utilisateur a sélectionné.</li>
<li>Une nouvelle ligne de placement a été créée.</li>
</ul>
</li>
<li>Une transaction de stock de type <strong>Comptage </strong>et le type de problème <strong>Vendu </strong>sont créés pour représenter l’ajustement.</li>
</ul>
</td>
<td>Non applicable</td>
</tr>
<tr>
<td>Une exception du travail de type <strong>Prélèvement partiel</strong> est configurée, où <strong>Réaffectation des articles </strong> = <strong>Manuel</strong>, <strong>Ajuster le stock </strong> = <strong>Oui</strong>, et <strong>Supprimer des réservations </strong> = <strong>Non</strong>. De plus, l’option <strong>Autoriser la réaffectation manuelle des articles </strong>est activée pour le collaborateur.</td>
<td>N°</td>
<td>
<ol>
<li>Sélectionnez l’élément de menu <strong>Prélèvement partiel</strong> sur l’application d’entrepôt lorsque vous exécutez le travail de prélèvement.</li>
<li>Dans le champ <strong>Prélever partiellemment une quantité</strong>, entrez <strong>0</strong> (zéro).</li>
<li>Dans le champ <strong>Motif</strong>, sélectionnez <strong>Prélèvement partiel avec réallocation manuelle</strong>.</li>
</ol>
</td>
<td>L’action de sélection rapide échoue et une erreur est générée.</td>
<td>Non applicable</td>
</tr>
<tr>
<td>Une exception du travail de type <strong>Prélèvement partiel</strong> est configurée, où <strong>Réaffectation des articles </strong> = <strong>Manuel</strong>, <strong>Ajuster le stock </strong> = <strong>Oui</strong>, et <strong>Supprimer des réservations </strong> = <strong>Oui</strong>. De plus, l’option <strong>Autoriser la réaffectation manuelle des articles </strong>est activée pour le collaborateur.</td>
<td>N°</td>
<td>
<ol>
<li>Sélectionnez l’élément de menu <strong>Prélèvement partiel</strong> sur l’application d’entrepôt lorsque vous exécutez le travail de prélèvement.</li>
<li>Dans le champ <strong>Prélever partiellemment une quantité</strong>, entrez <strong>0</strong> (zéro).</li>
<li>Dans le champ <strong>Motif</strong>, sélectionnez <strong>Prélèvement partiel avec réallocation manuelle</strong>.</li>
<li>Sélectionnez l’emplacement / le contenant dans la liste.</li>
</ol>
</td>
<td>
<ul>
<li>Sur le travail en cours, les actions suivantes se produisent :
<ul>
<li>La ligne de prélèvement est fermée et la quantité prélevée est 0 (zéro).</li>
<li>La ligne de placement est annulée.</li>
</ul>
</li>
<li>Une transaction de stock de type <strong>Comptage </strong>et le type de problème <strong>Vendu </strong>sont créés pour représenter l’ajustement.</li>
</ul>
</td>
<td>Toutes les réservations existantes qui sont affectées par l’ajustement de quantité dans l’emplacement/contenant faisant l’objet d’un prélèvement partiel supprimées.</td>
</tr>
<tr>
<td>Une exception du travail de type <strong>Prélèvement partiel</strong> est configurée, où <strong>Réaffectation des articles </strong> = <strong>Automatique</strong>, <strong>Ajuster le stock </strong> = <strong>Oui/Non</strong>, et <strong>Supprimer des réservations </strong> = <strong>Oui/Non</strong>.</td>
<td>Non applicable</td>
<td>
<ol>
<li>Sélectionnez l’élément de menu <strong>Prélèvement partiel</strong> sur l’application d’entrepôt lorsque vous exécutez le travail de prélèvement.</li>
<li>Dans le champ <strong>Prélever partiellemment une quantité</strong>, entrez <strong>0</strong> (zéro).</li>
<li>Dans le champ <strong>Motif</strong>, sélectionnez <strong>Prélèvement partiel avec réallocation automatique</strong>.</li>
</ol>
</td>
<td>Le prélèvement partiel qui implique une réallocation automatique n’est pas pris en charge.</td>
<td>Le prélèvement partiel qui implique une réallocation automatique n’est pas pris en charge.</td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a>Modifier le statut du stock

> [!NOTE]
> Cette action d’entrepôt peut être effectuée à partir de plusieurs points d’entrée. L’exemple présenté ici utilise l’action **Modification du statut du stock** sur la page **Disponible par emplacement**.

<table>
<thead>
<tr>
<th>Paramètre de configuration clé</th>
<th>La quantité de lot est disponible</th>
<th>Étapes clés pour l’utilisateur</th>
<th>Travail d’entrepôt</th>
<th>Réservation de lots validée par la commande</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>Sur l’onglet <strong>Entrepôt</strong>, dans l’enregistrement <strong>Entrepôt</strong>, le champ <strong>Supprimer les réservations et marquages </strong>est défini sur <strong>Réservations </strong>ou <strong>Marquages et réservations</strong>.</td>
<td>Oui</td>
<td>
<ol>
<li>Sélectionnez un emplacement spécifique.</li>
<li>Sélectionnez une ligne qui a un élément, un emplacement et un contenant spécifiques (si l’emplacement est contrôlé par le contenant).</li>
<li>Sélectionnez <strong>Modification du statut du stock</strong>.</li>
<li>Définissez le champ <strong>Statut du stock </strong>sur <strong>Blocage</strong>.</li>
</ol>
</td>
<td>Les modifications de l’état des stocks ne sont pas autorisées pour les quantités réservées pour le travail.</td>
<td>
<ul>
<li>La quantité est réservée de nouveau pour le même lot. Le système attribue au hasard un emplacement et un contenant (si l’emplacement est contrôlé par le contenant) où la quantité est disponible.</li>
<li>Deux transactions de stock de type <strong>Modification du statut du stock </strong>sont créés pour représenter la modification de la dimension d’état de stock.</li>
<li>Une transaction de stock de type <strong>Blocage su stock </strong>et le type de problème<strong>Physique réservé </strong>est créé pour représenter la réservation de la quantité bloquée.</li>
</ul>
</td>
</tr>
<tr>
<td>Non</td>
<td>Voir la ligne précédente.</td>
<td>Les modifications de l’état des stocks ne sont pas autorisées pour les quantités réservées pour le travail.</td>
<td>
<ul>
<li>La réservation est supprimée.</li>
<li>Deux transactions de stock de type <strong>Modification du statut du stock </strong>sont créés pour représenter la modification de la dimension d’état de stock.</li>
<li>Une transaction de stock de type <strong>Blocage su stock </strong>et le type de problème<strong>Physique réservé </strong>est créé pour représenter la réservation de la quantité bloquée.</li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'>Sur l’onglet <strong>Entrepôt</strong>, dans l’enregistrement <strong>Entrepôt</strong>, le champ <strong>Supprimer les réservations et marquages</strong> est défini sur <strong>Aucun</strong>.</td>
<td>Oui</td>
<td>
<ol>
<li>Sélectionnez un emplacement spécifique.</li>
<li>Sélectionnez une ligne qui a un élément, un emplacement et un contenant spécifiques (si l’emplacement est contrôlé par le contenant).</li>
<li>Sélectionnez <strong>Modification du statut du stock</strong>.</li>
<li>Définissez le champ <strong>Statut du stock </strong>sur <strong>Blocage</strong>.</li>
</ol>
</td>
<td>Les modifications de l’état des stocks ne sont pas autorisées pour les quantités réservées pour le travail.</td>
<td>La quantité est réservée de nouveau pour le même lot. Le système attribue au hasard un emplacement et un contenant (si l’emplacement est contrôlé par le contenant) où la quantité est disponible.</td>
</tr>
<tr>
<td>Non</td>
<td>Voir la ligne précédente.</td>
<td>Les modifications de l’état des stocks ne sont pas autorisées pour les quantités réservées pour le travail.</td>
<td>Les modifications de l’état du stock ne sont pas autorisées.</td>
</tr>
</tbody>
</table>

## <a name="limitations"></a>Limites

- La fonctionnalité de réservation de dimension flexible au niveau de l’entrepôt ne prend pas en charge les fonctionnalités suivantes :

    - Gestion du poids variable
    - Stock physique négatif
    - Réservation contre fourniture commandée
    - Ordres de transfert et prélèvement des matières premières

- La règle de consolidation des conteneurs pour l’emballage par unité de directive présente des limites. Pour les réservations validées par la commande, nous vous recommandons de ne pas utiliser de modèles de construction de conteneur où le cham **Pack par unité de directive** est activé. Dans la conception actuelle, les directives d’emplacement ne sont pas utilisées lors de la création d’un travail d’entrepôt. Par conséquent, seule l’unité la plus basse du groupe de séquences d’unités (l’unité d’inventaire) est appliquée pendant l’étape de vague de conteneurisation.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]