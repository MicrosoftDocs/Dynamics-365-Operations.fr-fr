---
title: Création de chargement avancée pendant une vague
description: Cet article donne des informations sur la création de chargement avancée, qui affecte automatiquement des expéditions aux vagues existantes pendant l’exécution de la vague. Par conséquent, vous pouvez créer des chargements significatifs qui représentent des camions sans avoir à utiliser l’atelier de planification des chargements.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPostMethod,WHSWaveTemplateTable,WHSLoadMixGroup,WHSLoadBuildTemplate, WHSWaveTableListPage, TMSLoadBuildTemplateApply, TMSLoadBuildTemplates, TMSLoadBuildTemplateCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 76aee3a736efa9ed7431d4e5127cd0abaccd659f
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218846"
---
# <a name="advanced-load-building-during-wave"></a>Création de chargement avancée pendant une vague

[!include [banner](../includes/banner.md)]

La création de chargement avancée affecte automatiquement des expéditions aux vagues existantes pendant l’exécution de la vague. Par conséquent, vous pouvez créer des chargements significatifs qui représentent des camions sans avoir à utiliser l’atelier de planification des chargements. Cette fonctionnalité est utile pour les entreprises qui souhaitent utiliser le concept de chargements pour suivre et planifier l’expédition de marchandises dans un camion/une remorque, mais qui ne souhaitent pas créer manuellement ces chargements chaque jour.

Pendant le traitement de la vague, le système crée généralement un nouveau chargement pour chaque expédition à laquelle aucun chargement n’est affecté. Cependant, lorsque la création de chargement avancée est activée, le système affecte chaque expédition non affectée à un chargement existant (s’il existe un chargement approprié), et de nouveaux chargements sont créés uniquement si nécessaire. La création de chargement avancée crée automatiquement les nouveaux chargements sur la base de critères que vous définissez.

Pour utiliser la fonctionnalité, vous devez configurer le système comme suit :

- Créez des *modèles de vague* qui incluent la nouvelle méthode **buildLoads**. Cette méthode rend la création de chargement avancée disponible pour les vagues qui utilisent ces modèles.
- Définissez des *modèles de création de chargement*, chacun étant lié à un modèle et une méthode de vague spécifiques. Les modèles de création de chargement contrôlent le chargement (existant ou nouveau) auquel sont ajoutées les lignes de chargement traitées par vagues. Vous pouvez combiner ou séparer les expéditions en fonction de critères tels que le modèle de chargement, l’équipement et d’autres valeurs de champ sur la ligne de chargement.
- Définissez des *groupes d’assocations de chargement* pour contrôler les articles qui doivent et ne doivent pas être combinés sur un seul chargement. Vous spécifiez également si la restriction doit produire un avertissement ou une erreur et si la restriction volumétrique du modèle de chargement doit être évaluée.

## <a name="turn-on-advanced-wave-load-building-in-your-system"></a>Activer la création de chargement avancée dans votre système

Avant de pouvoir utiliser la création de chargement avancée, deux fonctionnalités doivent être activées dans votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de ces fonctionnalités et les activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, les fonctionnalités sont répertoriées comme suit :

- Fonctionnalité de création de chargement :

    - **Module :** *Gestion des entrepôts*
    - **Nom de la fonctionnalité :** *Fonctionnalité de création de chargement*

- Code étape de vague à l’échelle de l’organisation :

    - **Module :** *Gestion des entrepôts*
    - **Nom de la fonctionnalité :** *Code étape de vague à l’échelle de l’organisation*

### <a name="make-sample-data-available"></a>Rendre les exemple de données disponibles

Pour utiliser cette démonstration à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

Vous pouvez également utiliser cette démonstration comme orientation pour utiliser cette fonctionnalité lorsque vous travaillez sur un système de production. Cependant, dans ce cas, vous devez remplacer vos propres valeurs, et il se peut que certains types d’enregistrements requis que les données de démonstration standard fournissent manquent.

### <a name="make-sure-that-the-scenario-setup-includes-enough-available-inventory"></a>Vérifier que la configuration du scénario comprend un stock disponible suffisant

Si vous utilisez les données de démonstration **USMF**, vous devez d’abord vous assurer que votre système est configuré de telle sorte qu’un stock suffisant soit disponible dans chaque emplacement approprié. Pour cette démonstration, le stock suivant devrait être disponible dans l’entrepôt *62* :

- **Article A0001 :** 10 pcs
- **Article A0002 :** 10 pcs
- **Article M9200 :** 10 ea

L’article **M9200** doit être ajouté à l’entrepôt. Exécutez les procédures des sous-sections suivantes pour ajouter le stock d’articles.

#### <a name="create-a-new-license-plate-id"></a>Créer un ID contenant

1. Allez à **Gestion des entrepôts** \> **Paramétrage** \> **Entrepôt** \> **Contenants**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la nouvelle ligne, dans le champ **Contenant**, entrez *LP6203*.
1. Sélectionnez **Enregistrer**.

#### <a name="create-a-standard-cost-for-item-m9200-in-site-6"></a>Créer un coût standard pour l’article M9200 dans le site 6

1. Allez à **Gestion des informations sur les produits** \> **Produits** \> **Produits lancés**.
1. Recherchez **M9200**.
1. Sélectionnez la ligne de l’article, puis, dans le volet Actions, sous l’onglet **Gérer les coûts**, dans le groupe **Paramétrer**, sélectionnez **Prix de l’article**.
1. Sur la page **Prix de l’article**, sélectionnez l’onglet **Prix en attente**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Type d’évaluation des coûts :** *Coût planifié*
    - **Type de prix :** *Coût*
    - **Version :** *10*
    - **Site :** *6*
    - **Prix :** *1,60*

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le volet Actions, sélectionnez **Activer le ou les prix en attente**.
1. Sélectionnez l’onglet **Prix actifs** pour vérifier que le nouveau prix de revient pour le site *6* a été ajouté.

#### <a name="create-inventory-in-warehouse-62"></a>Créer un stock dans l’entrepôt 62

1. Allez à **Gestion des stocks** \> **Entrées de journal** \> **Articles** \> **Ajustement de stock**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer un journal de stock**, dans l’organisateur **Vue d’ensemble**, dans le champ **Entrepôt**, entrez *62*. Acceptez les valeurs par défaut dans tous les autres champs.
1. Sélectionnez **OK** pour fermer la boîte de dialogue.
1. La page **Ajustement de stock** est ouverte. Dans l’organisateur **Lignes de journal**, sélectionnez **Nouveau** pour ajouter une ligne.
1. Sur la nouvelle ligne, définissez les valeurs suivantes. Acceptez les valeurs par défaut dans tous les autres champs.

    - **Numéro d’article :** *M9200*
    - **Emplacement :** *bulk-003*
    - **Quantité :** Modifiez la valeur sur *10*.

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le volet Actions, sélectionnez **Valider** pour rechercher des erreurs.
1. Dans la boîte de dialogue **Vérifier le journal**, cliquez sur **OK** pour démarrer la vérification. Vous recevez un message lorsque la vérification est terminée.
1. Dans le volet Actions, sélectionnez **Valider** pour valider l’ajustement du stock.
1. Dans la boîte de dialogue **Valider le journal**, cliquez sur **OK** pour démarrer la validation. Vous recevez un message lorsque la validation est terminée.

## <a name="set-up-advanced-wave-load-building"></a>Configurer la création de chargement avancée

### <a name="regenerate-wave-process-methods"></a>Régénérer les méthodes de traitement de la vague

Vous devrez peut-être régénérer vos méthodes de traitement de la vague pour rendre la méthode de création de chargement (**buildLoads**) disponible.

1. Allez à **Gestion des entrepôts** \> **Paramétrage** \> **Vagues** \> **Méthodes de traitement de la vague**.
2. Vérifiez que la méthode **buildLoads** est présente dans la liste. Si elle n’est pas présente, sélectionnez **Régénérer des méthodes** dans le volet Actions pour l’ajouter.

### <a name="set-up-wave-templates"></a>Définir des modèles de vague

Pour tirer parti de la création de chargement avancée, vous devez inclure la méthode **buildLoads** dans chaque [modèle de vague](tasks/configure-wave-processing.md) approprié.

1. Allez à **Gestion des entrepôts** \> **Paramétrage** \> **Vagues** \> **Modèles de vague**.
1. Sélectionnez un modèle de vague.

    Si vous utilisez les données de démnstration **USMF**, sélectionnez le modèle **62 Expédition par défaut**.

1. Dans le volet Actions, sélectionnez **Modifier** pour afficher la page en mode d’édition.
1. Dans l’organisateur **Méthodes**, dans la grille **Méthodes restantes**, sélectionnez la méthode **buildLoads**.
1. Sélectionnez le bouton Flèche droite pour déplacer la méthode **buildLoads** vers la grille **Méthodes sélectionnées**.
1. Pour attribuer une valeur **Code étape de vague** à la méthode **buildLoads**, vous devez d’abord créer un code sur la page **Codes étape de vague**. Vous pouvez utiliser n’importe quelle valeur de votre choix, mais veillez à en prendre note, car vous en aurez besoin plus tard. Pour créer un code **WSC2112**, procédez comme suit :

    1. Dans la ligne de la méthode **buildLoads**, cliquez avec le bouton droit sur la flèche vers le bas dans le champ **Code étape de vague**, puis sélectionnez **Afficher les détails**.
    1. Sur la page **Codes étape de vague**, dans le volet Actions, sélectionnez **Nouveau**.
    1. Dans le champ **Code étape de vague**, entrez *WSC2112*.
    1. Dans le champ **Description de l’étape de vague**, entrez *WSC2112*.
    1. Dans le champ **Type d’étape de vague**, sélectionnez *Création de chargement*.

1. Cliquez sur **Enregistrer**, puis fermez la page.
1. Dans la ligne de la méthode **buildLoads**, dans le champ **Code étape de vague**, sélectionnez le code que vous venez de créer (**WSC2112**).
1. Dans le volet Actions, sélectionnez **Enregistrer**.

> [!NOTE]
> Les codes étape de vague désignent des codes que les utilisateurs peuvent paramétrer et utiliser pour lier des instances spécifiques de méthodes de vague aux modèles correspondants. Parmi les modèles figurent des modèles pour le réapprovisionnement, la mise en conteneur, l’impression d’étiquettes, la création de chargement et le tri.
>
> Lorsque les codes étape de vague ne sont pas utilisés, les utilisateurs doivent saisir un texte libre en référence à un modèle spécifique depuis l’instance de la méthode de vague. Le texte libre engendre des erreurs, car les utilisateurs doivent s’assurer à ce que le texte de l’étape de vague qu’ils ajoutent pour une méthode d’étape de vague spécifique dans un modèle de vague corresponde exactement au texte de l’étape de vague dans le modèle cible.
>
> Les codes étape de vague pour un type d’étape de vague spécifique sont configurés sur une page à part. Pour chaque instance d’une méthode d’étape de vague dans un modèle de vague qui exige un code étape de vague, il convient de sélectionner ce dernier dans une liste déroulante. La sélection dans une liste déroulante remplace la saisie de texte libre et permet de réduire le risque et l’impact d’erreurs humaines. Les codes de configuration sont utilisés pour associer une méthode d’étape de vague dans un modèle de vague à un modèle cible pour la méthode.

### <a name="set-up-load-mix-groups"></a>Définir des groupes de combinaisons de chargement

Les groupes de combinaisons de chargement établissent des règles pour les types d’articles pouvant être combinés sur un seul chargement. Vous pouvez définir autant de groupes de combinaisons de chargement que vous le souhaitez. Cependant, pour utiliser la création de chargement avancée, vous devez en avoir au moins un. Pour créer un groupe de combinaisons de chargement, procédez comme suit :

1. Allez dans **Gestion des entrepôts** \> **Paramétrage** \> **Chargement** \> **Groupes de combinaisons de chargement**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un groupe de chargement.
1. Dans le champ **ID groupe de combinaisons de chargement**, entrez un nom pour le nouveau groupe.

    Si vous utilisez les données de démonstration **USMF**, définissez les valeurs suivantes :

    - **ID groupe de combinaisons de chargement :** *TV*
    - **Description :** *TV*

1. Dans le volet Actions, sélectionnez **Enregistrer** pour rendre l’organisateur **Critères du groupe de combinaisons de chargement** disponible.
1. Dans l’organisateur **Critères du groupe de combinaisons de chargement**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Dans la nouvelle ligne, définissez les valeurs souhaitées dans chaque champ. Ces valeurs déterminent les groupes d’articles pris en compte pour la combinaison de chargement.

    Si vous utilisez les données de démonstration **USMF**, sélectionnez *TV et vidéo* dans le champ **Groupe d’articles**.

1. Dans le volet Actions, sélectionnez **Enregistrer** pour rendre l’organisateur **Contraintes du groupe de combinaisons de chargement** disponible.
1. Dans l’organisateur **Contraintes du groupe de combinaisons de chargement**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Dans la nouvelle ligne, définissez les valeurs souhaitées dans chaque champ.

    Si vous utilisez les données de démonstration **USMF**, définissez les valeurs suivantes :

    - **Groupe d’articles :** *CarAudio*
    - **Action de création de chargement :** *Restreindre* (Cette valeur va empêcher les articles appartenant au groupe d’articles **CarAudio** de figurer sur le même chargement que les articles appartenant au groupe d’articles **TV et vidéo**.)

1. Continuez à utiliser les règles jusqu’à ce que vous ayez ajouté tous les critères et toutes les contraintes nécessaires pour le groupe de combinaisons de chargement.

Si vous utilisez les données de démonstration **USMF**, vous avez maintenant terminé cette configuration.

### <a name="set-up-load-build-templates"></a>Définir des modèles de création de chargement

Vous pouvez définir autant de modèles de création de chargement que vous le souhaitez. Cependant, pour utiliser la création de chargement avancée, vous devez en avoir au moins un. Pour créer un modèle de création de chargement, procédez comme suit.

1. Allez à **Gestion des entrepôts** \> **Paramétrage** \> **Chargement** \> **Modèles de création de chargement**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Dans la nouvelle ligne, définissez les valeurs suivantes.

    | Champ | Description | Valeur dans les données de démonstration USMF |
    |---|---|---|
    | Numéro de séquence | Ordre d’évaluation du modèle. | *1* |
    | Nom du modèle de création de chargement | Entrez l’identificateur unique du modèle de création de chargement. Vous devez entrer le nom du modèle que vous avez créé ou mis à jour précédemment dans cette configuration. | *62 Expédition par défaut* |
    | Code étape de vague | Entrez le code étape de vague à utiliser pour lier le modèle à une méthode de vague. Vous devez entrer le code que vous avez sélectionné pour la méthode **buildLoads** lorsque vous avez défini le modèle de vague précédemment dans cette configuration. | *WSC2112* |
    | ID modèle de charge | Sélectionnez le modèle de chargement à utiliser lors de la création de nouveaux chargements et à mettre en correspondre lors de l’affectation à des chargements existants. Le modèle de chargement définit le poids et le volume maximum autorisés pour l’ensemble du chargement. | *Modèle de chargement standard* |
    | Matériel | Équipement à mettre en correspondre lors de l’affectation à des chargements existants, et à entrer sur les nouveaux chargements créés. | Laissez ce champ vide. |
    | ID du groupe de mélange de charge | Sélectinnez le groupe de combinaisons de chargement à utiliser si l’article est autorisé sur le chargement. Le groupe de combinaisons établit des règles pour les types d’articles pouvant être combinés sur un seul chargement. Vous devez sélectionner l’un des groupes de combinaisons que vous avez créés précédemment dans cette configuration. | *TV* |
    | Utiliser les chargements en cours | Indiquez si les chargements en cours existants doivent être ajoutés. Les options suivantes sont disponibles :<ul><li>**Aucun** - N’ajoutez pas les chargements en cours aux chargements existants.</li><li>**N’importe lequel/laquelle** - Ajoutez les chargements en cours aux chargements existants valides pour la ligne.</li><li>**Affecté** - Ajoutez les chargements en cours au chargement affecté à la vague.</li></ul> | *N’importe lequel/laquelle* |
    | Créer des chargements | Spécifiez si de nouveaux chargements doivent être créés si aucun chargement existant ne correspond aux critères. | Sélectionné (= *Oui*) |
    | Autoriser le fractionnement de la ligne d’expédition | Indiquez si une ligne de chargement unique peut être fractionnée en plusieurs chargements si la ligne entière dépasse la capacité maximale du modèle de chargement. | Désactivé (= *Non*) |
    | Valider les mesures de volume | Indiquez si la création de chargement doit vérifier le poids et le volume lorsque chaque ligne de chargement est ajoutée pour s’assurer que les limites volumétriques du modèle de chargement sont respectées. | Désactivé (= *Non*) |

1. Dans le volet Actions, sélectionnez **Enregistrer** pour rendre l’option **Modifier la requête** disponible.
1. Dans le volet Actions, sélectionnez **Modifier la requête** pour ouvrir une boîte de dialogue permettant de modifier la requête.
1. Dans la boîte de dialogue, sous l’onglet **Tri**, sélectionnez **Ajouter** pour ajouter une ligne à la grille.
1. Dans la nouvelle ligne, définissez les règles de tri que vous souhaitez utiliser. Par exemple, définissez les valeurs suivantes pour trier les résultats de la recherche dans l’ordre croissant par numéro de commande :

    - **Table :** *Détails du chargement*
    - **Table dérivée :** *Détails du chargement*
    - **Champ :** *Numéro de commande*
    - **Ordre de tri :** *Croissant*

1. Cliquez sur **OK** pour enregistrer vos modifications et fermer la boîte de dialogue.
1. Dans l’organisateur **Répartir par**, définissez des règles pour contrôler le fractionnement de vos chargements. Généralement, vous pouvez répartir selon les champs personnalisés qui ont été étendus sur la ligne de chargement, par exemple **Gamme**, **Visite guidée** ou **Exécuter**. Par exemple, pour créer un chargement par numéro de commande, cochez la case **Répartir par** pour la ligne présentant les valeurs suivantes :

    - **Nom de la table de référence :** *Détails du chargement*
    - **Nom du champ de référence :** *Numéro de commande*

## <a name="scenario"></a>Scénario

Ce scénario montre comment les paramètres décrits précédemment dans cet article affectent les opérations d’entrepôt pendant le traitement d’une commande client. Ce scénario utilise les données de démonstration **USMF** ainsi que d’autres valeurs de démonstration fournies dans ces instructions de configuration.

### <a name="create-sales-orders"></a>Créer des commandes client

1. Accédez à **Ventes et marketing** \> **Commandes client** \> **Toutes les commandes client**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ouvrir la boîte de dialogue **Créer une commande client**.
1. Dans la boîte de dialogue, définissez les valeurs suivantes :

    - Dans l’organisateur **Client**, définissez le champ **Compte client** sur *US-007*.
    - Dans l’organisateur **Général**, définissez le champ **Entrepôt** sur *62*.

1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.
1. Votre nouvelle commande client est ouverte. Elle doit inclure une nouvelle ligne vide dans la grille de l’organisateur **Lignes de commande client**. Sur cette nouvelle ligne, définissez le champ **Numéro d’article** sur *A0001* et le champ **Quantité** sur *1*.
1. Dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.
1. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot**.
1. Sélectionnez le bouton **Fermer** (**X**) dans le coin supérieur droit de la page pour revenir à la commande client.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**. Le système crée une expédition et l’ajoute à un nouveau chargement, car aucun chargement existant ne contient de lignes de chargement portant ce numéro de commande.

    Vous recevez des messages d’information indiquant le travail, la vague et l’expédition créés pour cette commande.

1. Pour confirmer les détails du chargement, de l’expédition et du travail sur la ligne de vente, sélectionnez la ligne, puis, dans le menu **Entrepôt** au-dessus de la grille, sélectionnez **Détails du chargement**, **Détails de l’expédition** ou **Détails du travail**.
1. Dans la commande client que vous venez de créer, Dans l’organisateur **Lignes de commande client**, sélectionnez **Ajouter une ligne** pour ajouter une autre ligne.
1. Sur la nouvelle ligne, définissez le champ **Numéro d’article** sur *A0002* et le champ **Quantité** sur *1*.
1. Répétez les lignes 6 à 9 pour réserver la ligne et la libérer dans l’entrepôt. Le système crée une **nouvelle** expédition pour la ligne que vous avez ajoutée. Cependant, comme vous utilisez la création de chargement avancée, le système ajoute cette ligne d’expédition et de chargement à la vague existante. Si vous n’utilisiez pas la création de chargement avancée, le système créerait un nouveau chargement pour l’expédition.
1. Dans la commande client que vous venez de créer, Dans l’organisateur **Lignes de commande client**, sélectionnez **Ajouter une ligne** pour ajouter une autre ligne.
1. Sur la nouvelle ligne, définissez le champ **Numéro d’article** sur *M9200* et le champ **Quantité** sur *1*.
1. Répétez les lignes 6 à 9 pour réserver la ligne et la libérer dans l’entrepôt. Comme précédemment, le système crée une **nouvelle** expédition pour la ligne que vous avez ajoutée. Cependant, comme l’article provient du groupe d’articles **CarAudio**, il **ne répond pas aux contraintes que vous avez définies pour le groupe de combinaisons de chargement**. Par conséquent, il est **ajouté à un nouveau chargement**. Si vous n’aviez pas spécifié de groupe de combinaisons de chargement sur le modèle de création de chargement, cette expédition aurait été ajoutée au premier chargement.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]