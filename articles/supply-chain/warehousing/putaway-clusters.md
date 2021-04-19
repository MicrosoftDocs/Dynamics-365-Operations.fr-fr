---
title: Clusters de rangement
description: Les cluster de rangement offrent un moyen de choisir plusieurs contenants en même temps, puis de les transférer pour les ranger à différents emplacements. Ils peuvent être très utiles pour les commerces de détail, où les contenants ne sont généralement pas des palettes complètes de stock.
author: Mirzaab
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: b3a7d1b7109b83b26c8187a7f0d271f1c82f6d63
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840363"
---
# <a name="putaway-clusters"></a>Clusters de rangement

[!include [banner](../includes/banner.md)]

Les cluster de rangement offrent un moyen de choisir plusieurs contenants en même temps, puis de les transférer pour les ranger à différents emplacements. Ce processus est souvent nommé *tournée du laitier*. Les clusters de rangement peuvent être très utiles pour les commerces de détail, où les contenants ne sont généralement pas des palettes complètes de stock. 

## <a name="turn-on-the-cluster-putaway-feature"></a>Activer la fonctionnalité de rangement de cluster

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Fonctionnalité de rangement de cluster*

## <a name="setup-for-the-example-scenario"></a>Configurer l’exemple de scénario

### <a name="cluster-profiles"></a>Profils de groupement

Le profil de cluster de rangement détermine où un article ira, en fonction de l’emplacement qui est attribué à l’article au moment de la réception. Si différents groupements sont requis, différents clusters de rangement doivent être créés pour chaque élément de menu de l’appareil mobile.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Appareil mobile \> Profils de groupement**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la vue **En-tête**, définissez les valeurs suivantes :

    - **ID profil de cluster de stockage :** *Rangement du cluster*
    - **Nom de l’ID profil de cluster de stockage :** *Rangement du cluster*
    - **Type de cluster :** *Rangement*
    - **Souche de N° :** Acceptez la valeur par défaut.

1. Sélectionnez **Enregistrer** pour rendre les champs obligatoires sur l’organisateur **Général** disponibles.
1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - **Calendrier d’attribution de cluster :** *À la réception*

        Ce champ définit si le cluster de stockage doit être affecté immédiatement à la réception du stock ou s’il doit être trié ultérieurement.

    - **Règle d’attribution de cluster :** *Manuel*

        Ce champ définit si l’affectation du groupement doit être déterminé automatiquement par le système ou manuellement par l’utilisateur.

    - **Code directif :** Laissez ce champ vide.
    - **Localisation du cluster de stockage :** *Accusé de réception*

        Les valeurs disponibles sont les suivantes :

        - **Accusé de réception** – Un emplacement est trouvé immédiatement lors de la réception.
        - **Fermeture du groupement** – Un emplacement est trouvé à la fermeture du groupement.
        - **Dirigé par l’utilisateur** – Un emplacement est trouvé lorsque le contenant est prélevé dans le groupe pour mise en stock. Dans ce cas, aucun emplacement n’est spécifié lors de la création du travail de rangement. Au cours de la mise en stock elle-même, l’utilisateur doit scanner l’ID de contenant ou de travail pour lancer l’étape de rangement. Le système trouve ensuite à nouveau l’emplacement de rangement et indique à l’utilisateur où ranger la quantité prélevée.

    - **Cluster de rangement par utilisateur :** *Non*

        Ce champ définit si chaque cluster doit être unique par utilisateur lorsque les clusters sont automatiquement attribués. Il est disponible uniquement lorsque le champ **Règle d’attribution de cluster** est défini sur *Automatique*.

    - **Restriction d’unité :** Laissez ce champ vide.

        Ce champ définit l’unité qui doit être reçue pour que le profil soit valide. Si ce champ est vide, toutes les unités sont valides.

    - **Répartition de l’unité de travail :** *Individuel*

        Ce champ définit si tout le stock doit être consolidé (en utilisant l’ID de cluster et de contenant) sur un contenant lorsqu’un cluster est fermé, et s’il doit être rangé comme un seul contenant ou séparément sur les contenants qui ont été reçus. Ce champ n’est pas disponible lorsque le champ **Localisation du cluster de stockage** est défini sur *Accusé de réception*.

    - **Le cluster persiste en tant que contenant parent :** *Non*

        Si cette option est définie sur *Oui*, une fois l’étape de mise en place terminée, l’ID du cluster deviendra un contenant parent, et tous les éléments de l’ID du cluster seront liés à ce contenant parent.

1. Sur le raccourci **Tri de cluster**, vous pouvez définir des critères de tri de rangement. Sélectionnez **Nouveau** sur la barre d’outil pour ajouter une deuxième ligne, puis définissez les valeurs suivantes pour elle :

    - **Souche de N° :** Acceptez la valeur par défaut.
    - **Nom du champ :** *WMSLocationId*

        Ce champ définit le champ que cette ligne doit utiliser comme critère de tri.

    - **Tri :** *Croissant*

        Ce champ définit si le tri doit être effectué par ordre croissant ou décroissant.

1. Dans l’organisateur **Modèle de travail en cluster**, sélectionnez **Nouveau** sur la barre d’outil pour ajouter une ligne, puis définissez les valeurs suivantes pour celle-ci :

    - **Type d’ordre de travail :** *Commandes fournisseur*
    - **Modèle de travail :** *61 CF Direct*

1. Sur le volet Actions, sélectionnez **Enregistrer**, puis cliquez sur **Modifier la requête**.
1. Dans la boîte de dialogue **Rangement de cluster**, sous l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une seconde ligne à la grille. Mettez ensuite à jour les lignes de requête comme indiqué dans le tableau suivant.

    | Enregistrement | Table dérivée | Champ | Critères |
    |---|---|---|---|
    | Travail | Travail | Entrepôt | *61* |
    | Travail | Travail | ID travail | Laissez ce champ vide. |

1. Sélectionnez **OK** pour enregistrer la requête et fermer la boîte de dialogue.
1. Sur le volet Action, sélectionnez **Enregistrer** et fermez la page.

> [!IMPORTANT]
> Les champs du profil de cluster qui apparaissent estompés lorsque **Générer un ID de cluster** est défini sur *Oui* ne sont pas disponibles et ne seront pas pris en compte lorsque cette fonctionnalité est utilisée.

### <a name="mobile-device-menu-items"></a>Options de menu d’appareil mobile

Deux nouveaux éléments de menu de l’appareil mobile sont disponibles pour cette fonction. L’élément de menu **Recevoir et trier le cluster** est utilisé pour trier le stock reçu dans un groupe de stockage à la réception. L’élément de menu **Rangement du cluster** est utilisé pour ranger le cluster après son affectation.

#### <a name="receive-and-sort-cluster"></a>Recevoir et trier le cluster

Créez un élément de menu d’appareil mobile pour recevoir le stock et le trier dans un cluster. Cet élément de menu créera du travail entrant après la réception du stock, ce qui indique que l’élément de menu de réception sera utilisé pour les clusters de stockage.

> [!NOTE]
> L’élément de menu **Recevoir et trier le cluster** peut être utilisé avec les éléments de menu de réception suivants :
>
> - Réception de ligne de commande fournisseur
> - Réception d’article de commande fournisseur
> - Réception des articles du chargement

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la vue **En-tête**, définissez les valeurs suivantes :

    - **Nom de l’élément de menu :** *Recevoir et trier le cluster*
    - **Titre :** *Recevoir et trier le cluster*
    - **Mode :** *Travail*
    - **Utiliser un travail existant :** *Non*

1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - **Processus de création de travail :** *Réception de l’article de commande fournisseur*
    - **Générer un contenant :** *Oui*
    - **Attribuer un cluster de stockage :** *Oui*

        > [!NOTE]
        > L’option **Attribuer un cluster de stockage** est disponible uniquement pour l’activité *Processus de création de travail* pour recevoir.

    Acceptez les valeurs par défaut pour les champs restants.

1. Dans le volet Actions, sélectionnez **Enregistrer**.

#### <a name="cluster-putaway"></a>Rangement de groupement

Créez un élément de menu d’appareil mobile pour ranger le cluster une fois qu’il a été attribué.

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la vue **En-tête**, définissez les valeurs suivantes :

    - **Nom de l’option de menu :** *Rangement de groupement*
    - **Titre :** *Mise en stock du cluster*
    - **Mode :** *Travail*
    - **Utiliser un travail existant :** *Oui*

1. Sur l’organisateur **Général**, définissez le champ **Dirigé par** sur *Rangement de cluster*. Acceptez les valeurs par défaut pour les champs restants.
1. Sur le raccourci **Classes de travail**, configurez la classe de travail valide pour cet élément de menu d’appareil mobile :

    - **ID classe de travail :** *Achat*
    - **Type d’ordre de travail :** *Commandes fournisseur*

1. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="mobile-device-menu"></a>Menu d’appareil mobile

Ajoutez les éléments de menu que vous venez de créer au menu entrant de l’application mobile.

1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d’appareil mobile**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans la liste des menus, sélectionnez **Entrant**.
1. Dans la liste **Menus et éléments de menus disponibles**, recherchez et sélectionnez **Recevoir et trier le cluster**.
1. Sélectionnez le bouton Flèche droite pour déplacer l’élément de menu sélectionné vers la liste **Structure du menu**.
1. Utilisez la flèche vers le haut ou la flèche vers le bas pour déplacer l’élément de menu dans la position souhaitée dans le menu.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Répétez les étapes 4 à 7 pour ajouter les éléments de menu restants :

    - Attribuer un cluster
    - Rangement de groupement

## <a name="example-scenario"></a>Exemple de scénario

Ce scénario simule le traitement de cluster rangé.

### <a name="create-a-purchase-order"></a>Créer une commande fournisseur

1. Accédez à **Comptabilité fournisseur \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande fournisseur**, définissez les valeurs suivantes :

    - **Compte fournisseur :** *1001*
    - **Entrepôt :** *61*

1. Cliquez sur **OK**.

    La page **Toutes les commandes fournisseur** s’affiche.

1. Sur la page **Toutes les commandes fournisseur**, sur le raccourci **Lignes de commande fournisseur**, utilisez le bouton **Ajouter une ligne** pour ajouter les lignes suivantes :

    - Ligne de commande fournisseur 1 :

        - **Numéro d’article :** *A0001*
        - **Quantité :** *10*

    - Ligne de commande fournisseur 2 :

        - **Numéro d’article :** *A0002*
        - **Quantité :** *20*

    - Ligne de commande fournisseur 3 :

        - **Numéro d’article :** *M9215*
        - **Quantité :** *30*

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Prenez note du numéro de la commande fournisseur.

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a>Recevoir le stock et le ranger de l’appareil mobile

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a>Recevoir et trier le stock dans un cluster

1. Connectez-vous à l’application mobile Gestion des entrepôts en tant qu’utilisateur configuré pour l’entrepôt *61*.
1. Dans le menu principal, sélectionnez **Entrant**.
1. Sur le menu **Entrant**, sélectionnez **Recevoir et trier le cluster**.
1. Dans le champ **Ponum**, entrez le numéro de commande fournisseur.
1. Cliquez sur **OK** (bouton de coche).
1. Sélectionnez le champ **Article**, entrez le numéro d’article *A0001* et cliquez sur **OK**.
1. Sélectionnez le champ **Qté**, entrez *10* à l’aide du pavé numérique, puis sélectionnez le bouton de coche.
1. Sur la page de tâches **Qté**, sélectionnez **OK** (le bouton de coche) pour confirmer la quantité que vous avez entrée.
1. Sur la page de tâche **Article**, sélectionnez **OK** pour confirmer que l’article *A0001* a été entré.
1. Sélectionnez le champ **ID de cluster** et entrez une valeur pour attribuer un ID au cluster que vous créez.

    L’ID que vous entrez ici sera utilisé lors de la réception des deux articles restants sur la commande fournisseur.

1. Cliquez sur **OK**.

    La page des tâches **Ponum** apparaît et affiche un message "Travail terminé".

    L’article *A0001* a maintenant été reçu à l’emplacement *RECV* et attribué à l’ID de cluster que vous avez entré à l’étape 10.

1. Répétez les étapes 4 à 11 pour recevoir les deux articles restants de la commande fournisseur et les affecter à l’ID de cluster :

    - Une quantité de *20* d’un article *A0002*
    - Une quantité de *30* d’un article *M9215*

#### <a name="close-the-cluster"></a>Fermer le cluster

Avant de pouvoir ranger les éléments du cluster, le cluster doit être fermé.

1. Dans Supply Chain Management, accédez à **Gestion d’entrepôt \> Travail \> Sortant \> Clusters de travail**.
1. Sur la page **Clusters de travail**, dans la section **Groupe de travail**, recherchez le champ **ID de cluster** pour l’ID de cluster que vous avez entré précédemment.
1. Si le cluster n’est pas affiché, il est peut-être déjà fermé. Pour déterminer si le cluster a été fermé, cochez la case **Afficher le travail fermé** et recherchez l’ID de cluster que vous avez entré précédemment. Suivez ensuite l’une des procédures suivantes :

    - Si le cluster a été fermé, ignorez les étapes restantes de cette procédure et passez à la procédure suivante, [Ranger le cluster](#put-the-cluster-away).
    - Si le cluster n’a pas été fermé, suivez les étapes restantes de cette procédure pour fermer manuellement le cluster. Ensuite, passez à la procédure suivante.

1. Dans la section **Cluster de travail**, sélectionnez l’ID de cluster que vous avez entré précédemment.
1. Dans le volet Actions, sélectionnez **Fermer le cluster**.

    Une fois le cluster fermé, il n’est plus affiché dans la section **Groupe de travail** (sauf si **Afficher le travail fermé** est coché).

#### <a name="put-the-cluster-away"></a>Ranger le cluster

1. Connectez-vous à l’application mobile Gestion des entrepôts en tant qu’utilisateur configuré pour l’entrepôt *61*.
1. Dans le menu principal, sélectionnez **Entrant**.
1. Dans le menu **Entrant**, sélectionnez **Rangement du cluster**.
1. Sélectionnez **ID de cluster** et entrez l’ID de cluster que vous avez entré précédemment pour le cluster fermé.
1. Cliquez sur **OK**.

    La page **Rangement du cluster : prélèvement** apparaît. Elle montre l’ID du cluster, l’emplacement de prélèvement, les articles (la valeur *Plusieurs* sera affichée) et la quantité totale dans le cluster qui doit être prélevée.

1. Cliquez sur **OK**.

    La page **Rangement du cluster : rangement** apparaît. Les instructions **Rangement** identifient l’ID de cluster, l’emplacement de rangement, les articles, la quantité totale et les ID de contenant pour les articles qui ont été reçus sur le cluster.

    Vous disposez des options standard pour remplacer ou passer cette étape.

    ![Rangement du cluster : page Rangement](media/Cluster_putaway-Put.png "Rangement du cluster : page Rangement")

1. Cliquez sur **OK** pour confirmer le rangement du cluster.

    Un message « Groupement terminé » s’affiche.

## <a name="notes-and-tips"></a>Remarques et conseils

Dans les cas où l’ID de cluster devient le contenant parent d’une palette imbriquée, la position de rangement est automatiquement donnée lorsque l’ID de cluster est scanné. Aucun autre contenant ne doit être scanné, même si la génération de contenant est définie sur manuelle.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]