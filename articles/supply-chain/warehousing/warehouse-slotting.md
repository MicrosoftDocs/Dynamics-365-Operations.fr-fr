---
title: Créneaux de l’entrepôt
description: Cette rubrique fournit des informations sur les créneaux de l’entrepôt. Les créneaux de l’entrepôt vous permettent de consolider la demande par article et unité de mesure à partir des commandes ayant le statut Commandé, Réservé ou Validé. Ils permettent aux gestionnaires d’entrepôt de planifier intelligemment les emplacements de prélèvement avant de passer des commandes à l’entrepôt et de créer des travaux de prélèvement.
author: mirzaab
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: fb39daba393944471ee5d412b1eb61754843926f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993751"
---
# <a name="warehouse-slotting"></a>Créneaux de l'entrepôt

[!include [banner](../includes/banner.md)]

Plusieurs fonctionnalités de créneaux d’entrepôt sont disponibles pour permettre aux gestionnaires d’entrepôt de planifier intelligemment les emplacements de prélèvement avant de passer des commandes à l’entrepôt et de créer des travaux de prélèvement.

La *fonctionnalité de créneaux de l’entrepôt* vous permet de consolider la demande par article et unité de mesure à partir des commandes ayant le statut *Commandé*, *Réservé* ou *Validé*. La demande générée peut ensuite être appliquée aux emplacements qui seront utilisés pour le prélèvement, en fonction de la quantité, de l’unité, des dimensions physiques, des emplacements fixes, etc. Une fois le plan des créneaux établi, le travail de réapprovisionnement peut être créé pour apporter la quantité appropriée de stock à chaque emplacement.

La fonctionnalité *Créneaux d'entrepôt pour les ordres de transfert* permet aux responsables d'entrepôt de réapprovisionner les emplacements de prélèvement, en fonction de la demande des ordres de transfert qui ne sont pas encore validés vers l'entrepôt. Cela garantit que les lieux de prélèvement incluront tous les articles requis pour les ordres de transfert après leur sortie dans l'entrepôt. Cette fonctionnalité nécessite que vous activiez également la fonctionnalité *Fonctionnalité de créneaux d'entrepôt*.

La fonctionnalité *Améliorations de l'allocation des créneaux d'entrepôt* ajoute une option pour les exemples de lignes utilisées par la fonctionnalité *Fonctionnalité de créneaux d'entrepôt*. L'option permet au système de prendre en compte le stock disponible existant à un emplacement cible. Par conséquent, moins de réapprovisionnements peuvent être générés pour les créneaux. La fonctionnalité *Améliorations de l'allocation des créneaux d'entrepôt* nécessite que vous activiez la fonctionnalité *Fonctionnalité de créneaux d'entrepôt*. Il peut éventuellement être utilisé avec la fonctionnalité *Créneaux d'entrepôt pour les ordres de transfert*.

## <a name="turn-on-the-warehouse-slotting-features"></a>Activer les fonctionnalités de créneaux d’entrepôt

Avant de pouvoir utiliser ces fonctionnalités, vous devez les activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut des fonctionnalités et les activer si nécessaire. Activez les fonctionnalités suivantes selon vos besoins :

- Fonction Entreposage
- Créneaux d'entrepôt pour les ordres de transfert

    > [!IMPORTANT]
    > La fonctionnalité *Fonctionnalité de créneaux d'entrepôt* doit être activée avant cette fonctionnalité.

- Améliorations de la répartition des créneaux d’entrepôt

    > [!IMPORTANT]
    > La fonctionnalité *Fonctionnalité de créneaux d'entrepôt* doit être activée avant cette fonctionnalité.

## <a name="set-up-warehouse-slotting"></a>Paramétrer les créneaux d’entrepôt

Pour utiliser les créneaux d’entrepôt, configurez les éléments suivants dans votre système :

- Barèmes d'unité de mesure des créneaux
- Codes instructions
- Modèles de créneaux
- Instructions d'emplacement

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a>Créer des niveaux d’unité de mesure pour les créneaux

Les niveaux d’unité de mesure permettent de regrouper plusieurs unités de mesure à des fins de créneaux. Par exemple, si plusieurs tailles de boîtes sont toutes prélevées dans la même zone de prélèvement de boîtes, un niveau peut être créé pour toutes les tailles. **Une ligne doit être créée pour chaque unité de mesure qui doit faire partie du niveau.**

1. Allez à **Gestion des entrepôts \> Paramétrer \> Réapprovisionnement \> Unité de mesure des niveaux de créneaux**.
1. Sélectionnez **Nouveau**.
1. Dans l'en-tête, définissez les valeurs suivantes :

    - **Niveau d’unité de mesure :** *EaBoxPl*
    - **Description :** *Chaque palette de boîte*

1. Sélectionnez **Enregistrer**.
1. Sur l’organisateur **Unités de mesure**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Unité :** *Boîte*
    - **Description :** Laissez ce champ vide. Il sera rempli automatiquement lorsque vous enregistrerez vos modifications.
    - **Classe d’unité :** *Quantité*

1. Cliquez sur **Nouveau** pour ajouter une seconde ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Unité :** *ea*
    - **Description :** Laissez ce champ vide. Il sera rempli automatiquement lorsque vous enregistrerez vos modifications.
    - **Classe d’unité :** *Quantité*

1. Cliquez sur **Nouveau** pour ajouter une troisième ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Unité :** *PL*
    - **Description :** Laissez ce champ vide. Il sera rempli automatiquement lorsque vous enregistrerez vos modifications.
    - **Classe d’unité :** *Quantité*

1. Sélectionnez **Enregistrer** pour enregistrer le niveau.

### <a name="create-a-directive-code-for-slotting"></a>Créer un code directif pour le créneau

Vous devez sélectionner le code de directive à associer à un modèle.

1. Allez dans **Gestion des entrepôts \> Configuration \> Codes de directives**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Code de directive**, entrez *Créneaux*.
1. Dans le champ **Description de la directive**, entrez *Créneaux*.

### <a name="set-up-slotting-templates"></a>Paramétrer les modèles de créneaux

Chaque modèle de créneau contrôle la façon dont le stock est affecté aux emplacements pour un entrepôt spécifique. Chaque modèle doit inclure une ligne pour chaque spécification de créneau. Utilisez les procédures de cette section pour configurer des modèles de créneau.

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Réapprovisionnement \> Modèles de créneaux**.
1. Sélectionnez **Nouveau** pour créer un modèle.

Ensuite, vous devez configurer l’en-tête du modèle, les spécifications de créneau et les directives d’emplacement, comme expliqué dans les sous-sections suivantes. La configuration des créneaux des ordres de transfert ressemble à la configuration des créneaux des commandes client, mais le champ **Type de demande** est défini sur *Ordres de transfert* au lieu de *Commande client*.

#### <a name="set-up-the-header-for-a-sales-order-slotting-template"></a>Configurer l'en-tête d'un modèle de créneau de commande client

1. Dans l’en-tête du modèle, définissez les valeurs suivantes :

    - **Modèle de créneau :** _61_
    - **Description :** _61_
    - **Type de demande :** *Commande client*

        > [!NOTE]
        > Actuellement, les *Commandes client* et les *Ordres de transfert* sont les seuls types de demandes pris en charge. Vous pouvez sélectionner *Ordres de transfert* seulement si la fonctionnalité *Créneaux d'entrepôt pour les ordres de transfert* est activée.

    - **Stratégie de demande :** _Commandé_

        Les valeurs suivantes sont disponibles dans ce champ :

        - **Commandé** - La quantité totale commandée sur la commande client doit être considérée comme une demande.
        - **Réservé** - Seules les quantités de ligne de commande client réservées (physiques et commandées) doivent être considérées comme une demande.
        - **Lancé** – La quantité lancée doit être considérée comme une demande.

    - **Entrepôt :** _61_
    - **Autoriser la demande de vague à utiliser des quantités non réservées :** _Oui_

Vous pouvez également spécifier une requête pour réduire l’étendue de la demande évaluée.

#### <a name="set-up-slotting-specifications-for-each-template"></a>Paramétrer les spécifications de créneau pour chaque modèle

Pour chaque modèle de commande client que vous créez, procédez comme suit pour ajouter une ligne pour chaque spécification de créneau.

1. Sur l’organisateur **Détails du modèle de créneau**, sélectionnez **Nouveau** pour créer un modèle de ligne.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Séquence :** _1_
    - **Description :** _Emplacement fixe_
    - **Quantité minimale :** _1_

        Ce champ définit la quantité minimale de demande requise pour la ligne.

    - **Quantité maximale :** _1000000_

        Ce champ définit la quantité maximale de demande valide pour la ligne.

    - **Unité :** Laissez ce champ vide.

        Ce champ définit l’unité de mesure à laquelle les quantités minimale et maximale se réfèrent.

    - **Niveau d’unité de mesure :** _EaBoxPl_

        Ce champ définit les unités de mesure de demande valides pour la ligne. (Pour plus d’informations, voir la section [Paramétrer les niveaux d’unités de mesure des créneaux](#unit-tiers) plus haut dans cette rubrique.)

    - **Attribuer des critères de créneau :** _Tenir compte de la quantité_

        Les valeurs suivantes sont disponibles dans ce champ :

        - **Supposer un emplacement vide** - Ce système doit supposer que tous les emplacements dans la zone de prélèvement sont vides et ne doit pas vérifier ces emplacements pour le stock.
        - **Tenir compte de la quantité** - Le système doit vérifier le stock des emplacements dans la zone de prélèvement et doit ignorer les emplacements non vides.
        - **Considérer comme disponible** – Le système doit vérifier si un emplacement cible contient des quantités non réservées pour l'article sur la ligne de demande. Si la quantité est suffisamment grande pour satisfaire au moins une unité de la ligne de demande, l'enregistrement de plan de créneau généré est réduit du montant disponible. Par exemple, si la demande est de 10 cartons et qu'un carton est disponible, la demande localisée sera de neuf cartons. Si la demande est de 10 cartons et qu'un de chaque est disponible, la demande localisée sera de 10 cartons. Cette valeur n’est disponible que lorsque la fonctionnalité *Améliorations de la répartition des créneaux d’entrepôt* est activée.

    - **Code de directive :** _Créneau_

        Ce champ définit la directive d’emplacement utilisée pour trouver l’emplacement de prélèvement du travail de réapprovisionnement.

    - **Emplacement de débordement :** Laissez ce champ vide.

        Ce champ définit l’emplacement dans lequel le stock est rangé si aucun emplacement ne peut être trouvé pour la quantité lorsque la ligne est traitée.

    - **Autoriser un creux :** _Oui_

        Lorsque cette option est définie sur *Oui*, si aucune demande ne peut être établie en créneau, un travail de mouvement sera créé pour retirer le stock des emplacements où il y en a, mais où rien n’a été réparti en créneaux. Le modèle est ensuite réexécuté. Cette fois, il ignore le stock des emplacements. Cette fonctionnalité fonctionne mieux lorsque le champ **Attribuer des critères de créneau** est défini sur _Tenir compte de la quantité_.

    - **Utilisation d’emplacement fixe :** _N’utiliser des emplacements fixes que pour le produit_

        Les valeurs suivantes sont disponibles dans ce champ :

        - **Emplacements fixes et non fixes** - Le système ne doit pas se limiter à n’utiliser que des emplacements fixes.
        - **N’utiliser des emplacements fixes que pour le produit** - Le système ne doit créer des créneaux qu’aux emplacements qui sont fixes pour le produit.
        - **N’utiliser des emplacements fixes que pour la variante de produit** - Le système ne doit créer des créneaux qu’aux emplacements qui sont fixes pour la variante de produit.

> [!NOTE]
> Si l'exemple de créneau contient au moins une ligne où le champ **Attribuer des critères de créneau** est défini sur *Considérer comme disponible*, les creux ne sont plus autorisés pour aucune ligne du modèle.

1. Sélectionnez **Enregistrer**.
1. Cliquez sur **Nouveau** pour créer une seconde ligne de modèle.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Séquence :** _2_
    - **Description :** _Autre_
    - **Quantité minimale :** _1_
    - **Quantité maximale :** _1000000_
    - **Unité :** Laissez ce champ vide.
    - **Niveau d’unité de mesure :** _EaBoxPl_
    - **Attribuer des critères de créneau :** _Tenir compte de la quantité_
    - **Code de directive :** _Créneau_
    - **Emplacement de débordement :** Laissez ce champ vide.
    - **Autoriser un creux :** _Oui_
    - **Utiliser des emplacements fixes :** _Emplacements fixes et non fixes_

    Dans la requête pour la deuxième ligne, vous allez maintenant spécifier les critères utilisés pour déterminer vers quels emplacements la demande pour cette ligne peut être insérée en créneau.

1. Sélectionnez la ligne où le champ **Séquence** est défini sur *2*.
1. Sélectionnez **Modifier une requête**.
1. Sous l'onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Table :** *Emplacements*
    - **Table dérivée :** *Emplacements*
    - **Champ :** *Location profile ID*
    - **Critères :** *Prélever-06* (Sélectionnez le double signe plus \[**++**\] dans le champ pour développer la liste, puis sélectionnez *Prélever-06* - *Site de prélèvement 6*.)

1. Cliquez sur **OK**.

#### <a name="set-up-location-directives"></a>Définir des instructions d’emplacement

Au moins une directive d’emplacement doit être configurée pour prendre en charge les choix de créneau. Utilisez les procédures de cette section pour configurer une nouvelle *directive sur l’emplacement de réapprovisionnement* pour les pics de créneaux.

1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d'emplacements**.
1. Dans le volet gauche, dans le champ **Type d’ordre de travail**, cliquez sur *Réapprovisionnement*.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans l’en-tête de la nouvelle directive d’emplacement, dans le champ **Nom**, entrez *Prélèvement de créneau 61*.
1. Dans le champ **Souche de N°**, acceptez la valeur par défaut.

##### <a name="configure-the-location-directives-fasttab"></a>Configurer l’organisateur Directives d’emplacement

1. Dans l’organisateur **Directives d’emplacement**, définissez les valeurs suivantes. Acceptez les valeurs par défaut pour tous les autres champs.

    - **Type de travail :** _Choisir_
    - **Site :** _6_
    - **Entrepôt :** _61_
    - **Code de directive :** _Créneau_

1. Sélectionnez **Enregistrer** pour rendre l'organisateur **Lignes** disponible.

##### <a name="configure-the-lines-fasttab"></a>Configurer l’organisateur Lignes

1. Dans l’organisateur **Lignes**, cliquez sur **Nouveau** pour créer une ligne.
1. Sur la nouvelle ligne, définissez les valeurs suivantes.

    - **Quantité de départ :** _0_
    - **Quantité d’arrivée :** _1000000_

1. Acceptez les valeurs par défaut pour les champs restants.
1. Sélectionnez **Enregistrer** pour rendre l'organisateur **Actions d'instruction d'emplacement** disponible.

##### <a name="configure-the-location-directive-actions-fasttab"></a>Configurer l’organisateur Actions des directives d’emplacement

1. Dans l’organisateur **Actions des directives d’emplacement**, cliquez sur **Nouveau** pour créer une ligne.
1. Sur la nouvelle ligne, définissez les valeurs suivantes. Acceptez les valeurs par défaut pour tous les autres champs.

    - **Souche de N° :** Acceptez la valeur par défaut.
    - **Nom :** _Vrac_
    - **Stratégie :** _Aucun_

1. Acceptez les valeurs par défaut pour les champs restants.
1. Sélectionnez **Enregistrer** pour rendre le bouton **Modifier la requête** disponible.

##### <a name="edit-the-query"></a>Modifier la requête

1. Dans l’organisateur **Actions de directive d’emplacement**, sélectionnez **Modifier la requête**.
1. Sous l'onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Table :** *Emplacements*
    - **Table dérivée :** *Emplacements*
    - **Champ :** *ID zone*
    - **Critères :** *Vrac* (Sélectionnez le double signe plus \[**++**\] dans le champ pour développer la liste, puis sélectionnez *Vrac*.)

1. Cliquez sur **OK**.

## <a name="scenario"></a>Scénario

### <a name="set-up-the-scenario"></a>Paramétrage du scénario

Pour ce scénario, utilisez les exemples de données intégrés et créez les enregistrements décrits dans cette section.

#### <a name="use-the-usmf-sample-data"></a>Utiliser les exemples de données USMF

Pour utiliser ce scénario à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

#### <a name="create-demand"></a>Créer une demande

Suivez ces étapes pour créer la demande à laquelle vous allez appliquer le créneau.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau** pour créer une commande client.
1. Dans la boîte de dialogue **Créer une commande client**, dans le champ **Compte client**, sélectionnez _US-007_.
1. Dans le champ **Entrepôt**, sélectionnez _61_.
1. Cliquez sur **OK**.
1. La nouvelle commande client est ouverte. Elle comprend une ligne vide sur l’organisateur **Lignes de commande client**. Sur cette ligne, définissez les valeurs suivantes :

    - **Article :** _L0101_
    - **Quantité :** _20_

1. Sélectionnez **Ajouter une ligne** pour ajouter une nouvelle ligne, puis définissez les valeurs suivantes :

    - **Article :** _T0100_
    - **Quantité :** _8_

1. Sélectionnez **Enregistrer**.
1. Sélectionnez **Nouveau** pour créer une deuxième commande client.
1. Dans la boîte de dialogue **Créer une commande client**, dans le champ **Compte client**, sélectionnez _US-008_.
1. Dans le champ **Entrepôt**, sélectionnez _61_.
1. La nouvelle commande client est ouverte. Elle comprend une ligne vide sur l’organisateur **Lignes de commande client**. Sur cette ligne, définissez les valeurs suivantes :

    - **Article :** _T0100_
    - **Quantité :** _1_

1. Sélectionnez **Enregistrer**.

### <a name="walk-through-a-typical-slotting-scenario"></a>Exécuter un scénario de créneau typique

Une fois que tous les éléments prérequis sont en place, comme décrit dans la section précédente, vous êtes prêt à essayer la fonctionnalité en effectuant chaque exercice de cette section.

#### <a name="generate-demand"></a>Générer une demande

1. Accédez à **Gestion des entrepôts \> Configuration \> Réapprovisionnement \> Modèles de créneaux**, puis sélectionnez le modèle de créneau créé précédemment.
1. Dans le volet Actions, sélectionnez **Générer la demande**. Cette commande évalue toute la demande qui se trouve dans le système et qui correspond à la requête de modèle de créneau. La demande totale de toutes les commandes est ensuite consolidée sur une ligne par quantité/unité de mesure. Un message d’information apparaît lorsque le processus est terminé.

#### <a name="slotting-demand"></a>Demande de créneaux

La *demande de créneau* affiche les résultats de la génération de la demande, en fonction de la configuration du modèle de créneau.

- Dans le volet Actions, sélectionnez **Demande de créneau** pour afficher les résultats de la commande **Générer une demande**. Les lignes de la demande de créneau peuvent être modifiées. Vous pouvez supprimer une ligne, ajouter une nouvelle ligne ou modifier les détails de la ligne.

> [!NOTE]
> Vous pouvez modifier la demande manuellement ou l’importer à partir d’un système externe à l’aide de la gestion des données. Tout ce qui se trouve dans le créneau sera utilisé à l’étape suivante, peu importe d’où il vient.

#### <a name="locate-demand"></a>Localiser la demande

Une fois la demande générée, vous devez utiliser la commande **Localiser la demande** pour générer le *plan de créneau*.

- Dans le volet Actions, sélectionnez **Localiser la demande**. Le processus de créneau s’exécute. Un message d’information apparaît lorsque le processus est terminé.

#### <a name="slotting-plan"></a>Plan de créneaux

Le plan de créneau indique l’emplacement auquel chaque article/quantité a été affecté(e), si un débordement a été utilisé, si un travail de creux a été créé et la ligne de modèle utilisée. *Toute demande qui n’a pas pu être insérée dans un créneau est surlignée en rouge.*

- Dans le volet Actions, sélectionnez **Plan de créneau** pour voir les résultats.

> [!NOTE]
> - Les processus **Générer une demande**, **Localiser une demande**, et **Exécuter le réapprovisionnement** sont maintenant exécutés dans un bac à sable. (Ces processus sont disponibles dans le volet Actions sur la page **Exemples de créneaux**.)
> - Les processus **Générer une demande**, **Localiser une demande**, et **Exécuter le réapprovisionnement** ont un verrou pour s'assurer qu'ils ne peuvent pas être déclenchés en même temps. Sinon, les données utilisées pourraient être supprimées.
> - Les processus **Générer une demande** et **Localiser une demande** affichent un avertissement si l'exécution n'a pas généré d'enregistrements ou si les enregistrements ne contiennent pas d'informations.
> - Lorsque vous sélectionnez **Plan de créneaux**, la page n'a pas les boutons **Nouveau**, **Modifier** ou **Supprimer** du volet Actions, car la source de données ne peut pas être modifiée.
> - Lorsque vous sélectionnez **Exécuter le réapprovisionnement**, le système valide le modèle de créneau sélectionné et traite.

#### <a name="create-replenishment"></a>Créer un réapprovisionnement

Une fois le plan de créneau créé, vous devez créer un *travail de réapprovisionnement*, sur la base du plan.

- Dans le volet Actions, sélectionnez **Exécuter le réapprovisionnement**. Un message d’information apparaît lorsque le processus est terminé. Ce message indique le nombre d’en-têtes créés pour l’ID de build de travail.

Les directives d’emplacement qui seront utilisées sont identifiées en fonction du code de directive spécifié sur chaque ligne de modèle.

## <a name="tips"></a>Conseils

### <a name="set-up-automatic-slotting"></a>Paramétrer les créneaux automatiques

Une fois que tous les éléments requis sont en place, vous pouvez configurer l’exécution automatique des créneaux en suivant ces étapes.

1. Allez dans **Gestion des entrepôts \> Réapprovisionnement \> Exécuter le créneau**.
1. Spécifiez les étapes de création de créneaux à exécuter. Sélectionnez une ou plusieurs des étapes de création de créneau suivantes :

    - Générer une demande
    - Localiser la demande
    - Créer un travail de réapprovisionnement

    > [!NOTE]
    > Les étapes de création de créneau sont progressives. Si vous souhaitez sélectionner *Localiser la demande*, vous devez d’abord sélectionner *Générer une demande*.

1. Spécifiez le modèle de créneau à utiliser.
1. Définissez la récurrence d’exécution automatique, si vous le souhaitez.

Pour les exercices du scénario, **ne paramétrez pas** la création de créneau automatique.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]