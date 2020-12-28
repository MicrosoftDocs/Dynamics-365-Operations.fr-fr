---
title: Association de dimensions de produit dans un emplacement
description: Cette rubrique donne des informations sur l'association de dimensions de produit dans un emplacement. Cette fonctionnalité de profil d'emplacement aide à améliorer la gestion des emplacements lorsque des variantes de produit ou des produits contenant des dimensions sont utilisés, comme dans le secteur de la mode. Elle vous permet de décider si des configurations, couleurs, styles et tailles peuvent être associés pour un profil d'emplacement spécifique, ou si une seule de ces dimensions ou une combinaison d'entre elles peut être placée au même emplacement.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 73519f3fe79d3d7d917d3044255f735640b8ccfd
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428211"
---
# <a name="location-product-dimension-mixing"></a>Association de dimensions de produit dans un emplacement

[!include [banner](../includes/banner.md)]

L'association de dimensions de produit dans un emplacement est une fonctionnalité de profil d'emplacement qui aide à améliorer la gestion des emplacements lorsque des variantes de produit ou des produits contenant des dimensions sont utilisés, comme dans le secteur de la mode. Elle vous permet de décider si des configurations, couleurs, styles et tailles peuvent être associés pour un profil d'emplacement spécifique, ou si une seule de ces dimensions ou une combinaison d'entre elles peut être placée au même emplacement.

## <a name="turn-on-the-location-product-dimension-mixing-feature"></a>Activer la fonctionnalité Association de dimensions de produit dans un emplacement

Avant de pouvoir utiliser l'association de dimensions de produit dans un emplacement, la fonctionnalité doit être activée dans votre système. Les administrateurs peuvent utiliser l'espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Association de dimensions de produit dans un emplacement*

## <a name="setup"></a>Paramétrage

Chaque emplacement de l'entrepôt doit avoir un profil d'emplacement qui lui est associé et qui décrit les propriétés de l'emplacement. Par conséquent, tous les emplacements qui utilisent le même profil d'emplacement pourront autoriser l'association de dimensions de produit une fois la configuration effectuée.

### <a name="configure-location-profiles-to-allow-product-dimension-mixing"></a>Configurer les profils d'emplacement pour autoriser l'association de dimensions de produit

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d'emplacement**.
1. Dans la liste des profils d'emplacement, sélectionnez **BULK**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans l'organisateur **Général**, définissez l'option **Activer l'association spécifique de dimensions de produit dans un emplacement** sur *Oui*.

    > [!NOTE]
    > Vous pouvez définir cette option sur *Oui* uniquement si l'option **Autoriser les articles mixtes** est définie sur *Non*.

1. Dans l'organisateur **Association de dimensions de produit autorisée**, définissez l'option **Taille** sur *Oui*. Dans le scénario décrit dans cette rubrique, l'association ne peut être effectuée que pour les produits dont les dimensions **Taille** sont différentes. Cependant, d'autres options sont également disponibles.
1. Sélectionnez **Enregistrer**.

### <a name="create-a-new-product-master-and-product-variants"></a>Créer un produit générique et des variantes de produit

1. Allez dans **Gestion des informations sur les produits \> Produits \> Produits génériques**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un produit générique.
1. Dans la boîte de dialogue **Nouveau produit**, définissez les valeurs suivantes :

    - **Type de produit :** *Article*
    - **Sous-type de produit :** *Produit générique*
    - **Numéro de produit :** *B0001*
    - **Nom du produit :** *Taille B0001*
    - **Groupe de dimensions de produit :** *Taille*
    - **Technologie de configuration :** *Variante prédéfinie*

1. Cliquez sur **OK**.
1. Sur la page **Détails du produit**, dans l'organisateur **Général**, définissez les valeurs suivantes :

    - **Générer les variantes automatiquement :** *Oui*
    - **Groupe de tailles :** *CASUALDHIR*

1. Pour afficher les variantes prédéfinies, dans le volet Actions, sélectionnez **Variantes de produit**.

    La page **Variantes de produit** apparaît et affiche une liste de variantes à partir de la configuration du groupe de tailles.

### <a name="release-products-to-the-usmf-company"></a>Lancer des produits dans la société USMF

1. Dans le volet Actions, sélectionnez **Lancer des produits**.
1. Sur la page **Sélectionner des produits à lancer**, confirmez que le numéro de produit *B0001* est présent dans la liste, puis sélectionnez **Suivant**.
1. Sélectionnez **Suivant** pour confirmer les variantes de produit à lancer.
1. Sur la page **Sélectionner les sociétés vers lesquelles lancer**, sélectionnez *USMF*, puis sélectionnez **Suivant** pour confirmer la sélection.
1. Sur la page **Confirmer la sélection**, sélectionnez **Terminer** pour terminer le lancement.

    Vous recevez un message « Opération terminée ».

### <a name="update-a-released-product-in-the-usmf-company"></a>Mettre à jour un produit lancé dans la société USMF

1. Assurez-vous d'être connecté à la société **USMF**.
1. Allez dans **Gestion des informations sur les produits \> Produits \> Produits lancés** pour terminer la création du produit lancé.
1. Recherchez et sélectionnez le numéro d'article *B0001* pour ouvrir la page **Détails des produits lancés**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans l'organisateur **Général**, assurez-vous que le champ **Groupe de modèles d'article** est défini sur *FIFO*.
1. Dans le volet Actions, sous l'onglet **Produit**, dans le groupe **Paramétrer**, sélectionnez **Groupes de dimensions**.
1. Définissez les valeurs suivantes :

    - **Groupe de dimension de stockage :** *Entrepôt*
    - **Groupe de dimension de suivi :** *Aucun*

1. Cliquez sur **OK**.
1. Dans le volet Actions, sous l'onglet **Produit**, dans le groupe **Paramétrer**, sélectionnez **Hiérarchie de réservation**.
1. Définissez le champ **Hiérarchie de réservation** sur *Valeur par défaut*, puis cliquez sur **OK**.
1. Dans l'organisateur **Général**, dans la section **Administration**, notez que vos sélections ont été mises à jour.
1. Dans l'organisateur **Achats**, dans le champ **Prix**, entrez *10*.
1. Dans l'organisateur **Gérer les coûts**, dans le champ **Groupe d'articles**, entrez *Audio*.
1. Dans l'organisateur **Achats**, dans le champ **Prix**, entrez *10*.
1. Dans l'organisateur **Entrepôt**, dans le champ **ID groupe de séquences d'unités**, entrez *ea*.
1. Sélectionnez **Enregistrer**.

### <a name="create-a-location-directive"></a>Créer une instruction d'emplacement

1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d'emplacements**.
1. Dans le volet gauche, dans le champ **Type d'ordre de travail**, sélectionnez *Commandes fournisseur*.
1. Dans la liste, sélectionnez l'instruction d'emplacement nommée *24 PO Direct*.
1. Dans l'organisateur **Actions d'instruction d'emplacement**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Numéro de souche :** *1*

        La nouvelle ligne doit être en face de la ligne précédemment existante. Pour effectuer la modification, utilisez les boutons **Déplacer vers le haut** et **Déplacer vers le bas** de la barre d'outils ou modifiez la valeur **Numéro de souche** de la ligne existante sur *2*.

    - **Nom :** *Placer dans le profil d'emplacement BULK*
    - **Utilisation d'un emplacement fixe :** *Emplacements fixes et non fixes*
    - **Autoriser le stock négatif :** *Décochez cette case (=Non)*
    - **Traitement par lots activé :** *Décochez cette case (=Non)*
    - **Stratégie :** *Aucun*

1. Alors que la nouvelle ligne est toujours sélectionnée, sélectionnez **Modifier la requête** au-dessus de la grille.
1. Dans la boîte de dialogue de requête, sous l'onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Table :** *Emplacements*
    - **Table dérivée :** *Emplacements*
    - **Champ :** *Location profile ID*
    - **Critères :** *BULK*

1. Cliquez sur **OK**.
1. Sur la page **Instructions d'emplacement**, dans le volet Actions, sélectionnez **Enregistrer**.

> [!NOTE]
> Dans l'organisateur **Actions d'instruction d'emplacement**, dans le champ **Stratégie**, si vous utilisez la stratégie d'emplacement *Consolider*, la configuration de l'organisateur **Association de dimensions de produit autorisée** dans **Profils d'emplacement** sera remplacée et les articles seront placés au même emplacement même si ce comportement n'est pas autorisé par la configuration.

### <a name="create-a-mobile-device-menu-item"></a>Créer une option de menu d'appareil mobile

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d'appareil mobile**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un élément de menu à utiliser pour le tri.
1. Dans l'en-tête, définissez les valeurs suivantes :

    - **Nom de l'option de menu :** *Réception de ligne de commande fournisseur*
    - **Titre :** *Réception de ligne de commande fournisseur*
    - **Mode :** *Travail*
    - **Utiliser un travail existant :** *Non*

1. Dans l'organisateur **Général**, définissez les valeurs suivantes :

    - **Processus de création du travail :** *Réception et rangement de la ligne de commande fournisseur*
    - **Générer un contenant :** *Oui*

1. Sélectionnez **Enregistrer**.

### <a name="configure-the-mobile-device-menu"></a>Configurer le menu sur l'appareil mobile

1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d'appareil mobile**.
1. Dans la liste des menus, sélectionnez **Entrant**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans la liste **Menus et éléments de menus disponibles**, recherchez et sélectionnez l'élément de menu **Réception de ligne de commande fournisseur**.
1. Sélectionnez le bouton Flèche droite pour déplacer l'élément de menu **Réception de ligne de commande fournisseur** vers la liste **Structure du menu**. De cette façon, vous ajoutez votre nouvel élément de menu au menu sélectionné.
1. Sélectionnez **Enregistrer**.

## <a name="scenario"></a>Scénario

Ce scénario de démonstration montre comment deux variantes de produit différentes peuvent être placées au même emplacement lorsque le profil d'emplacement n'autorise pas les articles mixtes, mais la fonctionnalité *Association de dimensions de produit dans un emplacement* est activée. Dans ce cas, vous utiliserez la variante **Taille** comme critère.

Avant de commencer, assurez-vous que des emplacements vides dans l'entrepôt *24* utilisent le profil d'emplacement *BULK*.

### <a name="create-a-purchase-order"></a>Créer une commande fournisseur

Vous allez créer une commande fournisseur comprenant trois lignes : deux lignes pour le même numéro de produit mais des variantes **Taille** différentes, et une troisième ligne pour un produit différent qui ne contient pas de variantes.

1. Accédez à **Comptabilité fournisseur \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande fournisseur**, définissez les valeurs suivantes :

    - **Compte fournisseur :** *1001*
    - **Entrepôt :** *24*

1. Cliquez sur **OK**.
1. La commande fournisseur est créée et une nouvelle ligne est ajoutée à l'organisateur **Lignes de commande fournisseur**. Prenez note du numéro de la commande fournisseur.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Numéro d'article :** *B0001*
    - **Taille** *L*
    - **Quantité :** *2*

1. Sélectionnez **Ajouter une ligne** au-dessus de la grille pour ajouter une deuxième ligne de commande et définissez les valeurs suivantes :

    - **Numéro d'article :** *B0001*
    - **Taille** *XL*
    - **Quantité :** *2*

1. Sélectionnez **Ajouter une ligne** pour ajouter une troisième ligne de commande fournisseur, puis définissez les valeurs suivantes :

    - **Numéro d'article :** *A0001*
    - **Quantité :** *1*

1.Sélectionnez **Enregistrer**.

### <a name="receive-purchase-order-lines-in-the-warehouse-app"></a>Recevoir des lignes de commande fournisseur dans l'application d'entrepôt

1. Connectez-vous à l'application d'entrepôt en tant qu'utilisateur activé pour l'entrepôt *24*.
1. Sélectionnez le menu **Entrant**.
1. Sélectionnez **Réception de ligne de commande fournisseur**.
1. Sélectionnez le champ **PONUM**, puis entrez le numéro de la commande fournisseur.
1. Confirmez votre entrée en sélectionnant le bouton de confirmation ( ✔ ) en bas de la page.
1. Entrez le numéro de ligne à partir de la commande fournisseur reçue. Sélectionnez le champ **LINENUM**, puis utilisez le pavé numérique pour entrer *1*.
1. Confirmez votre entrée.
1. Entrez la quantité à recevoir. Cliquez deux fois sur le bouton signe plus (**+**) pour augmenter la valeur du champ **Qté** à *2*.
1. Enregistrez votre entrée en sélectionnant le bouton ( ✔ ) en bas de la page, puis confirmez votre entrée en sélectionnant à nouveau le bouton ( ✔ ).
1. Affichez les informations sur la page **Commandes fournisseur : Placer**. Cette page montre le travail qui a été créé pour le rangement (travail 1).

    L'emplacement de rangement de l'article reçu, le contenant, l'article, la taille et la quantité de la tâche **Réception de ligne de commande fournisseur** que vous venez de terminer s'affichent.

1. Confirmez le travail de rangement.
1. Répétez les étapes 4 à 11 pour la ligne de commande fournisseur 2. Cependant, à l'étape 8, spécifiez une quantité de *1*.

    Un nouveau travail de rangement (travail 2) est créé pour le même emplacement que le travail 1.

1. Répétez à nouveau les étapes 4 à 11 pour la ligne de commande fournisseur 2. À l'étape 8, spécifiez une quantité restante de *1*.

    Un nouveau travail de rangement (travail 3) est créé pour le même emplacement que le travail 1 et le travail 2. Ce comportement se produit car la stratégie de l'instruction d'emplacement *Consolider* est utilisée, et l'organisateur **Association de dimensions de produit autorisée** dans la configuration **Profils d'emplacement** *BULK* autorise l'association de la variante **Taille** dans un emplacement.

1. Répétez les étapes 4 à 11 pour la ligne de commande fournisseur 3. À l'étape 8, spécifiez une quantité de *1* pour le numéro d'article *A0001*.

    Un nouveau travail de rangement (travail 4) est créé pour un emplacement différent de celui utilisé pour les lignes de commande fournisseur 1 et 2. Ce comportement se produit car le profil d'emplacement n'autorise pas les produits mixtes, mais il autorise les dimensions mixtes du même produit générique.

1. Sélectionnez le bouton Menu en haut de la page (parfois appelé hamburger ou bouton hamburger), puis sélectionnez **Annuler** pour quitter **Réception de ligne de commande fournisseur**.

> [!TIP]
> Vous pouvez répéter ce scénario, mais cette fois-ci, définissez **Taille** - *Non* dans l'organisateur **Autoriser l'association de dimensions de produit** de la configuration **Profils d'emplacement** *BULK*, afin qu'aucune des dimensions de produit ne puisse être associée. Dans ce cas, lorsque vous recevez la commande fournisseur, chaque variante de produit est placée dans un nouvel emplacement.