---
title: Cross-docking planifié
description: Cet article décrit le cross-docking planifié avancé, où la quantité de stock requise pour une commande est envoyée directement de la réception ou la création vers le quai d’expédition ou la zone de transit correct. L’ensemble du stock restant de la source entrante est envoyé vers l’emplacement de stockage correct via le processus de rangement normal.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: b530cc1403458775fd330e826a32417d3b03bf25
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334563"
---
# <a name="planned-cross-docking"></a>Cross-docking planifié

[!include [banner](../includes/banner.md)]

Cet article décrit le cross-docking planifié avancé. Le cross-docking est un processus d’entrepôt dans lequel la quantité de stock requise pour une commande est envoyée directement de la réception ou la création vers le quai d’expédition ou la zone de transit correct. L’ensemble du stock restant de la source entrante est envoyé vers l’emplacement de stockage correct via le processus de rangement normal.

Le cross-docking permet aux employés d’ignorer le rangement entrant et le prélèvement de stock sortant qui est déjà marqué pour une commande sortante. Par conséquent, la fréquence d’utilisation du stock est limitée, si possible. De plus, comme il y a moins d’interaction avec le système, les gains de temps et d’espace dans l’atelier sont augmentés.

Avant de pouvoir exécuter le cross-docking, vous devez configurer un nouveau modèle de cross-docking dans lequel la source d’approvisionnement et d’autres exigences de cross-docking sont spécifiées. Lorsque la commande sortante est créée, la ligne doit être marquée par rapport à une commande entrante contenant le même article. Vous pouvez sélectionner le champ de code directif sur le modèle de cross-docking, de la même manière que vous configurez le réapprovisionnement et les commandes fournisseur.

Au moment de la réception de la commande entrante, la configuration du cross-docking identifie automatiquement la nécessité de cross-docking et crée le travail de mouvement pour la quantité requise en fonction de la configuration de l’instruction d’emplacement.

> [!NOTE]
> L’enregistrement des transactions de stock *n’est pas* annulé lorsque le travail de cross-docking est annulé, même si le paramètre de cette fonctionnalité est activé dans les paramètres de gestion des entrepôts.

## <a name="turn-on-the-planned-cross-docking-features"></a>Activer les fonctionnalités Cross-docking planifiées

Si vous exécutez Supply Chain Management version 10.0.28 ou antérieure, vous devrez peut-être activer le cross-docking planifié avant de pouvoir l’utiliser. Allez à [Gestion des caractéristiques](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activer les caractéristiques suivantes dans l’ordre indiqué :

1. *Cross-docking planifié*<br>(Depuis la version 10.0.29 de Supply Chain Management, cette fonctionnalité est obligatoire et ne peut pas être désactivée.)
1. *Modèles de cross-docking avec instructions d’emplacement*<br>(Depuis la version 10.0.29 de Supply Chain Management, cette fonctionnalité est activée par défaut.)
    > [!NOTE]
    > Cette fonction permet au champ **Code directif** d’être spécifié sur le modèle de cross-docking, de la même manière que vous configurez les modèles de réapprovisionnement. L’activation de cette fonctionnalité vous empêche d’ajouter un code directif sur les lignes du modèle de travail de cross-docking pour la dernière ligne *Placement*. Cela garantit que l’emplacement final de placement pourra être déterminé lors de la création du travail avant de prendre en compte les modèles de travail.

## <a name="setup"></a>Paramétrage

### <a name="regenerate-load-posting-methods"></a>Régénérer les méthodes de validation du chargement

Le cross-docking planifié est implémenté en tant que méthode de validation du chargement. Après avoir activé la fonctionnalité, vous devez régénérer les méthodes.

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Méthode de validation du chargement**.
1. Dans le volet Actions, sélectionnez **Régénérer des méthodes**.

    Une fois la régénération terminée, vous devriez voir une méthode dont la valeur **Nom de la méthode** est *planCrossDocking*.

1. Fermez la page.

### <a name="create-a-cross-docking-template"></a>Créer une modèle de cross-docking

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Travail \> Modèles de cross-docking**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un modèle.
1. Dans l’en-tête, définissez les valeurs suivantes :

    - **Séquence :** *1*

        Ce champ définit l’ordre d’évaluation des modèles.

    - **ID du modèle de cross-docking :** *51*
    - **Description :** *Entrepôt 51*
    - **Stratégie de libération de la demande :** *Avant la réception de l’approvisionnement*
    - **Entrepôt :** *51*

1. La configuration de l’organisateur **Planification** contrôle le fonctionnement du modèle. Définissez les valeurs suivantes :

    - **Exigences de la demande :** *Aucun*

        Ce champ définit les exigences de l’inventaire de la demande. Si la demande doit être liée à l’approvisionnement avant la libération, sélectionnez *Marquage*. Si la demande doit être réservée sur commande par rapport à l’approvisionnement avant la libération, sélectionnez *Réservation de commande*.

    - **Type d’emplacement :** *Emplacements d’expédition*

        Ce champ définit si le travail de cross-docking doit utiliser les emplacements intermédiaires/de chargement de l’expédition ou s’il doit utiliser les instructions d’emplacement pour trouver ses propres emplacements intermédiaires/de chargement.

    - **Modèle de travail :** Laissez ce champ vide.

        Ce champ définit le modèle de travail à utiliser lors de la création d’un travail de cross-docking.

    - **Revalider à la réception de l’approvisionnement :** *Non*

        Cette option définit si l’approvisionnement doit être revalidé à la réception. Si cette option est définie sur *Oui*, l’intervalle de temps maximum et la plage de jours d’expiration sont cochés.

    - **Code directif :** Laissez ce champ vide

        Cette option est activée par la caractéristique des *Modèles de cross-docking avec directives de localisation* (à partir de la version 10.0.29 de Supply Chain Management, la caractéristique est activée par défaut). Le système utilise des directives d’emplacement pour aider à déterminer le meilleur emplacement vers lequel déplacer l’inventaire de cross-docking. Vous pouvez le configurer en attribuant un code de directive à chaque modèle de cross-docking pertinent. Si un code directif est défini, le système recherche les instructions d’emplacement par code directif lorsque le travail est généré. De cette manière, vous pouvez limiter les directives d’emplacement utilisées pour un modèle de cross-docking particulier.

    - **Valider l’intervalle de temps :** *Oui*

        Cette option définit si l’intervalle de temps maximum doit être évalué lorsqu’une source d’approvisionnement est sélectionnée. Si cette option est définie sur *Oui*, les champs liés aux intervalles de temps maximum et minimum deviennent disponibles.

    - **Intervalle de temps maximum :** *5*

        Ce champ définit la période maximum autorisée entre l’arrivée de l’approvisionnement et le départ de la demande.

    - **Unité d’intervalle de temps maximum :** *Jours*
    - **Intervalle de temps minimum :** *0*

        Ce champ définit la période minimum autorisée entre l’arrivée de l’approvisionnement et le départ de la demande.

    - **Unité d’intervalle de temps minimum :** *Jours*
    - **Plage de jours d’expiration :** *0*

        *Critères FEFO :* Ce champ définit le nombre maximum de jours entre la date d’expiration du traitement par lots arrivant le premier à expiration actuellement dans l’entrepôt et le traitement par lots en cours de réception.

1. Dans l’organisateur **Sources d’approvisionnement**, vous spécifiez les types d’approvisionnement valides pour ce modèle. Sélectionnez **Nouveau**, puis définissez les valeurs suivantes :

    - **Souche de N° :** *1*
    - **Source d’approvisionnement :** *Commande fournisseur*

> [!NOTE]
> Vous pouvez paramétrer une requête pour contrôler le moment où un modèle spécifique de cross-docking est utilisé. La requête pour les modèles de cross-docking n’a que la table *InventTable* (articles) et la table de type jointure interne *WHSInventTable* (articles WMS). Si vous souhaitez ajouter d’autres tables à la requête, vous pouvez les joindre en utilisant uniquement *jointures existantes* ou *aucune jointure*. Lorsque vous filtrez sur les tables jointes, un enregistrement de la table principale est récupéré pour chaque enregistrement correspondant dans la table jointe. Si le type de jointure est *jointure existante*, la recherche se termine une fois la première correspondance trouvée. Par exemple, si vous joignez la table des lignes de commande client à la table des articles, le système valide et renvoie les articles pour lesquels au moins une ligne de commande client a la condition définie. Essentiellement, les données sont extraites de la table parent (articles) et non de la table enfant (ligne de commande client). Par conséquent, le filtrage par documents source tels que les lignes de commande client ou les clients ne peut pas être effectué directement.

### <a name="create-a-work-class"></a>Créer une classe de travail

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Travail \> Classes de travail**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une classe de travail.
1. Définissez les valeurs suivantes :

    - **ID classe de travail :** *CrossDock*
    - **Description :** *Cross Dock*
    - **Type d’ordre de travail :** *Cross docking*

### <a name="create-a-work-template"></a>Créer un modèle de travail

1. Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.
1. Définissez le champ **Type d’ordre de travail** sur *Cross docking*.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à l’onglet **Vue d’ensemble**.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Numéro de souche :** *1*
    - **Modèle de travail :** *51 Cross Dock*
    - **Description du modèle de travail :** *51 Cross Dock*

1. Sélectionnez **Enregistrer** pour rendre l’organisateur **Détails du modèle de travail** disponible.
1. Dans l’organisateur **Détails du modèle de travail**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Type de travail :** *Choisir*
    - **ID classe de travail :** *CrossDock*

1. Sélectionnez **Nouveau** pour ajouter une autre ligne, puis définissez les valeurs suivantes :

    - **Type de travail :** *Put*
    - **ID classe de travail :** *CrossDock*

1. Sélectionnez **Enregistrer** et confirmez que la case **Valide** est cochée pour le modèle *51 Cross Dock*.
1. Facultatif : Sélectionnez **Modifier la requête** si vous souhaitez définir des critères pour contrôler quand et où le modèle de travail est utilisé.

    Vous pouvez paramétrer une requête pour contrôler le moment où un modèle spécifique de travail est utilisé. Par exemple, vous pouvez spécifier qu’un modèle peut être utilisé pour travailler uniquement à un emplacement spécifique. Si vous souhaitez que le modèle de travail de cross-docking soit appliqué à un emplacement spécifique, vous devez filtrer sur le champ **Lieu de départ**, non le champ **Emplacement**, car la création de travail pour les processus entrants (achat, cross-docking et réapprovisionnement) commence à partir de la ligne de rangement. Lorsque le travail est créé, la directive d’emplacement définit le champ **Lieu** sur l’emplacement de rangement. Cependant, le lieu de prélèvement est stocké dans le champ **Lieu de départ**.

> [!NOTE]
> Les ID de classe de travail pour les types de travail *Prélever* et *Placer* doivent être identiques.

### <a name="create-location-directives"></a>Créer des instructions d’emplacement

1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.
1. Dans le volet gauche, définissez le champ **Type d’ordre de travail** sur *Cross docking*.
1. Dans le volet Actions, sélectionnez **Nouveau**, puis définissez les valeurs suivantes :

    - **Numéro de souche :** *1*
    - **Nom :** *51 Cross Dock Put*
    - **Type de travail :** *Put*
    - **Site :** *5*
    - **Entrepôt :** *51*

1. Sélectionnez **Enregistrer** pour rendre l’organisateur **Lignes** disponible.
1. Dans l’organisateur **Lignes**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Quantité de départ :** *1*
    - **Quantité d’arrivée :** *1000000*

1. Sélectionnez **Enregistrer** pour rendre l’organisateur **Actions d’instruction d’emplacement** disponible.
1. Dans l’organisateur **Actions d’instruction d’emplacement**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Nom :** *Baydoor*
    - **Utilisation d’un emplacement fixe :** *Emplacements fixes et non fixes*

1. Sélectionnez **Enregistrer** pour rendre le bouton **Modifier la requête** de la barre d’outils **Actions d’instruction d’emplacement** disponible.
1. Sélectionnez **Modifier la requête** pour ouvrir l’éditeur de requêtes.
1. Sous l’onglet **Plage**, assurez-vous que les deux lignes suivantes sont configurées :

    - Ligne 1 :

        - **Table :** *Emplacements*
        - **Table dérivée :** *Emplacements*
        - **Champ :** *Entrepôt*
        - **Critères :** *51*

    - Ligne 2 :

        - **Table :** *Emplacements*
        - **Table dérivée :** *Emplacements*
        - **Champ :** *Emplacement*
        - **Critères :** *Baydoor*

1. Cliquez sur **OK** pour fermer l’éditeur de requêtes.

### <a name="create-a-mobile-device-menu-item"></a>Créer une option de menu d’appareil mobile

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans la liste des éléments de menu du volet gauche, sélectionnez **Rangement d’achat**.
1. Sélectionnez **Modifier**.
1. Dans l’organisateur **Classes de travail**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **ID classe de travail :** *CrossDock*
    - **Type d’ordre de travail :** *Cross docking*

1. Sélectionnez **Enregistrer**.

## <a name="scenario"></a>Scénario

### <a name="create-a-purchase-order"></a>Créer une commande fournisseur

Suivez les étapes ci-après pour créer une commande fournisseur comme source d’approvisionnement.

1. Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande fournisseur**, définissez les valeurs suivantes :

    - **Compte fournisseur :** *104*
    - **Entrepôt :** *51*

1. Cliquez sur **OK** et prenez note du numéro de commande.
1. Une nouvelle ligne est ajoutée à l’organisateur **Lignes de commande fournisseur**. Sur cette ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *5*

### <a name="create-a-sales-order"></a>Créer une commande client

Suivez les étapes ci-après pour créer une commande client comme source de demande.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Compte client :** *US-002*
    - **Entrepôt :** *51*

1. Cliquez sur **OK**.
1. Une nouvelle ligne est ajoutée à l’organisateur **Lignes de commande client**. Sur cette ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *3*

### <a name="create-planned-cross-docking"></a>Créer le cross-docking planifié

Suivez les étapes ci-après pour créer le cross-docking planifié à partir de la commande client.

1. Dans la page **Détails de la commande client** de la commande client que vous venez de créer, dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.

    L’action de libération dans l’entrepôt crée une ligne d’expédition et de chargement pour la ligne de commande client et tente d’allouer le stock.
    
    Vous recevez un message d’information. Vous recevez également le message d’avertissement suivant : « Aucun travail n’a été créé pour la vague XXXX. Pour plus de détails, consultez le journal historique de création de travail. » Ce comportement est attendu, car il n’y a pas de stock dans l’entrepôt.

1. Dans l’organisateur **Lignes de commande client**, dans le menu **Entrepôt**, sélectionnez **Détails de l’expédition**.

    La page **Détails de l’expédition** apparaît et affiche l’expédition créée pour la ligne de commande client.

1. Dans l’organisateur **Lignes de chargement**, notez que le champ **Quantité de cross docking planifié** est défini sur *3*. Étant donné qu’aucun stock n’était disponible dans l’entrepôt, mais une source d’approvisionnement valide arrivera dans l’intervalle de temps défini dans le modèle de cross-docking, la quantité de cross-docking a été créée.
1. Dans l’organisateur **Lignes de chargement**, sélectionnez **Cross docking planifié** pour afficher les détails du cross-docking créé.

## <a name="process-the-cross-docking"></a>Traiter le cross-docking

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a>Réception de commande fournisseur sur l’application mobile d’entreposage

Le système recevra la quantité de 5 de la commande fournisseur dans l’emplacement de réception et créera deux travaux.

Le premier ID de travail créé a une valeur **Type d’ordre de travail** de *Cross docking* et est lié à la commande client. Sa quantité est 3 et il est envoyé vers l’emplacement d’expédition finale afin de pouvoir être expédié immédiatement.

Le deuxième ID de travail créé a une valeur **Type d’ordre de travail** de *Commandes fournisseur* et est lié à la commande fournisseur. Sa quantité restante est 2 et n’a pas fait l’objet d’un cross docking. Il est envoyé pour rangement dans l’emplacement de stockage.

1. Connectez-vous à l’appareil mobile en tant qu’utilisateur dans l’entrepôt *51*.
1. Allez à **Entrant \> Réception d’achat**.
1. Dans le champ **PONum**, entrez votre numéro de commande fournisseur.
1. Dans le champ **Qté**, entrez *5*.
1. Cliquez sur **OK**.
1. Dans la page suivante, définissez le champ **Article** sur *A0001*.
1. Cliquez sur **OK**.
1. Dans la page suivante, confirmez les valeurs **PONum**, **Article** et **Qté** en cliquant sur **OK**.

    Vous recevez un message « Travail terminé ».

1. Sélectionnez **Annuler** pour quitter.

### <a name="put-away-to-cross-docking-and-bulk"></a>Ranger dans le cross-docking et en bloc

Actuellement, les deux ID de travail ont le même contenant cible. Pour effectuer les étapes suivantes, vous devez obtenir l’ID de travail et l’ID de contenant cible. Vous pouvez obtenir ces informations à partir des détails du travail de la ligne de commande fournisseur et de la ligne de commande client. Vous pouvez également aller dans **Gestion des entrepôts \> Travail \> Détails du travail** et filtrer le travail où la valeur **Entrepôt** est *51*.

1. Sur l’appareil mobile, accédez à **Entrant \> Rangement d’achat** et entrez le contenant cible à partir du travail.
1. Dans le champ **ID**, entrez l’ID de contenant cible à partir des détails du travail.

    La page de prélèvement du cross-docking indique l’emplacement de prélèvement (*RECV*), le contenant cible (*contenant*), l’article (*A0001*) et la quantité (*3*).

1. Cliquez sur **OK**.
1. Dans le champ **Contenant cible**, entrez un contenant cible pour l’ID de contenant qui doit être placé (faire l’objet d’un cross-docking) dans l’emplacement d’expédition. Vous pouvez sélectionner n’importe quel ID de contenant de votre choix.
1. Cliquez sur **OK**.
1. Dans la page suivante, dans le champ **ID**, entrez l’ID de contenant cible.
1. Cliquez sur **OK**.
1. Confirmez le travail de prélèvement de la quantité restante de 2, puis cliquez sur **OK**.
1. Dans la page suivante, sélectionnez **Terminé** pour terminer le processus de prélèvement et commencer le processus de rangement.

    L’application mobile vous présente l’emplacement et le contenant dans lesquels placer l’article.

1. Confirmez le stockage en bloc **Placer** en cliquant sur **OK**.
1. Dans la page suivante, confirmez le cross-docking **Placer** en cliquant sur **OK**.

    Vous recevez un message « Travail terminé ».

1. Sélectionnez **Annuler** pour quitter.

L’illustration suivante montre comment le travail de cross-docking terminé peut apparaître dans Microsoft Dynamics 365 Supply Chain Management.

![Travail de cross-docking terminé.](media/PlannedCrossDockingWork.png "Travail de cross-docking terminé")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
