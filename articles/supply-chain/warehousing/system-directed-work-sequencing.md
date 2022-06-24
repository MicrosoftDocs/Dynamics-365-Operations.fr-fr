---
title: Classement des travaux dirigés par le système
description: Cet article fournit des informations sur le classement des travaux dirigés par le système. Cette fonctionnalité vous permet de trier et de filtrer les ordres de travail que le système présente aux utilisateurs pour exécution. Elle est utile dans les scénarios où des critères supplémentaires sont nécessaires pour piloter le processus de prélèvement de l’entrepôt.
author: Mirzaab
ms.date: 07/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFSystemDirectedWorkSequenceQuery, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-03
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 8dfa7d8e3bdbfd74c6f95d8b79ac1b0698f73bd6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849124"
---
# <a name="system-directed-work-sequencing"></a>Classement des travaux dirigés par le système

[!include [banner](../includes/banner.md)]

Le classement des travaux dirigés par le système vous permet de trier et de filtrer les ordres de travail que le système présente aux utilisateurs pour exécution. Elles est utile dans les scénarios où des critères supplémentaires (tels que l’heure de l’expédition, la zone de prélèvement, le profil d’emplacement ou une combinaison de divers critères) sont nécessaires pour piloter le processus de prélèvement de l’entrepôt.

Cette fonctionnalité étend la fonctionnalité de prélèvement pilotée par le système en ajoutant un ordre de requête piloté par le système, dans lequel les utilisateurs peuvent configurer un classement et une ou plusieurs requêtes qui évalueront tous les ordres de travail créés. Seuls les ordres de travail qui répondent aux critères spécifiés dans la configuration de l’élément de menu de l’appareil mobile seront capturés et présentés.

Par conséquent, cette fonctionnalité permet d’optimiser davantage les processus de prélèvement de l’entrepôt, car elle identifie les ordres de travail qui correspondent aux critères spécifiés, les affecte au bon élément de menu de l’appareil mobile, puis les présente à un collaborateur, en fonction d’un ensemble de qualifications spécifiques, de l’équipement de prélèvement ou de toute autre exigence.

> [!NOTE]
> Si différents critères sont nécessaires, plusieurs éléments de menu de l’appareil mobile doivent être utilisés.

## <a name="turn-on-the-organization-wide-system-directed-work-sequencing-feature"></a>Activer la fonctionnalité de classement des travaux dirigés par le système à l’échelle de l’organisation

Avant de pouvoir utiliser le classement des travaux dirigés par le système, la fonctionnalité doit être activée sur votre système. Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Classement des travaux dirigés par le système à l’échelle de l’organisation*

## <a name="setup"></a>Paramétrage

### <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Pour utiliser le scénario à l’aide des valeurs présentées dans cet article, vous devez utiliser un système sous lequel les données de démonstration standard sont installées. De plus, vous devez sélectionner l’entité juridique **USMF**. Le scénario utilise l’entrepôt *51* à partir des données de démonstration.

> [!IMPORTANT]
> Avant de lancer les commandes à l’entrepôt, assurez-vous que les emplacements de prélèvement disposent d’un stock suffisant pour tous les articles des commandes.
>
> Les données USMF par défaut doivent prendre en charge ce scénario. Si vous n’utilisez pas les données de démonstration, vérifiez le paramètre **Instruction d’emplacement** pour connaître les emplacements de prélèvement utilisés pour le prélèvement des commandes client. Si vous devez ajuster le stock, vous pouvez créer des mouvements manuels, utiliser le réapprovisionnement ou utiliser tout autre flux.

### <a name="set-up-a-mobile-device-menu-item"></a>Configurer un élément de menu d’appareil mobile

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans la liste des éléments de menu d’appareil mobile, sélectionnez **Prélèvement des ventes - Système**. L’élément de menu requis doit déjà exister. 
1. Confirmez les paramètres suivants :

    - Sur l’organisateur **Général**, le champ **Dirigé par** doit être défini sur *Dirigé par le système*.
    - L’organisateur **Classes de travail** doit afficher les paramètres suivants.

        | ID classe de travail | Type d’ordre d’exécution |
        |---|---|
        | Vente | Commandes client |
        | Prélèvement CC | Commandes client |

1. Dans le volet Actions, sélectionnez **Requêtes de classement des travaux dirigés par le système**.
1. Sélectionnez **Modifier**.
1. Supprimez la ligne existante, puis confirmez l’action en sélectionnant **Oui**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une ligne.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Souche de N° :** *1*
    - **Champ Description :** *Quantité de travail inférieure à 20 et décroissante*

1. Sélectionnez **Enregistrer**.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Sur l’onglet **Jointures**, développez la hiérarchie de la jointure pour afficher la table **Lignes de travail**.
1. Sélectionnez la jointure de table **Lignes de travail**.
1. Sélectionnez **Ajouter une jointure de table**.
1. Dans la liste qui apparaît, recherchez et sélectionnez la ligne contenant les paramètres suivants :

    - **Mode de jointure :** *n à 1*
    - **Relation :** *Emplacements (emplacement)*

1. Cliquez sur **Sélectionner**.

    Les emplacements sont ajoutés à la jointure de table.

1. Sous l’onglet **Tri**, sélectionnez **Ajouter** pour ajouter une ligne.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Table :** *Lignes de travail*
    - **Table dérivée :** *Lignes de travail*
    - **Champ :** *Quantité de travail* (Dans la zone de message qui apparaît, sélectionnez **Oui** pour ajouter un tri à ce champ.)
    - **Direction de recherche :** *Décroissant*

1. Sélectionnez l’onglet **Plage**.

    Si seuls des critères de travail spécifiques doivent être inclus dans le classement, vous pouvez les spécifier sur l’onglet **Plage**. Dans cet exemple, vous souhaitez inclure uniquement les travaux dont la quantité est inférieure à 20 unités (l’unité de mesure la plus petite).

    Notez que certaines lignes sont déjà incluses. Ces lignes ne doivent pas être supprimées.

1. Sélectionnez **Ajouter** pour ajouter une ligne.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Table :** *Lignes de travail*
    - **Table dérivée :** *Lignes de travail*
    - **Champ :** *Quantité de travail en stock*
    - **Critères :** *\<20* (moins de 20)

1. Sélectionnez **Ajouter** pour ajouter une autre ligne.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Table :** *Lignes de travail*
    - **Table dérivée :** *Lignes de travail*
    - **Champ :** *Type de travail*
    - **Critères :** *Prélèvement*

1. Sélectionnez **Ajouter** pour ajouter une autre ligne.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Table :** *Emplacements*
    - **Table dérivée :** *Emplacements*
    - **Champ :** *Location profile ID*
    - **Critères :** *!PHASE*

        > [!IMPORTANT]
        > Assurez-vous d’inclure le point d’exclamation (*!*) devant *PHASE*.

1. Sélectionnez **OK** pour enregistrer et fermer la requête.
1. Sélectionnez **Enregistrer**.
1. Fermez la page pour revenir à la page **Éléments de menu d’appareil mobile**.

> [!NOTE]
> Cette configuration définit les critères qui seront utilisés pour alimenter le travail éligible vers l’élément de menu de l’appareil mobile. Si vous ajoutez plus de lignes de critères à la requête, le système utilisera d’abord la ligne de requête avec le numéro de classement le plus petit. En d’autres termes, tous les travaux éligibles pour le numéro de classement 1 seront d’abord présentés à l’utilisateur, puis tous les travaux pour le numéro de classement 2. Par conséquent, si une plage et un tri spécifiques doivent être utilisés ensemble, ils doivent être spécifiés dans la même requête de classement de travaux dirigés par le système.
>
> Cette configuration capturera tout travail comportant au moins une ligne dont la quantité est inférieure à 20 untés. Par conséquent, si le travail a une ligne où la quantité est exactement de 20 unités ou supérieure à 20 unités, il sera valide, à condition qu’il ait également au moins une ligne où la quantité est inférieure à 20 unités.

### <a name="location-directives"></a>Instructions d’emplacement

Si vous utilisez les données Contoso par défaut, la requête pour l’action de directive d’emplacement ne nécessitera pas de modifications. Toutefois, pour vous assurer que les directives d’emplacement captureront les articles des commandes client lorsque vous appliquez la fonctionnalité dans un environnement non Contoso, créez une directive d’emplacement. Pour vérifier les paramètres dans l’environnement de démonstration, procédez comme suit.

1. Allez dans **Gestion des entrepôts** \> **Configuration** \> **Instructions d’emplacements**.
1. Dans le champ **Type d’ordre de travail**, sélectionnez *Commandes client*.
1. Sélectionnez la directive d’emplacement nommée *51 Prélever*.
1. Sur l’organisateur **Actions de la directive d’emplacement**, sélectionnez la ligne de l’action **Prélever**.
1. Sélectionnez **Modifier la requête** au-dessus de la grille.
1. Vérifiez la requête **Plage**.

    1. Recherchez la ligne où le champ **Champ** est défini sur *Emplacement*.
    2. Assurez-vous que le champ **Critères** est vide (c’est-à-dire qu’il n’y a aucune restriction).

## <a name="scenario"></a>Scénario

### <a name="create-sales-order-picking-work"></a>Créer un travail de prélèvement de commande client

Avant d’exécuter le prélèvement dirigé par le système, certains travaux sortants doivent être créés. Pour ce scénario, vous allez créer quatre commandes client basées sur les requêtes de classement de travaux dirigés par le système spécifiées.

Vous réserverez des quantités en stock pour chaque commande client. Par conséquent, le stock réservé ne peut pas être retiré de l’entrepôt pour les autres commandes, à moins que la réservation de stock ou une partie de celle-ci soit annulée.

Vous libérerez ensuite chaque commande client dans l’entrepôt pour créer le travail sortant.

#### <a name="sales-order-1"></a>Commande client 1

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer la commande client 1.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - Dans la section **Client**, définissez le champ **Compte client** sur *US-004*.
    - Dans la section **Général**, définissez le champ **Entrepôt** sur *51*.

1. Sélectionnez **OK** pour fermer la boîte de dialogue. Prenez note du numéro de la commande client.
1. Ajoutez une ligne à la nouvelle commande client et définissez les valeurs suivantes :

    - **Numéro d’article :** *M9200*
    - **Quantité :** *20*

1. Dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.
1. Sur la page **Réservation**, sélectionnez **Réserver un lot** pour réserver le stock.
1. Fermez la page **Réservation**.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt** pour créer un travail pour l’entrepôt.

    Vous recevez des messages d’information indiquant l’ID de vague, et les ID d’expédition créés pour la commande client.

#### <a name="sales-order-2"></a>Commande client 2

1. Dans le volet Actions, sélectionnez **Nouveau** pour créer la commande client 2.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Compte client :** *US-007*
    - **Entrepôt :** *51*

1. Sélectionnez **OK** pour fermer la boîte de dialogue. Prenez note du numéro de la commande client.
1. Ajoutez une ligne à la nouvelle commande client et définissez les valeurs suivantes :

    - **Numéro d’article :** *M9200*
    - **Quantité :** *5*

1. Sélectionnez **Ajouter une ligne** pour ajouter une deuxième ligne, puis définissez les valeurs suivantes :

    - **Numéro d’article :** *M9201*
    - **Quantité :** *1*

1. Réservez le stock pour les deux lignes.
1. Libérez la commande dans l’entrepôt.

#### <a name="sales-order-3"></a>Commande client 3

1. Dans le volet Actions, sélectionnez **Nouveau** pour créer la commande client 3.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Compte client :** *US-009*
    - **Entrepôt :** *51*

1. Sélectionnez **OK** pour fermer la boîte de dialogue. Prenez note du numéro de la commande client.
1. Ajoutez une ligne à la nouvelle commande client et définissez les valeurs suivantes :

    - **Numéro d’article :** *M9200*
    - **Quantité :** *7*

1. Sélectionnez **Ajouter une ligne** pour ajouter une deuxième ligne, puis définissez les valeurs suivantes :

    - **Numéro d’article :** *M9202*
    - **Quantité :** *8*

1. Réservez le stock pour les deux lignes.
1. Libérez la commande dans l’entrepôt.

#### <a name="sales-order-4"></a>Commande client 4

1. Dans le volet Actions, sélectionnez **Nouveau** pour créer la commande client 4.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Compte client :** *US-010*
    - **Entrepôt :** *51*

1. Sélectionnez **OK** pour fermer la boîte de dialogue. Prenez note du numéro de la commande client.
1. Ajoutez une ligne à la nouvelle commande client et définissez les valeurs suivantes :

    - **Numéro d’article :** *M9200*
    - **Quantité :** *25*

1. Sélectionnez **Ajouter une ligne** pour ajouter une deuxième ligne, puis définissez les valeurs suivantes :

    - **Numéro d’article :** *M9202*
    - **Quantité :** *10*

1. Réservez le stock pour les deux lignes.
1. Libérez la commande dans l’entrepôt.

### <a name="get-work-ids-for-the-work-that-was-created"></a>Obtenir des ID de travail pour le travail créé

1. Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.
1. Filtrez le champ **Entrepôt** de sorte que seul le travail de l’entrepôt *51* soit montré.
1. Quatre ID de travaux ont été créés. Notez l’ID de travail de chaque commande client.

    | ID commande client | ID travail | Quantité de travail |
    |---|---|---|
    | Commande client 1 | ID travail 1 | 20 unités |
    | Commande client 2 | ID travail 2 | 6 unités (somme des deux lignes) |
    | Commande client 3 | ID travail 3 | 15 unités (somme des deux lignes) |
    | Commande client 4 | ID travail 4 | 35 unités (somme des deux lignes) |

Avant d’exécuter le flux sur l’appareil mobile, assurez-vous que seul le travail que vous venez de créer a le statut *Ouvert* pour l’entrepôt *51* et le type d’ordre de travail *Commande client*. Sinon, les résultats du test peuvent varier, car le prélèvement dirigé par le système comprendra tous les travaux éligibles.

1. Allez à **Gestion des entrepôts \> Travail \> Sortant \> Travaux sortants ouverts**.
1. Dans la grille **Travaux de vente ouverts**, filtrez le champ **Entrepôt** de sorte que seul le travail de l’entrepôt *51* soit affiché.
1. Confirmez que seuls les quatre ID de travaux créés précédemment sont affichés.
1. Fermez la page **Travail**.

### <a name="mobile-device-flow-execution"></a>Exécution du flux de l’appareil mobile

En fonction de la configuration, le système alimentera le travail de l’utilisateur trié à partir de la quantité de ligne de travail la plus élevée à la plus faible. La quantité sur chaque ligne sera inférieure à 20 unités.

N’oubliez pas que cette configuration capturera tout travail comportant au moins une ligne dont la quantité est inférieure à 20 untés. Par conséquent, si le travail comporte une autre ligne dont la quantité est exactement de 20 unités ou supérieure à 20 unités, il sera également valide.

#### <a name="mobile-app"></a>Application mobile

1. Connectez-vous à l’application d’entreposage en tant qu’utilisateur de l’entrepôt *51*.
1. Allez à **Sortant \> Prélèvement des ventes - Système**.

    L’étape de prélèvement de l’ID de travail *4* est indiquée. Cet ID de travail est présenté en premier en raison de la configuration de l’ordre de requête dirigé par le système, où vous avez spécifié que le travail doit être classé en fonction de la quantité de ligne de travail décroissante.

1. Effectuez le prélèvement et le rangement nécessaires pour fermer l’ID de travail.

    Ensuite, l’ID de travail *3* est présenté. L’une de ses lignes de travail est la suivante dans le classement, en fonction de la quantité de la ligne de travail.

1. Effectuez le prélèvement et le rangement pour fermer l’ID de travail.

    Ensuite, l’ID de travail *2* est présenté. La ligne de prélèvement de ce travail est la suivante dans le classement.

1. Effectuez le prélèvement et le rangement pour fermer l’ID de travail.

    Aucun autre travail ne doit vous être présenté. L’ID de travail *1* n’est pas éligible pour cet élément de menu de l’appareil mobile, car la requête spécifie que les en-têtes de travail ne sont pris en compte que si la quantité sur les lignes de travail est inférieure à 20 unités.

## <a name="tips"></a>Conseils

Les requêtes de classement des travaux dirigés par le système sont *inclusives*. Il est important que vous vous souveniez de ce fait pour certaines configurations. Par exemple, vous souhaitez qu’un élément de menu spécifique traite uniquement le travail dans lequel l’unité de travail est *unité* et vous spécifiez cette restriction sur l’onglet **Plage** de la requête. Dans ce cas, tous les travaux où au moins une ligne de travail a l’unité de travail définie sur *unité* seront fournis au collaborateur. Par conséquent, ce travail peut également inclure le travail dans lequel les lignes de travail ont une unité de travail autre que *unité* (telle que *boîte* ou *palette*). La requête exclura uniquement le travail où aucune ligne de travail n’a l’unité de travail définie sur *unité*.

Par conséquent, dans l’exemple de ce scénario, l’ID de travail *4* a également été capturé par la requête. Lors de sa création, deux lignes ont été ajoutées : une pour 25 unités et une autre pour 10 unités. Le travail était toujours présenté à l’utilisateur, car au moins une ligne de travail a une quantité inférieure à 20 unités.

Selon le scénario, vous pouvez empêcher ce comportement en utilisant des répartitions du travail.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]