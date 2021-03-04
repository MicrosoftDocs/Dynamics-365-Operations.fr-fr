---
title: Règle de lancement dans l’entrepôt
description: Cette rubrique fournit des informations sur la fonctionnalité de règle de libération dans l’entrepôt, qui offre de la flexibilité lors de la libération dans l’entrepôt. Elle ajoute une option de configuration qui contrôle si le système autorise la libération des lignes de commande partiellement réservées.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 27030e8dd58b290d80f6b00cbd250e09c1e50819
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427682"
---
# <a name="release-to-warehouse-rule"></a>Règle de lancement dans l’entrepôt

[!include [banner](../includes/banner.md)]

La fonctionnalité *Règle de libération dans l’entrepôt* offre de la flexibilité lors de la mise à disposition dans l’entrepôt. Elle ajoute une option de configuration pour chaque entrepôt. Vous pouvez utiliser cette option pour spécifier si des lignes de commande partiellement réservées peuvent être validées pour cet entrepôt. Cette fonctionnalité utilise une fonctionnalité avancée de cross-docking dans les situations où une partie d’une quantité de ligne de commande est marquée par rapport à une source d’approvisionnement, mais que la partie restante peut être traitée dans l’entrepôt. Par conséquent, la ligne peut être validée afin que le traitement en entrepôt de la quantité de stock disponible puisse continuer.

## <a name="turn-on-and-initialize-the-release-to-warehouse-rule-feature"></a>Activer et initialiser la fonctionnalité de la Règle de libération dans l’entrepôt

### <a name="turn-on-the-feature"></a>Activer la fonctionnalité

Avant de pouvoir utiliser la fonctionnalité *Règle de libération dans l’entrepôt* doit être activée sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire. Dans l'espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Règle de libération dans l’entrepôt*

### <a name="initialize-the-feature"></a>Initialiser la fonctionnalité

Une fois la fonctionnalité activée dans votre système, vous devez l’initialiser pour définir la règle sur l’état initial correct pour tous les entrepôts.

- Pour les entrepôts qui ne sont pas activés pour la gestion des entrepôts, la règle est initialement définie sur **Non applicable**.
- Pour les entrepôts qui sont activés pour la gestion des entrepôts, la règle est initialement définie sur **Autoriser une réservation partielle**

Pour initialiser la fonctionnalité et définir la règle de libération dans l’entrepôt pour tous les entrepôts, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.
1. Sur la page **Paramètres de gestion des entrepôts**, sur l’onglet **Général**, dans la section **Informations sur la société**, sélectionnez le lien pour la règle **Initialiser la libération dans l’entrepôt**. (Si ce lien n’est pas affiché, la fonctionnalité n’est pas activée ou elle a déjà été initialisée.)
1. Lorsque vous êtes invité à confirmer l’action, sélectionnez **Oui** pour initialiser la fonctionnalité.

## <a name="set-the-release-to-warehouse-rule-for-each-warehouse"></a><a name="set-option-warehouse"></a>Définir la règle de libération dans l’entrepôt pour chaque entrepôt

Une fois la fonctionnalité activée et initialisée, tous vos entrepôts auront un paramètre initial, comme décrit dans la section précédente. Vous pouvez modifier ce paramètre pour des entrepôts individuels en suivant ces étapes.

1. Accédez à **Gestion des entrepôts \> Configuration \> Entrepôt \> Emplacements fixes**.
1. Sélectionnez l’entrepôt à configurer.
1. Sélectionnez **Modifier** pour afficher la page en mode d’édition.
1. Sur l’organisateur **Entrepôt**, dans la section **Réservations**, le champ **Conditions requises pour la réservation de stock** contrôle si la libération partielle des commandes est autorisée. Vous devez sélectionner l’une des valeurs suivantes :

    - **Non applicable** - Lorsque la fonctionnalité est activée et initialisée pour la première fois, cette valeur est automatiquement attribuée à tous les entrepôts qui ne sont pas activés pour la gestion des entrepôts. Cette valeur peut être modifiée. Cette valeur n’est pas disponible pour les entrepôts activés pour la gestion des entrepôts.
    - **Autoriser une réservation partielle** - Les commandes peuvent être libérées lorsqu’une quantité est réservée. Le système évaluera si la quantité non réservée doit être marquée pour le cross-docking avancé et marquera cette quantité comme requise. S’il n’y a pas de marquage, le système créera du travail uniquement pour la quantité réservée. Lorsque la fonctionnalité est activée et initialisée pour la première fois, cette valeur est automatiquement attribuée à tous les entrepôts qui sont activés pour la gestion des entrepôts. Cette valeur n’est pas disponible pour les entrepôts qui ne sont pas activés pour la gestion des entrepôts.
    - **Exiger une réservation complète** - Les commandes ne peuvent être validées que si la totalité de la quantité est réservée. Elles ne peuvent pas être libérées si la quantité totale n’est ni réservée physiquement ni prévue pour le cross-docking. Cette valeur n’est pas disponible pour les entrepôts qui ne sont pas activés pour la gestion des entrepôts.

1. Sélectionnez **Enregistrer**.

## <a name="scenarios"></a>Scénarios

Cette section fournit deux scénarios que vous pouvez étudier pour savoir ce que fait la fonctionnalité et comment l’utiliser.

### <a name="make-sample-data-available"></a>Rendre les exemple de données disponibles

Pour exécuter ces scénarios à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

Vous pouvez également utiliser ces scénarios comme orientation pour utiliser la fonctionnalité lorsque vous travaillez sur un système de production. Cependant, dans ce cas, vous devez remplacer vos propres valeurs, et il se peut que certains types d’enregistrements requis que les données de démonstration standard fournissent manquent.

### <a name="scenario-1-require-full-release-no-planned-cross-docking"></a><a name="scenario1"></a>Scénario 1 : Exiger une libération complète (pas de cross-docking prévu)

Ce scénario montre comment la fonctionnalité fonctionne pour les entrepôts définis sur **Exiger une réservation complète**.

1. Accédez à **Gestion des entrepôts \> Configuration \> Entrepôt \> Emplacements fixes**.
1. Pour l’entrepôt _62_, définissez le champ **Conditions requises pour la réservation de stock** sur **Exiger une réservation complète**, comme décrit dans la section [Définir la règle de libération dans l’entrepôt pour chaque entrepôt](#set-option-warehouse) plus haut dans cette rubrique.
1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau** pour créer une commande client.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - Dans le raccourci **Client**, définissez le champ **Compte client** sur _US-004_.
    - Dans l’organisateur **Général**, définissez le champ **Entrepôt** sur _62_.

1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.
1. Votre nouvelle commande client est ouverte. Elle comprend une ligne vide dans la grille dans la section **Lignes de commande client**. Sur cette ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *2*

1. Sélectionnez **Ajouter une ligne** pour ajouter une nouvelle ligne, puis définissez les valeurs suivantes :

    - **Numéro d’article :** *A0002*
    - **Quantité :** *2*

1. Sélectionnez la première ligne de commande, puis, sur le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.
1. Sur la page **Réservation**, sélectionnez **Réserver un lot** pour réserver la quantité totale de la ligne sélectionnée dans l’entrepôt.
1. Fermez la page **Réservation** pour revenir à la commande client.
1. Ne réservez pas la deuxième ligne de commande.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.
1. Notez que le message d’erreur suivant s’affiche : « La quantité totale doit être réservée physiquement. » Par conséquent, le système ne crée aucun travail, expédition ou chargement pour la commande.

    > [!NOTE]
    > Vous recevrez le même message d’erreur si vous réservez partiellement la deuxième ligne.

### <a name="scenario-2-allow-partial-release"></a>Scénario 2 : Autoriser la libération partielle

Ce scénario montre comment la fonctionnalité fonctionne pour les entrepôts définis sur **Autoriser la libération partielle**.

1. Accédez à **Gestion des entrepôts \> Configuration \> Entrepôt \> Emplacements fixes**.
1. Pour l’entrepôt _62_, définissez le champ **Conditions requises pour la réservation de stock** sur **Autoriser la libération partielle**, comme décrit dans la section [Définir la règle de libération dans l’entrepôt pour chaque entrepôt](#set-option-warehouse) plus haut dans cette rubrique.
1. Comme vous l’avez fait dans le [scénario précédent](#scenario1), aller à **Ventes et marketing \> Commandes client \> Toutes les commandes client** et créez une commande client pour le compte client _US-004_ de l’entrepôt _62_. Ajoutez les deux lignes de commande suivantes :

    - **Ligne 1 :** Définissez le champ **Numéro d’article** sur _A0001_ et le champ **Quantité** sur _2_, et le champ **Unité** sur _Pcs_.
    - **Ligne 2 :** Définissez le champ **Numéro d’article** sur _A0002_ et le champ **Quantité** sur _2_, et le champ **Unité** sur _Pcs_.

1. Comme vous l’avez fait dans le [scénario précédent](#scenario1), réservez la quantité totale pour la ligne de commande 1, mais ne réservez pas la ligne de commande 2.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.
1. Notez que vous ne recevez pas de message d’erreur cette fois. Au lieu de cela, le système crée du travail, des expéditions et des chargements selon les besoins et affiche les résultats.
1. Pour afficher les informations d’expédition, de chargement et de travail, utilisez les options du menu **Entrepôt** au dessus de la grille :

    - **Ligne 1 :** Trois options sont disponibles : **Détails de l’expédition**, **Détails du chargement** et **Détails du travail**. Sélectionnez chaque option pour afficher les détails de l’expédition, du chargement et du travail créés lors de la libération de la commande dans l’entrepôt.
    - **Ligne 2 :** Seule l’option **Détails du travail** est disponible. Sélectionnez-la et notez qu’aucun travail n’a été créé, car aucun stock n’a été réservé. Par conséquent, aucune expédition ou chargement n’a été créé non plus.

> [!NOTE]
> Le même résultat est attendu lorsque la deuxième ligne est partiellement réservée. Dans ce cas, le travail sera créé pour la quantité de ligne réservée mais pas pour la quantité non réservée.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]