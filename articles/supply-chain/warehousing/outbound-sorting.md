---
title: Tri sortant
description: Cette rubrique fournit des informations sur le tri sortant. Cette fonctionnalité facilite la manipulation des petits conteneurs et aide les employés d’entrepôt à mieux planifier et organiser la capacité des palettes dans le camion.
author: Mirzaab
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPack, WHSOutboundSortTemplate, WHSOutboundSortPositionAssignments, WHSLocationType, WHSLoactionProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 3c576209a86f776ac424f7fb9f2b606bea774a67
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828392"
---
# <a name="outbound-sorting"></a>Tri sortant

[!include [banner](../includes/banner.md)]

Cette fonctionnalité facilite la manipulation des petits conteneurs et aide les employés d’entrepôt à mieux planifier et organiser la capacité des palettes dans le camion. Lorsque vous utilisez le tri sortant, vous pouvez trier les conteneurs emballés sur la palette appropriée après leur arrivée dans une station de conditionnement. Vous pouvez également créer une hiérarchie de conditionnement.

Cette fonctionnalité vous permet de créer des palettes à partir de conteneurs emballés via la fonctionnalité d’emballage. Le conteneur n’est pas envoyé au lieu d’expédition final car il se trouve dans le flux d’emballage d’origine. Au lieu de cela, les employés peuvent fermer le conteneur et le déplacer vers un emplacement de type de tri. Ils peuvent ensuite trier les conteneurs dans des emplacements, chacun ayant un contenant (LP, License Plate). Une fois que les conteneurs ont été triés, un travail peut être créé pour envoyer l’ensemble de la LP au quai d’expédition final ou aux emplacements intermédiaires, en fonction des directives d’emplacement ou de vos propres besoins. De plus, l’action de fermer la position de tri peut immédiatement déplacer le stock vers le lieu d’expédition final et le prélever pour la commande.

## <a name="turn-on-the-outbound-sorting-feature"></a>Activer la fonction de tri sortant

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonction :** *Tri sortant*

## <a name="setup"></a>Paramétrage

Pour ce scénario, vous devez utiliser les données de démonstration **USMF** standard et l’entrepôt *62*. Vous devez également mener à bien la configuration décrite dans les sous-sections suivantes.

### <a name="set-up-a-wave-template"></a>Paramétrage d’un modèle de vague

Cette configuration traite automatiquement la vague et crée le travail lorsqu’une ligne est libérée pour l’entrepôt.

1. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.
1. Dans la liste des modèles, sélectionnez **Entrepôt 62**.
1. Dans l’organisateur **Général**, assurez-vous que l’option **Traiter la vague à la libération dans l’entrepôt** est définie sur *Oui*.

### <a name="set-up-a-worker"></a>Paramétrer un employé

La station d’emballage est considérée comme un emplacement. Les employés de l’entrepôt qui se connectent à la station d’emballage ne voient et ne travaillent que sur les expéditions et les conteneurs prévus à cet emplacement de conditionnement spécifique. Un utilisateur qui se connecte à Microsoft Dynamics 365 doit être configuré en tant qu’employé dans la gestion d’entrepôt. Si le nom de l’utilisateur n’apparaît pas dans la liste des utilisateurs employés, appliquez la procédure suivante pour l’ajouter.

> [!NOTE]
> Ces étapes supposent que l’utilisateur existe déjà dans le système et a été associé en tant qu’employé ou travailleur dans le module **Human Resources**.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Employé**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **Employé**, sélectionnez l’utilisateur cible dans la liste des employés.
1. Cliquez sur **Sélectionner**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans l’organisateur **Utilisateurs**, sélectionnez **Nouveau** pour créer un compte d’appareil mobile et définissez pour lui les valeurs suivantes :

    - **ID utilisateur :** entrez un ID unique.
    - **Nom d’utilisateur :** entrez un nom pour l’ID.
    - **Entrepôt par défaut :** *62*
    - **Nom du menu :** *Principal*

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. La boîte de dialogue **Définir le mot de passe** s’affiche ; vous pouvez y créer un mot de passe simple que l’utilisateur utilisera pour se connecter à l’application mobile. Définissez les valeurs suivantes :

    - **Mot de passe :** entrez un mot de passe simple.
    - **Confirmer le mot de passe :** saisissez à nouveau le même mot de passe.

1. Sélectionnez **Définir le mot de passe**.

    Une notification dans le centre d’action vous informe que le mot de passe a été défini pour l’utilisateur que vous avez créé.

### <a name="create-a-location-type"></a>Créer un type d’emplacement

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Types d’emplacements**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un type d’emplacement et définissez-lui les valeurs suivantes :

    - **Type d’emplacement :** *TRI*
    - **Description :** *Tri*

1. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="set-up-warehouse-management-parameters"></a>Définir les paramètres de gestion des entrepôts

1. Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.
1. Dans l’onglet **Général**, dans l’organisateur **Types d’emplacement**, définissez le champ **Type d’emplacement de tri** sur *TRI*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="set-up-a-location-profile"></a>Définir un profil d’emplacement

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d’emplacement**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans l’en-tête, définissez les valeurs suivantes :

    - **ID de profil d’emplacement :** *Tri*
    - **Nom :** *Tri*

1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - **Format de l’emplacement :** *ASRB* (Aisle-Rack-Shelf-Bin [Allée, Rayon, Étagère, Casier])
    - **Type d’emplacement :** *TRI*
    - **Utiliser le suivi du contenant :** *Oui*
    - **Autoriser les articles mixtes :** *Oui* (Lorsque vous définissez cette option sur *Oui*, l’option **Autoriser les traitement par lots de stock mixtes** est automatiquement définie sur *Oui* et ne peut pas être modifiée indépendamment.)

1. Sélectionnez **Enregistrer**.

### <a name="set-up-a-location"></a>Définir un emplacement

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Emplacements**.
1. Dans l’en-tête, décochez la case **Générer des chiffres de contrôle pour l’emplacement**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un emplacement et définissez-lui les valeurs suivantes :

    - **Entrepôt :** *62*
    - **Emplacement :** *SORT*
    - **ID de profil d’emplacement :** *TRI*

1. Sélectionnez **Enregistrer**.

### <a name="set-up-an-outbound-sorting-template"></a>Configurer un modèle de tri sortant

Le modèle de tri sortant détermine si le travail est créé à partir de l’emplacement de tri et si le tri est effectué manuellement ou automatiquement.

Pour ce scénario, vous allez créer un modèle de tri sortant pour composer des palettes après la station de conditionnement.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Emballage \> Modèles de tri sortants**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans l’en-tête du nouveau modèle, définissez les valeurs suivantes :

    - **ID du modèle de tri sortant :** *AutoWork*
    - **Description :** *Création de travail automatique*
    - **Type de modèle de tri sortant :** *Conteneur*
    - **Entrepôt :** *62*
    - **Emplacement :** *SORT*

1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - **Vérification du tri :** *Analyse de position*
    - **Créer un travail à la clôture de la position :** *Oui*

        Si cette option est définie sur *Oui*, un travail sera créé à la clôture de la position pour déplacer le stock vers l’emplacement d’expédition final. Si cette option est définie sur *Non*, le stock sera immédiatement prélevé pour la commande au moment de la clôture de la position.

    - **Affectation de position :** *Automatique*

        Si ce champ est défini sur *Manuel*, l’utilisateur doit toujours indiquer la position de destination de tri du stock. S’il est défini sur *Automatique*, le système guidera automatiquement le stock vers une position chaque fois que cela est possible, selon les répartitions du modèle de tri.

1. Sélectionnez **Enregistrer** pour rendre le bouton **Modifier la requête** disponible dans le volet Actions.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans l’éditeur de requêtes, dans l’onglet **Tri**, ajoutez une ligne comportant les valeurs suivantes :

    - **Table :** *Expéditions*
    - **Table dérivée :** *Expéditions*
    - **Champ :** *Service de transporteur*

        Quand vous sélectionnez cette valeur, le message suivant peut s’afficher : « Le champ Service de transporteur n’est pas un champ d’index. Voulez-vous ajouter un tri à ce sujet ? » Cliquez sur **Oui**.

    - **Ordre de tri :** *Croissant*

1. Cliquez sur **OK**.
1. Le message suivant peut s’afficher : « Le regroupement sera réinitialisé, continuer ? » Cliquez sur **Oui**.

    Le bouton **Répartitions du modèle de tri sortant** du volet Actions devient disponible.

1. Dans le volet Actions, sélectionnez **Répartitions du modèle de tri sortant**.
1. Dans la boîte de dialogue **Critères du tri sortant**, définissez les valeurs suivantes :

    - **Nom de la table de référence :** *Expéditions*
    - **Nom du champ de référence :** *Service de transporteur*
    - **Grouper par domaine :** cochez cette case pour regrouper les envois par service de transporteur.

1. Sélectionnez **OK** pour enregistrer vos paramètres et fermer la boîte de dialogue.

### <a name="set-up-container-packing-policies"></a>Définir des stratégies d’emballage de conteneurs

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Conteneurs \> Stratégies d’emballage de conteneurs**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans l’en-tête de la nouvelle stratégie, définissez les valeurs suivantes :

    - **Stratégie d’emballage de conteneur :** *Trier*
    - **Description :** *Tri*

1. Dans l’organisateur **Vue d’ensemble**, définissez les valeurs suivantes :

    - **Entrepôt :** *62*
    - **Emplacement de tri par défaut :** *TRI*
    - **Unité de poids :** *kg*
    - **Stratégie de fermeture des conteneurs :** *Libération automatique*
    - **Stratégie de libération des conteneurs :** *Attribuer le conteneur à une position de tri sortant*

1. Sélectionnez **Enregistrer**.

### <a name="set-up-packing-profiles"></a>Paramétrer les profils de conditionnement

Créez un nouveau profil d’emballage qui sera utilisé avec la fonctionnalité de tri.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Emballage \> Profils d’emballage**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une ligne et définissez-lui les valeurs suivantes :

    - **ID du profil d’emballage :** *Tri*
    - **Description :** *Tri*
    - **Stratégie d’emballage de conteneur :** *Trier*
    - **Mode d’identification du conteneur :** *Auto*
    - **Type de conteneur :** *Boîte-Large*
    - **Créer automatiquement un conteneur à la fermeture du conteneur :** Décoché (= *Non*)

1. Sélectionnez **Enregistrer**.

### <a name="set-up-work-classes"></a>Définir des classes de travail

Définissez une classe de travail qui sera utilisée avec le tri.

1. Accédez à **Gestion des entrepôts \> Configuration \> Travail \> Classes de travail**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une classe de travail pour le tri et définissez-lui les valeurs suivantes :

    - **ID classe de travail :** *Tri*
    - **Description :** *Tri*
    - **Type d’ordre de travail :** *Prélèvement de stock trié*

1. Sélectionnez **Enregistrer**.

### <a name="set-up-mobile-device-menu-items"></a>Configurer des éléments de menu d’appareil mobile

#### <a name="set-up-a-new-pallet-menu-item"></a>Configurer un nouvel élément de menu de palette

Créez un élément de menu d’appareil mobile pour composer des palettes pendant le tri.

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans l’en-tête, définissez les valeurs suivantes :

    - **Nom de l’élément de menu :** *Composition de palette*
    - **Titre :** *Composition de palette*
    - **Mode :** *Indirect*
    - **Utiliser un travail existant :** *Non*

1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - **Code d’activité :** *Tri sortant*

        Lorsque ce champ est défini sur *Tri sortant*, le champ **ID du modèle de tri sortant** s’affiche.

    - **Utiliser le guide de processus :** *Oui*

        Quand le champ **Code d’activité** est défini sur *Tri sortant*, cette option est automatiquement définie sur *Oui*.

    - **ID du modèle de tri sortant :** *AutoWork*

1. Sélectionnez **Enregistrer**.

#### <a name="set-up-a-new-loading-menu-item"></a>Configurer un nouvel élément de menu de chargement

Ensuite, créez un élément de menu qui permet aux utilisateurs de déplacer les articles en stock triés vers le lieu d’expédition.

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans l’en-tête, définissez les valeurs suivantes :

    - **Nom de l’élément de menu :** *Charger à partir du tri*
    - **Titre :** *Charger à partir du tri*
    - **Mode :** *Travail*
    - **Utiliser un travail existant :** *Oui*

1. Sur l’organisateur **Général**, définissez le champ **Dirigé par** sur *Dirigé par l’utilisateur*.
1. Dans l’organisateur **Classes de travail**, sélectionnez **Nouveau**, puis définissez les valeurs suivantes :

    - **ID classe de travail :** *TRI*
    - **Type d’ordre de travail :** *Prélèvement de stock trié*

1. Sélectionnez **Enregistrer**.

### <a name="set-up-the-mobile-device-menu"></a>Configurer le menu de l’appareil mobile

Vous devez maintenant ajouter les nouveaux éléments de menu au menu de l’appareil mobile.

1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d’appareil mobile**.
1. Sélectionnez le menu **Sortant**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans la colonne **Menus et éléments de menu disponibles**, recherchez et sélectionnez **Composition de palette**.
1. Sélectionnez le bouton en forme de flèche vers la droite pour déplacer **Composition de palette** vers la colonne **Structure du menu**.
1. Utilisez les boutons en forme de flèche vers le haut et le bas pour placer l’élément de menu **Composition de palette** à la position souhaitée dans le menu de l’appareil mobile.
1. Sélectionnez **Enregistrer**.
1. Répétez cette procédure pour ajouter l’élément de menu **Charger à partir du tri** au menu **Sortant**.

### <a name="set-up-location-directives"></a>Définir des instructions d’emplacement

Les *Instructions d’emplacement* sont des règles qui aident à identifier les emplacements de prélèvement et de rangement pour le mouvement du stock. Vous devez maintenant créer une règle pour gérer le travail de tri.

#### <a name="set-up-a-single-sku-directive"></a>Paramétrer une instruction relative à une seule SKU

1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.
1. Dans le volet de gauche, modifiez la valeur du champ **Type d’ordre de travail** sur *Prélèvement de stock trié*.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans l’en-tête, définissez les valeurs suivantes :

    - **Séquence :** *1*
    - **Nom :** *Baydoor*

1. Dans l’organisateur **Directives d’emplacement**, définissez les valeurs suivantes :

    - **Type de travail :** *Put*
    - **Site :** *6*
    - **Entrepôt :** *62*
    - **Plusieurs SKU :** *Non*

1. Sélectionnez **Enregistrer** pour rendre la barre d’outils dans l’organisateur **Lignes** disponible.
1. Dans l’organisateur **Lignes**, sélectionnez **Nouveau**, puis définissez les valeurs suivantes pour la nouvelle ligne. Acceptez les valeurs par défaut dans tous les autres champs.

    - **Séquence :** *1*
    - **De :** *0*
    - **À :** *1 000 000*

1. Sélectionnez **Enregistrer** pour rendre la barre d’outils dans l’organisateur **Actions d’instruction d’emplacement** disponible.
1. Dans l’organisateur **Actions d’instruction d’emplacement**, sélectionnez **Nouveau**, puis définissez les valeurs suivantes pour la nouvelle ligne. Acceptez les valeurs par défaut dans tous les autres champs.

    - **Séquence :** *1*
    - **Nom :** *Baydoor*

1. Sélectionnez **Enregistrer**.
1. Dans l’organisateur **Actions de directive d’emplacement**, sélectionnez **Modifier la requête**.
1. Dans l’éditeur de requêtes, dans l’onglet **Plage**, recherchez la ligne où le champ **Domaine** est défini sur *Emplacement*. Définissez le champ **Critères** de cette ligne sur *Porte baie*.
1. Sélectionnez **OK** pour enregistrer vos paramètres et fermer l’éditeur de requêtes.

#### <a name="set-up-a-multiple-sku-directive"></a>Paramétrer une instruction relative à plusieurs SKU

1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.
1. Dans le volet de gauche, modifiez la valeur du champ **Type d’ordre de travail** sur *Prélèvement de stock trié*.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans l’en-tête, définissez les valeurs suivantes :

    - **Séquence :** *2*
    - **Nom :** *Porte baie Multi*

1. Dans l’organisateur **Directives d’emplacement**, définissez les valeurs suivantes :

    - **Type de travail :** *Put*
    - **Site :** *6*
    - **Entrepôt :** *62*
    - **Plusieurs SKU :** *Oui*

1. Sélectionnez **Enregistrer** pour rendre la barre d’outils dans l’organisateur **Lignes** disponible.
1. Dans l’organisateur **Lignes**, sélectionnez **Nouveau**, puis définissez les valeurs suivantes pour la nouvelle ligne. Acceptez les valeurs par défaut dans tous les autres champs.

    - **Séquence :** *1*
    - **De :** *0*
    - **À :** *1 000 000*

1. Sélectionnez **Enregistrer** pour rendre la barre d’outils dans l’organisateur **Actions d’instruction d’emplacement** disponible.
1. Dans l’organisateur **Actions d’instruction d’emplacement**, sélectionnez **Nouveau**, puis définissez les valeurs suivantes pour la nouvelle ligne. Acceptez les valeurs par défaut dans tous les autres champs.

    - **Séquence :** *1*
    - **Nom :** *Porte baie Multi*

1. Sélectionnez **Enregistrer**.
1. Dans l’organisateur **Actions de directive d’emplacement**, sélectionnez **Modifier la requête**.
1. Dans l’éditeur de requêtes, dans l’onglet **Plage**, recherchez la ligne où le champ **Domaine** est défini sur *Emplacement*. Définissez le champ **Critères** de cette ligne sur *Porte baie*.
1. Sélectionnez **OK** pour enregistrer vos paramètres et fermer l’éditeur de requêtes.

### <a name="set-up-work-templates"></a>Définir des modèles de travail

1. Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.
1. Modifiez la valeur du champ **Type d’ordre de travail** sur *Prélèvement de stock trié*.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un modèle de travail.
1. Dans l’onglet **Vue d’ensemble**, définissez les valeurs suivantes :

    - **Séquence :** *1*
    - **Modèle de travail :** *Tri*
    - **Description du modèle de travail :** *Tri*

1. Sélectionnez **Enregistrer** pour rendre l’organisateur **Détails du modèle de travail** disponible.
1. Dans l’organisateur **Détails du modèle de travail**, sélectionnez **Nouveau** pour ajouter une ligne, puis définissez les valeurs suivantes pour celle-ci :

    - **Type de travail :** *Choisir*
    - **ID classe de travail :** *TRI*

1. Sélectionnez à nouveau **Nouveau** pour ajouter une deuxième ligne, puis définissez les valeurs suivantes pour elle :

    - **Type de travail :** *Put*
    - **ID classe de travail :** *TRI*

1. Sélectionnez **Enregistrer**.

## <a name="scenario"></a>Scénario

Ce scénario simule une situation dans laquelle les conteneurs emballés doivent être automatiquement triés vers différentes positions (palettes) après la station d’emballage, en fonction du service du transporteur. Une fois que tous les articles du chargement sont emballés et triés par adresse, les palettes seront déplacées vers la porte de la baie.

### <a name="create-sales-orders-and-picking-work"></a>Créer des commandes client et des travaux de prélèvement

#### <a name="create-sales-order-1"></a>Créer une commande client 1

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Compte client :** *US-005*
    - **Entrepôt :** *62*

1. Sélectionnez **OK** pour fermer la boîte de dialogue.

    La nouvelle commande client est ouverte.

1. Basculez sur la vue **En-tête**.
1. Sur l’organisateur **Livraison**, dans la section **Transport**, définissez les valeurs suivantes :

    - **Transporteur :** *Fret aérien*
    - **Service de transporteur :** *Air*

1. Revenez à la vue **Lignes**.
1. Si aucune nouvelle ligne n’est ajoutée automatiquement à la grille dans l’organisateur **Lignes de commande client**, sélectionnez **Ajouter une ligne** pour en ajouter une.
1. Dans la nouvelle ligne de commande, définissez les valeurs suivantes :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *2*

1. Alors que la nouvelle ligne de commande est toujours sélectionnée dans l’organisateur **Lignes de commande client**, dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.
1. Sur la page **Réservation**, sélectionnez **Réserver un lot** pour réserver la quantité complète de la ligne sélectionnée dans l’entrepôt.
1. Fermez la page **Réservation** pour revenir à la commande client.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.
1. Vous recevez un message d’information indiquant l’expédition et la vague de cette commande. Notez le numéro d’identification de la vague et les numéros d’identification d’expédition.

#### <a name="sales-order-2"></a>Commande client 2

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Compte client :** *US-006*
    - **Entrepôt :** *62*

1. Sélectionnez **OK** pour fermer la boîte de dialogue.
1. La nouvelle commande client est ouverte. Elle doit inclure une nouvelle ligne vide dans la grille de l’organisateur **Lignes de commande client**. Sur cette ligne de commande, définissez les valeurs suivantes :

    - **Article :** *A0001*
    - **Quantité :** *1*

1. Dans le raccourci **Détails de ligne**, sur l’onglet **Livraison**, définissez le champ **Mode de livraison** sur *Flowe-STD*.
1. Dans l’organisateur **Lignes de commande client**, sélectionnez **Ajouter une ligne**, puis définissez les valeurs suivantes pour la deuxième ligne de commande :

    - **Article :** *A0002*
    - **Quantité :** *1*

1. Dans le raccourci **Détails de ligne**, sur l’onglet **Livraison**, changez la valeur du champ **Mode de livraison** en *Air C-Air*.
1. Dans l’organisateur **Lignes de commande client**, sélectionnez la première ligne de commande. Ensuite, dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.
1. Sur la page **Réservation**, sélectionnez **Réserver un lot** pour réserver la quantité complète de la ligne sélectionnée dans l’entrepôt.
1. Fermez la page **Réservation** pour revenir à la commande client.
1. Dans l’organisateur **Lignes de commande client**, sélectionnez la deuxième ligne de commande. Ensuite, dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.
1. Sur la page **Réservation**, sélectionnez **Réserver un lot** pour réserver la quantité complète de la ligne sélectionnée dans l’entrepôt.
1. Fermez la page **Réservation** pour revenir à la commande client.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.
1. Vous recevez un message d’information indiquant l’expédition et la vague de cette commande. Notez que deux numéros d’identification de vague et deux numéros d’identification d’expédition ont été créés, un pour chaque mode de livraison des lignes de commande client.

#### <a name="get-the-work-ids-from-the-work-details"></a>Obtenir les ID de travail à partir des détails du travail

1. Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.
1. La page affiche les ID de travail créés à partir des commandes client. Utilisez les ID de vague et les ID d’expédition des commandes client que vous avez créées pour trouver l’ID de travail de chaque vague et expédition. Notez ces identificateurs de travail, car vous en aurez besoin dans les étapes suivantes. Notez que deux ID de travail ont été créés pour la deuxième commande client. Si différents articles sont sélectionnés à différents endroits, des ID sont générés avec des mots distincts.

### <a name="pick-items-for-the-sales-orders"></a>Prélever des articles pour les commandes client

Terminez le travail créé en utilisant l’appareil mobile pour déplacer les articles vers la station d’emballage.

1. Sur l’appareil mobile, connectez-vous à l’entrepôt *62* en utilisant l’ID utilisateur que vous avez créé pour ce scénario (ou l’ID utilisateur d’un utilisateur de démonstration existant).
1. Dans le menu principal, sélectionnez **Sortant**.
1. Dans le menu **Sortant**, sélectionnez **Prélèvement des ventes**.
1. Dans le champ **ID**, saisissez l’ID de travail qui a été créé pour la commande client 1.
1. Cliquez sur **OK**.
1. Dans la page **Commandes client - Prélever**, entrez une LP cible qui a été créé pour la commande client 1. Notez que l’emplacement du prélèvement (*bulk-001*), l’article (*A0001*) et la quantité (*2 pièces*) sont indiqués.
1. Cliquez sur **OK**.
1. Examinez les informations sur la page **Commandes client - Placer**. Le champ **Loc** doit indiquer que les articles sélectionnés vont à l’emplacement *Emballer*.
1. Cliquez sur **OK**.

    Dans la page **Scanner un ID de travail/ID de LP**, vous recevez un message « Travail terminé ׃, qui indique que l’ID de travail de la commande client 1 est terminé.

    Vous allez maintenant prélever la commande client 2.

1. Dans le champ **ID**, saisissez l’ID de travail qui a été créé pour la commande client 2, où la ligne 1 comporte l’article *A0001*.
1. Cliquez sur **OK**.
1. Dans la page **Commandes client - Prélever**, entrez une LP cible. Notez que l’emplacement du prélèvement (*bulk-001*), l’article (*A0001*) et la quantité (*1 pièces*) sont indiqués.
1. Cliquez sur **OK**.
1. Examinez les informations sur la page **Commandes client - Placer**. Le champ **Loc** doit indiquer que les articles sélectionnés vont à l’emplacement *Emballer*.
1. Cliquez sur **OK**.

    Dans la page **Scanner un ID de travail/ID de LP**, vous recevez un message « Travail terminé ». Ce message indique que l’ID de travail de la ligne 1 de la commande client 2 est terminé.

1. Dans le champ **ID**, saisissez l’ID de travail qui a été créé pour la commande client 2, où la ligne 2 comporte l’article *A0002*.
1. Cliquez sur **OK**.
1. Dans la page **Commandes client - Prélever**, entrez une LP cible. Notez que l’emplacement du prélèvement (*bulk-002*), l’article (*A0001*) et la quantité (*1 pièces*) sont indiqués.
1. Cliquez sur **OK**.
1. Examinez les informations sur la page **Commandes client - Placer**. Le champ **Loc** doit indiquer que les articles sélectionnés vont à l’emplacement *Emballer*.
1. Cliquez sur **OK**.

    Dans la page **Scanner un ID de travail/ID de LP**, vous recevez un message « Travail terminé ». Ce message indique que l’ID de travail de la ligne 2 de la commande client 2 est terminé.

### <a name="pack-sales-orders-into-containers"></a>Emballer des commandes client dans des conteneurs

#### <a name="pack-sales-order-1-into-containers"></a>Emballer la commande client 1 dans des conteneurs

1. Accédez à **Gestion d’entrepôt \> Emballage et conteneurisation \> Emballer**.

    La boîte de dialogue **Sélectionner une station de conditionnement** s’affiche. Par défaut, le champ **Employé** doit être défini sur le nom du travailleur que vous avez configuré précédemment.

1. Définissez les valeurs suivantes pour afficher et travailler sur les expéditions et les conteneurs qui sont planifiés à l’emplacement d’emballage concerné :

    - **Site :** *6*
    - **Entrepôt :** *62*
    - **Emplacement :** *Emballer*
    - **ID du profil d’emballage :** *Tri*

1. Sélectionnez **OK** pour fermer la boîte de dialogue.
1. Dans la page **Emballer**, dans le champ **Contenant ou expédition**, saisissez la LP cible pour la commande client 1. Sélectionnez ensuite la touche **Tab** ou **Entrée** de votre clavier pour quitter le champ.
1. Dans le volet Actions, sélectionnez **Nouveau conteneur**.
1. Acceptez tous les paramètres par défaut et sélectionnez **OK**. Prenez note de l’ID du conteneur.
1. Dans l’organisateur **Emballage de l’article**, définissez les valeurs suivantes :

    - **Quantité :** *1*
    - **Identificateur :** Article *A0001*

1. Dans le volet Actions, sélectionnez **Fermer le conteneur**.
1. Dans la boîte de dialogue **Fermer le conteneur**, sélectionnez **Obtenir le poids système** pour que le système mette à jour le champ **Poids brut**.
1. Cliquez sur **OK**. Le conteneur est déplacé vers l’emplacement *TRIER* et est prêt pour le tri.
1. Créez un deuxième conteneur pour ajouter le deuxième article à partir de la LP de la commande client 1 à un nouveau conteneur.
1. Dans le volet Actions, sélectionnez **Nouveau conteneur**.
1. Acceptez tous les paramètres par défaut et sélectionnez **OK**. Prenez note de l’ID du conteneur.
1. Dans l’organisateur **Emballage de l’article**, définissez les valeurs suivantes :

    - **Quantité :** *1*
    - **Identificateur :** Article *A0001*

1. Dans le volet Actions, sélectionnez **Fermer le conteneur**.
1. Dans la boîte de dialogue **Fermer le conteneur**, sélectionnez **Obtenir le poids système** pour que le système mette à jour le champ **Poids brut**.
1. Cliquez sur **OK**. Le conteneur est déplacé vers l’emplacement *TRIER* et est prêt pour le tri.

#### <a name="pack-sales-order-2-into-containers"></a>Emballer la commande client 2 dans des conteneurs

1. Dans la page **Emballer**, dans le champ **Contenant ou expédition**, saisissez la LP cible pour la ligne 1 de la commande client 2. Sélectionnez ensuite la touche **Tab** ou **Entrée** de votre clavier pour quitter le champ.
1. Dans le volet Actions, sélectionnez **Nouveau conteneur**.
1. Acceptez tous les paramètres par défaut et sélectionnez **OK**. Prenez note de l’ID du conteneur.
1. Dans l’organisateur **Emballage de l’article**, définissez les valeurs suivantes :

    - **Quantité :** *1*
    - **Identificateur :** Article *A0001*

1. Dans le volet Actions, sélectionnez **Fermer le conteneur**.
1. Dans la boîte de dialogue **Fermer le conteneur**, sélectionnez **Obtenir le poids système** pour que le système mette à jour le champ **Poids brut**.
1. Cliquez sur **OK**. Le conteneur est déplacé vers l’emplacement *TRIER* et est prêt pour le tri.
1. Dans le champ **Contenant ou expédition**, saisissez la LP cible pour la ligne 2 de la commande client 2. Sélectionnez ensuite la touche **Tab** ou **Entrée** de votre clavier pour quitter le champ.
1. Dans le volet Actions, sélectionnez **Nouveau conteneur**.
1. Acceptez tous les paramètres par défaut et sélectionnez **OK**. Prenez note de l’ID du conteneur.
1. Dans l’organisateur **Emballage de l’article**, définissez les valeurs suivantes :

    - **Quantité :** *1*
    - **Champ identificateur :** Article *A0002*

1. Dans le volet Actions, sélectionnez **Fermer le conteneur**.
1. Dans la boîte de dialogue **Fermer le conteneur**, sélectionnez **Obtenir le poids système** pour que le système mette à jour le champ **Poids brut**.
1. Cliquez sur **OK**. Le conteneur est déplacé vers l’emplacement *TRIER* et est prêt pour le tri.

Pour afficher les détails du conteneur, accédez à **Gestion d’entrepôt \> Emballage et conteneurisation \> Conteneurs** et recherchez les ID de conteneur créés lors de l’emballage.

### <a name="sort-the-containers"></a>Trier les conteneurs

> [!IMPORTANT]
> Lorsque vous accédez à l’élément de menu **Composition de palette** sur l’application mobile pour effectuer le tri sortant, vous voyez un bouton étiqueté **Complet**. *N’utilisez pas le bouton **Complet** pour trier ou fermer la position.*
>
> Le bouton **Complet** est fourni par défaut et ne peut pas être désactivé ou supprimé de la page. Il n’est pas utilisé pour la fonction *Tri sortant*.

#### <a name="sort-the-first-container"></a>Trier le premier conteneur

1. Sur l’appareil mobile, connectez-vous à l’entrepôt *62* en utilisant l’ID utilisateur que vous avez créé pour ce scénario (ou l’ID utilisateur d’un utilisateur de démonstration existant).
1. Dans le menu principal, sélectionnez **Sortant**.
1. Dans le menu **Sortant**, sélectionnez **Composition de palette**.
1. Dans le champ **LP/Cont**, entrez le premier ID de conteneur associé à la commande client 1.
1. Cliquez sur **OK**.
1. Étant donné qu’aucune position de tri n’existe actuellement, vous devez en spécifier une. Dans le champ **ID de position de tri**, entrez *SP01*.
1. Comme aucune LP n’est actuellement associée à la position de tri *SP01*, vous devez en spécifier une. Dans le champ **LP**, entrez *PLP01*.
1. Cliquez sur **OK**.
1. La validation de la position de tri étant activée, vous devez saisir à nouveau l’ID de position de tri. Dans le champ **ID de position de tri**, entrez *SP01*.
1. Cliquez sur **OK**.

    Vous recevez un message « Travail terminé ».

> [!TIP]
> Pour afficher la position de tri et la LP qu’elle contient, accédez à **Gestion d’entrepôt \> Emballage et conteneurisation \> Affectations de position de tri sortant**.
>
> La page **Affectations de position de tri sortant** affiche toutes les positions de tri actuellement actives. Le champ **Transactions de positions de tri** affiche la LP associée à chaque position de tri et les conteneurs qui se trouvent à la position de tri. Notez qu’une position de tri existe actuellement et que l’organisateur **Critères de position de tri** affiche un critère **Expédition - Service de transporteur - Aérien**.

#### <a name="sort-the-remaining-containers"></a>Trier les conteneurs restants

1. Sur l’appareil mobile, connectez-vous à l’entrepôt *62* en utilisant l’ID utilisateur que vous avez créé pour ce scénario (ou l’ID utilisateur d’un utilisateur de démonstration existant).
1. Dans le menu principal, sélectionnez **Sortant**.
1. Dans le menu **Sortant**, sélectionnez **Composition de palette**.
1. Dans le champ **LP/Cont**, entrez le deuxième ID de conteneur associé à la commande client 1.
1. Cliquez sur **OK**. Étant donné que le modèle de tri est configuré pour trier automatiquement et qu’une position de tri comportant des critères correspondants existe déjà, vous êtes automatiquement dirigé vers la position de tri correcte.
1. Cliquez sur **OK**.
1. Confirmez l’ID de la position de tri pour indiquer que le stock est au bon endroit. Dans le champ **ID de position de tri**, entrez *SP01*.
1. Cliquez sur **OK**.

    Le travail est terminé sur le deuxième conteneur de la commande client 1. Vous allez maintenant trier les conteneurs restants de la commande client 2.

1. Dans le champ **LP/Cont**, saisissez l’ID de conteneur du conteneur de la commande client 2 qui contient l’article *A0001*. Étant donné que le service de transporteur diffère, vous êtes invité à entrer une nouvelle position de tri et à affecter une LP à cette position. Utilisez la position de tri *SP02* et la LP *PLP02*.
1. Cliquez sur **OK**.
1. Confirmez la position de tri en saisissant *SP02* dans le champ **ID de position de tri**.
1. Cliquez sur **OK**.

    Le travail est terminé sur le conteneur.

1. Dans le champ **LP/Cont**, saisissez l’ID de conteneur pour le conteneur restant de la commande client 2 qui contient l’article *A0002*. Étant donné que le service de transporteur est le même que pour la commande client 1, le système affiche la position de tri existante qui a des critères correspondants.
1. Cliquez sur **OK**.
1. Confirmez la position de tri en saisissant *SP01* dans le champ **ID de position de tri**.
1. Cliquez sur **OK**.

    Le travail est terminé sur le conteneur.

### <a name="close-the-outbound-sorting-positions"></a>Fermer les positions de tri sortant

Lorsque tout le stock a été trié, la position doit être fermée avant que le travail ne puisse être créé. Un travail de prélèvement du stock trié sera créé pour apporter le stock à la porte de la baie.

#### <a name="close-a-position-from-the-mobile-device"></a>Fermer une position depuis l’appareil mobile

1. Sur l’appareil mobile, connectez-vous à l’entrepôt *62* en utilisant l’ID utilisateur que vous avez créé pour ce scénario (ou l’ID utilisateur d’un utilisateur de démonstration existant).
1. Dans le menu principal, sélectionnez **Sortant**.
1. Dans le menu **Sortant**, sélectionnez **Composition de palette**.
1. Dans le champ **LP/Cont**, entrez un ID de conteneur qui a été trié pour trier la position *SP01*.
1. Cliquez sur **OK**.
1. Le message suivant s’affiche : « Le conteneur est déjà trié à la position SP01. Fermer la position ? » Sélectionnez **Fermer**.

    Le travail est terminé.

#### <a name="close-a-position-from-outbound-sorting-position-assignments"></a>Fermer une position à partir des affectations de position de tri sortant

1. Accédez à **Gestion d’entrepôt \> Emballage et conteneurisation \> Affectations de position de tri sortant**.
1. Dans la colonne de gauche, sélectionnez **SP02**. Cette ligne de position de tri sortant est celle que vous fermerez.
1. Dans le volet Actions, sélectionnez **Fermer la position**. L’enregistrement de position de tri est fermé et n’est plus affiché.

    > [!TIP]
    > Pour afficher tous les enregistrements de positions fermées, cochez la case **Afficher fermées**.

### <a name="sorted-inventory-picking"></a>Prélèvement du stock trié

Vous devez terminer le travail de prélèvement du stock trié. Une fois terminé, le stock sera prélevé vers la commande client. À ce stade, tous les autres processus d’entrepôt s’appliquent.

1. Sur l’appareil mobile, connectez-vous à l’entrepôt *62* en utilisant l’ID utilisateur que vous avez créé pour ce scénario (ou l’ID utilisateur d’un utilisateur de démonstration existant).
1. Dans le menu principal, sélectionnez **Sortant**.
1. Dans le menu **Sortant**, sélectionnez **Charger à partir du tri**.
1. Entrez l’ID de la LP cible à partir de la première position de tri, *SP01*. Définissez le champ **ID** sur *PLP01*.
1. Cliquez sur **OK**.
1. La page **Prélèvement de stock trié : Prélever** affiche le travail de prélèvement qui doit être effectué. Choisissez l’emplacement *TRIER* et la LP cible *PLP01*, qui comporte plusieurs articles et une quantité de *3*.
1. Cliquez sur **OK**.
1. La page **Prélèvement de stock trié : Placer** affiche le travail de placement qui doit être effectué. Choisissez l’emplacement *Porte baie* et la LP cible *PLP01*, qui comporte plusieurs articles et une quantité de *3*.
1. Cliquez sur **OK**.

    Le travail est terminé.

1. Entrez l’ID du contenant cible à partir de la deuxième position de tri, *SP02*. Définissez le champ **ID** sur *PLP02*.
1. Cliquez sur **OK**.
1. La page **Prélèvement de stock trié : Prélever** affiche le travail de prélèvement qui doit être effectué. Choisissez l’emplacement *TRIER* et la LP cible *PLP02*, qui comporte plusieurs articles et une quantité de *1*.
1. Cliquez sur **OK**.
1. La page **Prélèvement de stock trié : Placer** affiche le travail de placement qui doit être effectué. Choisissez l’emplacement *Porte baie* et la LP cible *PLP02*, qui comporte plusieurs articles et une quantité de *1*.
1. Cliquez sur **OK**.

    Le travail est terminé.

À partir de ce stade, tous les autres processus d’entrepôt s’appliquent.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]