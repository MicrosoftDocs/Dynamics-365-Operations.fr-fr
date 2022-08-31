---
title: Réapprovisionnement du seuil de zone
description: Le réapprovisionnement basé sur une zone utilise une stratégie de réapprovisionnement minimum/maximum (min/max), mais il évalue des zones d’entrepôt entières au lieu de seulement des emplacements individuels. Par conséquent, les gestionnaires d’entrepôt peuvent apprendre plus rapidement lorsqu’un inventaire supplémentaire est requis dans une zone de prélèvement.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocDirHint, WHSLocDirTable, WHSRequestType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 44e7dfdbc980c5df6b9426515365611bc0de45c2
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335943"
---
# <a name="zone-threshold-replenishment"></a>Réapprovisionnement du seuil de zone

[!include [banner](../includes/banner.md)]

Le réapprovisionnement basé sur une zone utilise une stratégie de [réapprovisionnement](replenishment.md) minimum/maximum (min/max), mais il évalue des zones d’entrepôt entières au lieu de seulement des emplacements individuels. Par conséquent, les gestionnaires d’entrepôt peuvent apprendre plus rapidement lorsqu’un inventaire supplémentaire est requis dans une zone de prélèvement.

La configuration de cette fonctionnalité ressemble à la configuration pour le réapprovisionnement basé sur l’emplacement. Cependant, lorsque vous configurez un modèle de réapprovisionnement min/max, vous pouvez également spécifier si le seuil doit être évalué par emplacement ou par zone. Si vous configurez une évaluation basée sur des zones, vous devez ajouter des zones spécifiques à la requête de sélection de zone.

Comme le réapprovisionnement min/max basé sur l’emplacement, le réapprovisionnement min/max basé sur la zone est basé sur la configuration d’un seuil de stock minimal qui déclenche la création d’un travail de réapprovisionnement pour les articles sélectionnés. Ce travail de réapprovisionnement augmentera le stock jusqu’au seuil maximal spécifié pour la zone.

> [!NOTE]
> Les processus de réapprovisionnement de zone pour les variantes de produit ne sont pas pris en charge dans la version actuelle.


Contrairement au réapprovisionnement min/max basé sur l’emplacement, le réapprovisionnement min/max basé sur la zone ne nécessite pas d’emplacements fixes pour évaluer si les emplacements doivent stocker un élément spécifique. Par conséquent, le réapprovisionnement basé sur une zone vous permet d’utiliser le réapprovisionnement min/max même si vous n’avez pas d’emplacements fixes pour chaque article ou variante d’article dans l’entrepôt. Lorsqu’une quantité dans la zone tombe en dessous du seuil minimal spécifié, un travail de réapprovisionnement est créé. Les directives de localisation détermineront dans quel emplacement spécifique le stock doit être placé.

## <a name="turn-on-the-zone-threshold-replenishment-feature"></a>Activer la fonctionnalité de réapprovisionnement du seuil de zone

Avant de pouvoir utiliser la fonctionnalité *Réapprovisionnement du seuil de zone*, elle doit être activée dans votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Réapprovisionnement du seuil de zone*

## <a name="set-up-zone-based-replenishment"></a><a name="setup"></a>Configurer le réapprovisionnement basé sur une zone

Pour configurer le réapprovisionnement basé sur une zone, vous devez configurer plusieurs parties du système. Cette section présente les différents paramètres et fournit des valeurs de données de démonstration que vous pouvez entrer si vous souhaitez exécuter le scénario à la fin de cet article.

### <a name="set-up-directive-codes"></a>Paramétrer des codes directifs

Les [codes directifs](control-warehouse-location-directives.md) vous permettent d’être plus précis lorsque vous définissez le modèle d’emplacement utilisé dans un modèle de travail. Chaque code établit une valeur commune à laquelle vous pouvez vous référer lorsque vous configurez chaque type de modèle.

#### <a name="view-and-edit-directive-codes"></a>Afficher et modifier les codes directifs

Pour afficher ou modifier vos codes directifs, accédez à **Gestion des entrepôts \> Paramétrage \> Codes directifs**.

#### <a name="prepare-demo-data-directive-codes"></a>Préparer des codes directifs de données de démonstration

Cet exemple montre comment préparer un code directif. Si vous prévoyez d’exécuter le scénario à la fin de cet article, utilisez les valeurs de données de démonstration fournies ici. Sinon, utilisez vos propres valeurs.

1. Sélectionnez l’entité juridique **USMF** pour travailler avec les données de démonstration.
1. Allez dans **Gestion des entrepôts \> Configuration \> Codes de directives**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Dans la nouvelle ligne, définissez les valeurs suivantes :

    - **Code directif :** _Réapprovisionnement de zone_
    - **Description directive :** _Réapprovisionnement de zone_

1. Sélectionnez **Enregistrer** pour enregistrer le nouveau code.

### <a name="set-up-replenishment-templates"></a>Définir des modèles de réapprovisionnement

Les [modèles de réapprovisionnement min/max](tasks/set-up-min-max-replenishment-process.md) constituent le mécanisme principal pour tenir à jour des niveaux optimaux aux emplacements de prélèvement. Dans ces modèles, vous devez configurer les règles qui seront utilisées pour reconstituer le stock dans l’entrepôt. Le réapprovisionnement pour lequel les modèles peuvent être utilisés inclut le réapprovisionnement basé sur une zone.

#### <a name="view-and-edit-replenishment-templates"></a>Afficher et modifier des modèles de réapprovisionnement

Un modèle de réapprovisionnement est un ensemble de règles contrôlant quand et comment un emplacement est réapprovisionné. Vous sélectionnez un modèle pour contrôler quand et comment le réapprovisionnement est effectué. Pour afficher ou modifier vos modèles de réapprovisionnement, accédez à **Gestion des entrepôts \> Configuration \> Réapprovisionnement \> Modèles de réapprovisionnement**.

#### <a name="prepare-a-demo-data-replenishment-template"></a>Préparer un modèle de réapprovisionnement des données de démonstration

Cet exemple montre comment préparer un modèle de réapprovisionnement. Si vous prévoyez d’exécuter le scénario à la fin de cet article, utilisez les valeurs de données de démonstration fournies ici. Sinon, utilisez vos propres valeurs.

1. Sélectionnez l’entité juridique **USMF** pour travailler avec les données de démonstration.
1. Allez dans **Gestion des entrepôts \> Paramétrage \> Réapprovisionnement \> Modèles de réapprovisionnement**.
1. Sélectionnez **Modifier** pour afficher la page en mode d’édition.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille **Vue d’ensemble**.
1. Dans la nouvelle ligne, définissez les valeurs suivantes. Acceptez les valeurs par défaut pour tous les autres champs.

    - **Réapprovisionner le modèle :** _Zone de réapprovisionnement min/max_
    - **Description :** _Réapprovisionnement min/max de zone_
    - **Type de réapprovisionnement :** _Minimum ou maximum_

1. Sélectionnez **Enregistrer**.
1. Alors que la nouvelle ligne est toujours sélectionnée dans la grille **Vue d’ensemble**, sélectionnez **Nouveau** au dessus de la grille **Détails du modèle de réapprovisionnement** pour ajouter une ligne associée au modèle de réapprovisionnement *Réapprovisionnement de zone min/max* que vous venez de créer.
1. Dans la nouvelle ligne, définissez les valeurs suivantes :

    - **Numéro de séquence :** Entrez _1_.
    - **Description :** Entrez _Réapprovisionnement de zone de prélèvement_.
    - **Unité de réapprovisionnement :** Sélectionnez _ea_.
    - **Type de demande :** Laissez ce champ vide.
    - **Code directif :** Ce champ associe le modèle de réapprovisionnement à une directive d’emplacement. Sélectionnez le code directif de données de démonstration créé précédemment (_Zone de réapprovisionnement_).
    - **Modèle de travail :** Laissez ce champ vide.
    - **Quantité minimale :** Ce champ définit la quantité à laquelle le réapprovisionnement sera déclenché. Entrez _50_.
    - **Quantité maximale :** Ce champ définit la quantité maximale d’un article qui peut être présent dans une zone. Le travail de réapprovisionnement généré augmentera le stock de cette quantité. Entrez _150_.
    - **Unité :** Ce champ définit l’unité pour les valeurs minimale et maximale. Cliquez sur _ea_.
    - **Incrément de demande :** Sélectionnez _Arrondir_.
    - **Réapprovisionner les emplacements fixes vides :** Cohez cette case.
    - **Réapprovisionner uniquement des emplacements fixes :** Décochez cette case.
    - **Mode de requête de produit :** Sélectionnez _Requête de produit_.
    - **Étendue du seuil de réapprovisionnement :** Ce champ définit si le modèle doit être évalué par zone ou par emplacement spécifique. Sélectionnez _Zone_.
    - **Entrepôt :** Sélectionner _61_.

1. Sélectionnez **Sélectionner les produits** au dessus de la grille **Détails du modèle de réapprovisionnement**.
1. Dans la boîte de dialogue **Requête de produit**, sous l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne à la grille.
1. Dans la nouvelle ligne, définissez les valeurs suivantes :

    - **Table :** _Articles_
    - **Table dérivée :** _Articles_
    - **Champ :** _Numéro d’article_
    - **Critères :** _A0001_

1. Sélectionnez **OK** pour enregistrer votre requête et fermer la boîte de dialogue.
1. Sélectionnez **Sélectionner les zones à réapprovisionner** au dessus de la grille **Détails du modèle de réapprovisionnement**.
1. Dans la boîte de dialogue **Requête de zone**, sous l’onglet **Plage**, ajoutez une ligne à la grille.
1. Dans la nouvelle ligne, définissez les valeurs suivantes :

    - **Table :** _Zone d’entrepôt_
    - **Table dérivée :** _Zone d’entrepôt_
    - **Champ :** _ID zone_
    - **Critères :** _SOL_

1. Sélectionnez **OK** pour enregistrer votre requête et fermer la boîte de dialogue.

### <a name="set-up-location-directives"></a>Définir des instructions d’emplacement

Contrairement au réapprovisionnement min/max basé sur l’emplacement, le réapprovisionnement min/max basé sur la zone nécessite que vous configuriez à la fois des directives d’emplacement de prélèvement et des directives d’emplacement de rangement, car le système évalue la zone entière au lieu de simplement l’emplacement de prélèvement pour le travail sortant.

#### <a name="view-and-edit-location-directives"></a>Afficher et modifier les directives d’emplacement

Pour afficher ou modifier les directives d’emplacement, accédez à **Gestion des entrepôts \> Paramétrage \> Directives d’emplacement**.

Pour des exemples qui montrent comment utiliser les paramètres pour créer les directives d’emplacement de prélèvement et les directives d’emplacement de rangement requises, consultez la section suivante.

#### <a name="prepare-demo-data-location-directives"></a>Préparer des directives d’emplacement de données de démonstration

Pour préparer des données de démonstration afin qu’elles puissent être utilisées dans le scénario à la fin de cet article, vous devez créer deux directives d’emplacement : une pour le prélèvement et l’autre pour le rangement.

##### <a name="create-a-replenishment-pick-directive"></a>Créer une directive de prélèvement de réapprovisionnement

1. Sélectionnez l’entité juridique **USMF** pour travailler avec les données de démonstration.
1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.
1. Dans le volet gauche, définissez le champ **Type d’ordre de travail** sur _Réapprovisionnement_.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une directive.
1. Définissez les valeurs suivantes :

    - **Souche de N° :** Acceptez la valeur par défaut.
    - **Nom :** Entrez _Zone de prélèvement_.
    - **Type de travail :** Sélectionnez _Prélèvement_.
    - **Site :** Sélectionnez _6_.
    - **Entrepôt :** Sélectionner _61_.
    - **Code directif :** Laissez ce champ vide.
    - **SKU multiple :** Définissez cette option sur _Non_.

1. Sélectionnez **Enregistrer** pour créer une directive contenant les paramètres que vous avez configurés jusqu’à présent.
1. Dans l’organisateur **Lignes**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Numéro de séquence :** Entrez _1_.
    - **Quantité de départ :** Entrez _0_.
    - **Quantité d’arrivée :** Entrez _10000000_.
    - **Unité :** Laissez ce champ vide.
    - **Localiser la quantité :** Sélectionnez _Aucun_.
    - **Restreindre par unité :** Décochez cette case.
    - **Arrondir à l’unité :** Décochez cette case.
    - **Localiser la quantité d’emballage :** Décochez cette case.
    - **Autoriser le fractionnement :** Cochez cette case.

1. Sélectionnez **Enregistrer** pour enregistrer la nouvelle ligne.
1. Alors que votre nouvelle ligne est toujours sélectionnée dans la grille **Lignes**, sélectionnez **Nouveau** sur l’organisateur **Actions de la directive d’emplacement** pour ajouter une ligne à la grille.
1. Dans la nouvelle ligne, définissez les valeurs suivantes :

    - **Numéro de séquence :** Entrez _1_.
    - **Nom :** Entrez _Prélèvement en vrac_.
    - **Utilisation de l’emplacement fixe :** Sélectionnez _Emplacements fixes et non fixes_.
    - **Autoriser le stock négatif :** Décochez cette case.
    - **Traitement par lots activé :** Décochez cette case.
    - **Stratégie :** Sélectionnez _Aucun_.

1. Sélectionnez **Enregistrer** pour enregistrer la nouvelle action.
1. Pendant que votre nouvelle action est toujours sélectionnée, sélectionnez **Modifier la requête** au dessus de la grille **Actions de la directive d’emplacement**.
1. Une boîte de dialogue de requête apparaît, dans laquelle vous pouvez sélectionner les emplacements à partir desquels vous réapprovisionnez. Sous l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne dans la grille.
1. Dans la nouvelle ligne, définissez les valeurs suivantes :

    - **Table :** _Emplacements_
    - **Table dérivée :** _Emplacements_
    - **Champ :** _ID zone_
    - **Critères :** _BULK_

1. Sélectionnez **OK** pour enregistrer votre requête et fermer la boîte de dialogue.
1. Sélectionnez **Enregistrer** pour enregistrer votre directive d’emplacement.

##### <a name="create-a-replenishment-put-directive"></a>Créer une directive de rangement de réapprovisionnement

1. Sur la page **Directives d’emplacement**, dans le volet gauche, assurez-vous que le champ **Type d’ordre de travail** est toujours défini sur _Réapprovisionnement_.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une autre directive.
1. Définissez les valeurs suivantes :

    - **Souche de N° :** Acceptez la valeur par défaut.
    - **Nom :** Entrez _Zone de rangement_.
    - **Type d’ordre de travail :** Sélectionnez _Rangement_.
    - **Site :** Sélectionnez _6_.
    - **Entrepôt :** Sélectionner _61_.
    - **Code directif :** Sélectionnez _Réapprovisionnement de zone_ pour lier cette directive d’emplacement au modèle de réapprovisionnement créé précédemment à l’aide du code créé précédemment.
    - **SKU multiple :** Définissez cette option sur _Non_.

1. Sélectionnez **Enregistrer** pour créer une directive contenant les paramètres que vous avez configurés jusqu’à présent.
1. Dans l’organisateur **Lignes**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Numéro de séquence :** Entrez _1_.
    - **Quantité de départ :** Entrez _0_.
    - **Quantité d’arrivée :** Entrez _10000000_.
    - **Unité :** Laissez ce champ vide.
    - **Localiser la quantité :** Sélectionnez _Aucun_.
    - **Restreindre par unité :** Décochez cette case.
    - **Arrondir à l’unité :** Décochez cette case.
    - **Localiser la quantité d’emballage :** Décochez cette case.
    - **Autoriser le fractionnement :** Cochez cette case.

1. Sélectionnez **Enregistrer** pour enregistrer la nouvelle ligne.
1. Alors que votre nouvelle ligne est toujours sélectionnée dans la grille **Lignes**, sélectionnez **Nouveau** sur l’organisateur **Actions de la directive d’emplacement** pour ajouter une ligne à la grille.
1. Dans la nouvelle ligne, définissez les valeurs suivantes :

    - **Numéro de séquence :** Entrez _1_.
    - **Nom :** Entrez _Zone de rangement_.
    - **Utilisation de l’emplacement fixe :** Sélectionnez _Emplacements fixes et non fixes_.
    - **Autoriser le stock négatif :** Décochez cette case.
    - **Traitement par lots activé :** Décochez cette case.
    - **Stratégie :** Sélectionnez _Consolider_.

1. Sélectionnez **Enregistrer** pour enregistrer la nouvelle action.
1. Pendant que votre nouvelle action est toujours sélectionnée, sélectionnez **Modifier la requête** au dessus de la grille **Actions de la directive d’emplacement**.
1. Une boîte de dialogue de requête apparaît, dans laquelle vous pouvez sélectionner la zone à réapprovisionner. Cette zone doit être la même que celle spécifiée dans le modèle de réapprovisionnement. Sous l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne dans la grille.
1. Dans la nouvelle ligne, définissez les valeurs suivantes :

    - **Table :** _Emplacements_
    - **Table dérivée :** _Emplacements_
    - **Champ :** _ID zone_
    - **Critères :** _SOL_

1. Sélectionnez **OK** pour enregistrer votre requête et fermer la boîte de dialogue.
1. Sélectionnez **Enregistrer** pour enregistrer votre directive d’emplacement.

## <a name="scenario"></a>Scénario

Cette section fournit un exemple de scénario qui montre comment utiliser la fonctionnalité.

### <a name="prepare-the-sample-data-that-is-required-for-the-sample-scenario"></a>Préparer les exemples de données requis pour l’exemple de scénario

Avant de commencer à travailler sur le scénario, vous devez activer des exemples de données et configurer la fonctionnalité comme décrit dans cette section et dans les sections précédentes de cet article.

#### <a name="use-the-usmf-legal-entity"></a>Utiliser l’entité juridique USMF

Pour utiliser le scénario à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

#### <a name="prepare-additional-sample-data"></a>Préparer des exemples de données supplémentaires

Après avoir sélectionné l’entité juridique **USMF**, ajoutez les données d’échantillon supplémentaires requises, comme décrit dans la section [Configurer le réapprovisionnement basé sur une zone](#setup) plus haut dans cet article.

#### <a name="check-your-on-hand-inventory"></a>Vérifier votre stock disponible

Suivez ces étapes pour vous assurer que votre système comprend suffisamment de stock pour prendre en charge l’exemple de scénario.

1. Assurez-vous qu’il y a un stock disponible pour l’article *A0001* à deux emplacements différents dans la zone de prélèvement (*SOL*) spécifié dans le modèle de réapprovisionnement. Cependant, le stock total doit être inférieur à la quantité minimale requise (*50*) spécifiée sur le modèle de réapprovisionnement. De cette façon, vous pouvez simuler la façon dont le calcul se produit pour la zone entière au lieu d’un seul emplacement. **Utilisez l’un des processus d’entrepôt pour ajuster le stock au besoin.**
1. Assurez-vous qu’il y a suffisamment de stock pour l’article *A0001* à un emplacement en vrac spécifié dans la directive d’emplacement de prélèvement de zone où le travail de réapprovisionnement doit prélever les articles de l’ID de zone *VRAC*. Le stock total doit être supérieur à la quantité maximale requise (*150*) spécifiée dans le modèle de réapprovisionnement.
1. Facultatif mais recommandé : Procédez comme suit pour créer un journal d’ajustement du stock :

    1. Accédez à **Gestion des stocks \> Entrées de journal \> Articles \> Ajustement de stock**.
    1. Sélectionnez **Nouveau**.
    1. Dans la la boîte de dialogue **Créer un journal de stock**, dans le champ **Entrepôt**, sélectionnez *61*.
    1. Cliquez sur **OK**.
    1. Sur l’organisateur **Lignes de journal**, utilisez le bouton **Nouveau** pour ajouter trois lignes à la grille et définissez les valeurs suivantes. Une fois la configuration de chaque ligne terminée, sélectionnez **Enregistrer**.

        - **Ligne 1 :**

            - **Numéro d’article :** *A0001*
            - **Site :** *6*
            - **Entrepôt :** *61*
            - **Emplacement :** *02A01R1S1B*
            - **Contenant :** Sélectionnez un contenant existant dans la liste ou créez un contenant.
            - **Quantité :** *1000*

        - **Ligne 2 :**

            - **Numéro d’article :** *A0001*
            - **Site :** *6*
            - **Entrepôt :** *61*
            - **Emplacement :** *07A01R2S1B*
            - **Contenant :** Sélectionnez un contenant existant dans la liste ou créez un contenant.
            - **Quantité :** *15*

        - **Ligne 3 :**

            - **Numéro d’article :** *A0001*
            - **Site :** *6*
            - **Entrepôt :** *61*
            - **Emplacement :** *07A01R1S1B*
            - **Contenant :** Sélectionnez un contenant existant dans la liste ou créez un contenant.
            - **Quantité :** *10*

    1. Dans le volet Action, sélectionnez **Valider**. Corrigez toutes les erreurs détectées avant de passer à l’étape suivante.
    1. Dans le volet Actions, sélectionnez **Valider** pour valider le stock dans l’entrepôt.

### <a name="sample-scenario-run-zone-based-minmax-replenishment"></a>Exemple de scénario : Exécuter un réapprovisionnement min/max basé sur une zone

Une fois que tous les exemples de données prérequis sont en place, vous pouvez déclencher le réapprovisionnement en suivant ces étapes.

1. Allez dans **Gestion des entrepôts \> Réapprovisionnement \> Réapprovisionnements**.
1. Dans la boîte de dialogue **Réapprovisionnement**, sur l’organisateur **Enregistrements à inclure**, sélectionnez **Filtrer**.
1. Dans la boîte de dialogue **Recherche**, sur l’onglet **Plage**, modifiez la ligne de la table par défaut de la manière suivante :

    - **Table :** Sélectionnez _Modèles de réapprovisionnement_.
    - **Table dérivée :** Sélectionnez _Modèles de réapprovisionnement_.
    - **Champ :** Sélectionnez _Modèle de réapprovisionnement_.
    - **Critères :** Sélectionnez _Zone min/max de réapprovisionnement_. Ce modèle de réapprovisionnement est le modèle de réapprovisionnement créé lors de la préparation des données de démonstration pour ce scénario.

1. Sélectionnez **OK** pour enregistrer la requête et revenez à la boîte de dialogue **Réapprovisionnement**.
1. Sélectionnez **OK** pour exécuter le modèle de réapprovisionnement.

Un travail de réapprovisionnement est maintenant créé pour prélever le zone de la zone *VRAC* et le réapprovisionner dans la zone *SOL*.

## <a name="notes-and-tips"></a>Remarques et conseils

Voici quelques remarques et conseils pour utiliser la fonctionnalité :

- Pour configurer le travail de réapprovisionnement qui va à la zone souhaitée, vous pouvez lier les lignes de modèle de réapprovisionnement et les directives d’emplacement de l’une des manières suivantes :

    - Modifiez la requête d’en-tête de directive d’emplacement et filtrez les lignes de modèle de réapprovisionnement sélectionnées.
    - Utiisez le code directif de la ligne d’emplacement de réapprovisionnement et mettez le en correspondance avec la directive d’emplacement de rangement.

- Si vous utilisez des emplacements dynamiques, le travail de réapprovisionnement sera créé soit pour le premier emplacement disponible, soit pour un emplacement qui contient déjà du stock, si l’action de directive d’emplacement est configurée pour utiliser la stratégie **Consolider**.
- Si vous utilisez des emplacements fixes au lieu de zones, vous devez utiliser le [réapprovisionnement min/max standard](tasks/set-up-min-max-replenishment-process.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]