---
title: Vue d'ensemble de configuration de l'entrepôt
description: Cet article explique comment configurer un entrepôt. Elle contient des informations sur l'activation d'une présentation d'entrepôt et sur les processus d'entrepôt.
author: perlynne
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, WHSLocation, WHSLocationBuild, WHSLocationProfile, WHSLocationType, WHSLocDirTable, WHSParameters, WHSWaveTemplateTable, WHSWorkPool, WHSWorkTemplateTable, WHSZone, WHSZoneGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 11554
ms.assetid: 262b7b88-2cce-44f7-9a5b-77c12af1be20
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8cd436f1b8324335cc39ce54344db834dddebc9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427750"
---
# <a name="warehouse-configuration-overview"></a>Vue d'ensemble de configuration de l'entrepôt

[!include [banner](../includes/banner.md)]

Cet article explique comment configurer un entrepôt. Elle contient des informations sur l'activation d'une présentation d'entrepôt et sur les processus d'entrepôt.

> [!NOTE]
> Cet article s'applique aux fonctionnalités du module **Gestion des entrepôts** (entreposage avancé). Il ne s'applique pas aux fonctionnalités dédiées aux entrepôts du module **Gestion des stocks**.

## <a name="warehouse-layout"></a>Disposition de l'entrepôt
Le système de gestion des entrepôts de Supply Chain Management vous offre des moyens flexibles de définir la disposition de votre entrepôt pour répondre à vos besoins variables, afin de pouvoir atteindre le rendement optimal de l'entrepôt.

-   Vous pouvez créer des zones de stockage à priorité haute et basse pour positionner les marchandises de manière optimale.
-   Vous pouvez diviser votre entrepôt en zones pour répondre à des besoins de stockage variés, tels qu'une température de préférence ou des taux de rotation variables d'un article à l'autre.
-   Vous pouvez spécifier des emplacements de l'entrepôt à n'importe quel niveau (par exemple : site, entrepôt, allée, rayon, étagère, casier.)
-   Vous pouvez regrouper des emplacements à l'aide des paramètres de contrainte de capacité physique.
-   Vous pouvez contrôler la façon dont les articles sont stockés et prélevés, en fonction de règles définies par des requêtes.

Pour utiliser la gestion des entrepôts dans Supply Chain Management, vous devez créer un entrepôt et l'activer pour des activités plus avancées ou plus spécialisées de gestion des entrepôts. Dans la page **Entrepôts**, sélectionnez l'option **Utiliser les processus de gestion des entrepôts**.

### <a name="zone-groups-zones-location-types-and-locations"></a>Groupes de zones, zones, types d'emplacements et emplacements

Dans le cadre du processus d'activation d'une disposition d'entrepôt, vous devez définir les groupes de zone d'entrepôt, les zones, les profils d'emplacement, les types d'emplacements et les emplacements.

-   **Groupes de zone** – Un regroupement logique ou physique des zones dans un entrepôt.
-   **Zones** – Un regroupement logique ou physique des emplacements dans un entrepôt.
-   **Profils d'emplacement** – Un regroupement logique ou physique des emplacements ayant les mêmes stratégies de processus d'emplacement d'entrepôt (par exemple, un assortiment de différents numéros d'article peuvent y être stocké, et les mêmes contraintes de capacité physique s'appliquent).
-   **Types d'emplacements** – Un regroupement logique ou physique des emplacements dans l'entrepôt. Par exemple, vous pouvez créer un type d'emplacement pour tous les emplacements temporaires. Les paramètres obligatoires de la page **Paramètres de gestion des entrepôts** pilotent le processus de définition des types d'emplacements temporaires et de type d'emplacement final pour expédition.
-   **Emplacements** – Le plus bas niveau d'information d'emplacement. Les emplacements sont utilisés pour suivre où le stock disponible est conservé et prélevé dans un entrepôt.

Les entités que vous créez pour définir votre disposition d'entrepôt sont utilisées dans les requêtes que vous paramétrez dans les modèles de travail pour piloter les ordres d'exécution dans l'entrepôt. Par conséquent, lorsque vous définissez les zones, les types d'emplacement, etc., prenez en compte la manière dont les différentes zones de l'entrepôt sont utilisées pour différents processus. En outre, tenez compte des facteurs tels que les caractéristiques physiques d'une région spécifique. Par exemple, il peut y avoir des secteurs où vous ne pouvez utiliser qu'un certain type de chariot élévateur. Ou, si dans votre société les biens en production et finis se trouvent dans le même établissement, vous pouvez créer un seul entrepôt dans Supply Chain Management, mais séparer les deux opérations en créant deux groupes de zones. Donnez à vos entités des noms descriptifs, de sorte qu'il soit facile de les identifier si vous les utilisez dans des requêtes de modèle.

### <a name="location-stocking-limits-location-profiles-and-fixed-picking-locations"></a>Limites de stockage d'emplacement, profils d'emplacement et emplacements de prélèvement fixes

Vous devez tenir compte la disposition physique de l'entrepôt, aussi bien pour déterminer les capacités de stockage (les limites de stockage d'emplacement et les profils d'emplacement) que dans le cadre de vos tentatives d'optimiser les processus d'entrepôt. 

Les limites de stockage de l'emplacement permettent de s'assurer que le travail n'est pas créé pour demander le déplacement du stock vers un emplacement qui n'a pas la capacité physique de l'accueillir. Par exemple, si certains emplacements d'un entrepôt ne peuvent contenir qu'une palette par emplacement, les limites de stockage d'emplacement peuvent être activées. La valeur **Quantité** peut être définie sur **1**, et la valeur **Unité** peut être définie sur **Palette** dans un regroupement de profils d'emplacement spécifique. 

Si les calculs plus avancés sont requis pour contrôler les contraintes de capacité d'emplacement, les paramètres de profil d'emplacement peuvent être utilisés. Dans ce cas, le poids et le volume sont considérés lorsque des calculs de capacité. 

Pour atteindre des processus de sortie optimaux, vous devez évaluer s'il convient d'utiliser des emplacements de prélèvement fixes et/ou des emplacements d'emballage. Souvent, on utilise un réapprovisionnement minimum/maximum pour les processus de réapprovisionnement des emplacements de prélèvement fixes à partir d'une zone de vrac, et il est possible d'activer plusieurs emplacements de prélèvement fixes au sein du même entrepôt pour les variantes de produit. Considérez la flexibilité que vous pouvez obtenir en activant des emplacements consacrés au dépassement de capacité de réapprovisionnement de la demande utilisés uniquement pour le processus de réapprovisionnement par vague ou de chargement.

### <a name="location-setup-wizard"></a>Assistant Paramétrage d'emplacement

Pour créer rapidement des emplacements dans un entrepôt, vous pouvez utiliser l'assistant **Paramétrage des emplacements**. Dans le cadre de ce processus, vous pouvez facilement conserver le format des noms d'emplacement.

## <a name="warehouse-processes"></a>Processus d'entrepôt
Dans le cadre de la configuration de l'entrepôt, il est important que vous activiez les processus d'entrepôt conformément aux besoins de l'activité. Les composants les plus importants que vous devez configurer sont les modèles de vague, les modèles de travail, les pools de travail et les directives d'emplacement.

### <a name="wave-templates"></a>Modèles de vague

Les modèles de vague permettent d'activer le processus « Libérer dans l'entrepôt ». Dès que les lignes de commande sont publiées (directement à partir des documents source, par des processus de traitement par lots, ou par des charges qui ont déjà été créées), la fonctionnalité de modèle de vague est utilisée. 

Vous pouvez créer les trois types de modèles de vague suivants : 
-   **Expédition**
-   **Ordre de fabrication**
-   **Kanban** 

Les paramètres sont utilisés pour définir jusqu'où le système doit poursuivre automatiquement dans le traitement du travail sortant. Un modèle de vague est sélectionné en fonction de la séquence du modèle de vague et des critères spécifiés dans le modèle. Si un modèle est répertorié en haut de la séquence, les critères de ce modèle sont vérifiés en premier. Si les critères peuvent être respectés, le modèle de vague est traité. Sinon, les critères du modèle suivant sont vérifiés, et ainsi de suite. Par conséquent, il est judicieux de mettre en haut de la liste de séquence de modèles de vague le modèle qui présente les critères les plus spécifiques, de sorte qu'il soit traité en premier. Par exemple, vous souhaitez traiter tout le travail d'un transporteur spécifique aujourd'hui et retarder temporairement le traitement du travail des autres transporteurs. Dans ce cas, le modèle de vague qui sélectionne le travail pour ce transporteur doit être répertorié plus haut dans la séquence que d'autres modèles. Sinon, le travail pour les autres transporteurs sera peut-être traité avant que le travail pour ce transporteur soit achevé. 

Vous devez spécifier les méthodes de processus de vague dans chaque modèle de vague. Les méthodes disponibles varient en fonction du type de modèle de vague.

### <a name="work-templates"></a>Modèles de travail

Les définitions de modèle de travail jouent un rôle important dans la définition des processus de travail de gestion des entrepôts. Ils définissent quel travail doit être effectué, et de quelle manière. Les modèles peuvent également contenir un code de directive qui pointe vers une directive d'emplacement pour déterminer où le travail doit être effectué. Les modèles de travail incluent une requête qui spécifie les critères pour le travail. Chaque modèle doit inclure au moins une opération de prélèvement et une opération de placement pour piloter l'opération de travail de base de transfert du stock disponible à partir d'un emplacement vers un autre. 

Si plusieurs collaborateurs doivent pouvoir exécuter un travail pour certaines de vos opérations d'entrepôt, vous voudrez peut-être utiliser le concept d'*échelonnement* pour le stock et séparer l'exécution du travail en différentes classes de travail.

### <a name="work-pools"></a>Pools de travail

Les pools de travail sont utilisés pour organiser le travail en groupes. Par exemple, vous pouvez créer un pool de travail pour classer le travail qui se produit dans un emplacement d'entrepôt particulier. Vous pouvez affecter un pool de travail à un modèle de travail pour tous les types de travail, sauf l'inventaire. Pour l'inventaire tournant, vous pouvez affecter un pool de travail aux pages suivantes :

-   Plans d'inventaire tournant
-   Seuils d'inventaire tournant
-   Travail d'inventaire tournant par emplacement
-   Travail d'inventaire tournant par article

Lorsque vous utilisez des modèles de travail pour créer un travail, le pool de travail est automatiquement affecté au travail. 

Les ID de pool de travail peuvent également être utilisés pour limiter le type de travail qui est dirigé vers un employé spécifique de l'entrepôt, à condition que cette fonction soit configurée dans l'option de menu de périphérique portable appropriée.

### <a name="location-directives"></a>Instructions d'emplacement

Comme leur nom l'indique, les directives d'emplacement sont utilisées pour diriger les transactions de travail vers les emplacements adaptés dans l'entrepôt. Autrement dit, elles définissent où réaliser les prélèvements et les placements. 

Pour faciliter et accélérer la définition des actions associées à chaque ligne de directive d'emplacement, utilisez l'une des stratégies prédéfinies. Par exemple, vous pouvez utiliser la stratégie **Emplacement vide sans travail entrant** pour rechercher des emplacements libres dans un entrepôt, ou vous pouvez utiliser la stratégie **Réservation de traitement par lots FEFO** pour le prélèvement sortant des ventes.

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Configurer des emplacements dans un entrepôt compatible WMS](tasks/configure-locations-wms-enabled-warehouse.md)



