---
title: Atelier de création de chargement
description: Cette rubrique décrit comment utiliser l’atelier de création de charge.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSLoadBuildWorkbench,TMSLoadBuildTemplateCreate,TMSLoadBuildStrategy,TMSLoadBuildTemplateApply
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7b8633adbab43c95366d42cf409f5e508771c906
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809036"
---
# <a name="load-building-workbench"></a>Atelier de création de chargement

L’atelier de création de charges vous permet d’appliquer des stratégies de création de charges lorsque vous créez des charges.

## <a name="create-a-load-building-strategy"></a>Créer une stratégie de création de chargement

Vous utilisez des stratégies de création de charges pour créer automatiquement des charges. Cette capacité peut être bénéfique dans les situations suivantes :

- Si vous expédiez régulièrement un ensemble spécifique de produits, les stratégies de chargement vous permettent de gagner du temps, car vous n’avez pas à créer la même charge à chaque fois.
- Si vous souhaitez éviter les charges à moitié pleines pour maximiser l’efficacité, les stratégies de charge peuvent aider à remplir chaque charge autant que possible.

Une classe de stratégie de création de charge nommée `TMSLoadBuildingVolumeStrategy` fournit une stratégie de création de charge nommée *Stratégie de création de charge basée sur le volume*. Cette stratégie vous permet d’utiliser les valeurs maximales spécifiées pour la hauteur et le poids dans le modèle de chargement, sinon vous pouvez remplacer les paramètres en entrant de nouvelles valeurs. Cette stratégie est la seule stratégie qui est incluse prête à l’emploi. (Cependant, vous pouvez avoir des stratégies personnalisées.)

Pour utiliser la *Stratégie de création de charge basée sur le volume* prête à l’emploi, sélectionnez-la dans le champ **Stratégie de construction de charge** sur la page **Atelier de création de chargement** (**Gestion des transports &gt; Planification &gt; Atelier de création de chargement**).

Pour créer une stratégie de création de chargement, procédez comme suit.

1. Aller à **Gestion des transports &gt; Configurer &gt; Création de charge &gt; Stratégies de création de charge**.
1. Dans le volet Actions, sélectionnez **Générer une liste de classes** pour vous assurer que vous disposez des dernières versions de toutes les classes disponibles.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Saisissez un nom unique pour la stratégie, sélectionnez la classe de stratégie de création de charge correspondante et saisissez une description.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Sélectionnez **Paramètres** dans le volet Actions.
1. Sur la page **Paramètres de stratégie de création de charge**, sélectionnez **Capacité de volume** dans la liste, puis, dans le champ **Valeur**, entrez le pourcentage de la capacité volumique totale de la charge qui doit être appliqué pour la nouvelle stratégie de création de charge.
1. Sélectionnez **Capacité de poids** dans la liste, puis, dans le champ **Valeur**, entrez le pourcentage de la capacité de poids totale de la charge qui doit être appliqué pour la nouvelle stratégie de création de charge.
1. Fermez la page **Paramètres de stratégie de création de charge**.
1. Fermez la page **Stratégie de création de charge**.

Vous pouvez maintenant affecter la stratégie de création de charge à un modèle de création de charge. Vous pouvez également l’utiliser directement dans l’atelier de planification de la charge.

## <a name="use-a-load-building-strategy-in-the-load-building-workbench"></a>Utilisez une stratégie de création de charge dans l’atelier de création de charge

1. Accédez à **Gestion du transport &gt; Planification &gt; Atelier de création de charge**.
1. Utilisez l’une des procédures suivantes :

    - Sélectionnez une stratégie dans le champ **Stratégie de création de charge**.
    - Si vous avez défini un modèle de création de charge et lui avez attribué la stratégie de création de charge, dans le volet Actions, sur l’onglet **Gérer les modèles**, sélectionnez **Appliquer le modèle**. Puis, dans la boîte de dialogue déroulante **Appliquer le modèle de création de charge**, sélectionnez un modèle dans le champ **Nom du modèle de création de charge**.

1. Sur le raccourci **Séquence des modèles de charges**, sélectionnez un ou plusieurs [modèles de charges](load-template.md). L’atelier essaiera d’adapter la charge dans ces types de conteneurs, dans l’ordre spécifié ici. En règle générale, vous devez placer les plus petits conteneurs en haut de la liste pour vous assurer que le plus petit conteneur possible est sélectionné en premier.
1. Dans le volet Actions, sélectionnez **Proposer des charges**.
1. Passez en revue les charges proposées et les lignes de charge proposées.
1. Dans le volet Actions, sélectionnez **Créer des charges** pour créer des charges basées sur les lignes du document source sur le raccourci **Lignes de charge proposées**.
1. Fermez la page **Atelier de création de charge**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]