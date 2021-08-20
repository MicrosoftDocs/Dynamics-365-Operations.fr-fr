---
title: Positionnement des contenants dans un emplacement
description: Le positionnement des contenants dans un emplacement vous permet de voir où se trouve un contenant dans un emplacement à palettes multiples, comme un emplacement qui utilise un rayonnage à palettes à double profondeur.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlate, WHSLocationProfile, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 4dc084e4ef568d97912bfa22657b616fd6e493e03ad95703db66584f03e5381e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739680"
---
# <a name="location-license-plate-positioning"></a>Positionnement des contenants dans un emplacement

[!include [banner](../includes/banner.md)]

Le positionnement des contenants dans un emplacement vous permet de voir où se trouve un contenant dans un emplacement à palettes multiples, comme un emplacement qui utilise un rayonnage à palettes à double profondeur.

La fonctionnalité ajoute un numéro de souche à chaque contenant placé dans un emplacement de stockage. Ce numéro de souche permet de classer les contenants dans l’emplacement de stockage. Par conséquent, la fonctionnalité prend en charge de manière intelligente les scénarios où les clients utilisent un système de rayonnage par gravité et doivent savoir, à des fins de prélèvement, quel contenant est orienté vers l’avant.

Cette rubrique présente un scénario qui montre comment configurer et utiliser la fonctionnalité.

## <a name="turn-on-the-location-license-plate-positioning-feature"></a>Activer la fonctionnalité Positionnement des contenants dans un emplacement

Avant de pouvoir utiliser le positionnement des contenants dans un emplacement, la fonctionnalité doit être activée dans votre système. Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Positionnement des contenants dans un emplacement*

## <a name="example-scenario"></a>Exemple de scénario

### <a name="make-sample-data-available"></a>Rendre les exemple de données disponibles

Pour exécuter ce scénario en utilisant les valeurs suggérées ici, vous devez utiliser un système dans lequel les exemples de données sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

### <a name="set-up-the-feature-for-this-scenario"></a>Configurer la fonctionnalité pour ce scénario

Exécutez les procédures suivantes pour configurer la fonctionnalité *Positionnement des contenants dans un emplacement* pour le scénario présenté dans cette rubrique.

#### <a name="location-profiles"></a>Profils d’emplacement

La fonctionnalité doit être activée dans le profil d’emplacement pour chaque emplacement où elle sera utilisée.

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d’emplacement**.
1. Dans la liste des profils d’emplacement du volet gauche, sélectionnez **VRAC-06**.
1. Dans l’organisateur **Général**, deux nouvelles options ont été ajoutées par la fonctionnalité. Définissez les valeurs suivantes :

    - **Activer le positionnement du contenant :** *Oui*

        Lorsque cette option est définie sur *Oui*, le positionnement du contenant sera conservé pour les contenants dans l’emplacement.

    - **Afficher le positionnement du contenant sur l’appareil mobile :** *Oui*

        Lorsque cette option est définie sur *Oui*, le positionnement du contenant sera visible par les utilisateurs sur l’appareil mobile pendant l’ajustement et l’inventaire. Vous ne pouvez modifier le paramètre de cette option que lorsque la fonctionnalité est activée.

1. Sélectionnez **Enregistrer**.

#### <a name="location-directives"></a>Instructions d’emplacement

1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.
1. Dans le volet gauche, assurez-vous que le champ **Type d’ordre de travail** est défini sur *Commandes client*.
1. Dans la liste des instructions d’emplacement, sélectionnez **61 Ordre de prélèvement de commande client**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans l’organisateur **Lignes**, sélectionnez la ligne dont la valeur **Numéro de souche** est *2*.
1. Dans l’organisateur **Actions d’instruction d’emplacement**, sélectionnez la ligne dont la valeur **Nom** est *Prélever pour moins que la palette* (ce devrait être la seule ligne) et modifiez sa valeur **Numéro de souche** sur *2*.
1. Sélectionnez **Nouveau** au-dessus de la grille pour ajouter une ligne pour une nouvelle action d’instruction d’emplacement.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Numéro de souche :** *1*
    - **Nom :** *Choisir la position 1*

1. Alors que la nouvelle ligne est toujours sélectionnée, sélectionnez **Modifier la requête** au-dessus de la grille.
1. Dans l’éditeur de requêtes, sélectionnez l’onglet **Jointures**.
1. Développez la jointure de table **Emplacements** pour afficher la jointure à la table **Dimensions de stock**.
1. Développez la jointure de table **Dimensions de stock** pour afficher la jointure à la table **Stock disponible**.
1. Sélectionnez **Dimensions de stock**, puis sélectionnez **Ajouter une jointure de table**.
1. Dans la liste des tables qui s’affiche, dans la colonne **Relation**, sélectionnez **Contenant (contenant)**. Sélectionnez ensuite **Sélectionner** pour ajouter **Contenant** à la jointure de table **Dimensions de stock**.
1. Alors que **Contenant** est toujours sélectionné, sélectionnez **Ajouter une jointure de table**.
1. Dans la liste des tables qui s’affiche, dans la colonne **Relation**, sélectionnez **Positionnement des contenants dans un emplacement (contenant)**. Sélectionnez ensuite **Sélectionner** pour ajouter **Positionnement des contenants dans un emplacement** à la jointure de table **Dimensions de stock**.

    ![Jointures de table.](media/LpTableJoin.png "Jointures de table")

1. Cliquez sur **OK** pour confirmer les tables jointes mises à jour et fermer l’éditeur de requêtes.
1. Dans l’organisateur **Actions d’instruction d’emplacement**, sélectionnez à nouveau **Modifier la requête** pour rouvrir l’éditeur de requêtes.
1. Sous l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Table :** *Positionnement des contenants dans un emplacement*
    - **Table dérivée :** *Positionnement des contenants dans un emplacement*
    - **Champ :** *Position du contenant*
    - **Critères :** *1*

    ![Nouvelle plage.](media/LpPositionCriteria.png "Nouvelle plage")

1. Cliquez sur **OK** pour confirmer vos modifications et fermer l’éditeur de requêtes.

### <a name="set-up-sample-data-for-this-scenario"></a>Configurer les exemples de données pour ce scénario

Pour ce scénario, l’utilisateur doit se connecter à l’application mobile d’entreposage en utilisant un collaborateur configuré pour l’entrepôt *61* pour effectuer le travail. L’utilisateur doit également exécuter les transactions.

Étant donné que la fonctionnalité *Positionnement des contenants dans un emplacement* ajoute un nouvel identifiant pour les positions de contenant dans un emplacement, vous devez commencer par créer des données pour prendre en charge le scénario.

#### <a name="spot-count-the-first-location"></a>Inventaire ponctuel du premier emplacement

1. Ouvrez l’application mobile d’entreposage et connectez-vous à l’entrepôt *61*.
1. Allez dans **Stock \> Inventaire ponctuel**.
1. Sur la page **Inventaire ponctuel**, définissez le champ **Emplacement** sur *01A01R1S1B*.
1. Cliquez sur **OK**.

    La page affiche l’emplacement que vous avez entré. Elle affiche également le message suivant : "Emplacement complet, ajouter un nouveau contenant ou un nouvel article ? »

1. Sélectionnez **Actualiser** pour ajouter un inventaire dans l’emplacement.
1. Sur la page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article**, sélectionnez le champ **Article**, puis entrez la valeur *A0001*.
1. Cliquez sur **OK**.
1. Sur la page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article**, sélectionnez le champ **Contenant**, puis entrez la valeur *LP1001* (ou tout autre numéro de contenant de votre choix).

    La page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article** affiche **Position 1 du contenant**.

1. Cliquez sur **OK**.

    Vous devez maintenant spécifier la quantité de l’article inventorié sur le contenant.

1. Définissez le champ **Qté** sur *10*.
1. Cliquez sur **OK**.

    La page affiche l’emplacement que vous avez entré. Elle affiche également le message suivant : "Emplacement complet, ajouter un nouveau contenant ou un nouvel article ? »

1. Sélectionnez **Actualiser** pour ajouter un autre inventaire dans l’emplacement.
1. Sur la page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article**, sélectionnez le champ **Article**, puis entrez la valeur *A0002*.
1. Cliquez sur **OK**.
1. Sur la page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article**, sélectionnez le champ **Contenant**, puis entrez la valeur *LP1002* (ou tout autre numéro de contenant de votre choix, à condition qu’il diffère du numéro de contenant que vous avez spécifié précédemment).
1. Modifiez la position du contenant en définissant le champ **Position du contenant** sur *2*.
1. Cliquez sur **OK**.
1. Spécifiez la quantité de l’article inventorié sur le contenant en définissant le champ **Qté** sur *10*.
1. Cliquez sur **OK**.

    La page affiche l’emplacement que vous avez entré. Elle affiche également le message suivant : "Emplacement complet, ajouter un nouveau contenant ou un nouvel article ? »

1. Cliquez sur **OK**.

Le travail est maintenant terminé.

#### <a name="spot-count-the-second-location"></a>Inventaire ponctuel du deuxième emplacement

1. Sur la page **Inventaire ponctuel**, définissez le champ **Emplacement** sur *01A01R1S2B*.
1. Cliquez sur **OK**.

    La page affiche l’emplacement que vous avez entré. Elle affiche également le message suivant : "Emplacement complet, ajouter un nouveau contenant ou un nouvel article ? »

1. Sélectionnez **Actualiser** pour ajouter un inventaire dans l’emplacement.
1. Sur la page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article**, sélectionnez le champ **Article**, puis entrez la valeur *A0002*.
1. Cliquez sur **OK**.
1. Sur la page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article**, sélectionnez le champ **Contenant**, puis entrez la valeur *LP1003* (ou tout autre numéro de contenant de votre choix, à condition qu’il diffère des deux numéros de contenant que vous avez spécifiés dans la procédure précédente).

    La page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article** affiche **Position 1 du contenant**.

1. Cliquez sur **OK**.
1. Spécifiez la quantité de l’article inventorié sur le contenant en définissant le champ **Qté** sur *10*.
1. Cliquez sur **OK**.

    La page affiche l’emplacement que vous avez entré. Elle affiche également le message suivant : "Emplacement complet, ajouter un nouveau contenant ou un nouvel article ? »

1. Cliquez sur **OK**.

Le travail est maintenant terminé.

#### <a name="work-details"></a>Détails du travail

> [!NOTE]
> Les inventaires ponctuels à partir de l’application mobile créent un travail d’inventaire tournant dans Microsoft Dynamics 365. Le travail nécessite que les inventaires soient acceptés avant d’être validés en stock.

1. Connectez-vous à Dynamics 365 Supply Chain Management.
1. Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.
1. Sous l’onglet **Vue d’ensemble**, recherchez les lignes présentant les valeurs suivantes :

    - **Type d’ordre de travail :** *Inventaire tournant*
    - **Entrepôt :** *61*
    - **Statut du travail :** *Révision en attente*

    Deux ID de travail devraient avoir été créés pour ces lignes. Les inventaires de ces deux ID de travail doivent être acceptés.

1. Dans la grille, sélectionnez le premier ID de travail pour le type d’ordre de travail *Inventaire tournant*.
1. Dans le volet Actions, sous l’onglet **Travail**, dans le groupe **Travail**, sélectionnez **Inventaire tournant**.

    Deux lignes sont affichées, une pour chaque article et contenant. Les valeurs des champs **Quantité comptée**, **Emplacement**, **Contenant** et **Article** doivent correspondre aux entrées d’inventaire que vous avez créées sur l’appareil mobile. Si l’un de ces champs n’est pas visible, sélectionnez **Afficher les dimensions** dans le volet Actions pour les ajouter à la grille.

1. Sélectionnez les deux lignes.
1. Dans le volet Actions, sélectionnez **Accepter l’inventaire**.
1. Vous recevez un message « Validation - Journal ». Sélectionnez **Détails du message** pour afficher le numéro de journal validé.
1. Fermez les détails du message.
1. Actualisez la page **Travail**.

    Le premier ID de travail a été fermé et n’est plus affiché.

    > [!TIP]
    > Pour afficher le travail fermé, cochez la case **Afficher fermé** au-dessus de la grille.

    Vous allez maintenant accepter le travail pour le contenant dans l’emplacement *01A01R1S2B*.

1. Sous l’onglet **Vue d’ensemble**, sélectionnez le deuxième ID de travail pour le type d’ordre de travail *Inventaire tournant*.
1. Dans le volet Actions, sous l’onglet **Travail**, dans le groupe **Travail**, sélectionnez **Inventaire tournant**.

    Une ligne est affichée, pour l’article et le contenant. Les valeurs des champs **Quantité comptée**, **Emplacement**, **Contenant** et **Article** doivent correspondre aux entrées d’inventaire que vous avez créées sur l’appareil mobile.

1. Sélectionnez la ligne.
1. Dans le volet Actions, sélectionnez **Accepter l’inventaire**.
1. Vous recevez un message « Validation - Journal ». Sélectionnez **Détails du message** pour afficher le numéro de journal validé.
1. Fermez les détails du message.
1. Actualisez la page **Travail**.

    Le deuxième ID de travail a été fermé et n’est plus affiché.

    > [!TIP]
    > Pour afficher le travail fermé, cochez la case **Afficher fermé** au-dessus de la grille.

#### <a name="on-hand-by-location"></a>Disponible par emplacement

1. Allez dans **Gestion des entrepôts \> Recherches et états \> Disponible par emplacement**.
1. Définissez les valeurs suivantes :

    - **Site :** *6*
    - **Entrepôt :** *61*
    - **Actualiser dans plusieurs emplacements :** *Oui*

1. Notez que l’emplacement *01A01R1S1B* a deux contenants :

    - **A0001**, où le champ **Position du contenant** est défini sur *1*
    - **A0002**, où le champ **Position du contenant** est défini sur *2*

1. Notez que l’emplacement *01A01R1S2B* a un contenant :

    - **A0002**, où le champ **Position du contenant** est défini sur *1*

### <a name="sales-order-scenario"></a>Scénario de commande client

Maintenant que la fonctionnalité *Positionnement des contenants dans un emplacement* a été configurée et que le stock a été placé, vous devez créer une commande client pour générer un travail de prélèvement qui va demander au magasinier de sélectionner l’article *A0002* dans l’emplacement de stock où l’ID de palette est en position *1*.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Compte client :** *US-004*
    - **Entrepôt :** *61*

1. Cliquez sur **OK**.
1. Une nouvelle ligne est ajoutée à la grille dans l’organisateur **Lignes de commande client**. Sur cette nouvelle ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** *A0002*
    - **Quantité :** *1*

1. Dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.
1. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver le stock pour la ligne de commande.
1. Fermez la page **Réservation**.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.

    Vous recevez un message d’information indiquant l’ID de vague et l’ID d’expédition créés pour la commande.

1. Dans l’organisateur **Lignes de commande client**, dans le menu **Entrepôt** au-dessus de la grille, sélectionnez **Détails du travail**.
1. La page **Travail** apparaît et affiche le travail créé pour la ligne de vente. Prenez note de l’ID de travail affiché.

### <a name="sales-picking-scenario"></a>Scénario de prélévement des ventes

1. Ouvrez l’application mobile et connectez-vous à l’entrepôt *61*.
1. Allez à **Sortant \> Prélèvement des ventes**.
1. Sur la page **Analyser un ID travail/ID contenant**, sélectionnez le champ **ID**, puis entrez l’ID de travail à partir de la ligne de vente.
1. Notez que le travail de prélèvement vous demande de sélectionner l’article *A0002* dans l’emplacement *01A01R1S2B*. Vous recevez cette instruction car l’article *A0002* se trouve sur un contenant en position *1* dans cet emplacement.

    ![Emplacement en position 1.](media/LocationLicensePlatePositioning.png "Emplacement en position 1")

1. Entrez l’ID de contenant que vous avez créé pour l’emplacement, puis suivez les invites pour sélectionner la commande client.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]