---
title: Prix de vente basés sur les attributs pour la configuration de produits basée sur les contraintes
description: Cette rubrique décrit comment créer des modèles de prix de vente avec des prix de vente basés sur des composants et des attributs plutôt que sur la nomenclature physique et la gamme.
author: sorenva
ms.date: 10/2/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2020-08-17
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 1538b806a60a9a9950f54c29bd19447c66ac9ec2
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359099"
---
# <a name="attribute-based-sales-prices-for-constraint-based-product-configuration"></a>Prix de vente basés sur les attributs pour la configuration de produits basée sur les contraintes

Cette rubrique décrit comment créer des modèles de prix de vente avec des prix de vente basés sur des composants et des attributs plutôt que sur la nomenclature physique et la gamme. Vous pouvez créer plusieurs modèles de prix de vente pour chaque modèle de configuration de produit.

## <a name="set-relevant-product-information-management-parameters"></a>Définissez les paramètres de gestion d’information produit appropriés

Avant de commencer à créer vos modèles de prix, vous devez définir une devise par défaut, qui est utilisée lorsque vous créez vos modèles de prix de vente. Vous pouvez également choisir de joindre un fichier Microsoft Excel avec une répartition des prix pour toutes les lignes de commande ou de devis. La répartition des prix vous permettra de partager des détails avec les clients sur la façon dont vous avez calculé un prix de vente spécifique pour un produit configuré.

Pour définir votre devise par défaut :

1. Accédez à **Gestion des informations sur les produits \> Paramétrage \> Paramètres de gestion des informations sur les produits**.
1. Ouvrez l’onglet **Modèles de configuration de produits basés sur les contraintes**.
1. Ouvrez la liste déroulante **Devise par défaut** et sélectionnez votre devise.

    ![Définissez la devise par défaut pour la configuration de produit basée sur les contraintes.](media/prod-config-currency.png "Définir la devise par défaut pour la configuration de produit basée sur les contraintes")

1. Si vous souhaitez joindre un fichier Excel avec une répartition des prix pour toutes les lignes de commande ou de devis, dans la section **Modèle de prix**, définissez **Attacher** sur *Oui*.

## <a name="build-your-sales-price-models"></a><a name="build-price-model"></a>Construire vos modèles de prix de vente

Pour construire votre modèle de prix de vente :

1. Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.
1. Sélectionnez le modèle de configuration de produit cible.
1. Dans le volet Action, ouvrez l’onglet **Modèle** et, dans le groupe **Paramétrer**, sélectionnez **Modèles de prix**.
1. La page **Modèles de prix** s’ouvre.
1. Sélectionnez un modèle de prix ou ajoutez-en un nouveau à la grille.
1. Sélectionnez **Modifier** pour ouvrir la page de modification du modèle sélectionné, qui offre les fonctionnalités suivantes :
    - L’en-tête du formulaire affiche la devise par défaut et vous permet d’ajouter de nouvelles devises pour le paramétrage du prix.
    - Le volet gauche affiche tous les composants et exigences utilisateur du modèle de produit. Chaque nœud de l’arborescence du modèle de produit peut avoir une expression de prix de base et un nombre facultatif de règles d’expression. Une règle d’expression se compose d’une condition et d’une expression, et chaque règle d’expression couvre une option de produit qui permet de contrôler le prix du produit.
    - Lorsque vous créez vos conditions et expressions, vous disposez des mêmes opérateurs que pour les calculs dans un modèle de produit. L’éditeur d’expression prend également en charge les conditions et les expressions.
1. Sélectionnez un nœud dans la colonne de gauche, puis utilisez les fonctionnalités décrites à l’étape précédente pour établir des règles de tarification pour celui-ci (voir également l’exemple fourni après cette procédure). Répétez cette étape pour chaque nœud si nécessaire.

L’exemple suivant montre un prix de base d’un nombre statique de 899,95 EUR, qui peut être modifié par une ou plusieurs des cinq règles d’expression suivantes, en fonction de la configuration sélectionnée par le client :

- Pour une finition Meuble blanch, déduire 59,95 EUR.
- Pour la protection des angles, ajouter 35,95 EUR.
- Pour une grille avant en métal, ajouter 89,95 EUR.
- Pour une finition Palissandre, ajouter 119,95 EUR.
- Ajouter 12,95 EUR pour chaque unité de hauteur de haut parleur.

![Exemple de modèle de prix.](media/prod-config-rules-example.png "Exemple de modèle de prix")

## <a name="add-support-for-multiple-currencies"></a>Ajouter la prise en charge de plusieurs devises

Lorsqu’un produit configurable est vendu, le système vérifie si les prix ont été définis explicitement dans la devise du client. Si tel est le cas, les valeurs explicites sont utilisées. Sinon, le système utilise les taux de change établis afin que la société de vente convertisse la valeur de la devise par défaut dans la devise du client.

Pour ajouter des prix explicites dans une devise supplémentaire :

1. Ouvrez la page de modification de votre modèle de prix, comme décrit dans [Construire vos modèles de prix de vente](#build-price-model).
1. Sélectionnez le bouton **Ajouter** dans l’en-tête du modèle de prix pour ouvrir la boîte de dialogue du menu déroulant **Devises**, qui répertorie les devises disponibles.
1. Sélectionnez la devise que vous souhaitez ajouter dans la boîte de dialogue déroulante **Devises**, puis sélectionnez **OK**.
1. La boîte de dialogue déroulante **Devise actuelle** comprend désormais la devise que vous venez d’ajouter, ainsi que toutes les autres devises qui peuvent avoir été ajoutées précédemment. Sélectionnez votre nouvelle devise et notez que la grille dans la section **Règles d’expression** comprend désormais deux champs d’expression :
    - **Expression** - Affiche l’expression (ou la valeur constante) pour trouver le prix en utilisant la devise actuellement sélectionnée pour **Devise actuelle**.
    - **Expressions par défaut** - Affiche l’expression (ou la valeur constante) pour trouver le prix en utilisant la devise par défaut (affichée dans le champ **Devise par défaut**).

    > [!NOTE]
    > Le champ **État** des règles d’expression est "détenu" par la devise par défaut, ce qui signifie que vous ne pouvez pas modifier la condition pour d’autres devises. Vous ne pouvez pas non plus ajouter de nouvelles règles d’expression lorsqu’une devise autre que la devise par défaut est sélectionnée comme **Devise actuelle**.
1. Modifiez les valeurs dans la colonne **Expression** comme souhaité pour la devise actuelle.

Dans l’exemple ci-dessous, _EUR_ est la devise par défaut, et _USD_ a été ajouté en tant que devise supplémentaire.

![Exemple de modèle avec plusieurs devises.](media/prod-config-rules-currency-example.png "Exemple de modèle avec plusieurs devises")

> [!NOTE]
> Vous ne pouvez pas ajouter de règles d’expression uniques pour une devise autre que celle par défaut. Pour créer des règles d’expression qui ne seraient pertinentes que pour une devise autre que la devise par défaut, définissez l’expression de prix pour la devise par défaut sur zéro. Définissez ensuite l’expression appropriée pour la devise autre que celle par défaut.

## <a name="test-your-price-model"></a>Tester votre modèle de prix

Pour tester le fonctionnement des prix de vente dans une session de configuration, ouvrez la page de modification de votre modèle de prix, comme décrit dans [Construire vos modèles de prix de vente](#build-price-model), puis sélectionnez **Tester** dans le volet Actions. La boîte de dialogue **Modèle de produit test** s’ouvre. Vous pouvez y effectuer les opérations suivantes :

- Utilisez les paramètres de configuration proposés ici pour sélectionner les options du produit, puis voir comment elles affectent la valeur indiquée pour **Prix et date d’expédition**.
- Sélectionnez **Afficher la répartition des prix** pour télécharger un document Excel qui montre tous les détails sur la façon dont le prix a été calculé.

![Testez votre modèle de produit.](media/prod-config-test.png "Tester votre modèle de produit")

La feuille de calcul téléchargée montre à la fois la valeur absolue et la contribution sous forme de pourcentage pour chaque élément de prix actif. Si vous avez défini l’option de modèle de prix **Attacher** sur la page **Paramètres de gestion des informations sur les produits**, cette feuille Excel est jointe à la ligne de commande ou de devis.

![Feuille de calcul Excel montrant la répartition des prix.](media/prod-config-excel-example.png "Feuille de calcul Excel montrant la répartition des prix")

## <a name="set-up-selection-criteria-for-price-models"></a>Configurer des critères de sélection pour les modèles de prix

Lorsque vos modèles de prix sont en place, vous devez établir au moins un critère de sélection pour choisir le modèle de prix lorsque vous configurez pour un devis ou une commande. Pour ce faire, configurez une ou plusieurs requêtes. Associées à des modèles de prix de vente correspondants, les requêtes offrent une grande flexibilité pour cibler les prix de vente pour des clients, des régions, des périodes et d’autres critères particuliers.

Pour configurer des critères de sélection pour les modèles de prix :

1. Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.
1. Sélectionnez le modèle de configuration de produit cible.
1. Dans le volet Action, ouvrez l’onglet **Modèle** et, dans le groupe **Paramétrer**, sélectionnez **Critères de modèle de prix**. La page **Critères de modèle de prix** s’ouvre.
1. Si la ligne de requête dont vous avez besoin n’existe pas encore, sélectionnez **Nouveau** dans le volet Actions pour ajouter une nouvelle ligne à la grille et définir les paramètres suivants :
    - **Nom** - Entrez un nom pour cette ligne.
    - **Description** - Décrivez brièvement la requête et ce à quoi elle sert.
    - **Modèle de prix** - Sélectionnez un [modèle de prix](#build-price-model) (à partir du modèle de configuration actuel) que la requête appliquera lorsqu’elle sera déclenchée.
    - **Type de commande** - Sélectionnez le type de commande auquel la requête s’appliquera.
    - **Début de validité** - Spécifiez le premier jour où la requête s’appliquera.
    - **Expiration** - Spécifiez la dernière date à laquelle la requête s’appliquera.

    ![Critères de modèle de prix.](media/prod-config-price-model-criteria.png "Critères de modèle de prix")

1. Sélectionnez la ligne de la requête que vous souhaitez définir, puis sélectionnez **Modifier** sur le **Volet Actions**. La boîte de dialogue du concepteur de requêtes s’ouvre. Le concepteur fonctionne comme la plupart des concepteurs de requêtes dans Supply Chain Management. Utilisez-le pour définir les conditions dans lesquelles le modèle de prix de la ligne sélectionnée doit être appliqué.

1. Répétez les étapes 4 à 5 pour chaque requête dont vous avez besoin.
    > [!TIP]
    > Vous pouvez gagner du temps en copiant une ligne existante similaire à une nouvelle ligne que vous devez ajouter. Pour ce faire, sélectionnez une ligne cible, puis sélectionnez **Dupliquer** dans le volet Actions.

1. Lorsque vous avez terminé de définir vos critères, classez-les dans le bon ordre dans la liste **Critères de modèle de prix**. Pour repositionner une ligne, sélectionnez-la, puis sélectionnez **Vers le haut** ou **Vers le bas** dans le volet Actions.

    > [!IMPORTANT]
    > Au moment de la configuration, le système commence la recherche à partir du haut de la liste et utilise la première requête qui correspond aux données du devis ou de la ligne de commande. Par conséquent, vous devez placer vos requêtes les plus spécifiques en premier. Si vous placez une requête générale en haut de la liste, c’est celle qui sera utilisée, même si une requête plus bas dans la liste cible le client ou le prospect exact de la configuration.

## <a name="set-attribute-based-sales-prices-for-the-product-model-version"></a>Définir les prix de vente basés sur les attributs pour la version du modèle de produit

La dernière étape consiste à spécifier les prix de vente basés sur les attributs pour la version du modèle de produit. Pour ce faire :

1. Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.
1. Sélectionnez le modèle de configuration de produit cible.
1. Dans le volet Action, ouvrez l’onglet **Modèle** et, dans le groupe **Détails du modèle de produit**, sélectionnez **Versions**.
1. La page **Versions** s’ouvre. Assurez-vous que **Méthode de tarification** est défini sur **Basé sur les attributs**.
    ![Définissez la méthode de tarification sur Basé sur les attributs.](media/prod-config-versions.png "Définir la méthode de tarification sur Basé sur les attributs")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]