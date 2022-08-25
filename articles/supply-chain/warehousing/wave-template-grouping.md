---
title: Regroupement de modèles de vague
description: Le regroupement de modèles de vagues permet au système d’utiliser des configurations de modèles de vagues afin de déterminer, en fonction des critères que vous définissez, comment il doit fractionner les lignes libérées et les affecter à des vagues nouvelles ou existantes. Cette fonctionnalité peut être utile dans les entrepôts où des vagues sont créées en fonction de critères spécifiques, mais où les gestionnaires préfèrent créer des vagues automatiquement plutôt que manuellement.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 0f0419f1a109f043cb1af6a575704c24420639f1
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218912"
---
# <a name="wave-template-grouping"></a>Regroupement de modèles de vague

[!include [banner](../includes/banner.md)]

Le regroupement de modèles de vagues permet au système d’utiliser des configurations de [modèles de vagues](tasks/configure-wave-processing.md) afin de déterminer, en fonction des critères que vous définissez, comment il doit fractionner les lignes libérées et les affecter à des vagues nouvelles ou existantes. Cette fonctionnalité peut être utile dans les entrepôts où des vagues sont créées en fonction de critères spécifiques, mais où les gestionnaires préfèrent créer des vagues automatiquement plutôt que manuellement. Elle permet au système d’ajouter chaque nouvelle expédition validée à la première vague qu’il trouve et ayant des valeurs de champ de regroupement correspondantes. Si aucune correspondance n’est trouvée, le système crée une vague pour la nouvelle expédition.

> [!IMPORTANT]
> Le regroupement de modèles de vagues n’est pas pris en charge pour les types de travail de *prélèvement de matières premières de production* ou de *prélèvement Kanban*. En effet, le regroupement de vagues est basé sur les expéditions et ces types de travaux n’utilisent pas les expéditions.

## <a name="turn-on-the-wave-template-grouping-feature"></a>Activer la fonctionnalité de regroupement de modèles de vagues

Avant de pouvoir utiliser la fonctionnalité *Regroupement de modèles de vagues*, celle-ci doit être activée sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Regroupement de modèles de vagues*

## <a name="set-a-wave-template-to-use-wave-template-grouping"></a><a name="set-up-template"></a>Définir un modèle de vague pour utiliser le regroupement de modèles de vagues

Pour rendre le regroupement de modèles de vagues disponible, procédez comme suit pour configurer votre [modèle de vague](tasks/configure-wave-processing.md).

1. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.
1. Dans le volet gauche, sélectionnez le modèle de vague à configurer. Si vous vous apprêtez à exécuter le scénario plus loin dans cet article à l’aide de données de démonstration, sélectionnez le modèle **62 Expédition par défaut**.
1. Sélectionnez **Modifier** pour afficher la page en mode d’édition.
1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - **Automatiser la création de vague :** *Oui*
    - **Attribuer aux vagues ouvertes :** *Oui*
    - **Traiter la vague à la libération dans l’entrepôt :** *Non*

1. Dans le volet Actions, sélectionnez **Modifier la requête** pour ouvrir la boîte de dialogue de requête.
1. Dans la boîte de dialogue de requête, sur l’onglet **Tri**, passez en revue les critères de tri et assurez-vous qu’il existe une règle qui inclut le champ que vous souhaitez utiliser pour regrouper vos vagues.

    Si vous vous préparez à exécuter le scénario à l’aide des données de démonstration, ajoutez une ligne avec les valeurs suivantes :

    - **Table :** *Expéditions*
    - **Table dérivée :** *Expéditions*
    - **Champ :** *Service de transporteur*

        > [!NOTE]
        > Une fois que vous avez sélectionné cette valeur, le message suivant peut s’afficher : « Le champ Service de transporteur n’est pas un champ d’index. Voulez-vous ajouter un tri à ce sujet ? » Sélectionnez **Oui** pour ajouter le tri.

    - **Ordre de tri :** *Croissant*

1. Sélectionnez **OK** pour enregistrer vos modifications et fermer la boîte de dialogue de requête.
1. Dans le volet Actions, sélectionnez **Regroupement de modèles de vagues**.
1. Sur la page **Regroupement de modèles de vagues**, cochez la case **Grouper par** pour chaque ligne à utiliser pour regrouper vos lignes de commande par vagues, selon les besoins. Si vous vous apprêtez à exécuter le scénario à l’aide des données de démonstration, cochez la case **Grouper par** pour la ligne *Service de transporteur*.
1. Sélectionnez **Enregistrer**.
1. Fermez la page **Regroupement de modèles de vagues**.
1. Sélectionnez **Enregistrer** pour enregistrer le modèle.

## <a name="scenario"></a>Scénario

Cette section fournit un script que vous pouvez exécuter pour découvrir ce que fait cette fonctionnalité et comment l’utiliser.

### <a name="make-sample-data-available"></a>Rendre les exemple de données disponibles

Pour utiliser ce scénario à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

Vous pouvez également utiliser ce scénario comme orientation pour utiliser la fonctionnalité lorsque vous travaillez sur un système de production. Cependant, dans ce cas, vous devez remplacer vos propres valeurs, et il se peut que certains types d’enregistrements requis que les données de démonstration standard fournissent manquent.

### <a name="scenario-wave-template-grouping"></a>Scénario : Regroupement de modèles de vagues

Ce scénario montre comment utiliser le regroupement de modèles de vagues pour créer automatiquement plusieurs vagues, en fonction de critères de regroupement définis dans un modèle de vague. Dans ce scénario, le modèle de vague est configuré dans le système pour créer une vague par service de transporteur.

Avant de commencer, préparez votre modèle de vague comme décrit dans la section [Définir un modèle de vague pour utiliser le regroupement de modèles de vagues](#set-up-template) plus haut dans cet article. Si vous utiliser des données de démonstration pour ce scénario, veillez à utiliser les valeurs de données de démonstration suggérées dans cette procédure. Cette configuration regroupera vos vagues en fonction du service de transporteur défini pour chaque commande client.

#### <a name="create-sales-order-1"></a>Créer une commande client 1

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau** pour créer une commande client.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - Dans l’organisateur **Client**, définissez le champ **Compte client** sur *US-004*.
    - Dans l’organisateur **Général**, définissez le champ **Entrepôt** sur *62*.

1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue **Créer une commande client**.
1. La nouvelle commande client est ouverte dans la vue **Lignes**. Prenez note du numéro de la commande client.
1. Basculez sur la vue **En-tête**.
1. Sur l’organisateur **Livraison**, dans la section **Transport**, définissez les valeurs suivantes :

    - **Transporteur :** *Fret aérien*
    - **Service de transporteur :** *Air*

1. Revenez à la vue **Lignes**.
1. Dans la section **Lignes de la commande client**, cliquez sur **Ajouter une ligne** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** *A0002*
    - **Quantité :** *2*

1. Sélectionnez la nouvelle ligne de commande, puis, sur le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.
1. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la quantité totale de la ligne sélectionnée dans l’entrepôt.
1. Fermez la page **Réservation** pour revenir à la commande client.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.
1. Vous recevez un message d’information indiquant l’expédition et la vague de cette commande. Notez le numéro d’identification de la vague et les numéros d’identification d’expédition.

#### <a name="view-the-wave-that-was-created-from-sales-order-1"></a>Afficher la vague créée à partir de la commande client 1

1. Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.
1. Sélectionnez l’ID de vague à partir duquel la commande client a été créée.
1. Sélectionnez le lien d’ID de vague pour ouvrir la page de détails de la vague.
1. Notez que l’expédition a été ajoutée à l’organisateur **Lignes de la vague**.

#### <a name="create-sales-order-2"></a>Créer une commande client 2

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau** pour créer une commande client.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - Dans l’organisateur **Client**, définissez le champ **Compte client** sur *US-005*.
    - Dans l’organisateur **Général**, définissez le champ **Entrepôt** sur *62*.

1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue **Créer une commande client**.
1. La nouvelle commande client est ouverte dans la vue **Lignes**. Prenez note du numéro de la commande client.
1. Basculez sur la vue **En-tête**.
1. Sur l’organisateur **Livraison**, dans la section **Transport**, définissez les valeurs suivantes :

    - **Transporteur :** *Farine en mouvement*
    - **Service de transporteur :** *Standard*

1. Revenez à la vue **Lignes**.
1. Dans la section **Lignes de la commande client**, cliquez sur **Ajouter une ligne** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *1*

1. Sélectionnez la nouvelle ligne de commande, puis, sur le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.
1. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la quantité totale de la ligne sélectionnée dans l’entrepôt.
1. Fermez la page **Réservation** pour revenir à la commande client.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.
1. Vous recevez un message d’information indiquant l’expédition et la vague de cette commande. Notez le numéro d’identification de la vague et les numéros d’identification d’expédition. Notez que l’ID de vague diffère de l’ID de vague de la première commande client.

#### <a name="view-the-wave-that-was-created-from-sales-order-2"></a>Afficher la vague créée à partir de la commande client 2

1. Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.
1. Sélectionnez l’ID de vague à partir duquel la seconde commande client a été créée.
1. Sélectionnez le lien d’ID de vague pour ouvrir la page de détails de la vague.
1. Notez que l’expédition a été ajoutée à l’organisateur **Lignes de la vague**.

Une vague a été créée pour cette expédition, car elle utilise un service de transporteur différent de la première commande client.

#### <a name="create-sales-order-3"></a>Créer une commande client 3

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau** pour créer une commande client.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - Dans l’organisateur **Client**, définissez le champ **Compte client** sur *US-006*.
    - Dans l’organisateur **Général**, définissez le champ **Entrepôt** sur *62*.

1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue **Créer une commande client**.
1. La nouvelle commande client est ouverte dans la vue **Lignes**. Prenez note du numéro de la commande client.
1. Basculez sur la vue **En-tête**.
1. Sur l’organisateur **Livraison**, dans la section **Transport**, définissez les valeurs suivantes :

    - **Transporteur :** *Fret aérien*
    - **Service de transporteur :** *Air*

1. Revenez à la vue **Lignes**.
1. Dans la section **Lignes de la commande client**, cliquez sur **Ajouter une ligne** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *1*

1. Sélectionnez la nouvelle ligne de commande, puis, sur le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.
1. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la quantité totale de la ligne sélectionnée dans l’entrepôt.
1. Fermez la page **Réservation** pour revenir à la commande client.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.
1. Vous recevez un message d’information indiquant l’expédition et la vague de cette commande. Notez le numéro d’identification de la vague et les numéros d’identification d’expédition. L’expédition a été affectée à la vague existante à partir de la première commande client.

#### <a name="view-the-wave-for-sales-orders-1-and-3"></a>Afficher la vague des commandes client 1 et 3

1. Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.
1. Sélectionnez l’ID de vague à partir duquel la troisième commande client a été créée.
1. Sélectionnez le lien d’ID de vague pour ouvrir la page de détails de la vague.
1. Notez que l’expédition a été ajoutée à l’organisateur **Lignes de la vague**, ainsi que l’expédition de la première commande client.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]