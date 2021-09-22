---
title: Lancement vers l’entrepôt
description: Cette rubrique fournit des détails sur le processus de lancement vers l'entrepôt. Elle décrit les entités qui sont créées lorsque vous lancez une commande vers l'entrepôt et les options que vous pouvez utiliser pour initier le processus.
author: mirzaab
ms.date: 8/13/2021
ms.topic: article
ms.search.form: WHSReleaseToWarehouse, WHSReleaseToWarehouseSalesOrder, WHSReleaseToWarehouseTransferOrder, WHSLoadPlanningWorkbench, WHSWaveTemplateTable, WHSWorkTemplateTable, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6c8aa0338ab30e6366601e3759141c7e41bf99fb
ms.sourcegitcommit: ab1455c67f6ee6ca36bec148bea0dbb0f7704eda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "7428929"
---
# <a name="release-to-warehouse"></a>Lancement vers l'entrepôt

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des détails sur le processus de lancement vers l'entrepôt. Elle décrit les entités qui sont créées lorsque vous lancez une commande vers l'entrepôt et les options que vous pouvez utiliser pour initier le processus.

## <a name="release-to-warehouse-overview"></a>Présentation du lancement vers l’entrepôt

Le lancement vers l'entrepôt est le processus de préparation du stock pour le traitement de l'expédition. Lorsque vous lancez une commande vers l'entrepôt, le système crée des lignes de chargement et des expéditions. Si le traitement automatique des vagues est configuré, les charges et le travail requis sont également créés. La configuration des entités impliquées dépend des paramètres système. Cette section de la rubrique passe en revue les entités qui sont créées pendant le processus de lancement vers l'entrepôt et les paramètres système qui les définissent.

Une *expédition* est un groupe de lignes de commande client ou d'ordre de transfert pour le même client ou la même adresse de livraison.

Un *chargement* est un groupe de lignes de commande client ou d'ordre de transfert qui sont regroupées et qui partent généralement sur un seul camion, un seul wagon ou autre mode de transport. Un chargement peut comporter une ou plusieurs expéditions. Vous pouvez créer manuellement un chargement en ajoutant des lignes de commande à un nouveau chargement. Dans ce cas, les lignes de commande sont affectées au chargement avant le processus de lancement vers l'entrepôt, et elles ne peuvent être lancées qu'à partir de la page **Atelier de planification des chargements**.

Un *travail* d'entrepôt correspond à toute opération d'entrepôt effectuée par un magasinier. Généralement, les opérations de travail d’entrepôt se composent d’au moins deux actions consécutives : un magasinier prend un stock disponible dans un emplacement et le range dans un autre emplacement.

Lorsque vous lancez des commandes vers l'entrepôt, le système crée des *lignes de chargement* et les regroupe en expéditions. Le processus de regroupement des expéditions permet un regroupement automatique des expéditions pendant le processus de lancement vers l'entrepôt. Pour plus d’informations, voir [Stratégies de regroupement des expéditions](about-shipment-consolidation-policies.md).

Le système utilise des *vagues* pour créer des travaux de préparation de commande et de chargement pour l'expédition. Un *modèle de vague* doit être disponible pour le type de vague que vous souhaitez créer et pour l'entrepôt de la ligne de commande. Les modèles de vague du type *Expédition* servent à expédier les articles des commandes client et des ordres de transfert.

Chaque modèle de vague contient des *méthodes de vague*. Les méthodes de vague effectuent des actions telles que la création de travail pour la vague ou la création de chargements. Par exemple, un modèle de vague pour les vagues d’expédition peut contenir des méthodes de création de chargement, d’allocation de lignes aux vagues, de réapprovisionnement, et de création d’un travail de prélèvement pour la vague. Le modèle de vague établit les paramètres qui définissent la façon dont la vague sera générée et traitée. Cela comprend les étapes qui doivent être effectuées manuellement et celles qui sont effectuées automatiquement. Pour plus d’informations, voir [Modèles de vague](wave-templates.md). Par conséquent, selon la configuration de votre modèle de vague, soit une vague est automatiquement créée, traitée et lancée lorsque vous lancez une commande vers un entrepôt, soit certaines ou toutes ces actions sont exécutées manuellement une fois le lancement vers l'entrepôt effectué.

Lorsqu'une vague est traitée, le système crée un travail de prélèvement basé sur un *modèle de travail* et une *directive d'emplacement* appropriés, et rend ce travail disponible sur les appareils mobiles. Le modèle de travail détermine la manière dont le travail est effectué pour chaque processus d'entrepôt, et la directive d'emplacement spécifie les emplacements de prélèvement et de mise en place pour le mouvement de stock. Pour plus d’informations, voir [Contrôler le travail d’entrepôt à l’aide de modèles de travail et d’instructions d’emplacement](control-warehouse-location-directives.md).

> [!NOTE]
> Par défaut, les vagues sont traitées en mode de traitement par lots.

Pendant le traitement de la vague, le système crée généralement un nouveau chargement pour chaque expédition à laquelle aucun chargement n’est affecté. Si vous souhaitez que le système affecte plutôt les expéditions non affectées aux chargements existants, vous pouvez utiliser la fonctionnalité avancée de création de chargement par vague. Pour plus d’informations, voir [Création de chargement avancée pendant une vague](advanced-load-building-during-wave.md).

Sur les pages **Commandes client** et **Ordres de transfert**, vous pouvez consulter les entités créées pour les lignes de commande pendant le processus de lancement vers l'entrepôt.

- Page **Commandes client** :

    - Dans le raccourci **Lignes de commande client**, sélectionnez **Entrepôt** puis, dans le menu, sélectionnez **Détails de l'expédition** pour ouvrir les expéditions associées, **Détails du chargement** pour ouvrir les chargements associés, ou **Détails du travail** pour ouvrir les détails du travail associé.
    - Dans le raccourci **Détails de la ligne**, sélectionnez l'onglet **Chargement** pour consulter les chargements associés.

- Page **Ordres de transfert** :

    - Dans le volet Actions, dans l'onglet **Expédition**, sélectionnez **Détails de l'expédition** pour ouvrir les expéditions liées ou **Détails du chargement** pour ouvrir les chargements associés.
    - Dans le raccourci **Lignes d'ordre de transfert**, sélectionnez **Détails du travail** pour ouvrir les détails du travail associé.

En conclusion, lorsqu'une commande est lancée vers l'entrepôt, le flux le plus automatisé fonctionne de la manière suivante :

1. Le système crée une expédition pour la commande et une vague.
1. La vague est traitée.
1. Le système crée un chargement et un ID de travail.

En fonction des paramètres du modèle de vague, des modèles de travail et des directives d'emplacement, certaines étapes de ce flux peuvent devenir manuelles. Le flux général demeure cependant le même.

Plusieurs options s'offrent à vous pour lancer une commande vers l'entrepôt. Vous pouvez effectuer l'opération manuellement ou configurer une tâche de traitement par lots. Les sections restantes de cette rubrique examinent en détail les différentes manières dont vous pouvez effectuer une opération de lancement vers l'entrepôt.

## <a name="manual-release-to-the-warehouse-from-the-sales-orders-and-transfer-orders-pages"></a>Lancement manuel vers l'entrepôt à partir des pages Commandes client et Ordres de transfert

Vous pouvez lancer une commande vers l'entrepôt directement à partir de la page **Commandes client** ou de la page **Ordres de transfert**, en sélectionnant **Lancement vers l'entrepôt**.

- Sur la page **Commandes client**, le bouton est sur l'onglet **Entrepôt** du volet Actions.
- Sur la page **Ordres de transfert**, le bouton est sur l'onglet **Expédition** du volet Actions.

Depuis la page **Commandes client**, vous pouvez lancer plusieurs commandes client simultanément.

## <a name="manual-release-to-the-warehouse-from-the-release-to-warehouse-pages"></a>Lancement manuel vers l'entrepôt à partir des pages Lancement vers l'entrepôt

Le système propose actuellement trois pages sur lesquelles vous pouvez consulter les lignes de plusieurs commandes et les envoyer à l'entrepôt :

- **Lancement vers l'entrepôt** (**Gestion d'entrepôt\> Lancement vers l'entrepôt \> Lancement vers l'entrepôt**) : cette page vous permet de travailler à la fois sur les commandes client et les ordres de transfert. Cependant, elle offre des performances plus lentes que les deux autres pages. Cette page sera bientôt obsolète.
- **Lancement des commandes client vers l'entrepôt** (**Gestion d'entrepôt\> Lancement vers l'entrepôt \> Lancement des commandes client vers l'entrepôt**) : cette page vous permet de travailler exclusivement sur les commandes client. Cependant, elle offre de meilleures performances que la page **Lancement vers l'entrepôt**.
- **Lancement des ordres de transfert vers l'entrepôt** (**Gestion d'entrepôt\> Lancement vers l'entrepôt \> Lancement des ordres de transfert vers l'entrepôt**) : cette page vous permet de travailler exclusivement sur les ordres de transfert. Cependant, elle offre de meilleures performances que la page **Lancement vers l'entrepôt**.

Les trois pages offrent des fonctionnalités similaires, comme décrit dans le reste de cette section. Toutes vous permettent de sélectionner des lignes de commande ou des commandes entières, puis de les envoyer à l'entrepôt.

Chacune des pages se compose d'une section supérieure, où vous pouvez sélectionner des lignes de commande, et d'une section inférieure, où vous pouvez initier le processus de lancement vers l'entrepôt. Vous pouvez utiliser les filtres de la section supérieure pour rechercher les lignes de commande client que vous souhaitez lancer. La page **Lancement vers l'entrepôt** fournit un onglet distinct pour les commandes clients et les ordres de transfert dans la section supérieure, tandis que chacune des deux autres pages n'affiche qu'un seul type de commande.

La barre d'outils de la section supérieure comprend les boutons suivants, que vous pouvez utiliser pour sélectionner les lignes de commande à lancer vers l'entrepôt :

- **Ajouter** : sélectionnez une ou plusieurs lignes de commande dans la section supérieure, puis sélectionnez ce bouton pour ces lignes dans la section inférieure.
- **Tout ajouter** : ajoutez toutes les lignes de la section supérieure à la section inférieure.
- **Ajouter une commande** : sélectionnez une commande, puis sélectionnez ce bouton pour ajouter toutes les lignes de cette commande à la section inférieure.

Une fois que vous avez terminé d'ajouter des lignes à la section inférieure, marquez chaque ligne que vous souhaitez lancer. Sélectionnez ensuite **Lancement vers l'entrepôt** sur la barre d'outils pour lancer ces lignes vers l'entrepôt.

## <a name="manual-release-to-the-warehouse-from-the-load-planning-workbench-page"></a>Lancement manuel vers l’entrepôt à partir de la page Atelier de planification des chargements

Vous pouvez également lancer manuellement les commandes vers l'entrepôt en utilisant la page **Atelier de planification des chargements**. Cette page vous permet d'organiser les lignes de commande en chargements, puis de libérer ces chargements vers l'entrepôt.

Pour ouvrir la page **Atelier de planification des chargements**, accédez à **Gestion des entrepôts \> Chargements**. Vous pouvez également l'ouvrir à partir des pages **Commandes client** et **Ordres de transfert**. Dans la partie supérieure de la page, vous pouvez sélectionner des lignes de commande client sur l'onglet **Lignes de vente** et des lignes d'ordre de transfert sur l'onglet **Lignes de transfert**, puis ajouter ces lignes à un chargement nouveau ou existant.

L'onglet **Approvisionnement et demande** du volet Actions comprend les boutons suivants que vous pouvez utiliser pour ajouter des lignes de commande de la section supérieure à un chargement :

- **Vers nouveau chargement** : sélectionnez des lignes de commande dans la section supérieure, puis sélectionnez ce bouton pour créer un chargement et y ajouter ces lignes.
- **Vers chargement existant** : sélectionnez des lignes de commande dans la section supérieure, puis sélectionnez ce bouton pour ajouter ces lignes à un chargement existant.
- **Commande entière vers nouveau chargement** : sélectionnez des commandes, puis sélectionnez ce bouton pour créer un chargement et y ajouter toutes les lignes de ces commandes.
- **Commande entière vers chargement existant** : sélectionnez une commande, puis sélectionnez ce bouton pour ajouter toutes les lignes de cette commande à un chargement existant.

Dans la section inférieure, vous pouvez consulter les chargements créés. Pour lancer des chargements vers un entrepôt, sélectionnez-les, puis sélectionnez **Lancer \> Lancement vers l'entrepôt** dans la barre d'outils. Si vous utilisez le traitement automatique des vagues, car les chargements sont déjà affectés à des lignes de commande, le système crée des expéditions et des ID de travail lorsque l'opération de lancement vers l'entrepôt est effectuée.

## <a name="automatic-release-to-the-warehouse"></a>Lancement automatique vers l’entrepôt

Pour lancer automatiquement des commandes vers l'entrepôt, utilisez les tâches **Lancement automatique des commandes client** et **Lancement automatique des ordres de transfert**.

Pour paramétrer le traitement par lots de lancement des commandes client, procédez comme suit :

1. Allez dans **Gestion des entrepôts \> Lancement dans l’entrepôt \> Lancement automatique des commandes client**.
1. Dans la boîte de dialogue **Lancement automatique des commandes client**, dans le raccourci **Paramètres**, définissez les champs suivants :

    - **Quantité à lancer** : sélectionnez si toute la quantité ou la quantité physiquement réservée seulement doit être lancée vers l'entrepôt.
    - **Autoriser le lancement des commandes partiellement lancées** : indiquez si les quantités restantes des commandes partiellement lancées doivent être lancées vers l'entrepôt.
    - **Conserver les réservations en cas d'échec du lancement** : indiquez si les quantités qui ont été automatiquement réservées pour une commande client doivent rester réservées en cas d'échec du processus de lancement vers l'entrepôt.
    - **Traitement des commandes verrouillé** : sélectionnez la manière dont le système doit traiter les commandes client actuellement verrouillées car elles sont en cours de modification par d'autres utilisateurs ou processus :

        - *Attendre le déverrouillage des commandes* : le système doit attendre que les commandes soient déverrouillées avant de les lancer vers l'entrepôt. Dans ce cas, le processus de lancement vers l'entrepôt peut prendre plus de temps.
        - *Ignorer les commandes verrouillées* : le système doit ignorer les commandes verrouillées.

    - **Types de commande valides** : sélectionnez les types de commandes client à inclure dans le traitement par lots.
    - **Type de limite de crédit** : sélectionnez si les contrôles des limites de crédit doivent être effectués pendant le processus de lancement vers l'entrepôt et, si les contrôles doivent être effectués, les informations de transaction à y inclure.

1. Pour contrôler quelles commandes doivent être traitées, dans le raccourci **Enregistrements à inclure**, sélectionnez **Filtrer**. Une boîte de dialogue de requête standard apparaît, dans laquelle vous pouvez définir des critères de sélection, des critères de tri et des jointures. Les champs fonctionnent comme pour d’autres types de requêtes dans Microsoft Dynamics 365 Supply Chain Management.
1. Dans le raccourci **Exécuter à l’arrière-plan**, choisissez si la tâche doit être exécutée en mode de traitement par lots, et/ou configurez un programme récurrent. Les champs fonctionnent comme pour d’autres types de [travaux d’arrière-plan](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) dans Supply Chain Management.
1. Sélectionnez **OK** pour appliquer vos paramètres et initier le processus de lancement vers l'entrepôt.

Pour paramétrer le traitement par lots de lancement des ordres de transfert, procédez comme suit :

1. Accédez à **Gestion des entrepôts \> Libérer dans l’entrepôt \> Libération automatique des ordres de transfert**.
1. Dans la boîte de dialogue **Lancement automatique des ordres de transfert**, dans le raccourci **Paramètres**, définissez les champs suivants :

    - **Quantité à lancer** : sélectionnez si toute la quantité ou la quantité physiquement réservée seulement doit être lancée vers l'entrepôt.
    - **Autoriser le lancement des commandes partiellement lancées** : indiquez si les quantités restantes des commandes partiellement lancées doivent être lancées vers l'entrepôt.
    - **Regrouper les lancements par entrepôt de destination** : indiquez si le système doit lancer tous les ordres de transfert en même temps, ou s'il doit regrouper les lignes d'ordre de transfert par entrepôt de destination, puis lancer chaque groupe vers l'entrepôt séparément.

1. Pour contrôler quelles commandes doivent être traitées, dans le raccourci **Enregistrements à inclure**, sélectionnez **Filtrer**. Une boîte de dialogue de requête standard apparaît, dans laquelle vous pouvez définir des critères de sélection, des critères de tri et des jointures. Les champs fonctionnent comme pour d’autres types de requêtes dans Supply Chain Management.
1. Dans le raccourci **Exécuter à l’arrière-plan**, choisissez si la tâche doit être exécutée en mode de traitement par lots, et/ou configurez un programme de récurrence. Les champs fonctionnent comme pour d’autres types de [travaux d’arrière-plan](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) dans Supply Chain Management.
1. Sélectionnez **OK** pour appliquer vos paramètres et initier le processus de lancement vers l'entrepôt.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
