---
title: Instruction d'emplacement relatif à l'âge du prélèvement du stock
description: Cette rubrique explique comment utiliser les stratégies de directive d'emplacement premier entré, premier sorti (FIFO) et dernier entré, premier sorti (LIFO) lors du prélèvement.
author: mirzaab
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile,WHSWorkTable,WHSWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: f8d5e4d82c66d178ceafcdbfb3eb9a941172aa01
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004625"
---
# <a name="location-directive-inventory-picking-aging"></a>Instruction d'emplacement relatif à l'âge du prélèvement du stock

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment utiliser les stratégies de directive d'emplacement premier entré, premier sorti (FIFO) et dernier entré, premier sorti (LIFO) lors du prélèvement. Ces stratégies fonctionnent en conjonction avec les dates d'âge qui sont enregistrées pour les emplacements et qui permettent de savoir à quel moment le stock est entré dans l'entrepôt. La fonction *Instruction d’emplacement relatif à l’âge du prélèvement du stock* utilise la date de l'emplacement pour déterminer l'âge. La fonction *Statut de l'emplacement de l'entrepôt* met à jour la date de l'emplacement en fonction de la date provenant du contenant.

Vous pouvez utiliser les stratégies FIFO et LIFO pour expédier à la fois les articles suivis par lots et les articles non suivis par lots, en fonction de la date à laquelle le stock est entré dans l'entrepôt. Cette fonctionnalité peut être particulièrement utile pour les stocks non suivis par lots, où une date d'expiration n'est pas disponible pour le tri.

Lors de la première réception ou de la création du stock dans l'entrepôt, le système met à jour le contenant approprié de sorte que la date actuelle soit affichée comme date d'âge. Cette date est ensuite utilisée par les stratégies de directive d'emplacement pour identifier le stock le plus ancien ou le plus récent de l'entrepôt. Si le stock est déplacé vers un emplacement qui n'est pas suivi par contenant, l'emplacement lui-même est mis à jour avec les informations d'âge, et ces informations seront ensuite utilisées par les stratégies.

## <a name="turn-on-the-feature"></a>Activer la fonctionnalité

Pour rendre cette fonctionnalité disponible, activez les fonctionnalités suivantes dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), dans l'ordre suivant :

1. Statut de l'emplacement de l'entrepôt
1. Instruction d'emplacement relatif à l'âge du prélèvement du stock

## <a name="feature-requirements"></a>Exigences relatives à la fonctionnalité

Pour utiliser cette fonction, vous devez définir l'option **Activer le statut de l'emplacement** sur *Oui* pour chaque [profil d'emplacement](tasks/create-location-profile.md) utilisé pour conserver le stock. Pour définir cette option pour un profil d'emplacement, accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d'emplacement** et sélectionnez le profil d'emplacement. Vous pouvez trouver l'option dans l'organisateur **Général**.

## <a name="feature-scenarios"></a>Scénarios de la fonctionnalité

Cette section illustre le paramétrage et l'utilisation des stratégies FIFO et LIFO.

> [!TIP]
> Cette section propose deux scénarios, un pour la stratégie FIFO et un pour la stratégie LIFO. Les procédures fournies supposent que vous effectuerez les deux scénarios, dans l'ordre. Nous vous recommandons de suivre les deux scénarios afin de pouvoir découvrir les différences entre les deux stratégies.

### <a name="make-sample-data-available"></a>Rendre les exemple de données disponibles

Pour exécuter ces scénarios à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

Vous pouvez également utiliser ces scénarios comme orientation pour utiliser la fonctionnalité dans un système de production. Cependant, dans ce cas, vous devez remplacer les valeurs de chaque paramètre décrit ici par les vôtres.

### <a name="set-up-the-scenarios"></a><a name="demo-set-up"></a>Paramétrage des scénarios

Les données de démonstration nécessitent des ajustements de configuration et de stock pour prendre en charge les scénarios. Suivez ces étapes pour créer les données de stock nécessaires à l'utilisation des scénarios FIFO et LIFO.

1. Connectez-vous à un système où les données de démonstration sont installées et sélectionnez l'entité juridique **USMF**.
1. Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d'emplacement**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans la liste des profils d'emplacement, sélectionnez **FLOOR-05**.
1. Dans le raccourci **Général**, définissez l'option **Activer le statut de l’emplacement** sur *Oui*.
1. Sélectionnez **Enregistrer**.
1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d'emplacements**.
1. Dans la liste des instructions d'emplacement, sélectionnez **63 Conteneurisation prélèvement**.
1. Sélectionnez **Modifier** pour afficher la page en mode d’édition.
1. Dans l'organisateur **Actions de directive d'emplacement**, trouvez la ligne où le champ **Numéro de séquence** est défini sur *1* et suivez l'une de ces étapes :

    - Si vous configurez un scénario FIFO, modifiez la valeur du champ **Stratégie** en *FIFO par âge d'emplacement*.
    - Si vous configurez un scénario LIFO, modifiez la valeur du champ **Stratégie** en *LIFO par âge d'emplacement*.

1. Dans l’organisateur **Actions de directive d’emplacement**, sélectionnez **Modifier la requête**.
1. Dans la boîte de dialogue de la requête, dans l'onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne, puis définissez les valeurs suivantes :

    - **Table :** *Emplacements*
    - **Table dérivée :** *Emplacements*
    - **Champ :** *ID zone*
    - **Critères :** *Sol*

1. Sélectionnez **OK** pour appliquer vos paramètres et fermer la boîte de dialogue de la requête.
1. Sélectionnez **Enregistrer** pour enregistrer les modifications de la directive d’emplacement.
1. Sur un appareil mobile ou dans l'application *Dynamics 365 for Finance and Operations - Entreposage* sur votre PC, procédez comme suit pour supprimer le stock existant de l'emplacement de l'entrepôt afin de prendre en charge les scénarios :

    1. Connectez-vous à l'entrepôt *63* en utilisant un ID d'utilisateur et un mot de passe appropriés.
    1. Dans le menu principal, sélectionnez **Qualité**.
    1. Dans le menu **Gestion de la qualité**, sélectionnez **Rebut**.
    1. Dans la page **Rebut**, sélectionnez le champ **LOC/LP**, puis entrez *63\_1*.
    1. Sélectionnez **Entrée** ou **OK**.
    1. Confirmez les détails **Rebut** pour **Ajustement en sortie** en sélectionnant **Entrée** ou **OK**.

    Lorsque le stock du contenant est ajusté, vous recevez un message « Travail terminé ».

    Ces étapes laissent le stock à deux emplacements dans les données de démonstration. Chaque emplacement a une date de vieillissement différente. L'emplacement *FL-001* a une date de vieillissement du 15 avril 2017 et l'emplacement *FL-002* a une date de vieillissement du 29 janvier 2017. Les deux emplacements contiennent un article *A0001*.

    Pour afficher ces données, accédez à **Gestion du stock \> Recherches et états \> Liste disponible**, puis filtrez sur l'entrepôt *63* et l'article *A0001*. Dans les rangées où le champ **Emplacement** est défini sur *FL-001* ou *FL-002*, sélectionnez une ligne qui a une valeur **Stock physique** positive, puis, dans le volet Actions, sélectionnez **Transactions**. Le champ **Date physique** affichera une date qui correspond à l'une des dates de vieillissement mentionnées précédemment.

### <a name="scenario-1-set-up-and-use-fifo-location-aging"></a><a name="fifo-demo"></a>Scénario 1 : configurer et utiliser la stratégie FIFO par âge d'emplacement

La stratégie FIFO recherche l'emplacement qui contient la date d'âge la plus ancienne et alloue le prélèvement en fonction de cette date d'âge.

1. Si vous ne l'avez pas déjà fait, [préparez les exemples de données](#demo-set-up) nécessaires pour ce scénario.
1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - Dans l’organisateur **Client**, définissez le champ **Compte client** sur *US-001*.
    - Dans l’organisateur **Général**, définissez le champ **Entrepôt** sur *63*.

1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.
1. La nouvelle commande client est ouverte. Elle comprend une nouvelle rangée vide dans la grille de l'organisateur **Lignes de commande client**. Pour cette ligne de commande, définissez le champ **Numéro d'article** sur *A0001* et le champ **Quantité** sur *1*.
1. Dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.
1. Sur la page **Réservation**, sélectionnez **Réserver un lot** pour réserver la quantité commandée de cet article dans le stock de l’entrepôt sélectionné.
1. Fermez la page **Réservation**.
1. Dans la page **Commande client**, dans le volet Actions, dans l'onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Lancer dans l'entrepôt**. Vous recevez des messages d'information. Le système crée une expédition, l’ajoute à un nouveau chargement et crée le travail requis.
1. Dans l'organisateur **Lignes de commande client**, dans le menu **Entrepôt**, sélectionnez **Détails du travail** pour ouvrir le travail qui a été créé pour cette commande client. Notez que la ligne où la valeur **Type de travail** est *Prélever* présente une valeur **Emplacement** de *FL-002*. Cet emplacement contient le contenant ayant la date d'âge la plus ancienne (FIFO).
1. Sélectionnez **Entrepôt \> Détails de l'expédition**.
1. Dans le raccourci **_Général_*, notez l'ID de la vague afin de pouvoir l'utiliser dans le scénario 2.

### <a name="scenario-2-set-up-and-use-lifo-location-aging"></a>Scénario 2 : configurer et utiliser la stratégie LIFO par âge d'emplacement

La stratégie LIFO recherche l'emplacement qui contient la date d'âge la plus récente et alloue le prélèvement en fonction de cette date d'âge. Dans le scénario 2, vous allez modifier la configuration du scénario 1 (FIFO) et réutiliser la commande client et la vague qui ont été créées au cours de ce scénario.

1. Avant de commencer ce scénario, configurez et terminez le scénario FIFO en entier comme décrit dans la [section précédente](#fifo-demo). Dans ce scénario, vous réutiliserez la vague et la plus grande partie de la configuration qui ont été créées pour le scénario précédent.
1. Modifiez la directive d'emplacement **63 Conteneurisation prélèvement** afin qu'elle utilise la stratégie *LIFO par âge d'emplacement*, comme décrit dans la première partie de la procédure [Paramétrage des scénarios](#demo-set-up).

    Ensuite, vous allez modifier la vague qui a été créée pour la commande client dans le scénario 1, afin qu'elle utilise la stratégie *LIFO par âge d'emplacement*.

1. Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.
1. Sélectionnez et ouvrez la vague qui contient la commande que vous avez créée pour le scénario FIFO.
1. Dans le volet Actions, dans l'onglet **Travail**, sélectionnez **Annuler** pour annuler le travail que vous avez créé pour le scénario FIFO.
1. Dans le volet Actions, sous l'onglet **Vague**, dans le groupe **Vague**, sélectionnez **Traiter**.
1. Une fois le processus terminé, dans le volet Actions, dans l'onglet **Vague**, dans le groupe **Informations connexes**, sélectionnez **Travail** pour ouvrir le travail créé.
1. Dans la page **Travail**, dans l'onglet **Aperçu**, il doit y avoir deux lignes. Sélectionnez la ligne où le champ **Statut du travail** est défini sur *Ouvert*.
1. Notez que la ligne où la valeur **Type de travail** est *Prélever* présente une valeur **Emplacement** de *FL-001*. Cet emplacement contient le contenant ayant la date d'âge la plus récente (LIFO).

Dans ces scénarios, vous avez vu comment la stratégie par âge d'emplacement oriente le travail vers l'emplacement de stock qui contient le stock le plus ancien ou le plus récent, selon la stratégie sélectionnée.
