---
title: Mettre au mur - Mettre en magasin
description: Cette rubrique fournit des informations sur la fonctionnalité Mettre au mur - Mettre en magasin. Cette fonctionnalité vous permet de gérer des scénarios dans lesquels vous devez regrouper un produit dans une zone de préparation à l'emballage, en fonction de critères configurables. Elle accélère le prélèvement car elle permet de sélectionner un seul contenant cible et peut utiliser plus de positions de placement que le prélèvement de groupement.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationType, WHSLocationProfile, WHSLocation, WHSPackProfile, WHSWaveStepCode, WHSOutboundSortTemplate, WHSPostMethod, WHSWaveTemplateTable, WHSLocDirTable, WHSWorkClass, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 12501b90e4b31ec11e3c59784ace9fd9a8b7d934
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428223"
---
# <a name="put-to-wall---put-to-store"></a>Mettre au mur - Mettre en magasin

[!include [banner](../includes/banner.md)]

Le fonctionnalité *Mettre au mur - Mettre en magasin* vous permet de gérer des scénarios dans lesquels vous devez regrouper un produit dans une zone de préparation à l'emballage, en fonction de critères configurables. Étant donné que cette fonctionnalité permet de sélectionner un seul contenant cible et peut utiliser plus de positions de placement que le prélèvement de groupement, les entreprises qui expédient vers des magasins ou manipulent de petits articles bénéficieront d'un temps de prélèvement réduit.

Le flux de travail de cette fonctionnalité dirige le produit prélevé vers un emplacement de tri pour le répartir dans différents types de conteneurs. En règle générale, chaque emplacement de tri comprend plusieurs positions de tri. Chaque position de tri est affectée selon les critères définis par le processus métier. Les critères typiques sont la destination finale, l'expédition ou le chargement. Après l'arrivée d'un produit, il est distribué à chaque position de tri, en fonction de la quantité associée à la commande, à la destination, à l'expédition ou au chargement. Lorsqu'un conteneur est plein ou complet, il est déplacé vers un lieu de transit ou un lieu d'expédition en vue d'une manipulation ultérieure, en fonction du processus métier.

Cette fonctionnalité d'entreposage est également désignée par d'autres noms, tels que « put-to-light » et « break opens ».

## <a name="turn-on-the-outbound-sorting-feature"></a>Activer la fonction de tri sortant

Avant de pouvoir utiliser la fonctionnalité *Mettre au mur - Mettre en magasin*, la fonctionnalité *Tri sortant* doit être activée dans votre système. Les administrateurs peuvent utiliser l'espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonction :** *Tri sortant*

La fonctionnalité *Tri sortant* peut être utilisée en conjonction avec la fonctionnalité *Code étape de vague à l'échelle de l'organisation* si elle est activée. Vous devez également activer cette fonction si vous comptez utiliser des codes prédéfinis qui sont configurés dans des codes d'étape de vague. Dans l'espace de travail **Gestion des fonctionnalités**, cette fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Code étape de vague à l'échelle de l'organisation*

## <a name="setup"></a>Paramétrage

Pour cette démonstration, nous utilisons les données standard et l'entrepôt Contoso *62*. Certains ajouts mentionnés plus loin sont également utilisés.

### <a name="location-type"></a>Type d’emplacement

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Types d'emplacements**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un type d'emplacement pour le tri.
1. Définissez les valeurs suivantes :

    - **Type d’emplacement :** *TRI*
    - **Description :** *Tri*

1. Sélectionnez **Enregistrer**.

### <a name="warehouse-management-parameters"></a>Paramètres de gestion des entrepôts

1. Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.
1. Dans l'onglet **Général**, dans l'organisateur **Types d'emplacement**, définissez le champ **Type d'emplacement de tri**, entrez *TRI*.
1. Sélectionnez **Enregistrer**.

### <a name="location-profile"></a>Profil d'emplacement

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d'emplacement**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un profil d'emplacement pour l'emplacement de tri.
1. Dans l'en-tête, définissez les valeurs suivantes :

    - **ID de profil d'emplacement :** *Tri*
    - **Nom :** *Trie*

1. Dans l'organisateur **Général**, définissez les valeurs suivantes :

    - **Format de l'emplacement :** *EMBALLER*
    - **Type d’emplacement :** *TRI*
    - **Utiliser le suivi du contenant :** *Oui*
    - **Autoriser les articles mixtes :** *Oui*
    - **Autoriser les statuts de stock mixtes :** *Oui*

1. Sélectionnez **Enregistrer**.

### <a name="locations"></a>Emplacements

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Emplacements**.
1. Décochez la case **Générer des chiffres de contrôle pour l'emplacement**.
1. Dans le volet Actions, sélectionnez **Nouveau**, puis définissez les valeurs suivantes :

    - **Entrepôt :** *62*
    - **Emplacement :** *Tri*
    - **ID de profil d'emplacement :** *Tri*

1. Sélectionnez **Enregistrer**.

### <a name="packing-profiles"></a>Profils d'emballage

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Emballage \> Profils d'emballage**.
1. Dans le volet Actions, sélectionnez **Nouveau**, puis définissez les valeurs suivantes :

    - **ID du profil d'emballage :** *Tri*
    - **Description :** *Tri*
    - **Stratégie d'emballage de conteneur :** laissez ce champ vide.
    - **Mode d'identification du conteneur :** *Auto*
    - **Type de conteneur :** *PALETTE 48X48*
    - **Créer automatiquement un conteneur à la clôture du conteneur :** laissez ce champ vide.

1. Sélectionnez **Enregistrer**.

### <a name="wave-step-codes"></a>Codes étape de vague

Si vous avez activé la fonction *Code étape de vague à l'échelle de l'organisation*, configurez le code suivant.

1. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Codes étape de vague**.
1. Dans le volet Actions, sélectionnez **Nouveau**, puis définissez les valeurs suivantes :

    - **Code étape de vague :** *Tri*
    - **Description étape de vague :** *Tri*
    - **Type étape de vague :** *Modèle de tri*

1. Sélectionnez **Enregistrer**.

### <a name="outbound-sorting-template"></a>Modèle de tri sortant

Le modèle de tri contrôle si des positions de tri sont créées, quels critères sont utilisés et d'autres attributs du processus de tri.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Emballage \> Modèles de tri sortants**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un modèle de tri.
1. Dans l’en-tête du nouveau modèle, définissez les valeurs suivantes :

    - **ID du modèle de tri sortant :** *Tri vague*
    - **Description :** *Tri vague*
    - **Type de modèle de tri :** *Demande de vague*

        Ce champ définit le processus pour lequel le modèle de tri est utilisé. Les valeurs disponibles sont les suivantes :

        - **Demande de vague** : le modèle de tri est utilisé pour le processus *Mettre au mur*. Ce type de modèle est utilisé pour contourner la station de conditionnement et traiter directement le stock en dehors de la vague. Vous ne pouvez utiliser ce type que si la méthode de traitement de vague **tri** est incluse dans le modèle de vague.
        - **Conteneur** : le modèle de tri est utilisé pour le processus *Composition de palette après emballage*. Ce type de modèle est utilisé pour traiter les conteneurs qui sont fermés à cette station de conditionnement et qui doivent être triés vers des palettes.

    - **Entrepôt :** *62*
    - **Emplacement :** *Tri*

1. Dans l'organisateur **Général**, définissez les valeurs suivantes :

    - **Vérification du tri :** *Analyse de position*

        Ce champ définit la vérification requise lors du tri. Les valeurs disponibles sont les suivantes :

        - None
        - Analyse de contenant
        - Analyse de position

    - **Créer un travail à la clôture de la position :** *Oui*

        Si cette option est définie sur *Oui*, un travail sera créé à la clôture de la position pour déplacer le stock vers l'emplacement d'expédition final. Si cette option est définie sur *Non*, le stock sera immédiatement prélevé pour la commande au moment de la clôture de la position.

    - **Affectation de position :** *Manuelle*

        Ce champ définit le type d'affectation de position. Les valeurs disponibles sont les suivantes :

        - **Manuelle** : l'utilisateur doit toujours indiquer la position de destination de tri du stock.
        - **Automatique** : le système guide automatiquement le stock vers une position chaque fois que cela est possible, selon les répartitions du modèle de tri.

    - **Critères d'affectation de position de tri :** *N'utiliser que des positions vides*

        Ce champ contrôle si le stock déjà présent sur les positions de tri sera pris en compte lors de l'affectation d'une position pour la demande. Les valeurs disponibles sont les suivantes :

        - **N'utiliser que des positions vides** : les positions auxquelles un stock est déjà associé seront prises en compte
        - **Supposer les positions vides** : tout stock déjà présent à a position sera ignoré lors de l'affectation. Toutes les positions disponibles seront utilisées.

    - **Code étape de vague :** *Tri*

        Si la fonction *Code étape de vague à l'échelle de l'organisation* est activée, le code étape de vague *Tri* doit également être configuré dans les codes étape de vague.

    - **Fermer automatiquement la position de tri :** *Oui*

        Si cette option est définie sur *Oui*, la position de tri sera automatiquement fermée une fois que tout le travail arrivant à la position aura été exécuté.

    - **Nombre de positions de tri :** *3*

        Ce champ définit le nombre maximum de positions de tri que le système créera.

    - **Préfixe de position de tri :** *SP-*

        Ce champ définit le préfixe que le système attribue avant le numéro de la position.

    - **Emballer automatiquement la position de tri :** *Oui*

        Si cette option est définie sur *Oui*, le stock à la position de tri sera emballé dans un conteneur une fois la position fermée.

    - **ID du profil d'emballage :** *Tri*

        Ce champ définit le profil d'emballage qui sera utilisé lorsque la position de tri sera emballée dans un conteneur.

1. Dans le volet Actions, sélectionnez **Modifier la requête** pour spécifier les critères utilisés pour ce modèle de tri.
1. Dans la boîte de dialogue de la requête, dans l'onglet **Tri**, sélectionnez **Nouveau** pour ajouter une ligne, puis définissez les valeurs suivantes :

    - **Table :** *Détails du chargement*
    - **Table dérivée :** *Détails du chargement*
    - **Champ :** *ID expédition*
    - **Ordre de tri :** *Croissant*

1. Cliquez sur **OK**.
1. Le message suivant peut s'afficher : « Le regroupement sera réinitialisé, continuer ? » Cliquez sur **Oui**.

    Le bouton **Répartitions du modèle de tri sortant** du volet Actions devient disponible.

1. Dans le volet Actions, sélectionnez **Répartitions du modèle de tri sortant**.
1. Cochez la case **Grouper par domaine** pour regrouper par ID d'expédition.

    Ce paramètre créera une position de tri par expédition qui correspond à un conteneur dans la vague.

1. Cliquez sur **OK**.

### <a name="wave-process-methods"></a>Méthodes de traitement de la vague

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Vagues \> Méthodes de traitement de la vague**.
1. Dans le volet Actions, sélectionnez **Régénérer des méthodes**.

    La méthode **tri** est ajoutée à la liste des méthodes disponibles, et le type de modèle de vague *livraison* est sélectionné pour elle.

### <a name="wave-templates"></a>Modèles de vague

Modifiez le modèle de vague utilisé pour le tri de la demande de vague.

1. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.
1. Dans le champ **Type de modèle de vague**, sélectionnez *Expédition*.
1. Sélectionnez le modèle existant **Livraison 62 par défaut**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans l'organisateur **Général**, apportez les modifications suivantes :

    - Définissez l'option **Traiter la vague à la sortie dans l'entrepôt** sur *Non*.
    - Définissez l'option **Affecter à des vagues en cours** sur *Oui*.

1. Dans l'organisateur **Méthodes**, configurez la méthode **tri** :

    1. Dans la grille **Méthodes restantes**, sélectionnez **tri**.
    2. Sélectionnez le bouton Flèche droite pour déplacer la méthode **tri** vers la grille **Méthodes sélectionnées**.
    3. Dans la grille **Méthodes sélectionnées**, sélectionnez **tri**.
    4. Définissez le champ **Code étape de vague** sur *Trier*.

1. Sélectionnez **Enregistrer**.

### <a name="mobile-device-menu-items"></a>Options de menu d'appareil mobile

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d'appareil mobile**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans l'en-tête, définissez les valeurs suivantes :

    - **Nom de l'option de menu :** *Trier*
    - **Titre :** *Trier*
    - **Mode :** *Indirect*
    - **Utiliser un travail existant :** *Non*

1. Dans l'organisateur **Général**, définissez les valeurs suivantes :

    - **Code d'activité :** *Tri sortant*
    - **Utiliser le guide de processus :** *Oui* (valeur par défaut)
    - **ID du modèle de tri sortant :** *Tri vague*

1. Sélectionnez **Enregistrer**.

### <a name="mobile-device-menu"></a>Menu d'appareil mobile

1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d'appareil mobile**.
1. Dans la liste des menus, sélectionnez **Sortant**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans la grille **Menus et éléments de menu disponibles**, recherchez et sélectionnez l'élément de menu **Trier** que vous venez de créer.
1. Sélectionnez le bouton en forme de flèche vers la droite pour déplacer **Trier** vers la grille **Structure du menu**. De cette façon, vous ajoutez votre nouvel élément de menu au menu **Sortant**.
1. Sélectionnez **Enregistrer**.

### <a name="location-directives"></a>Instructions d'emplacement

Vous devez créer des directives d'emplacement pour guider le travail créé une fois le tri terminé.

1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d'emplacements**.
1. Dans le champ **Type d'ordre de travail**, sélectionnez *Prélèvement de stock trié*.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans l'en-tête, définissez les valeurs suivantes :

    - **Séquence :** *1*
    - **Nom :** *Placer à la porte baie*

1. Dans l’organisateur **Directives d’emplacement**, définissez les valeurs suivantes :

    - **Type de travail :** *Put*
    - **Site :** *6*
    - **Entrepôt :** *62*
    - **Code directif :** Laissez ce champ vide.
    - **Plusieurs SKU :** *Non*

1. Sélectionnez **Enregistrer** pour rendre l'organisateur **Lignes** disponible.
1. Dans l'organisateur **Lignes**, sélectionnez **Nouveau**, puis définissez les valeurs suivantes. Acceptez les valeurs par défaut dans tous les autres champs.

    - **Souche de N° :** *1*
    - **Quantité de départ :** *0*
    - **Quantité d'arrivée :** *1000000*

1. Sélectionnez **Enregistrer** pour rendre l'organisateur **Actions d'instruction d'emplacement** disponible.
1. Dans l'organisateur **Actions d'instruction d'emplacement**, sélectionnez **Nouveau**, puis définissez les valeurs suivantes. Acceptez les valeurs par défaut dans tous les autres champs.

    - **Souche de N° :** *1*
    - **Nom :** *Baydoor*

1. Sélectionnez **Enregistrer** pour rendre le bouton **Modifier la requête** de l'organisateur **Actions d'instruction d'emplacement** disponible.
1. Dans l’organisateur **Actions de directive d’emplacement**, sélectionnez **Modifier la requête**.
1. Dans la boîte de dialogue de la requête, dans l'onglet **Plage**, recherchez la ligne où le champ **Domaine** est défini sur *Emplacement*. Définissez le champ **Critères** de cette ligne sur *Porte baie*.
1. Cliquez sur **OK** pour confirmer les modifications.

### <a name="work-classes"></a>Classes de travail

1. Accédez à **Gestion des entrepôts \> Configuration \> Travail \> Classes de travail**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans l'en-tête, définissez les valeurs suivantes :

    - **ID classe de travail :** *Tri*
    - **Description :** *Tri*
    - **Type d'ordre de travail :** *Prélèvement de stock trié*

1. Sélectionnez **Enregistrer**.

### <a name="work-templates"></a>Modèles de travail

1. Accédez à **Gestion des entrepôts \> Travail \> Modèles de travail**.
1. Dans le champ **Type d’ordre de travail**, sélectionnez *Commandes client*.
1. Dans la grille, sélectionnez le modèle de travail **62 Prélever pour emballage**.
1. Dans le volet Actions, sélectionnez **Décompositions de l'en-tête de travail**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Sur la ligne où le champ **Nom de domaine** est défini sur *ID d'expédition*, décochez la case **Regrouper par ce champ**.
1. Sélectionnez **Enregistrer**, puis fermez la boîte de dialogue **Décompositions de l'en-tête de travail**.
1. Dans le champ **Type d'ordre de travail**, sélectionnez *Prélèvement de stock trié*.
1. Sélectionnez **Nouveau** pour créer un modèle de travail.
1. Dans la section **Vue d'ensemble**, définissez les valeurs suivantes : Acceptez les valeurs par défaut dans tous les autres champs.

    - **Modèle de travail :** *Prélèvement triés*
    - **Description du modèle de travail :** *Prélèvement triés*

1. Sélectionnez **Enregistrer** pour rendre la section **Détails du modèle de travail** disponible.
1. Dans la section **Détails du modèle de travail**, vous allez créer deux lignes. Sélectionnez **Nouveau**, puis définissez les valeurs suivantes pour la ligne 1 :

    - **Type de travail :** *Choisir*
    - **Obligatoire :** Sélectionné (=*Oui*)
    - **ID classe de travail :** *Tri*

1. Sélectionnez **Nouveau** à nouveau, puis définissez les valeurs suivantes pour la ligne 2 :

    - **Type de travail :** *Put*
    - **Obligatoire :** Sélectionné (=*Oui*)
    - **ID classe de travail :** *Tri*

1. Sélectionnez **Enregistrer**.

## <a name="example-scenario"></a>Exemple de scénario

Ce scénario simule une situation où l'entrepôt stocke de petits articles dans des emplacements et doit les emballer dans des boîtes avant de les expédier, et où la fonctionnalité de station de conditionnement n'est pas vraiment adaptée. Les travailleurs prélèvent les commandes pour plusieurs clients et différentes adresses en même temps pour augmenter la vitesse de prélèvement. Une fois le prélèvement terminé, les employés arrivent à l'emplacement du tri, où les articles prélevés peuvent être triés dans la bonne boîte, en fonction des critères requis. Dans cet exemple, l'ID d'expédition sera utilisé pour déterminer la boîte correcte, car chaque expédition a une adresse différente. Une fois que tous les articles du chargement sont emballés et triés par expédition, les boîtes sont déplacées vers la zone de transit et sont finalement chargées sur un camion.

Avant de démarrer le scénario, assurez-vous que toutes les fonctionnalités d'entrepôt standard sont correctement configurées pour votre entrepôt. Nous utilisons l'entrepôt standard Contoso *62* à cet effet. Les configurations standard n'ont pas été modifiées par rapport à ce qui est décrit dans la configuration.

### <a name="create-demand"></a>Créer une demande

Avant de pouvoir faire la démonstration de cette fonctionnalité, vous devez créer une demande. Pour ce scénario, vous allez créer trois commandes client pour trois clients différents afin de simuler différentes adresses de livraison. De cette manière, vous créerez trois expéditions distinctes.

Avant de créer des commandes client et des expéditions, assurez-vous que les emplacements de prélèvement disposent d'un stock suffisant pour tous les articles des commandes client. Examinez les paramètres des instructions d'emplacement pour vérifier les emplacements de prélèvement utilisés pour le prélèvement des commandes client. Si vous devez ajuster le stock, vous pouvez créer des mouvements manuels, utiliser le réapprovisionnement ou utiliser tout autre flux. Réservez ensuite le stock.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau** pour créer une commande client pour la commande 1.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Client :** *US-001*
    - **Entrepôt :** *62*

1. Cliquez sur **OK**.
1. Une nouvelle ligne est ajoutée à l'organisateur **Lignes de commande client**. Définissez les valeurs suivantes :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *5*

1. Sélectionnez **Ajouter une ligne** pour ajouter une deuxième ligne, puis définissez les valeurs suivantes :

    - **Numéro d’article :** *A0002*
    - **Quantité :** *10*

1. Répétez les étapes suivantes pour chaque ligne de la commande afin de réserver le stock qui y correspond :

    1. Sur l’organisateur **Lignes de commande client**, dans le menu **Stock**, sélectionnez **Réservation**.
    1. Dans la page **Réservation**, sélectionnez **Réserver un lot**, puis fermez la page.
    1. Sélectionnez **Enregistrer**.

1. Sélectionnez **Nouveau** pour créer une commande client pour la commande 2.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Client :** *US-004*
    - **Entrepôt :** *62*

1. Cliquez sur **OK**.
1. Une nouvelle ligne est ajoutée à l'organisateur **Lignes de commande client**. Définissez les valeurs suivantes :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *7*

1. Sélectionnez **Ajouter une ligne** pour ajouter une deuxième ligne, puis définissez les valeurs suivantes :

    - **Numéro d’article :** *A0002*
    - **Quantité :** *3*

1. Répétez les étapes suivantes pour chaque ligne de la commande afin de réserver le stock qui y correspond :

    1. Sur l’organisateur **Lignes de commande client**, dans le menu **Stock**, sélectionnez **Réservation**.
    1. Dans la page **Réservation**, sélectionnez **Réserver un lot**, puis fermez la page.
    1. Sélectionnez **Enregistrer**.

1. Sélectionnez **Nouveau** pour créer une commande client pour la commande 3.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Client :** *US-007*
    - **Entrepôt :** *62*

1. Cliquez sur **OK**.
1. Une nouvelle ligne est ajoutée à l'organisateur **Lignes de commande client**. Définissez les valeurs suivantes :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *8*

1. Procédez comme suit pour réserver le stock pour la ligne de commande :

    1. Sur l’organisateur **Lignes de commande client**, dans le menu **Stock**, sélectionnez **Réservation**.
    1. Dans la page **Réservation**, sélectionnez **Réserver un lot**, puis fermez la page.
    1. Sélectionnez **Enregistrer**.

Exécutez la procédure suivante pour libérer chaque commande client vers l'entrepôt. Trois expéditions différentes seront créées. Vous ajouterez ensuite les trois expéditions à une nouvelle vague.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Dans la grille, sélectionnez la première commande client que vous avez créée.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.

    Vous recevez un message d'information indiquant l'ID de vague et l'ID d'expédition ont été créés.

1. Répétez les étapes précédentes pour libérer les commandes client 2 et 3 vers l'entrepôt. Notez que le message d'information que vous recevez indique qu'une expédition a été ajoutée à la vague qui a été créée lorsque vous avez lancé la commande client 1.
1. Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.
1. Sélectionnez l'ID de vague qui a été créé à partir du lancement des commandes client pour ouvrir la page **Vagues**. Cette page affiche les détails de la vague. L'organisateur **Lignes de vague** affiche les expéditions qui ont été créées.

    Vous devez maintenant créer un travail pour apporter les articles des lieux de prélèvement au lieu de tri.

1. Dans le volet Actions, sélectionnez **Processus**.

    Pendant le traitement de la vague, la méthode de tri utilisera le modèle de tri pour affecter le stock aux positions de tri. Une fois le traitement de la vague terminé, vous recevez un message d'information indiquant que le travail a été créé et que la vague a été validée.

1. Dans le volet Actions, dans l'onglet **Vague**, dans le groupe **Informations connexes**, sélectionnez **Travail** pour afficher le travail créé. Prenez note de l'ID du travail.
1. Accédez à **Gestion d'entrepôt \> Emballage et conteneurisation \> Affectations de position de tri sortant**.
1. Dans la colonne de gauche, vous pouvez afficher la position de tri sortant qui a été créée pour chaque expédition.
1. Dans l'organisateur **Critères de position de tri**, vous pouvez afficher l'ID d'expédition pour cette position.

Un ID de travail a été créé pour apporter le stock des lieux de prélèvement au lieu de tri. Pour terminer le travail, vous aurez besoin de l'ID de travail qui aura été créé lors du traitement de la vague.

### <a name="sales-order-picking-to-the-sorting-location"></a>Prélèvement de la commande client vers le lieu de tri

1. Connectez-vous à l'application mobile en tant qu'employé de l'entrepôt *62*.
1. Dans le menu principal, sélectionnez **Sortant**.
1. Dans le menu **Sortant**, sélectionnez **Prélèvement des ventes**.
1. Sélectionnez le champ **ID**, puis entrez l'ID de travail du traitement de la vague.
1. Confirmez votre entrée.

    Vous êtes ensuite invité à entrer un contenant cible (LP). Notez que la ligne 1 de la commande client 1 correspond à ce qui doit être prélevé et ajouté au contenant cible. Le numéro d'article, la quantité, la description de l'article et l'emplacement du prélèvement sont affichés.

1. Dans le champ **LP cible**, entrez un numéro de contenant cible.

    Vous prélèverez toutes les lignes créées à partir de la vague traitée dans le même contenant cible.

1. Confirmez votre entrée.

    L'application mobile présente désormais une série de pages **Prélever** qui pointent vers le lieu de prélèvement et vers l'article et la quantité à prélever. Une fois l'article prélevé ajouté au contenant, vous confirmez le travail de prélèvement. La dernière page correspond au travail de placement des articles prélevés dans l'emplacement de tri.

1. Confirmez le premier travail de prélèvement.
1. Le travail de prélèvement suivant est affiché. Confirmez le prélèvement.
1. Continuez à confirmer le travail de prélèvement restant.
1. La dernière étape consiste à terminer le travail de placement. Confirmez le rangement dans l'emplacement de tri.

    Vous recevez un message « Travail terminé ».

1. Quittez le **Prélèvement des ventes** dans l'application mobile.

### <a name="sortingput-to-wall"></a>Tri/Mettre au mur

Maintenant que tout le stock a été placé à l'emplacement de tri, il doit être trié dans la position de tri correcte.

1. Connectez-vous à l'application mobile.
1. Dans le menu principal, sélectionnez **Sortant**.
1. Dans le menu **Sortant**, sélectionnez **Trier** pour commencer à trier les articles.
1. Dans le champ **LP/CONT**, entrez le contenant cible du travail de la commande client prélevée.
1. Confirmez votre entrée.
1. Entrez le numéro de l'article à trier en premier.
1. Le système détermine la première position de tri à afficher. Confirmez la position de tri.
1. Vous êtes invité à attribuer un contenant à la position de tri. Sélectionnez le champ **LP**, entrez un numéro de contenant, puis confirmez votre entrée.

    Étant donné que la position de tri est liée à l'ID d'expédition, vous allez trier les articles prélevés dans un contenant spécifique à l'expédition sortante et à la commande client.

    La page suivante affiche l'ID de l'article, la quantité, l'ID de position de tri et les ID de contenant « de » (prélèvement) et « à » (tri). Les informations de cette page vous indiquent de trier l'article et les quantités spécifiés entre le contenant de prélèvement et le contenant de tri.

1. Confirmez la position de tri.
1. Triez les articles dans la première position de tri. Lorsque vous avez terminé, le système vous dirige vers la position de tri suivante.
1. Répétez ce processus pour toutes les lignes sélectionnées sur l'ordre de travail. Vous devez également utiliser ce processus lorsque plusieurs lignes de prélèvement portent le même numéro d'article.

    Au fur et à mesure que vous répétez ce processus pour tous les articles, le système évalue les critères de l'article numérisé suivant (ligne de travail) et détermine à quelle position de tri il doit être placé. Vous êtes automatiquement invité à placer l'article dans la bonne position de tri. Selon la configuration de la confirmation, vous êtes également invité à confirmer cette action en entrant le numéro de la position ou l'ID du contenant.

    > [!NOTE]
    > Si le tri automatique est activé, le remplacement manuel n'est pas disponible.

1. Lorsque vous avez terminé, dans Microsoft Dynamics 365 Supply Chain Management, ouvrez la page **Affectations de position de tri sortante** pour consulter l'état des positions.

    - Si les positions sont fermées automatiquement, sélectionnez **Afficher fermées** pour afficher les positions fermées.
    - Notez que les transactions de position de tri sont affichées. L'article et la quantité qui ont été traités au niveau de la position sont affichés.

    Lorsque vous configurez le modèle de tri sortant, vous définissez l'option **Fermer automatiquement la position de tri** sur *Oui*. Par conséquent, la position est automatiquement fermée une fois que le dernier article de stock attendu y a été placé. Les positions de tri ont le statut **Fermé**, et un travail a été créé pour déplacer le stock trié vers l'emplacement *Porte baie*.

1. Terminez le travail de prélèvement du stock trié pour déplacer le stock vers le lieu d'expédition. Lorsque le stock est prêt, confirmez-le pour expédition.

> [!NOTE]
> Pour que le travail de prélèvement du stock trié soit traité correctement, il convient d'utiliser un élément de menu d'appareil mobile ayant un ID de classe de travail où le champ **Type d'ordre de travail** est défini sur *Prélèvement de stock trié* pour le processus de déplacement et de chargement.

### <a name="manually-close-a-position-optional"></a>Fermer manuellement une position (facultatif)

Si les positions de tri doivent être fermées manuellement, l'option **Fermer automatiquement la position de tri** pour le modèle de tri sortant doit être définie sur *Non*, et la fermeture doit être effectuée avant que le stock ne puisse être déplacé vers la zone de la porte de la baie. Il est possible de fermer les positions de différentes manières :

- Via l'application d'entrepôt :

    - L'utilisateur peut scanner l'un des articles qui sont déjà sur la position, puis sélectionner **Fermer** pour fermer la position.
    - Si l'utilisateur scanne un conteneur qui a déjà été trié, un message d'erreur s'affiche. Cependant, l'utilisateur peut continuer à fermer la position.

- Depuis la page **Affectations de position de tri sortante** de Microsoft Dynamics 365 Supply Chain Management :

    - L'utilisateur peut sélectionner l'enregistrement de position de tri sortant, puis sélectionner **Fermer la position** dans le volet Actions.

## <a name="tips"></a>Conseils

- Les articles ne peuvent pas être déplacés d'une position à une autre une fois qu'ils ont été affectés à une d'elles. Le système évalue combien de chaque article doit aller à une position spécifique.
- Le modèle de tri peut être configuré pour créer automatiquement des conteneurs lorsque les positions sont fermées. Cette approche créera une structure d'ID de conteneur standard basée sur le profil d'emballage spécifié.

> [!IMPORTANT]
> Une fois que le travail de déplacement a été créé à partir de l'emplacement de tri, vous ne devez pas annuler le travail. Sinon, la position et les conteneurs qu'elle contient seront supprimés du système et ne seront pas disponibles pour un traitement ultérieur. Le stock sera également supprimé.
