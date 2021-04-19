---
title: Regroupement des lignes de prélèvement
description: Cette rubrique fournit une vue d’ensemble du Regroupement des lignes de prélèvement.
author: Mirzaab
ms.date: 12/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: fe0e63ef742b7bfd09684a94d273a1841d24599c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828271"
---
# <a name="pick-line-grouping"></a>Regroupement des lignes de prélèvement

[!include [banner](../includes/banner.md)]

Le regroupement des lignes de prélèvement permet de combiner plusieurs lignes de travail qui ont le même article et le même emplacement en un seul prélèvement qui est présenté à l’utilisateur sur l’appareil mobile. Par conséquent, les magasiniers peuvent recevoir les instructions les plus efficaces, mais la séparation des lignes de travail requises (pour différents conteneurs, commandes, etc) peut toujours être maintenue dans le système.

## <a name="turn-on-the-pick-line-grouping-feature"></a>Activer la fonctionnalité de regroupement des lignes de prélèvement

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Regroupement des lignes de prélèvement*

## <a name="set-up-pick-line-grouping"></a>Configurer le regroupement des lignes de prélèvement

### <a name="create-a-mobile-device-menu-item"></a>Créer une option de menu d’appareil mobile

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Nom de l’élément de menu**, entrez *Prélèvement des lignes de groupe de vente*.
1. Dans le champ **Titre**, entrez *Prélèvement des lignes de groupe de vente*. Ce titre sera affiché sur le menu de l’appareil mobile.
1. Dans le champ **Mode**, sélectionnez *Travail*.
1. Définissez l’option **Utiliser un travail existant** sur *Oui*.
1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - Dans le champ **Dirigé par**, sélectionnez *Dirigé par l’utilisateur*.
    - Définissez l’option **Générer un contenant** sur *Oui*.
    - Définissez l’option **Prélèvement de groupe** sur *Oui*.
    - Acceptez les valeurs par défaut pour les options restantes.

1. Procédez comme suit pour configurer les classes de travail valides pour l’élément de menu de l’appareil mobile :

    1. Dans le raccourci **Classes de travail**, sélectionnez **Nouveau**.
    2. Dans le champ **ID de classe de travail**, vous pouvez sélectionner *Ventes* ou *Prélèvement CC*, en fonction de l’entrepôt que vous utiliserez. Pour ce scénario, sélectionnez *Prélèvement CC*.

        Le champ **Type d’ordre de travail** est automatiquement défini sur *Commandes client*.

### <a name="set-up-a-mobile-device-menu"></a>Configurer un menu d’appareil mobile

Procédez comme suit pour ajouter l’élément de menu que vous venez de créer au menu **Sortant**.

1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d’appareil mobile**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Le volet de liste affiche tous les menus existants de l’appareil mobile. Sélectionnez *Sortant* dans la liste.
1. Dans la liste **Menus et éléments de menu disponibles**, recherchez et sélectionnez l’élément de menu *Prélèvement de lignes de groupe de vente* que vous venez de créer.
1. Sélectionnez le bouton Flèche droite pour déplacer l’élément de menu *Prélèvement de lignes de groupe de vente* vers la liste **Structure du menu**.
1. Utilisez les boutons Flèche haut et Flèche bas pour déplacer l’élément de menu dans la position souhaitée de la structure du menu.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="set-up-a-work-template"></a>Définir un modèle de travail

1. Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.
1. Dans le champ **Type d’ordre de travail**, sélectionnez *Commandes client*.
1. Dans la grille **Vue d’ensemble**, recherchez et sélectionnez le modèle de travail à utiliser avec cette fonction. Pour ce scénario, sélectionnez le modèle *51 Prélever pour échelonner*.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requêtes, dans l’onglet **Tri**, sélectionnez **Ajouter**, puis définissez les valeurs suivantes pour la nouvelle ligne :

    - Dans la colonne **Table**, sélectionnez *Transactions de travail temporaire*.
    - Dans la colonne **Table dérivée**, sélectionnez *Transactions de travail temporaire*.
    - Dans la colonne **Champ**, sélectionnez *Numéro d’article*.
    - Dans la colonne **Direction de recherche**, sélectionnez *Ascendant*.

1. Sélectionnez **OK** pour fermer la boîte de dialogue et enregistrer votre sélection.
1. Le message suivant s’affiche : « Le regroupement sera réinitialisé, continuer ? » Sélectionnez **Oui** pour continuer.

> [!IMPORTANT]
> Pour que la fonctionnalité de regroupement des lignes de prélèvement fonctionne, les lignes de travail doivent être triées par ID article. Si les lignes qui ont les mêmes articles ne sont pas séquencées les unes après les autres, elles ne seront pas groupées.

## <a name="example"></a>Exemple

### <a name="create-picking-work"></a>Création de tâches de prélèvement

Avant de pouvoir configurer le regroupement des lignes de prélèvement, vous devez créer des travaux sortants éligibles.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau** pour créer une commande client.
1. Dans le champ **Compte client**, sélectionnez *US-004*.
1. Dans l’organisateur **Général**, dans le champ **Entrepôt**, sélectionnez *51*.
1. Cliquez sur **OK**.
1. Dans le raccourci **Lignes de commande client**, ajoutez les six lignes suivantes :

    - **Ligne 1 :** Dans le champ **Numéro d’article**, sélectionnez *M9200*. Dans le champ **Quantité**, entrez *3*.
    - **Ligne 2 :** Dans le champ **Numéro d’article**, sélectionnez *M9201*. Dans le champ **Quantité**, entrez *3*.
    - **Ligne 3 :** Dans le champ **Numéro d’article**, sélectionnez *M9202*. Dans le champ **Quantité**, entrez *2*.
    - **Ligne 4 :** Dans le champ **Numéro d’article**, sélectionnez *M9200*. Dans le champ **Quantité**, entrez *1*.
    - **Ligne 5 :** Dans le champ **Numéro d’article**, sélectionnez *M9200*. Dans le champ **Quantité**, entrez *3*.
    - **Ligne 6 :** Dans le champ **Numéro d’article**, sélectionnez *M9202*. Dans le champ **Quantité**, entrez *7*.

    Voici un résumé des quantités totales pour chaque article :

    - **Article M9200 :** *7* chacun
    - **Article M9201 :** *3* chacun
    - **Article M9202 :** *9* chacun

1. Avant de lancer les commandes à l’entrepôt, vous devez vous assurer que les emplacements de prélèvement disposent d’un stock suffisant pour tous les articles de toutes les commandes. Revoir le paramètre **Instruction d’emplacement** pour déterminer les emplacements de prélèvement utilisés pour le prélèvement des commandes client. Si vous utilisez l’environnement de données de démonstration de Contoso pour l’entrepôt *51*, confirmez que le stock est disponible.

    Vous devez maintenant réserver le stock pour chaque ligne.

1. Dans le raccourci **Lignes de commande client**, sélectionnez l’une des lignes à réserver.
1. Dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.
1. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour appliquer la réservation. Fermez ensuite la page.
1. Répétez les étapes 8 à 10 pour les lignes restantes qui doivent être réservées.

    Vous devez maintenant lancer la commande client dans l’entrepôt.

1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.

    Vous recevez un message indiquant qu’une expédition et une vague ont été créées et que la vague a été envoyée pour exécution dans un lot.

    Lorsque la vague et toutes les tâches en aval sont terminées, un ID de travail est créé pour le travail contenant six lignes. Les lignes sont triées par numéro d’article.

1. Accédez à **Gestion des entrepôts \> Travail \> Tout le travail** pour afficher le travail créé. Prenez note de la valeur **ID de travail**, car vous en aurez besoin dans la procédure suivante.

### <a name="initiate-picking-from-the-mobile-device"></a>Lancer le prélèvement à partir de l’appareil mobile

1. Connectez-vous à l’appareil mobile en tant qu’utilisateur activé pour l’entrepôt *51*.
1. Sur l’appareil mobile, sélectionnez le menu qui inclut la nouvelle option de menu appareil mobile. Pour ce scénario, sélectionnez **Sortant**.
1. Sélectionnez l’élément de menu **Prélèvement de lignes de groupe de vente** pour lancer le prélèvement.
1. Entrez la valeur **ID de travail** que vous avez notée dans la procédure précédente.

    Vous devriez voir une étape de prélèvement où toutes les lignes de prélèvement de l’article *M9200* sont regroupées, et vous devriez recevoir une instruction pour prélever *7* de chaque article *M9200*.

    > [!IMPORTANT]
    > Sur l’appareil mobile, le travail de prélèvement pour les trois lignes de travail de prélèvement a été regroupé en une seule étape de prélèvement pour l’utilisateur.

1. Confirmez l’étape de prélèvement.
1. Accédez à la page de travail de l’ID de travail et notez que les trois lignes de prélèvement de l’article *M9200* ont été clôturées simultanément.
1. Revenez à l’appareil mobile et continuez le prélèvement. La ligne de travail 4 de l’article *M9201* doit être présentée. Comme il n’y avait qu’une seule ligne de travail sur la commande, il n’y a rien à regrouper.
1. Confirmez l’étape de prélèvement.
1. La dernière étape de prélèvement sur l’appareil mobile regroupe les deux dernières lignes de prélèvement de l’ordre de travail.
1. Terminez l’étape de prélèvement pour *9* de chaque article *M9202*.
1. Confirmez l’étape de placement et toute autre paire prélèvement/placement pour terminer le travail.

> [!IMPORTANT]
>
> - Les lignes de travail ne peuvent être regroupées que si elles sont en séquence.
> - La fonctionnalité suivante n’est pas prise en charge :
>
>   - Articles en poids variable
>
>    S’il y a des articles en poids variable sur le travail, vous recevez un message d’erreur avant de commencer le prélèvement.
>
>   - Prélèvement de pièces
>   - Lignes de travail qui ont un travail de réapprovisionnement inachevé
>   - Prélèvement excessif
>   - Prélèvement partiel avec réaffectation des articles


[!INCLUDE[footer-include](../../includes/footer-banner.md)]