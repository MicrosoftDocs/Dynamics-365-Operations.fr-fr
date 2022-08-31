---
title: Stratégies de conditionnement en conteneurs
description: Cet article décrit les différences entre les stratégies d’emballage dans des conteneurs et en donne des exemples.
author: GalynaFedorova
ms.date: 08/09/2022
ms.topic: article
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5a9a0066abaa76294faebcb15d5091ba36e8a60d
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335763"
---
# <a name="container-packing-strategies"></a>Stratégies de conditionnement en conteneurs

[!include [banner](../includes/banner.md)]

Une *stratégie de conditionnement en conteneurs* est une stratégie que vous pouvez utiliser pour définir les répartitions entre les conteneurs. Cet article explique les différences entre les stratégies *Conditionner dans tous les conteneurs ouverts* et *Conditionner dans le conteneur en cours uniquement*.

- **Conditionner dans tous les conteneurs ouverts** : le système doit vérifier tous les conteneurs ouverts qui ont déjà été créés pendant le cycle de conteneurisation, pour s’assurer que l’article rentrera dans l’un d’entre eux. Lors de l’emballage, le système vérifie chaque article pour déterminer s’il rentre dans l’un des conteneurs créés précédemment. Si l’article ne rentre dans aucun conteneur existant, le système crée un nouveau conteneur et continue jusqu’à ce qu’il ait fini d’emballer toute la commande.

    Par example, *n* articles commandés nécessitent une conteneurisation. Dans le pire des cas, chaque fois que le système traite un article qui ne rentre dans aucun conteneur existant, il effectue un total de (\[(*n* – 1) × (*n* + 1)\] ÷ 2) contrôles pour voir si l’article rentre dans les conteneurs existants.

- **Conditionner dans le conteneur en cours uniquement** – Le système ne vérifie que le conteneur créé le plus récemment pour s’assurer que l’article y rentrera. Lors de l’emballage, le système vérifie chaque article pour déterminer s’il rentre dans le conteneur créé le plus récemment. Si l’article ne rentre pas dans ce conteneur, le système crée un nouveau conteneur et continue jusqu’à ce qu’il ait fini d’emballer toute la commande.

    Par example, *n* articles commandés nécessitent une conteneurisation. Dans le pire des cas, le système fera un total de (*n* – 1) contrôles pour évaluer si l’article rentre dans les conteneurs.

## <a name="example-of-the-flow-for-container-packing-strategies"></a>Exemple de flux pour les stratégies de conditionnement en conteneurs

Vous configurez les articles suivants pour la conteneurisation.

| Article | Dimensions physiques (largeur × profondeur × hauteur) | Pondération |
|---|---|---|
| Câble HDMI 6 po | 1 × 1 × 1 | 1 |
| Câble HDMI 12 po | 2 × 1 × 1 | 1 |
| Câble HDMI 18 po | 3 × 1 × 1 | 2 |

Vous configurez également le carton suivant qui sera utilisé pour l’emballage.

| Conteneur | Dimensions physiques (longueur × largeur × hauteur) | Pondération | Volume |
|---|---|---|---|
| Carton moyen | 6 × 3 × 2 | 10 | 100 |

Enfin, vous configurez une commande qui contient les produits et quantités suivants.

| Ligne de commande client | Quantité |
|---|---|
| Câble HDMI 12 po | 9 |
| Câble HDMI 18 po | 8 |
| Câble HDMI 6 po | 13 |

Le tableau suivant résume le fonctionnement de la conteneurisation lorsque vous utilisez la stratégie *Conditionner dans tous les conteneurs ouverts* et lorsque vous utilisez la stratégie *Conditionner dans le conteneur en cours uniquement*.

| Conditionner dans tous les conteneurs ouverts | Conditionner dans le conteneur en cours |
|---|---|
| <p>Câble HDMI 12 po :</p><ol><li>Créez un nouveau conteneur, CONT0001.</li><li>Mettez 9 unités dans le conteneur CONT0001.</li></ol> | <p>Câble HDMI 12 po :</p><ol><li>Créez un nouveau conteneur, CONT0001.</li><li>Mettez 9 unités dans le conteneur CONT0001.</li></ol> |
| <p>Câble HDMI 18 po :</p><ol><li>Vérifiez si l’article peut tenir dans le conteneur CONT0001.</li><li>Créez un nouveau conteneur, CONT0002.</li><li>Mettez 5 unités dans le conteneur CONT0002.</li><li>Créez un nouveau conteneur, CONT0003.</li><li>Mettez 3 unités dans le conteneur CONT0003.</li></ol> | <p>Câble HDMI 18 po :</p><ol><li>Vérifiez si l’article peut tenir dans le conteneur CONT0001.</li><li>Créez un nouveau conteneur, CONT0002.</li><li>Mettez 5 unités dans le conteneur CONT0002.</li><li>Créez un nouveau conteneur, CONT0003.</li><li>Mettez 3 unités dans le conteneur CONT0003.</li></ol> |
| <p>Câble HDMI 6 po :</p><ol><li>Vérifiez si l’article peut tenir dans le conteneur CONT0001.</li><li>Mettez 1 unité dans le conteneur CONT0001.</li><li>Vérifiez si l’article peut tenir dans le conteneur CONT0002.</li><li>Vérifiez si l’article peut tenir dans le conteneur CONT0003.</li><li>Mettez 4 unités dans le conteneur CONT0003.</li><li>Créez un nouveau conteneur, CONT0004.</li><li>Mettez 8 unités dans le conteneur CONT0004.</li></ol> | <p>Câble HDMI 6 po :</p><ol><li>Vérifiez si l’article peut tenir dans le conteneur CONT0003.</li><li>Mettez 4 unités dans le conteneur CONT0003.</li><li>Créez un nouveau conteneur, CONT0004.</li><li>Mettez 9 unités dans le conteneur CONT0004.</li></ol> |

## <a name="example-scenario-pack-single-orders-per-container"></a>Exemple de scénario : emballer des commandes uniques par conteneur

Cette section présente un scénario dans lequel le système est configuré pour regrouper plusieurs commandes en une seule expédition. Par conséquent, la conteneurisation sera effectuée à partir de la commande client pour garantir que chaque commande contenant plusieurs produits est emballée dans son propre conteneur.

Cette fonctionnalité vous permet de gérer des scénarios dans lesquels vous ne devez emballer qu’une seule commande client dans chaque conteneur, afin que le centre de distribution puisse transborder des conteneurs pleins entre les magasins de vente au détail. En plus des scénarios de vente au détail (commande par magasin de détail et expédition vers un centre de distribution pour le transbordement), cette technique est également couramment utilisée dans les chaînes d’approvisionnement « lean » (commande client par ligne de production juste à temps).

Ce scénario montre comment vous pouvez réduire le nombre de conteneurs évalués lors de l’emballage en utilisant la stratégie *Conditionner dans le conteneur en cours uniquement* pour la conteneurisation.

### <a name="prerequisites"></a>Conditions préalables

#### <a name="turn-on-the-consolidate-shipments-feature-in-your-system"></a>Activer la fonction Regrouper les expéditions dans votre système

Ce scénario utilise la fonctionnalité *Regrouper les expéditions*. Depuis la version 10.0.29 de Supply Chain Management, la fonctionnalité est obligatoire et ne peut pas être désactivée. Si vous exécutez une version antérieure à 10.0.29, les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Consolider les expéditions* dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

#### <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Ce scénario fait référence à des valeurs et des enregistrements inclus dans les données de démonstration standard fournies pour Microsoft Dynamics 365 Supply Chain Management. Pour utiliser les valeurs fournies ici lorsque vous effectuez les exercices, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l’entité juridique sur **USMF** avant de commencer.

### <a name="inspect-or-create-container-types"></a>Inspecter ou créer des types de conteneurs

Pour inspecter vos types de conteneurs ou pour en créer de nouveaux au besoin, procédez comme suit.

1. Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Conteneurs** \> **Types de conteneurs**.
1. Assurez-vous que chacun des types de conteneurs suivants est disponible dans vos données de démonstration. Modifiez ou créez des types de conteneurs selon vos besoins.

    - Type de conteneur 1 :

        - **Code de type de conteneur :** *Boîte-Large*
        - **Description:** *Grande boîte*
        - **Poids net maximal :** *100*
        - **Volume :** *400*
        - **Longueur :** *4*
        - **Largeur :** *10*
        - **Hauteur :** *10*

    - Type de conteneur 2 :

        - **Code de type de conteneur :** *Boîte-Moyenne*
        - **Description :** *Boîte moyenne*
        - **Poids net maximal :** *50*
        - **Volume :** *200*
        - **Longueur :** *2*
        - **Largeur :** *10*
        - **Hauteur :** *10*

    - Type de conteneur 3 :

        - **Code de type de conteneur :** *Boîte-Petite*
        - **Description :** *Petite boîte*
        - **Poids net maximal :** *20*
        - **Volume :** *100*
        - **Longueur :** *1*
        - **Largeur :** *10*
        - **Hauteur :** *10*

### <a name="inspect-or-create-container-groups"></a>Inspecter ou créer des groupes de conteneurs

Pour inspecter vos groupes de conteneurs ou pour en créer de nouveaux au besoin, procédez comme suit.

1. Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Conteneurs** \> **Groupes de conteneurs**.
1. Assurez-vous que chacun des groupes de conteneurs suivants est disponible dans vos données de démonstration. S’il n’est pas disponible, sélectionnez **Nouveau** pour le créer.

    - **ID groupe de conteneurs :** *Boîtes*
    - **Description :** *Tailles de boîte*

1. Dans le raccourci **Détails** du groupe de conteneurs *Boîtes*, assurez-vous que les lignes suivantes existent. Si ce n’est pas le cas, sélectionnez **Nouveau** pour les ajouter.

    - Ligne 1 :

        - **Souche de N° :** *1*
        - **Type de conteneur :** *Boîte-Large*
        - **Pourcentage d’utilisation du conteneur :** *100*

    - Ligne 2 :

        - **Souche de N° :** *2*
        - **Type de conteneur :** *Boîte-Moyenne*
        - **Pourcentage d’utilisation du conteneur :** *100*

    - Ligne 3 :

        - **Souche de N° :** *3*
        - **Type de conteneur :** *Boîte-Petite*
        - **Pourcentage d’utilisation du conteneur :** *100*

### <a name="create-a-new-container-build-template"></a>Créer un modèle de création de conteneur

Pour créer un modèle de création de conteneur, suivez les étapes suivantes.

1. Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Conteneurs** \> **Modèles de création de conteneur**.
1. Sélectionnez **Nouveau** pour créer un modèle de ccréation de conteneur avec les paramètres suivants :

    - **Souche de N° :** *1*
    - **ID modèle de conteneur :** *Boîte*
    - **ID groupe de conteneurs :** *Boîtes*
    - **Types de requêtes de base :** *Ligne de répartition des ventes*
    - **Code étape de vague :** *234*
    - **Autoriser la répartition des prélèvements :** *Oui*
    - **Stratégie de conditionnement en conteneurs :** *Conditionner dans le conteneur en cours uniquement*
    - **Conditionner par unité de directive :** *Non*

1. Alors que la ligne du nouveau modèle est toujours sélectionnée, sélectionnez **Modifier la requête** dans le volet Actions.
1. Une boîte de dialogue d’éditeur de requête standard s’affiche. Dans l’onglet **tri**, sélectionnez **Ajouter** pour ajouter une ligne ayant les paramètres suivants :

    - **Table :** *Transactions de travail temporaire*
    - **Table dérivée :** *Transactions de travail temporaire*
    - **Champ :** *Numéro de commande*
    - **Ordre de tri :** *Croissant*

    > [!IMPORTANT]
    > Pour éviter de parcourir tous les autres conteneurs ouverts et pour accélérer le processus en vérifiant un conteneur à la fois, utilisez la stratégie *Conditionner dans le conteneur en cours uniquement* en plus du tri par numéro de commande. Cette combinaison fonctionnera comme une répartition du travail dans un modèle de travail.

1. Sélectionnez **OK** pour fermer la boîte de dialogue de l’éditeur de requêtes.
1. Alors que la ligne du nouveau modèle est toujours sélectionnée, sélectionnez **Contraintes de mélange en conteneur** dans le volet Actions.

    Vous allez maintenant ajouter une contrainte qui place les articles d’une seule commande dans un seul conteneur. Les articles de toute autre commande seront placés dans un conteneur séparé.

1. Sélectionnez **Nouveau** pour créer une contrainte de mélange avec les paramètres suivants :

    - **Table :** *Commandes client*
    - **Sélection de champ :** *SalesId* (Le champ apparaîtra comme *Commande client* dans la grille.)

1. Sélectionnez **OK** pour ajouter la contrainte.
1. Fermez la page.

### <a name="set-up-a-wave-template-for-containerization"></a>Paramétrer un modèle de vague pour la mise en conteneur

Pour paramétrer un modèle de vague, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.
1. Dans le volet de liste, définissez le champ **Type de modèle de vague** sur *Expédition*.
1. Sélectionnez le modèle **Conteneurisation 63** dans la liste.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Sur l’organisateur **Méthodes**, dans la colonne **Méthodes sélectionnées**, recherchez la ligne suivante :

    - **Nom de la méthode :** *conteneurisation*
    - **Nom :** *Conteneurisation*

1. Définissez le champ **Code d’étape de vague** pour la ligne sur *234*.

### <a name="set-up-a-work-template"></a>Définir un modèle de travail

Pour paramétrer un modèle de travail, procédez comme suit.

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Travail \> Modèles de travail**.
1. Définissez le champ **Type d’ordre de travail** sur *Commandes client*.
1. Dans la grille **Vue d’ensemble**, recherchez et sélectionnez le modèle de travail à utiliser pour conditionner les commandes uniques par conteneur. Pour ce scénario, sélectionnez le modèle **63 Prélever vers le conteneur**.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Une boîte de dialogue d’éditeur de requête standard s’affiche. Sous l’onglet **Tri**, ajoutez les ligne suivantes :

    - Ligne 1 :

        - **Table :** *Transactions de travail temporaire*
        - **Table dérivée :** *Transactions de travail temporaire*
        - **Champ :** *ID expédition*
        - **Ordre de tri :** *Croissant*

    - Ligne 2 :

        - **Table :** *Transactions de travail temporaire*
        - **Table dérivée :** *Transactions de travail temporaire*
        - **Champ :** *Numéro de commande*
        - **Ordre de tri :** *Croissant*

    - Ligne 3 :

        - **Table :** *Transactions de travail temporaire*
        - **Table dérivée :** *Transactions de travail temporaire*
        - **Champ :** *ID conteneur*
        - **Ordre de tri :** *Croissant*

1. Sélectionnez **OK** pour fermer la boîte de dialogue de l’éditeur de requêtes.
1. Le message suivant s’affiche : « Le regroupement sera réinitialisé, continuer ? » Sélectionnez **Oui** pour continuer.
1. Tandis que le modèle **63 Prélever vers le conteneur** est toujours sélectionné, sélectionnez **Décompositions de l’en-tête de travail** dans le volet Actions.

    Vous allez maintenant appliquer des paramètres pour décomposer le travail de sorte que chaque conteneur de la commande soit lié à un seul ordre de travail.

1. Sélectionnez la case à cocher **Regrouper par ce champ** pour chaque ligne de la page **Décompositions de l’en-tête de travail** (**ID expédition**, **Numéro de commande** et **ID conteneur**).
1. Fermez la page.

### <a name="set-up-shipment-consolidation-policies"></a>Configurer des stratégies de regroupement des expéditions

Pour configurer une stratégie de regroupement des expéditions, procédez comme suit.

1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.
1. Dans le volet de liste, définissez le champ **Type de stratégie** sur *Commandes client*.
1. Sélectionnez la stratégie **Par défaut** dans la liste.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans le raccourci **Champs de regroupement**, dans la liste **Champs sélectionnés**, sélectionnez la ligne où **Nom de champ** est défini sur *Numéro de commande*.
1. Sélectionnez le bouton **Supprimer** ![Flèche vers la gauche.](media/backward-button.png) pour déplacer le champ vers la liste **Champs restants**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="set-up-physical-dimensions-for-the-product"></a>Configurer les dimensions physiques du produit

Pour configurer les dimensions physiques des produits qui seront utilisés dans ce scénario, procédez comme suit.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez le produit dont le champ **Numéro d’article** est défini sur *A0001*.
1. Dans le volet Action,s dans l’onglet **Gérer le stock**, dans le groupe **Entrepôt**, sélectionnez **Dimensions physiques**.
1. Sur la page **Dimensions physiques**, vous devriez voir la ligne suivante dans la grille :

    - **Unité :** *pièces*
    - **Poids brut :** *3,00*
    - **Largeur :** *2,00*
    - **Profondeur :** *2,00*
    - **Hauteur :** *4,00*
    - **Volume :** *16,00*

1. Fermez la page.
1. Sélectionnez le produit dont le champ **Numéro d’article** est défini sur *A0002*.
1. Dans le volet Action,s dans l’onglet **Gérer le stock**, dans le groupe **Entrepôt**, sélectionnez **Dimensions physiques**.
1. Sur la page **Dimensions physiques**, vous devriez voir la ligne suivante dans la grille :

    - **Unité :** *pièces*
    - **Poids brut :** *4,00*
    - **Largeur :** *3,00*
    - **Profondeur :** *1,00*
    - **Hauteur :** *3,00*
    - **Volume :** *9,00*

### <a name="create-sales-order-1"></a>Créer une commande client 1

Pour créer une commande vente, procédez comme suit :

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Une boîte de dialogue de création d’une nouvelle commande client apparaît. Définissez les valeurs suivantes :

    - **Compte client :** *US-001*
    - **Entrepôt :** *63*

1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.
1. La nouvelle commande client est ouverte. Dans le raccourci **Lignes de commande client**, ajoutez les lignes de vente +suivantes :

    - Ligne 1 :

        - **Numéro d’article :** *A0001*
        - **Quantité :** *2*

    - Ligne 2 :

        - **Numéro d’article :** *A0002*
        - **Quantité :** *2*

1. Sélectionnez la première ligne, puis sélectionnez **Stock \> Réservation**.
1. Sur la page **Réservation**, sélectionnez **Réserver un lot**. Fermez ensuite la page.
1. Répétez les deux étapes précédentes pour la deuxième ligne.
1. Fermez la page.

### <a name="create-sales-order-2"></a>Créer une commande client 2

Procédez comme suit pour créer une deuxième commande client.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Une boîte de dialogue de création d’une nouvelle commande client apparaît. Définissez les valeurs suivantes :

    - **Compte client :** *US-001*
    - **Entrepôt :** *63*

1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.
1. La nouvelle commande client est ouverte. Dans le raccourci **Lignes de commande client**, ajoutez les lignes de vente +suivantes :

    - Ligne 1 :

        - **Numéro d’article :** *A0001*
        - **Quantité :** *4*

    - Ligne 2 :

        - **Numéro d’article :** *A0002*
        - **Quantité :** *4*

1. Sélectionnez la première ligne, puis sélectionnez **Stock \> Réservation**.
1. Sur la page **Réservation**, sélectionnez **Réserver un lot**. Fermez ensuite la page.
1. Répétez les deux étapes précédentes pour la deuxième ligne.
1. Fermez la page.

### <a name="create-the-load"></a>Créer le chargement

Pour créer un chargement pour chaque commande que vous avez créée pour ce scénario, puis le lancer dans l’entrepôt, procédez comme suit.

1. Allez dans **Gestion des entrepôts \> Chargements \> Atelier de planification des chargements**.
1. Sur l’onglet **Lignes de vente**, recherchez et sélectionnez toutes les lignes de commande client des commandes client que vous avez créées pour ce scénario.
1. Dans le volet Actions, sous l’onglet **Approvisionnement et demande**, dans le groupe **Ajouter**, sélectionnez **Dans un nouveau chargement**. Les lignes de commande sélectionnées sont ajoutées à un nouveau chargement.
1. Dans la boîte de dialogue **Affectation des modèles de chargement**, dans le champ **ID du modèle de chargement**, sélectionnez un modèle de chargement, tel que *Conteneur 40 po*.
1. Sélectionnez **OK** pour fermer la boîte de dialogue.
1. Dans la section **Chargements**, recherchez et sélectionnez le chargement que vous venez de créer.
1. Sélectionnez **Lancer \> Lancement dans l’entrepôt**.
1. Dans la boîte de dialogue **Lancement dans l’entrepôt**, sélectionnez **OK** pour lancer le chargement sélectionné dans l’entrepôt.

### <a name="verify-the-shipments-and-containers"></a>Vérifier les expéditions et les conteneurs

La procédure suivante vous permet de vérifier les expéditions qui ont été créées. Utilisez-la pour examiner la commande que vous avez créée pour ce scénario, afin de vous assurer que vous avez obtenu les résultats attendus.

1. Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**.
1. Recherchez et sélectionnez l’expédition qui a été créée pour le chargement que vous venez de lancer.
1. Dans le volet Actions, dans l’onglet **Transport**, sélectionnez **Afficher les conteneurs**.
1. Vérifiez que les articles des commandes clients ont été conteneurisés dans deux conteneurs différents.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Mise en conteneur](wave-containerization.md)
