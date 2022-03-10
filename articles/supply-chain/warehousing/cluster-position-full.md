---
title: Poste de groupement complet
description: Cette rubrique fournit des informations sur la fonctionnalité Poste de groupement complet. Cette fonctionnalité offre une alternative à une application plus rigide des règles de pause de travail lorsque le prélèvement de groupement est utilisé, car elle permet une plus grande marge d’erreur dans les contraintes volumétriques des conteneurs ou des bacs.
author: Mirzaab
ms.date: 08/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 459c8fce892d9437c7466458b7e53743c71da38f
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8102825"
---
# <a name="cluster-position-full"></a>Poste de groupement complet

[!include [banner](../includes/banner.md)]

La fonctionnalité *Poste de groupement complet* offre une alternative à une application plus rigide des règles de pause de travail lorsque le prélèvement de groupement est utilisé, car elle permet une plus grande marge d’erreur dans les contraintes volumétriques des conteneurs ou des bacs. Dans un scénario courant, tous les éléments d’un ordre de travail ne rentrent pas dans un conteneur sélectionné. Dans ce scénario, les manutentionnaires qui effectuent des prélèvements de groupement ont peu d’options : ils doivent soit passer à une taille de conteneur plus grande, soit travailler avec leur superviseur pour trouver une solution différente.

Cette fonctionnalité introduit la possibilité d’exécuter le bouton **Plein** sur l’une des unités de travail d’un groupement. Dans les anciennes versions, cette option n’était disponible que pour la préparation de commandes standard, pas pour le prélèvement de groupement. Cependant, cette fonctionnalité diffère du bouton **Plein** standard en ce qu’il annule le travail restant. Cela ne suggère pas que l’utilisateur ajoute un autre bac au même groupement et ne crée pas automatiquement de travail.

## <a name="turn-the-cluster-position-full-feature-on-or-off"></a>Activer ou désactiver la fonctionnalité Poste de groupement complet

Pour utiliser la fonctionnalité décrite dans cette rubrique, la fonctionnalité *Poste de groupement complet* doit être activée pour votre système. Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est obligatoire et peut être désactivée. Si vous exécutez une version antérieure à 10.0.25, les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Poste de groupement complet* dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="setup"></a>Paramétrage

Cette section fournit des instructions et un exemple qui montre comment configurer et utiliser la fonctionnalité *Poste de groupement complet*.

### <a name="make-sample-data-available"></a>Rendre les exemple de données disponibles

Pour utiliser [l’exemple de scénario](#example-scenario) à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

Vous pouvez également utiliser cet exemple de scénario comme orientation pour utiliser cette fonctionnalité lorsque vous travaillez sur un système de production. Cependant, dans ce cas, vous devez remplacer les valeurs des paramètres décrits ici par les vôtres.

### <a name="cluster-profiles"></a>Profils de groupement

Vous devez spécifier si les ID de groupement sont générés automatiquement, combien de postes sont utilisés, quand les groupements sont interrompus et comment le travail de prélèvement est séquencé et vérifié.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Appareil mobile \> Profils de groupement**.
1. Dans le volet de liste, sélectionnez l’enregistrement **Créer un groupement**.
1. Dans l’organisateur **Général**, vérifiez les valeurs suivantes :

    - **Générer un ID de groupement :** Sélectionnez *Oui*
    - **Activer des postes :** *Oui*
    - **Nombre de postes :** *2*
    - **Nom du poste :** *Numérique*
    - **Rompre le groupement à :** *Rangement*
    - **Type de vérification du tri :** *Analyse de poste*

1. Dans le raccourci **Tri de groupement**. La grille doit être vide (c’est-à-dire qu’elle ne doit contenir aucune ligne).

### <a name="work-templates"></a>Modèles de travail

Vous devez définir comment créer le travail de prélèvement pour le prélèvement de groupement.

1. Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.
1. En haut de la page, définissez le champ **Type d’ordre de travail** sur *Commandes client*.
1. Assurez-vous que les modèles de travail suivants des données de démonstration sont répertoriés. S’ils ne sont pas disponibles, vous ne pourrez pas terminer le scénario.

    - Phase CC 61
    - Prélèvement de groupement CC 61

### <a name="location-directives"></a>Instructions d’emplacement

Vous devez spécifier où les articles sont prélevés et où ils sont placés.

1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.
1. Dans l’en-tête de liste, définissez le champ **Type d’ordre de travail** sur *Commandes client*.
1. Assurez-vous que les directives de commande client suivantes des données de démonstration sont répertoriées. S’ils ne sont pas disponibles, vous ne pourrez pas terminer le scénario.

    - Prélèvement de groupement 61
    - Ordre de prélèvement CC 61

### <a name="mobile-device-menu-items"></a>Options de menu d’appareil mobile

Vous devez configurer une option de menu d’appareil mobile pour utiliser le travail existant qui est dirigé par le prélèvement de groupement. Dans l’élément de menu de l’appareil mobile pour la sélection de groupement, le paramètre **Autoriser le fractionnement du travail** doit être activé et le la classe de travail *Prélèvement CC* doit être ajoutée.

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans le volet de liste, sélectionnez l’enregistrement **Création de prélèvement de groupement**.
1. Sélectionnez **Modifier** dans le volet Actions.
1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - **Dirigé par :** *Prélèvement de groupement*
    - **Générer un contenant :** *Oui*
    - **Autoriser le fractionnement du travail :** *Oui*
    - **ID de profil de groupement :** *Créer un cluster*

    Acceptez les valeurs par défaut pour tous les autres champs.

1. Sur le raccourci **Classes de travail**, ajoutez les deux lignes suivantes, si nécessaire :

    - Ligne 1 (généralement présente dans les données de démonstration) :

        - **ID classe de travail :** *Ventes* 
        - **Type d’ordre de travail :** *Commandes client*

    - Ligne 2 (probablement absente dans les données de démonstration) :

        - **ID classe de travail :** *Prélèvement CC*
        - **Type d’ordre de travail :** *Commandes client*

1. Allez à **Configuration de la confirmation de travail** dans le volet Action.
1. Sélectionnez **Modifier**.
1. Entrez l’une des valeurs suivantes sur la ligne de la grille.
    - **Type de travail** - *Prélèvement*
    - **Confirmation du produit** - *Cocher la case*

1. Sélectionnez **Enregistrer** dans le volet Action et fermez la page.

## <a name="create-picking-work"></a>Création de tâches de prélèvement

Avant de pouvoir commencer la sélection de groupement, vous devez créer du travail sortant. Le profil de groupement créé précédemment spécifie deux positions de groupement. Par conséquent, au moins deux ID de travail doivent être créés pour la préparation des commandes client. Pour ce scénario, les transactions se produiront dans l’entrepôt *61*, et ils utiliseront des éléments *L0101* et *T0100*. Les données de démonstration doivent avoir un stock disponible de ces éléments suffisant. Assurez-vous que vous disposez d’un stock suffisant pour effectuer les transactions.

### <a name="create-sales-order-1"></a>Créer une commande client 1

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau** pour créer une commande client 1.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Compte client :** *US-010*
    - **Entrepôt :** *61*

1. Cliquez sur **OK**.
1. La nouvelle commande client est ouverte. Dans l’organisateur **Lignes de commande client**, ajoutez une ligne présentant les paramètres suivants :

    - **Numéro d’article :** *T0100*
    - **Quantité :** *5*

1. Sur le raccourci **Détails de ligne**,sur l’onglet **Livraison**, définissez le champ **Date d’expédition confirmée** sur la date du jour.
1. Dans l’organisateur **Lignes de commande client**, ajoutez une seconde ligne présentant les paramètres suivants :

    - **Numéro d’article :** *L0101*
    - **Quantité :** *20*

1. Sur le raccourci **Détails de ligne**,sur l’onglet **Livraison**, définissez le champ **Date d’expédition confirmée** sur la date du jour.
1. Pour chaque ligne que vous venez d’ajouter, procédez comme suit pour réserver le stock :

    1. Sélectionnez la ligne à réserver.
    2. Sur l’organisateur **Lignes de commande client**, sélectionnez **Stock \> Réservation**.
    3. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver le stock.
    4. Fermez la page **Réservation**.

1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.

    Une fois le lancement terminé, vous recevez des messages d’information indiquant les ID de vague et de chargement créés.

### <a name="create-sales-order-2"></a>Créer une commande client 2

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau** pour créer une commande client 2.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Compte client :** *US-011*
    - **Entrepôt :** *61*

1. Cliquez sur **OK**.
1. La nouvelle commande client est ouverte. Dans l’organisateur **Lignes de commande client**, ajoutez une ligne présentant les paramètres suivants :

    - **Numéro d’article :** *L0101*
    - **Quantité :** *20*

1. Sur le raccourci **Détails de ligne**,sur l’onglet **Livraison**, définissez le champ **Date d’expédition confirmée** sur la date du jour.
1. Dans l’organisateur **Lignes de commande client**, ajoutez une seconde ligne présentant les paramètres suivants :

    - **Numéro d’article :** *T0100*
    - **Quantité :** *2*

1. Sur le raccourci **Détails de ligne**,sur l’onglet **Livraison**, définissez le champ **Date d’expédition confirmée** sur la date du jour.
1. Pour chaque ligne que vous venez d’ajouter, procédez comme suit pour réserver le stock :

    1. Sélectionnez la ligne à réserver.
    2. Sur l’organisateur **Lignes de commande client**, sélectionnez **Stock \> Réservation**.
    3. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver le stock.
    4. Fermez la page **Réservation**.

1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.

    Une fois le lancement terminé, vous recevez des messages d’information indiquant les ID de vague et de chargement créés.

### <a name="get-work-ids-and-license-plate-numbers"></a>Obtenez des identifiants de travail et des numéros de contenants

Deux ID de travail doivent avoir été créés, chacun ayant deux lignes de prélèvement. Suivez ces étapes pour trouver les ID de travail et les attributions de contenants.

1. Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.
1. Dans la grille **Vue d’ensemble**, recherchez la colonne **Numéro de commande** pour les deux commandes que vous venez de créer. Pour chaque commande client, notez l’ID de travail correspondant.
1. Sélectionnez la ligne de chaque commande client pour afficher les informations associées dans la grille **Lignes**. Notez l’emplacement à partir duquel chaque article sera prélevé.
1. Accédez à **Gestion des stocks \> Recherches et états \> Stock disponible**.
1. Dans le volet Actions, sélectionnez **Dimensions** pour ouvrir la boîte de dialogue **Affichage des dimensions**.
1. Assurez-vous que les cases **Contenant**, **Entrepôt** et **Numéro d’article** sont cochées, puis sélectionnez **OK**.
1. Dans le volet **Filtre**, définissez les filtres suivants :

    - **Numéro d’article** – **fait partie de** – *L0101* et *T100*
    - **Entrepôt** – **commence par** – *61*

1. Notez les valeurs du **contenant** affichées.

## <a name="example-scenario"></a><a name="example-scenario"></a>Exemple de scénario

### <a name="mobile-device-flow-execution--work-confirmation-setup-for-the-product"></a>Exécution du flux d’appareil mobile – Configuration de la confirmation de travail pour le produit

1. Connectez-vous à l’application mobile Gestion des entrepôts en tant qu’utilisateur de l’entrepôt *61*.
1. Aller à **Sortant \> Création de prélèvement de groupement**.

    La page **TÂCHE : Attribuer le travail au groupement** apparaît.

1. Saisissez l’ID de travail de la commande client 1 pour l’affecter au poste de groupement 1.
1. Sélectionnez **OK** (symbole de coche).
1. Saisissez l’ID de travail de la commande client 2 pour l’affecter au poste de groupement 2.
1. Sélectionnez **OK** (symbole de coche).

    La page **TÂCHE : Création de prélèvement de groupement : Prélèvement** apparaît et affiche *Article L0101 2 PL*.

Étant donné que le profil de groupement définit le nombre de postes sur 2, le système vous dirige automatiquement vers le premier prélèvement groupé : deux palettes (PL) d’article *L0101*.

A tout moment au cours des étapes suivantes, vous pouvez sélectionner l’onglet **Détails** pour afficher des informations supplémentaires sur la tâche, telles que le lieu de prélèvement.

1. Définissez le champ **ARTICLE** sur *L0101*. Cela confirme le numéro d’article, qui est requis pour cet élément de menu (vous l’avez configuré plus tôt en sélectionnant **Configuration de la confirmation de travail** sur la page **Élément de menu d’appareil mobile** lorsque vous avez créé cet élément de menu).
1. Saisissez le numéro de contenant associé à l’article à l’emplacement sélectionné. Vous choisirez deux palettes.
1. Définissez le champ **LP** sur *LP\_PICK\_01*.
1. Sélectionnez **OK** (symbole de coche).

    La page **TÂCHE : Tri : Création de prélèvement de groupement** apparaît. Ici, vous allez trier les deux palettes prélevées à un poste de prélèvement. Ce poste peut être un chariot ou un conteneur utilisé pour séparer le stock prélevé par la commande client.

1. Afficher les détails affichés pour l’élément (*L0101*) et la quantité (*20* unités) qui seront triés au poste 1 (pour la commande client 1).
1. Définissez le champ **POSTE S/O** sur *1*.
1. Sélectionnez **OK** (symbole de coche).
1. Afficher les détails affichés pour l’élément (*L0101*) et la quantité (*20* unités) qui seront triés au poste 2 (pour la commande client 2).
1. Définissez le champ **POSTE S/O** sur *2*.
1. Sélectionnez **OK** (symbole de coche).

    La page **TÂCHE : Création de prélèvement de groupement : Prélèvement** apparaît et affiche *Article T0100 7 unités*.

Dans ce scénario, le poste 1 ne peut pas accepter la quantité totale d’articles qui doivent être prélevés pour exécuter la commande client 1. Un poste doit être marqué comme plein. Dans ce scénario, vous effectuerez un prélèvement partiel du deuxième article. Le deuxième article sera partiellement sélectionné pour le poste 1, et un nouveau travail sera créé pour prélever la quantité restante pour exécuter la commande.

1. Sélectionnez le bouton Menu (parfois appelé hamburger ou bouton hamburger), puis sélectionnez **Poste complet**.
1. Identifiez le poste qui est plein et sélectionnez *1*.
1. Sélectionnez **OK** (symbole de coche).
1. Saisissez la quantité prélevée qui peut encore être prélevée au poste 1. Le système peut déterminer quel numéro d’article est prélevé.
1. Entrez *2*.
1. Sélectionnez **OK** (symbole de coche).
1. Confirmez le numéro d’article pour terminer le prélèvement de l’article restant au poste 2.
1. Définissez le champ **ARTICLE** sur *T0100*.
1. Sélectionnez **OK** (symbole de coche).
1. Entrez le contenant à partir duquel l’article est prélevé en définissant le champ **LP** sur *LPREPL04*.
1. Sélectionnez **OK** (symbole de coche).
1. Afficher les détails affichés pour l’élément (*T0100*) et la quantité (*2* unités) qui seront triés au poste 2 (pour la commande client 2).
1. Définissez le champ **POSTE S/O** sur *2*.
1. Sélectionnez **OK** (symbole de coche).
1. Afficher les détails affichés pour l’élément (*T0100*) et la quantité (*2* unités) qui seront triés au poste 1 (pour la commande client 1).
1. Définissez le champ **POSTE S/O** sur *1*.
1. Sélectionnez **OK** (symbole de coche).

    La page **TÂCHE : Création de prélèvement de groupement : Rangement** apparaît.

Dans ce scénario, le prélèvement de groupement est terminé et l’utilisateur est invité à ranger les articles sélectionnés du poste 1 et du poste 2 à l’emplacement de préparation *STAGE01*.

1. Passez en revue les informations sur la page. Elle montre qu’une quantité totale de *44* sera placé à l’emplacement de préparation.
1. Sélectionnez **OK** (symbole de coche).

    Vous recevez un message « Groupement terminé ».

Vous pouvez maintenant utiliser l’élément de menu **Prélèvement des ventes** pour prélever la quantité restante. Vous pouvez ensuite utiliser l’élément de menu **Chargement des ventes** pour déplacer les éléments de l’emplacement de préparation vers le quai de chargement.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]