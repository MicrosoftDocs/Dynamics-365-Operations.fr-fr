---
title: Créer des ordres de transfert depuis l’application d’entreposage
description: Cette rubrique décrit comment créer et traiter des ordres de transfert à partir de l’application mobile Gestion des entrepôts
author: perlynne
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: fe5983d40033c0cd15674815067eaa969e97d38b
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6343623"
---
# <a name="create-transfer-orders-from-the-warehouse-app"></a>Créer des ordres de transfert depuis l’application d’entrepôt

[!include [banner](../includes/banner.md)]

Cette fonctionnalité permet aux magasiniers de créer et de traiter des ordres de transfert directement à partir de l’application mobile Gestion des entrepôts. Les magasiniers commencent par sélectionner l’entrepôt de destination et peuvent ensuite scanner un ou plusieurs contenants à l’aide de l’application afin d’ajouter des contenants à l’ordre de transfert. Lorsque le magasinier sélectionne **Terminer la commande**, un traitement par lots créera l’ordre de transfert requis et les lignes de commande en fonction du stock disponible enregistré pour ces contenants.

## <a name="enable-the-create-transfer-orders-from-the-warehouse-app-feature"></a><a name="enable-create-transfer-order-from-warehouse-app"></a>Activer la fonctionnalité Créer des ordres de transfert à partir de la l’application d’entreposage

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer et activer les éléments requis sur votre système. Les administrateurs peuvent utiliser les paramètres de la page de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.

1. Activez d’abord la fonctionnalité [Traiter les événements de l’application d’entreposage](warehouse-app-events.md), qui est répertoriée dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) de la manière suivante :
    - **Module** - Gestion des entrepôts
    - **Nom de la fonction** - Traiter les événements de l’application d’entreposage
1. Puis activez la fonctionnalité *Créer des ordres de transfert depuis l’application d’entreposage*, qui est répertoriée en tant que :
    - **Module** - Gestion des entrepôts
    - **Nom de la fonctionnalité** - Créer et traiter des ordres de transfert à partir de la l’application d’entreposage
1. Pour automatiser le traitement des expéditions sortantes, vous devez également activer la fonctionnalité [Confirmer les expéditions sortantes des traitements par lots](confirm-outbound-shipments-from-batch-jobs.md). Cette fonctionnalité est répertoriée comme suit :
    - **Module** - Gestion des entrepôts
    - **Nom de la fonctionnalité** - Confirmer les expéditions sortantes des traitements par lots

## <a name="set-up-a-mobile-device-menu-item-to-create-transfer-orders"></a><a name="setup-warehouse-app-menu"></a>Paramétrer une option de menu d’appareil mobile pour créer des ordres de transfert

Voici des recommandations générales pour configurer une option de menu d’appareil mobile afin de créer un ordre de transfert. En fonction des besoins de votre entreprise concernant le niveau d’automatisation à définir lorsque les utilisateurs créent des ordres de transfert à partir de l’atelier, différentes configurations seront activées. Le scénario de ce document décrira une telle configuration.

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Sélectionnez **Nouveau** pour ajouter une option de menu. Ensuite, définissez les paramètres suivants pour commencer :

    - **Nom de l’option de menu** - Attribuez un nom tel qu’il doit apparaître dans Supply Chain Management.
    - **Titre** - Attribuez un nom de menu tel qu’il doit être présenté aux collaborateurs dans l’application mobile Gestion des entrepôts.
    - **Mode** - Défini sur *Indirect* (cet élément de menu ne créera pas de travail).
    - **Code d’activité** - Défini sur *Créer un ordre de transfert à partir des contenants* pour permettre aux magasiniers de créer un ordre de transfert basé sur un ou plusieurs contenants scannés.

1. Utilisez le paramètre **Stratégie de création de ligne d’ordre de transfert** pour contrôler la façon dont les lignes d’ordre de transfert seront créées par cette option de menu. Ces lignes seront créées/mises à jour en fonction du stock disponible enregistré pour les contenants scannés. Choisissez l’une des valeurs suivantes :

    - **Aucune réservation** - Les lignes d’ordre de transfert ne seront pas réservées.
    - **Guidé par contenant avec réservation de ligne** - Les lignes d’ordre de transfert seront réservées et utiliseront l’option de stratégie guidée par contenant, qui stocke les ID de contenant pertinents associés aux lignes de commande. Les valeurs d’ID contenant localisé peuvent donc être utilisées dans le cadre du processus de création des travaux pour les lignes d’ordre de transfert.

1. Utilisez le paramètre **Stratégie d’expédition sortante** pour ajouter plus d’automatisation au processus d’expédition des ordres de transfert sortants, si nécessaire. Lorsqu’un collaborateur clique sur le bouton **Terminer la commande**, l’application crée l’événement d’application d’entreposage *Terminer la commande* qui enregistrera la valeur choisie ici dans le champ **Stratégie d’expédition sortante** pour chaque ligne de l’ordre de transfert actuel. Ensuite, lorsque la file d’attente d’événements est traitée par un traitement par lots pour créer l’ordre de transfert, la valeur stockée dans ce champ peut être lue par le traitement par lots et peut donc contrôler la manière dont ce travail traite chaque ligne. Choisissez l’une des méthodes suivantes :

    - **Aucun** - Aucun traitement automatisé n’est effectué.
    - **Libération dans l’entrepôt** - Automatise le processus de sortie vers l’entrepôt.
    - **Confirmation de l’expédition** - Automatise le processus de confirmation du navire.
    - **Confirmation de la libération et de l’expédition** - Automatise les processus de confirmation de libération dans l’entrepôt et d’expédition.

## <a name="add-the-mobile-device-menu-item-to-a-menu"></a>Ajouter l’option de menu d’appareil mobile à un menu

1. Accéder à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d’appareil mobile**
1. Sélectionnez **Modifier**.
1. Sélectionnez un menu existant après avoir sélectionné la nouvelle option de menu sous **Menus et options de menu disponibles**. Ajoutez l’option de menu en sélectionnant le bouton de flèche vers la droite.

## <a name="create-a-transfer-order-based-on-license-plates"></a>Créer un ordre de transfert basé sur des contenants

L’application mobile Gestion des entrepôts dispose d’un processus simple pour créer des ordres de transfert basés sur des contenants. Pour ce faire, le collaborateur effectue les opérations suivantes à l’aide de l’application mobile Gestion des entrepôts :

1. Créer l’ordre de transfert et identifier l’entrepôt de destination.
1. Identifier chaque contenant à expédier.
1. Sélectionner **Terminer la commande**.

>[!NOTE]
> Plusieurs collaborateurs peuvent attribuer des contenants destinés au même ordre de transfert à l’aide du bouton **Sélectionner l’ordre de transfert** pour sélectionner un numéro d’ordre de transfert existant et non traité dans la file d’attente des événements de l’application d’application d’entreposage. Pour plus d’informations sur la recherche des valeurs de numéro d’ordre de transfert, voir [Demander les événements de l’application d’entreposage](#inquire-the-warehouse-app-events).

## <a name="example-scenario"></a>Exemple de scénario

Ce scénario fournit une vue d’ensemble du processus de création et de traitement automatique des ordres de transfert en fonction du stock disponible enregistré sur les contenants sélectionnés.

Pour exécuter ce scénario à l’aide des valeurs suggérées, vous devez travailler sur un système dans lequel des données de démonstration sont installées et sélectionner l’entité juridique *USMF* avant de commencer.

Ce scénario suppose que vous avez déjà activé les fonctionnalités [Créer et traiter des ordres de transfert à partir de la fonctionnalité de l’application d’entreposage](#enable-create-transfer-order-from-warehouse-app) et [Traitement des événements de l’application d’entreposage](warehouse-app-events.md).

Outre la configuration de la création de l’ordre de transfert dans les options de menu d’appareil mobile, des modèles supplémentaires, des directives d’emplacement et des traitements par lots doivent également être configurés et activés.

### <a name="example-scenario-blueprint"></a>Exemple de projet de scénario

Vous êtes un détaillant et vous avez plusieurs contenants, chacun renfermant plusieurs articles placés à un endroit spécifique dans l’un de vos entrepôts (*Entrepôt 51*). Vous souhaitez activer le processus qui permet aux collaborateurs de créer un ordre de transfert vers un autre entrepôt (*Entrepôt 61*) pour un ensemble de contenants scannés. Vous expédierez-mettrez à jour automatiquement l’ordre de transfert dès que le dernier contenant de la commande aura été identifié.

![Exemple de processus d’ordre de transfert automatisé.](media/create-transfer-order-from-app-example.png "Exemple de processus d’ordre de transfert automatisé")

### <a name="create-a-mobile-device-menu-item-for-creating-transfer-orders"></a>Créer une option de menu d’appareil mobile pour créer des ordres de transfert

Cette section explique comment créer une option de menu d’appareil mobile pour créer des ordres de transfert. Définissez **Mode** sur *Indirect* et **Code d’activité** sur *Créer un ordre de transfert à partir des contenants*.

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **Nom de l’option de menu**, entrez le nom *Créer un ordre de transfert*.
1. Dans le champ **Titre**, entrez la description *Créer un ordre de transfert*.
1. Dans le champ **Mode**, sélectionnez *Indirect*.
1. Dans **Code d’activité**, sélectionnez *Créer un ordre de transfert à partir des contenants*
1. Dans **Stratégie de création de lignes de commande**, sélectionnez *Guidé par contenant avec réservation de ligne*.
1. Dans **Stratégie d’expédition sortante**, sélectionnez *Confirmation de la libération et de l’expédition*.
1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d’appareil mobile**.
1. Sélectionnez **Modifier**.
1. Sélectionnez le menu **Stock** existant, puis sélectionnez la nouvelle option de menu sous **Menus et options de menu disponibles**. Ajoutez l’option de menu dans le menu **Stock** en sélectionnant le bouton de flèche vers la droite.

### <a name="set-up-work-templates-to-auto-process-and-break-work-by-located-license-plate"></a>Configurer des modèles de travail pour traiter automatiquement et décomposer le travail par contenant localisé

Cette section explique comment activer un modèle de travail pour traiter automatiquement le travail créé par le modèle lorsqu’une vague est lancée.

1. Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.
1. Dans le champ **Type d’ordre de travail**, sélectionnez *Sortie de transfert*.
1. Sélectionnez **Nouveau** pour créer un modèle de travail.
1. Dans le champ **Modèle de travail**, entrez *51 Traiter automatiquement le contenant*.
1. Dans le champ **Description du modèle de travail**, entrez *51 Traiter automatiquement le contenant*.
1. Cochez la case **Traiter automatiquement**. Cette case doit être cochée pour que toutes les étapes d’automatisation soient traitées.
1. Dans les données de démonstration, il existe déjà un modèle de travail nommé *51 Transfert*, modifiez le champ **Numéro de séquence** de sorte que le nouveau modèle de travail ait un numéro de séquence inférieur à celui du modèle de travail existant *51 Transfert*.
1. Sélectionnez **Enregistrer** dans la barre d’outils pour activer le raccourci **Détails du modèle de travail**.
1. Dans le raccourci **Détails du modèle de travail**, sélectionnez **Nouveau** dans la barre d’outils. Vous allez ajouter deux lignes.
1. Dans le champ **Type de travail**, sélectionnez *Prélever*.
1. Dans le champ **ID classe de travail**, sélectionnez *TransfOut*.
1. Sélectionnes **Nouveau** dans la barre d’outils **Détails du modèle de travail**.
1. Dans le champ **Type de travail**, sélectionnez *Put*.
1. Dans le champ **ID classe de travail**, sélectionnez *TransfOut*.
1. Sélectionnez **Enregistrer** pour activer le champ **Code instructions**.
1. Sur la ligne **Type de travail** *Placer*, sélectionnez **Code instructions** *Baydoor*. Assurez-vous que ce nouveau modèle de travail obtient la valeur **Numéro de séquence** la plus basse.
1. Dans la barre d’outils, sélectionnez **Modifier la requête** pour ouvrir l’éditeur de requêtes.
1. Dans l’onglet **Plage**, sélectionnez **Ajouter**.
1. Sur la ligne ajoutée, dans **Champ**, sélectionnez *Entrepôt*.
1. Dans le champ **Critères**, sélectionnez *51*.
1. Sélectionnez l’onglet **Tri**.
1. Sélectionnez **Ajouter** et définissez **Champ** sur *ID contenant localisé*. Le fait de sélectionner ce champ activera le bouton de la barre d’outils **Décompositions de l’en-tête de travail**.
1. Sélectionnez **OK** suivi par **Oui** pour réinitialiser le regroupement et revenir à la page **Modèles de travail**.
1. Sélectionnez **Décompositions de l’en-tête de travail** et activez **Regrouper selon ce champ** pour l’**ID contenant localisé** et fermez.

> [!NOTE]
> Toutes les configurations ne peuvent pas être traitées automatiquement. Par exemple, les éléments de poids variable et l’utilisation de dimensions de suivi mixtes.

### <a name="set-up-location-directives-for-the-license-plate-guided-strategy"></a>Configurer les directives d’emplacement pour la stratégie guidée par contenant

Cette section explique comment configurer un processus de sélection avec instructions d’emplacement pour utiliser la stratégie **Guidé par contenant**.

1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.
1. Sélectionnez **Modifier**.
1. Dans l’en-tête de la liste de navigation, sélectionnez **Type d’ordre de travail** *Sortie de transfert*.
1. Dans la liste de navigation, sélectionnez l’instruction d’emplacement existante **51 Prélèvement ordre de transfert**.
1. Dans le raccourci **Lignes**, cochez la case **Autoriser le fractionnement**.
1. Dans le raccourci **Actions d’instruction d’emplacement**, sélectionnez **Nouveau** pour ajouter une ligne d’action.
1. Dans le champ **Nom**, entrez *Guidé par contenant*.
1. Dans la champ **Stratégie**, sélectionnez *Guidé par contenant*. Cette action nécessite le numéro de séquence le plus bas.
1. Sélectionnez **Enregistrer** dans la barre d’outils.
1. Sélectionnez l’icône **Rafraîchir** la page dans la barre d’outils.
1. Dans le raccourci **Actions des directives d’emplacement**, sélectionnez la ligne *TOPick*.
1. Dans la barre d’outils **Actions des directives d’emplacement**, sélectionnez **Déplacer vers le bas** pour modifier le numéro de séquence afin qu’il soit supérieur au numéro de séquence de l’action *Guidé par contenant* que vous venez de créer.

> [!NOTE]
> La stratégie guidée par contenant tentera de réserver et de créer un travail de prélèvement aux emplacements renfermant les contenants demandés qui ont été associés aux lignes d’ordre de transfert. Mais si cela n’est pas possible et que vous souhaitez toujours créer un travail de prélèvement, vous devez revenir à une autre stratégie d’action de directive d’emplacement, et peut-être également rechercher un stock dans une autre zone de l’entrepôt, en fonction de vos besoins en matière de processus métier.

### <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Configurer un traitement par lots pour traiter les événements de l’application d’entreposage

Cette section explique comment configurer un traitement par lots planifié pour traiter les événements de l’application d’entreposage.

1. Accédez à **Gestion des entrepôts \> Tâches périodiques \> Traiter les événements de l’application d’entreposage**.
2. Dans la boîte de dialogue, activez **Traitement par lots** sous la section **Exécuter en arrière-plan**.
3. Sélectionnez **Récurrence** et configurez le traitement par lots afin de traiter en fonction de l’intervalle requis pour votre entreprise.
4. Sélectionnez **OK** pour revenir à la boîte de dialogue principale.
5. Sélectionnez **OK** dans la boîte de dialogue principale pour ajouter le traitement à la file d’attente des traitements par lots.

### <a name="set-up-a-batch-job-to-release-transfer-orders-automatically"></a>Configurer un traitement par lots afin de lancer automatiquement des ordres de transfert

Cette section explique comment configurer un traitement par lots planifié pour lancer les ordres de transfert qui ont été marqués comme "Prêt pour libération".

1. Accédez à **Gestion des entrepôts \> Libérer dans l’entrepôt \> Libération automatique des ordres de transfert**.
1. Dans la boîte de dialogue, développez la section **Enregistrements à inclure**.
1. Sélectionnez **Filtre**, dans la section **Enregistrements à inclure**.
1. Sur la page de requête **WHSTransferAutoRTWQuery**, sous l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une nouvelle ligne à la requête.
1. Dans le champ **Table** de la nouvelle ligne, sélectionnez le menu déroulant et sélectionnez la table **Transférer la libération de la ligne vers l’entrepôt**.
1. Dans le menu déroulant **Champ**, sélectionnez **Stratégie d’expédition sortante**.
1. Dans le champ **Critère**, sélectionnez **Confirmation de la libération et de l’expédition**.
1. Dans la ligne où **Champ** est définir sur *Entrepôt d’origine*, dans le champ **Critère**, sélectionnez *51*.
1. Sélectionnez **OK** pour revenir à la boîte de dialogue principale.
1. Développez la section **Exécuter en arrière-plan** pour configurer le traitement par lots.
1. Activez **Traitement par lots** sous la section **Exécuter en arrière-plan**.
1. Sélectionnez **Récurrence** et configurez le traitement par lots afin de traiter en fonction de l’intervalle requis pour votre entreprise.
1. Sélectionnez **OK** pour revenir à la boîte de dialogue principale.
1. Sélectionnez **OK** dans la boîte de dialogue principale pour ajouter le traitement par lots à la file d’attente des traitements par lots.

### <a name="set-up-the-process-outbound-shipment-batch-job"></a>Configurer le traitement par lots "Traiter les expéditions sortantes"

Cette section explique comment configurer un traitement par lots planifié pour exécuter la confirmation de l’expédition sortante pour les chargements prêts à être expédiés et liés aux lignes d’ordre de transfert qui sont "prêtes à être expédiées".

1. Allez dans **Gestion des entrepôts \> Tâches périodiques \> Traiter les expéditions sortantes**.
1. Développez la section **Enregistrements à inclure**.
1. Sélectionnez **Filtrer**.
1. Dans la requête **WHSLoadShipConfirm**, sélectionnez l’onglet **Jointures**.
1. Développez la hiérarchie des tables afin que **Charges** et **Détails de la charge** soient développés.
1. Sélectionnez la table **Détails de la charge**.
1. Sélectionnez le bouton **Ajouter une jointure de table**.
1. Dans la liste des relations de table, filtrez la colonne **Relation** ou effectuez une recherche pour trouver *Lignes d’ordre de transfert (référence)*.
1. Concentrez-vous sur la relation de table dans la liste, puis appuyez sur la touche **Sélectionner**.
1. Sélectionnez la table **Lignes d’ordre de transfert**.
1. Sélectionnez le bouton **Ajouter une jointure de table**.
1. Dans la liste des relations de table, filtrez la colonne **Relation** ou effectuez une recherche pour trouver *Champs supplémentaires Transfert de stock (ID enregistrement)*.
1. Concentrez-vous sur la relation de table dans la liste, puis appuyez sur la touche **Sélectionner**.
1. Sélectionnez l’onglet **Plage**.
1. Dans les tables de requête **Plage**, vous configurez trois plages de critères de requête. Sélectionnez le bouton **Ajouter** pour ajouter une ligne.
1. Ajoutez une plage pour la table **Charges**. Définissez **Champ** sur *État du chargement* et **Critères** sur *Chargé*.
1. Ajoutez une autre plage pour la table **Champs supplémentaires Transfert de stock**. Définissez **Champ** sur *Stratégie d’expédition sortante* et **Critères** sur *Confirmation de la libération et de l’expédition*.
1. Ajoutez une autre plage pour la table **Détails de la charge**. Définissez **Champ** sur *Référence* et **Critères** sur *Expédition de l’ordre de transfert*.
1. Sélectionnez **OK** pour revenir à la boîte de dialogue principale.
1. Développez la section **Exécuter à l’arrière-plan**.
1. Activez **Traitement par lots**.
1. Sélectionnez **Récurrence** et configurez le traitement par lots afin de traiter en fonction de l’intervalle requis pour votre entreprise.
1. Sélectionnez **OK** pour revenir à la boîte de dialogue principale.
1. Sélectionnez **OK** dans la boîte de dialogue principale pour ajouter le traitement par lots à la file d’attente des traitements par lots.

> [!NOTE]
> Pour plus d’informations, voir [Confirmer les expéditions sortantes à partir des traitements par lots](confirm-outbound-shipments-from-batch-jobs.md).

## <a name="processing-the-example-for-create-transfer-order-from-the-warehouse-app"></a>Traitement de l’exemple pour "Créer un ordre de transfert à partir de l’application d’entreposage"

### <a name="add-on-hand-on-a-license-plate"></a>Ajouter un stock disponible sur un contenant

Comme point de départ pour ce scénario, vous devrez disposer d’un contenant renfermant l’inventaire physique disponible.

| Article | Entrepôt | Statut du stock | Entrepôt | Contenant | Quantité |
| --- | --- | --- | --- | --- | --- |
| A0001 | 51 | Disponible | LP-010 | LP10 | 1 |
| A0002 | 51 | Disponible | LP-010 | LP10 | 2 |

Ajoutez les quantités disponibles du stock physique en utilisant les valeurs suivantes :

> [!NOTE]
> Vous devrez créer le contenant et utiliser des emplacements qui vous permettent de porter des articles mixtes, comme LP-010.

### <a name="create-and-process-transfer-orders-from-the-warehouse-app"></a>Créer et traiter les ordres de transfert à partir de l’application d’entrepôt

1. Ouvrez l’application et connectez-vous en tant qu’utilisateur *51*. L’entrepôt utilisateur actuel sera 51.
1. Sélectionnez l’option de menu **Créer un ordre de transfert** à partir de l’emplacement du menu que vous avez ajouté lors de la configuration.
1. Démarrez la création d’un ordre de transfert en saisissant l’entrepôt de destination (Entrepôt de destination) dans le champ **Entrepôt**, entrez *61*. Le nouvel ordre de transfert passera de l’entrepôt actuel, 51 (Entrepôt d’origine), à l’entrepôt de destination, *61*.
1. Cliquez sur **OK**.
1. Scannez un ID de contenant dans le champ **Contenant**. Entrez le contenant du stock ajouté lors d’une étape précédente, *LP10*.
1. Cliquez sur **OK**.
1. Sélectionnez le bouton de menu, puis sélectionnez **Terminer la commande** pour finaliser la création de l’ordre de transfert de l’application d’entreposage.

Pour l’exemple mentionné, deux **Événements de l’application d’entreposage** (*Créer un ordre de transfert* et *Terminer l’ordre de transfert*) sont utilisés.

### <a name="inquire-the-warehouse-app-events"></a><a name="#inquire-the-warehouse-app-events"></a>Demander les événements de l’application d’entreposage

Vous pouvez afficher la file d’attente et les messages d’événements générés par l’application mobile Gestion des entrepôts en accédant à **Gestion des entrepôts \> Recherches et états \> Journaux des appareils mobiles \> Événements de l’application d’entreposage**.

Les messages de l’événement *Créer un ordre de transfert* passeront à l’état *En attente*, ce qui signifie que le traitement par lots **Traiter les événements de l’application d’entreposage** ne prélèvera pas et ne traitera pas les messages d’événement. Dès que le message d’événement passe à l’état *En file d’attente*, le traitement par lots traitera les événements. Cela se produira en même temps que la création de l’événement *Terminer l’ordre de transfert* (lorsqu’un collaborateur sélectionne le bouton **Terminer la commande** sur l’application mobile Gestion des entrepôts). Quand les messages d’événement *Créer un ordre de transfert* ont été traités, l’état devient *Terminé* ou *Échec*. Lorsque l’état *Terminer l’ordre de transfert* devient *Terminé*, tous les événements associés sont supprimés de la file d’attente.

Étant donné que **Événements de l’application d’entreposage** pour la création de données de l’ordre de transfert ne seront pas traités par le traitement par lots avant que les messages ne soient mis à jour à l’état *En file d’attente*, vous devrez rechercher les numéros d’ordre de transfert demandés dans le champ **Identificateur**. Le champ **Identificateur** est situé dans l’en-tête de la page **Événements de l’application d’entreposage**.

Dans le cadre du traitement des événements d’entrepôt, la création de la ligne d’ordre de transfert peut échouer. Dans ce cas, l’état du message d’événement devient *Échec* et vous pouvez utiliser l’information **Journal des traitements par lots** informations pour savoir pourquoi et agir pour corriger les problèmes.

Les problèmes courants peuvent être liés à une configuration manquante pour le processus, par exemple un entrepôt de transit manquant pour l’événement *Créer un ordre de transfert*. Dans un exemple comme celui-ci, vous ajouteriez un entrepôt de transit à l’entrepôt d’expédition et utiliseriez l’option **Réinitialiser** pour modifier l’état de tous les messages d’événement de l’application d’entreposage de *Échec* à *En file d’attente*, ce qui signifie que le traitement par lots traitera à nouveau les messages d’événement après la correction des données de configuration.

Dans les environnements de production, les exceptions sont davantage liées au processus, comme le fait d’avoir un contenant demandé qui, au moment du traitement par lots, est vide, ce qui empêche la création de lignes d’ordre de transfert. Ce message d’événement ayant échoué peut être supprimé à l’aide de l’option **Supprimer**. Vous pouvez également ajouter le stock physique disponible nécessaire sur le contenant et utiliser l’option **Réinitialiser** pour tous les messages d’événements associés.

Pour plus d’informations, voir [Traitement des événements de l’application d’entreposage](warehouse-app-events.md).

### <a name="follow-up-on-the-example-scenario-processing"></a>Suivi du traitement de l’exemple de scénario

Dans ce scénario, les événements suivants sont survenus :

1. À l’aide de l’application mobile Gestion des entrepôts, vous avez sélectionné une option de menu qui utilise le code d’activité **Créer un ordre de transfert à partir des contenants**.
1. L’application vous a invité à sélectionner l’entrepôt de destination pour l’ordre de transfert. L’entrepôt source est toujours celui auquel vous êtes actuellement connecté en tant que collaborateur.
1. Lors de la sélection de l’entrepôt de destination, le système a réservé un numéro d’identification pour l’ordre de transfert à venir (en fonction de la séquence de numéros d’ordre de transfert définie sur votre système), mais n’a pas encore créé l’ordre de transfert.
1. Lorsque vous avez scanné le contenant *LP10* refermant le stock disponible qui devrait être déplacé vers le nouvel entrepôt, un **Événement d’application d’entreposage** a été ajouté à la file d’attente des événements afin d’être traité ultérieurement. L’événement d’entrepôt contenait des détails de message sur l’analyse, y compris le numéro d’ordre de transfert prévu.
1. Sur l’application mobile Gestion des entrepôts, lorsque le bouton **Terminer la commande** est sélectionné, un nouvel événement d’application d’entreposage, **Terminer l’ordre de transfert**, est créé et l’état de l’événement existant associé, **Créer un ordre de transfert**, est devenu **En file d’attente**.
1. En arrière-plan, le traitement par lots **Traiter les événements de l’application d’entreposage** a prélevé l’événement **En file d’attente** et a collecté le stock disponible lié au contenant scanné. Sur la base du stock disponible, l’enregistrement de l’ordre de transfert réel et les lignes associées ont été créés. Le traitement a également rempli le champ **Stratégie d’expédition sortante** pour l’ordre de transfert avec la valeur basée sur l’option *Confirmation de la libération et de l’expédition* configurée et lié le contenant avec les lignes pour la stratégie **Guidé par contenant**.
1. Selon la valeur du champ **Stratégie d’expédition sortante** de la ligne d’ordre de transfert, la requête **Libération automatique du traitement par lots des ordres de transfert** aboutissait alors à la libération de l’ordre de transfert vers l’entrepôt d’expédition. Et étant données la configuration des paramètres **Modèle de vague**, **Modèle de travail** et **Instructions d’emplacement** utilisées, le traitement a obtenu des processus automatiques, qui ont mis à jour la valeur de **État du chargement** sur *Chargé*.
1. Le traitement par lots **Traiter les expéditions sortantes** est exécuté pour le chargement, ce qui entraîne l’expédition de l’ordre de transfert et la génération de l’avis préalable d’expédition (APE).
1. Le calendrier de tous ces événements dépend des paramètres de **Périodicité** des traitements par lots créés.

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="mobile-device-menu-item-setup"></a>Paramètre d’option de menu d’appareil mobile

#### <a name="why-cant-i-see-create-transfer-order-from-license-plate-in-the-menu-item-work-activity-drop-down-list"></a>Pourquoi ne puis-je pas voir "Créer un ordre de transfert à partir des contenants" dans la liste déroulante des activités des options de menu ?

La fonctionnalité *Créer et traiter des ordres de transfert à partir de la l’application d’entreposage* doit être activée. Pour plus d’informations, voir [Activer la création d’ordres de transfert à partir de la l’application d’entreposage](#enable-create-transfer-order-from-warehouse-app).

### <a name="warehouse-management-mobile-app-processes"></a>Processus de l’application mobile Gestion des entrepôts

#### <a name="why-cant-i-see-the-menu-button-complete-order"></a>Pourquoi ne puis-je pas voir le bouton de menu "Terminer la commande" ?

Vous devez avoir au moins un contenant affecté à l’ordre de transfert.

#### <a name="can-several-warehouse-management-mobile-app-users-add-license-plates-to-the-same-transfer-order-at-the-same-time"></a>Est-il possible que plusieurs utilisateurs de l’application mobile Gestion des entrepôts puissent ajouter des contenants au même ordre de transfert en même temps ?

Oui, plusieurs magasiniers peuvent scanner des contenants dans le même ordre de transfert.

#### <a name="can-the-same-license-plate-be-added-to-different-transfer-orders"></a>Un même contenant peut-il être ajouté à différents ordres de transfert ?

Non, un contenant ne peut être ajouté qu’à un seul ordre de transfert à la fois.

#### <a name="after-having-selected-the-complete-order-button-can-i-then-add-more-license-plates-for-that-transfer-order"></a>Après avoir sélectionné le bouton "Terminer la commande", puis-je ajouter d’autres contenants pour cet ordre de transfert ?

Non, vous ne pouvez pas ajouter d’autres contenants à un ordre de transfert ayant un événement d’application d’entreposage **Terminer l’ordre de transfert**.

#### <a name="how-can-i-find-existing-transfer-orders-to-be-used-via-the-select-transfer-order-button-in-the-warehouse-management-mobile-app-if-the-order-has-not-yet-been-created-in-the-backend-system"></a>Comment puis-je trouver des ordres de transfert existants à utiliser via le bouton « Sélectionner un ordre de transfert » dans l’application mobile Gestion des entrepôts, si la commande n’a pas encore été créée dans le système de back-end ?

Actuellement, vous ne pouvez pas rechercher les ordres de transfert dans l’application, mais vous pouvez trouver les numéros d’ordre de transfert sur la page **Événements de l’application d’entreposage**. Pour plus d’informations, voir [Demander les événements de l’application d’entreposage](#inquire-the-warehouse-app-events).

#### <a name="can-i-manually-select-the-transfer-order-number-to-be-used-from-the-warehouse-management-mobile-app"></a>Puis-je sélectionner manuellement le numéro d’ordre de transfert à utiliser à partir de l’application mobile Gestion des entrepôts ?

Seuls les numéros d’ordre de transfert générés automatiquement via des séquences de numéros sont pris en charge.

### <a name="background-processing"></a>Traitement en arrière-plan

#### <a name="how-should-i-clean-up-records-in-my-warehouse-app-events-queue-message-tables"></a>Comment nettoyer les enregistrements dans les tables de messages de file d’attente d’événements de mon application d’entreposage ?

Vous pouvez afficher et tenir à jour les enregistrements sur la page **Événements de l’application d’entreposage**. Pour plus d’informations, voir [Demander les événements de l’application d’entreposage](#inquire-the-warehouse-app-events).

#### <a name="why-is-the-transfer-order-receipt-date-not-updated-according-to-my-delivery-date-control-setup"></a>Pourquoi la valeur de "Date de réception" de l’ordre de transfert n’est-elle pas mise à jour en fonction de ma configuration "Contrôle de la date de livraison" ?

Les ordres de transfert sont créés sans avaoir recours aux capacités **Contrôle de la date de livraison**.

#### <a name="can-i-use-a-license-plate-having-physical-negative-inventory-on-hand"></a>Puis-je utiliser un contenant dont le stock disponible est négatif ?

La fonction ne prend en charge que les quantités physiques positives en stock au niveau du contenant, mais vous pouvez avoir des quantités physiques négatives en stock aux niveaux supérieurs de l’entrepôt et du statut du stock lors de l’attribution de contenants aux ordres de transfert.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]