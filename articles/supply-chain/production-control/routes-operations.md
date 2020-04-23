---
title: Gammes et opérations
description: Cette rubrique fournit des informations sur les gammes et les opérations.
author: sorenva
manager: tfehr
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMDesigner, BOMDesignerRouteVersion, Route, RouteInventProd, RouteOpr, RouteOprTable
ms.author: sorenand
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 268124
ms.assetid: f78d5836-3e71-42b7-a5d1-41f19228d9d2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a6d792a0e52d2b82b25de461dcec358fdc8f439
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211075"
---
# <a name="routes-and-operations"></a>Gammes et opérations

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur les gammes et les opérations. Une gamme définit le processus de fabrication d'un produit ou d'une variante de produit. Elle décrit chaque étape (opération) dans le processus de fabrication et l'ordre dans lequel ces étapes doivent être effectuées. Pour chaque étape, la gamme définit également les ressources opérationnelles requises, la durée de configuration et d'exécution requise et la manière dont le coût doit être calculé.

<a name="overview"></a>Vue d'ensemble
--------

Une gamme décrit l'ordre des opérations nécessaires pour fabriquer un produit ou une variante de produit. Pour chaque opération, la gamme définit également les ressources opérationnelles requises, le temps nécessaire pour paramétrer et exécuter l'opération, et la manière dont le coût doit être calculé. Vous pouvez utiliser la même gamme pour fabriquer plusieurs produits, ou vous pouvez définir une seule gamme pour chaque produit ou variante de produit. Vous pouvez même avoir plusieurs gammes pour le même produit. Dans ce cas, la gamme utilisée varie en fonction de facteurs tels que la quantité qui doit être produite. La définition d'une gamme dans Supply Chain Management se compose de quatre éléments distincts qui, ensemble, décrivent le processus de production :

-   **Gamme** – Une gamme définit la structure du processus de production. Autrement dit, elle définit l'ordre des opérations.
-   **Opération** – Une opération identifie une étape nommée dans une gamme, par exemple **Assemblage**. La même opération peut se produire dans plusieurs gammes et peut avoir plusieurs numéros d'opération.
-   **Relation d'opération** – Une relation d'opération définit les propriétés opérationnelles d'une opération, telles que le temps de réglage et d'exécution, les catégories de coûts, les paramètres de consommation et les besoins en ressources. La relation d'opération permet de faire varier les propriétés opérationnelles d'une opération selon la gamme dans laquelle l'opération est utilisée ou les produits qui sont fabriqués.
-   **Version de gamme** – Une version de gamme définit la gamme utilisée pour fabriquer un produit ou une variante de produit. Les versions de gamme permette de réutiliser les gammes pour différents produits ou de les modifier au fil du temps. Elles permettent également d'utiliser différentes gammes pour fabriquer le même produit. Dans ce cas, la gamme utilisée dépend de facteurs tels que l'emplacement ou la quantité qui doit être produite.

## <a name="routes"></a>Gammes
Une gamme décrit l'ordre des opérations accomplies pour fabriquer un produit ou une variante de produit. Chaque opération est associée à un numéro d'opération et à une opération successive. L'ordre des opérations forme un réseau de gamme qui peut être représenté par un graphique dirigé ayant un ou plusieurs points de départ et un point d'arrivée unique. Dans Supply Chain Management, les gammes se distinguent en fonction du type de structure. Les deux types de gammes sont les gammes simples et les réseaux de gammes. Dans les paramètres de contrôle de la production, vous pouvez indiquer d'utiliser uniquement des gammes simples, ou s'il est possible d'utiliser des réseaux de gammes plus complexes.

### <a name="simple-routes"></a>Gammes simples

Une gamme simple est séquentielle et ne présente qu'un seul point de départ.  

[![Gamme simple](./media/routes-and-operations-1-simple-route.png)](./media/routes-and-operations-1-simple-route.png)  

Si vous activez uniquement les gammes simples dans les paramètres de contrôle de la production, Supply Chain Management génère automatiquement les numéros d'opération (10, 20, 30, etc.) lorsque vous définissez la gamme.

### <a name="route-networks"></a>Réseaux de gammes

Si vous activez les réseaux de gammes plus complexes dans les paramètres de contrôle de la production, vous pouvez définir des gammes ayant plusieurs points de départ et des opérations pouvant être exécutées en parallèle.  

[![Réseau de gammes](./media/routes-and-operations-2-route-network.png)](./media/routes-and-operations-2-route-network.png)  

> [!NOTE]
> -   Chaque opération ne peut avoir qu'une opération successive, et la gamme entière doit se terminer par une seule opération.
> -   Cela ne garantit pas que plusieurs opérations ayant la même opération successive (par exemple, les opérations 30 et 40 dans l'illustration précédente) seront réellement exécutées en parallèle. La disponibilité et la capacité des ressources peuvent imposer des contraintes à la planification des opérations.
> -   Vous ne pouvez pas utiliser 0 (zéro) comme numéro d'opération. Ce numéro est réservé et permet d'indiquer que la dernière opération de la gamme n'a aucune opération successive.

### <a name="parallel-operations"></a>Opérations parallèles

Parfois, une combinaison de plusieurs ressources opérationnelles ayant des spécifications différentes est requise pour exécuter une opération. Par exemple, une opération d'assemblage peut nécessiter une machine, un outil, et un collaborateur pour chacune des machines pour superviser l'opération. Cet exemple peut être modélisé à l'aide d'opérations parallèles, où une opération est désignée comme opération primaire et les autres comme secondaires.  

[![Gamme ayant des opérations primaire et secondaires](./media/routes-and-operations-3-parallel-operations.png)](./media/routes-and-operations-3-parallel-operations.png)  

Généralement, l'opération primaire représente la ressource critique et dicte le temps d'exécution pour les opérations secondaires. Toutefois, lors d'une planification qui implique une capacité finie, les ressources planifiées à la fois pour l'opération primaire et les opérations secondaires doivent être disponibles et avoir une capacité libre simultanément.  

L'opération primaire et les opérations secondaires doivent avoir le même numéro d'opération (30 dans l'illustration précédente).  

Dans l'exemple précédent, la ressource nécessaire de l'opération primaire (30) est la machine, alors que la ressource nécessaire des opérations secondaires (30' et 30'') sont l'outil et le collaborateur. Une charge de cinquante pour cent garantit que le collaborateur planifié peut superviser deux machines simultanément.

### <a name="approval-of-routes"></a>Approbation des gammes

Une gamme doit être approuvée avant de pouvoir être utilisée dans le processus de fabrication ou de planification. L'approbation Indique que la conception de la gamme a été menée à bien. Le même produit ou variante de produit lancé peut avoir plusieurs gammes approuvées. Généralement, l'approbation d'une gamme se produit lorsque la première version de gamme pertinente est approuvée. Toutefois, dans certains scénarios métier, l'approbation de la gamme et la version de gamme sont des activités distinctes qui peuvent impliquer des propriétaires de processus différents.  

Chaque gamme peut être séparément approuvée ou non approuvée. Toutefois, notez que, lorsqu'une gamme est non approuvée, toutes les versions de gamme associées sont également non approuvées. Dans les paramètres de contrôle de la production, vous pouvez spécifier si les gammes peuvent être non approuvées, et si les gammes approuvées peuvent être modifiées.  

Si vous devez tenir un journal qui consigne qui approuve chaque gamme, vous pouvez demander des signatures électroniques pour l'approbation de gamme. Les utilisateurs doivent alors confirmer leur identité à l'aide d'une [signature électronique](../../fin-and-ops/organization-administration/electronic-signature-overview.md).

## <a name="operations"></a>Operations
Une opération est une étape du processus de production. Chaque opération a un ID et une description simple. Les tableaux suivants montrent des exemples typiques d'opérations réalisées dans un atelier.

| Opération  | description ;        |
|------------|--------------------|
| PipeCut    | Tronçonnage de tube       |
| TIGweld    | Soudage TIG        |
| JigAssy    | Montage       |
| Inspection | Inspection de qualité |

Les propriétés opérationnelles de l'opération, telles que le temps de réglage et d'exécution, les ressources nécessaires, les informations de coûts et le calcul de la consommation, sont spécifiées dans la relation d'opération. (Pour plus d'informations sur les relations d'opération, consultez la section suivante.)

## <a name="operation-relations"></a>Groupes d'opérations
Les propriétés opérationnelles suivantes d'une opération sont conservées dans la relation d'opération :

-   Catégories de coûts
-   Paramètres de consommation
-   Durées du traitement
-   Quantités du traitement
-   Demandes de ressources
-   Notes et instructions

Vous pouvez définir plusieurs relations d'opération pour la même opération. Toutefois, chaque relation d'opération est spécifique à une opération, et enregistre les propriétés spécifiques à une gamme, à un produit, ou à un ensemble de produits associés à un groupe d'articles. Par conséquent, la même opération peut être utilisée dans plusieurs gammes ayant différentes propriétés opérationnelles. En outre, vous pouvez plus facilement maintenir vos données principales si vous utilisez des opérations standard ayant les mêmes propriétés opérationnelles, indépendamment de la gamme utilisée et du produit fabriqué. La portée de la relation d'opération est définie par les propriétés **Code article**, **Relation d'article**, **Code gamme** et **Relation de gamme**, comme l'indique le tableau suivant.

| Article - valide pour | Relation d'article         | Gamme - valide pour | Gamme - numéro ou groupe   | Portée de la relation d'opération                                                                                                                                                                                                                                                                              |
|-----------|-----------------------|------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Enregistrement     | &lt;ID article&gt;       | Gamme      | &lt;ID route&gt; | Les propriétés opérationnelles d'une opération lorsqu'elle est utilisée dans la gamme où **Numéro de gamme**=&lt;ID de gamme&gt; pour fabriquer le produit où **Numéro d'article**=&lt;ID d'article&gt;.                                                                                                                        |
| Enregistrement     | &lt;ID article&gt;       | Tout        |                  | Les propriétés opérationnelles par défaut d'une opération lorsqu'elle est utilisée pour fabriquer le produit où **Numéro d'article**=&lt;ID d'article&gt;. En d'autres termes, ces propriétés opérationnelles s'appliquent lorsqu'il n'y a aucune relation d'opération spécifique à la gamme pour le produit lancé.                                     |
| Regrouper     | &lt;ID groupe d'articles&gt; | Gamme      | &lt;ID route&gt; | Les propriétés opérationnelles d'une opération lorsqu'elle est utilisée dans la gamme où **Numéro de gamme**=&lt;ID de gamme&gt; pour fabriquer les produits associés au groupe d'articles &lt;ID groupe d'articles&gt;, sauf s'il existe une opération spécifique à la gamme pour le produit.                         |
| Regrouper     | &lt;ID groupe d'articles&gt; | Tout        |                  | Les propriétés opérationnelles par défaut d'une opération lorsqu'elle est utilisée pour fabrique les produits associés au groupe d'articles &lt;ID groupe d'articles&gt;, sauf s'il existe une relation d'opération plus spécifique.                                                                                                  |
| Tout       |                       | Gamme      | &lt;ID route&gt; | Les propriétés opérationnelles par défaut de l'opération lorsqu'elle est utilisée dans la gamme où **Numéro de gamme**=&lt;ID de gamme&gt;. En d'autres termes, ces propriétés opérationnelles s'appliquent lorsqu'il n'y a aucune relation d'opération pour cette gamme, spécifique au produit lancé ou à son groupe d'articles associé. |
| Tout       |                       | Tout        |                  | Les propriétés opérationnelles par défaut d'une opération. Ces propriétés opérationnelles s'appliquent lorsqu'une relation d'opération plus spécifique n'existe pas.                                                                                                                                                                |

Vous pouvez également spécifier qu'une relation d'opération est spécifique à un site. Ainsi, les propriétés opérationnelles d'une opération peuvent varier selon l'emplacement (autrement dit, le site) où l'opération est réalisée. Pour les produits configurés, vous pouvez également spécifier plusieurs propriétés opérationnelles pour chaque configuration de produit.  

Les relations d'opération vous accordent une grande flexibilité lorsque vous définissez vos gammes. En outre, la capacité de définir propriétés par défaut permettent de réduire la quantité de données principales à maintenir. Toutefois, cette flexibilité signifie également que vous devez tenir compte du contexte dans lequel vous modifiez une relation d'opération.  

> [!NOTE]
> Comme les propriétés opérationnelles sont enregistrées dans les relations d'opération par opération et pour chaque gamme, toutes les occurrences de la même opération (par exemple, l'assemblage) ont les mêmes temps de réglage, temps d'exécution et ressources nécessaires. Par conséquent, si deux occurrences d'une opération doivent se produire dans la même gamme mais avoir des temps d'exécution différents, vous devez créer deux opérations distinctes, telles que Assemblage1 et Assemblage2.

### <a name="modifying-product-specific-routes"></a>Modifier les gammes spécifiques à un produit

Lorsque vous ouvrez la page **Gamme** à partir de la page **Détails du produit lancé**, les versions de gamme associées au produit lancé sélectionné sont affichées. Dans ce contexte, pour chaque opération, Supply Chain Management affiche les propriétés opérationnelles de la relation d'opération qui est la mieux adaptée à la version de gamme. Vous remarquerez que la liste des opérations inclut les propriétés **Code article** et **Code gamme** à partir de la relation d'opération. Par conséquent, vous pouvez déterminer quelle relation d'opération est affichée.  

Dans la page **Gamme**, vous pouvez modifier les propriétés opérationnelles de l'opération, telles que le temps d'exécution ou les catégories de coûts. Vos modifications sont enregistrées dans la relation d'opération spécifique à la gamme et au produit lancé référencés dans la version de gamme actuelle. Si la relation d'opération qui est affichée n'est pas spécifiques à la gamme et au produit lancé, avant que vos modifications ne soient enregistrées, le système crée une copie de la relation d'opération. Cette copie *est* spécifique à la gamme et au produit lancé. Par conséquent, vos modifications n'affecteront pas les autres gammes ou produits lancés. Pour vérifier quelle relation d'opération est modifiée dans la page **Gamme**, observez les champs **Code article** et **Code gamme**.  

Vous pouvez également créer manuellement une opération spécifique à une gamme et à un produit lancé en utilisant la fonction **Copier et modifier la relation**.  

> [!NOTE]
> Si vous ajoutez une opération à une gamme dans la page **Gamme**, une relation d'opération est créée uniquement pour le produit lancé actuel. Par conséquent, si la gamme est également utilisée pour fabriquer d'autres produits lancés, aucune relation d'opération applicable n'existera pour ces produits lancés, et la gamme ne pourra plus être utilisée pour ces produits lancés.

### <a name="maintaining-operation-relations-per-route"></a>Conservation des relations d'opération par gamme

Lorsque vous ouvrez la page **Détails de la gamme** à partir de la page de liste **Gammes** une liste de toutes les relations d'opération qui s'appliquent à la gamme sélectionnée s'affiche. Par conséquent, vous pouvez facilement vérifier quelles sont les propriétés opérationnelles utilisées pour quels produits. Vous pouvez modifier aussi bien les valeurs de propriétés par défaut et les valeurs de propriétés spécifiques à un produit.  

Si vous ajoutez une nouvelle relation d'opération dans la page **Détails de la gamme**, le champ **Code gamme** est automatiquement défini sur **Gamme**, et le champ **Relation de gamme** est défini sur le numéro de gamme de la gamme actuelle.

### <a name="maintaining-operation-relations-per-operation"></a>Conservation des relations d'opération par opération

Dans la page **Opérations**, vous pouvez ouvrir la page **Relations d'opération**. Dans cette page, vous pouvez modifier toutes les relations d'opération pour une opération spécifique. Vous pouvez même modifier les relations d'opération qui contiennent des valeurs par défaut.  

Si votre société utilise des opérations standard, et si les paramètres opérationnels sont les mêmes pour l'ensemble des produits et processus, la page **Relations d'opération** offre un moyen pratique de maintenir les propriétés opérationnelles par défaut de ces opérations.

### <a name="applying-operation-relations"></a>Application des relations d'opération

Dans certains cas, Supply Chain Management doit trouver les propriétés opérationnelles d'une opération. Par exemple, lorsqu'une commande fournisseur est créée, les propriétés opérationnelles de chaque opération doivent être copiées à partir des relations d'opération vers la gamme de production. Dans ce cas, Supply Chain Management recherche les relations d'opération correspondantes en partant de la combinaison la moins spécifique vers la combinaison la moins spécifique.  

Lorsque Supply Chain Management recherche la relation d'opération la plus appropriée pour un produit lancé, une relation d'opération qui correspond à l'ID article du produit lancé est préférée à une relation d'opération qui correspond à l'ID groupe d'articles. Consécutivement, une relation d'opération qui correspond à l'ID groupe d'articles est préférée à la relation d'opération par défaut. La recherche s'effectue dans l'ordre suivant :

1.  **Code article**=**Table** and **Relation d'article**=&lt;ID article&gt;
2.  **Code article**=**Groupe** and **Relation d'article**=&lt;ID groupe d'articles&gt;
3.  **Code article**=**Tous**
4.  **Code gamme**=**Gamme** et **Relation de gamme**=&lt;ID gamme&gt;
5.  **Code gamme**=**Tous**
6.  **Configuration**=&lt;ID configuration&gt;
7.  **Configuration**=
8.  **Site**=&lt;ID site&gt;
9.  **Site**=

Par conséquent, une opération doit être utilisée une seule fois pour chaque gamme. Si l'opération est effectuée la plusieurs fois dans la même gamme, toutes les occurrences de cette opération auront la même relation d'opération, et vous ne pourrez pas avoir différentes propriétés (par exemple, les temps d'exécution) pour chaque occurrence.

## <a name="route-versions"></a>Versions de gamme
Les versions de gamme permettent de tenir compte de variations dans la production des produits ou de mieux contrôler le processus de production. Elles définissent quelle gamme doit être utilisée lors de la fabrication d'un produit ou d'une variante de produit spécifique. Vous pouvez utiliser les contraintes suivantes pour indiquer quelle gamme utiliser pour un produit lancé :

-   dimensions de produit (taille, couleur, style ou configuration)
-   quantité de fabrication
-   site de production
-   date de production

Lorsque vous fabriquer le produit sur un site particulier, dans une quantité donnée, ou dans une période donnée, vous pouvez indiquer une version de gamme spécifique comme version de gamme par défaut. Toutefois, notez qu'une seule gamme active est permise pour un produit lancé et un ensemble de contraintes donnés.  

Dans les paramètres de contrôle de la production, vous pouvez demander de spécifier toujours la période de validité d'une version de gamme.

### <a name="approval-of-route-versions"></a>Approbation des versions de gamme

Avant d'utiliser une version de gamme dans le processus de fabrication ou de planification, elle doit être approuvée. Lorsque vous approuvez une version de gamme, vous approuvez également la gamme associée. Toutefois, notez qu'une version de gamme ne peut être approuvée que si la gamme associée est également approuvée.

### <a name="activating-the-default-route-version"></a>Activation de la version de gamme par défaut

Lorsque vous activez une version de gamme, vous la désignez comme la version de gamme par défaut qui sera utilisée par la planification ou qui sera utilisée pour créer des ordres de fabrication. Vous ne pouvez avoir qu'une version de gamme active pour un ensemble de contraintes donné (par exemple, la période, le site ou la quantité). Vous recevez un message d'erreur si la version que vous tentez d'activer est en conflit avec une version qui est déjà active. Vous devez alors désactiver la version en conflit ou modifier les contraintes de la version de gamme (généralement la période) pour empêcher une activation ambiguë.

### <a name="electronic-signatures"></a>Signatures électroniques

Si vous devez tenir un journal qui consigne qui approuve et active chaque version de gamme, vous pouvez demander des signatures électroniques pour ces tâches. Les utilisateurs qui approuvent et activent les versions de gamme doivent alors confirmer leur identité à l'aide d'une [signature électronique](../../fin-and-ops/organization-administration/electronic-signature-overview.md).

### <a name="product-change-that-uses-case-management"></a>Modification de produit qui utilise la gestion de dossier

Le dossier de modification de produit pour l'approbation et l'activation de la gammes et de versions de gamme nouvelles ou modifiée fournit un moyen facile pour afficher une vue d'ensemble des contraintes de version de gamme. Vous pouvez également approuver et activer toutes les gammes liées à une modification spécifique d'une opération et documenter les résultats dans le dossier de modification de produit.

## <a name="maintaining-routes"></a>Tenue à jour des gammes
Selon vos exigences métier, vous pouvez réduire l'effort requis par la tenue à jour de vos définitions de processus.

### <a name="making-routes-independent-of-resources"></a>Réalisation de gammes indépendantes des ressources

Dans de nombreux système, la ressource opérationnelle ou le groupe de ressources nécessaires à la réalisation d'une opération doivent être spécifiés dans la gamme. Toutefois, dans Supply Chain Management, vous pouvez définir un ensemble de contraintes que doit respecter une ressource opérationnelle pour être utilisable par l'opération. Par conséquent, la ressource opérationnelle ou le groupe de ressources spécifiques qui doivent être utilisés ne doivent pas être déterminés tant que l'opération n'est pas réellement planifiée. Cette fonctionnalité est particulièrement utile si vous avez de nombreux collaborateurs ou machines capables d'exécuter la même opération.  

Par exemple, vous spécifiez qu'une opération requiert une ressource opérationnelle du type **Machine** ayant une capacité d'**estampage** de 20 tonnes. Le moteur de planification résoudra ces exigences de ressource opérationnelle ou de groupe de ressources lorsque l'opération sera planifiée. Comme vous pouvez définir ces exigences au lieu de lier l'opération à une machine spécifique, votre flexibilité est améliorée. En outre, la maintenance est plus facile lors du déplacement de ressources ou de l'ajout de nouvelles ressources.  

Pour plus d'informations sur les différents types de demandes de ressources et leur utilisation, voir les demandes de ressources opérationnelles et [Capacités de ressources](resource-capabilities.md).

### <a name="sharing-routes-across-sites"></a>Partage de gammes entre plusieurs sites

Si vous fabriquez le même produit sur plusieurs sites de production, et si les étapes pour la fabrication de ce produit sont identiques sur tous les sites, vous pouvez souvent créer une gamme partagée qui sera utilisée sur tous les sites de production. Pour créer une gamme partagée, ne spécifiez pas de site dans la gamme elle-même. Toutefois, vous devez toujours créer une version de gamme qui associe la gamme partagée avec le produit sur chaque site.  

Vous devez également vous assurer que les demandes de ressources pour chaque opération de la gamme n'exigent pas de ressources opérationnelles ou de groupes de ressources spécifiques, mais sont exprimées en termes de caractéristiques des ressources requises. Le moteur de planification pourra alors affecter les ressources opérationnelles appropriées pour le site sur lequel la production est planifiée. Par exemple, s'il existe de petites différences de temps d'exécution, ou si le temps de réglage pour une certaine opération est spécifique à un site, vous pouvez spécifier ces informations en ajoutant une relation d'opération supplémentaire pour ce site.  

Pour bénéficier pleinement des avantages des gammes partagées, vous devez également utiliser la consommation de ressources dans la nomenclature correspondante. Lorsque vous définissez l'indicateur de consommation de ressources sur la ligne de nomenclature, l'entrepôt et l'emplacement d'où doivent être consommées les matières premières est inféré de la ressource opérationnelle pour laquelle l'opération est planifiée. Par conséquent, l'entrepôt et l'emplacement ne doivent pas être déterminés tant que la production n'est pas réellement planifiée. De cette manière, vous pouvez rendre la nomenclature et la gamme indépendantes de l'emplacement physique où le produit est fabriqué.

### <a name="standard-operation-relations"></a>Relations d'opération standards

Si votre société utilise des opérations de production standardisées et qu'il n'existe que peu ou pas de variation du temps de réglage, du temps d'exécution, du calcul de la consommation, du calcul des coûts, etc., vous pouvez profiter de la création de relations d'opération par défaut pour toutes les opérations. Dans ce cas, évitez de créer des relations d'opération qui sont spécifiques à une gamme ou à un produit lancé.  

Si vous exprimez également les demandes de ressources en termes de qualifications et d'aptitudes, et que vous rendez vos gammes indépendantes des sites, vous pouvez réduire au minimum la maintenance continue de vos processus métier.  

Lorsque vous utilisez cette approche, la page **Relations d'opération** devient votre destination première pour tenir à jour les temps d'exécution et les autres propriétés.

### <a name="resource-specific-process-times"></a>Temps de traitement spécifique aux ressources

Si vous ne spécifiez pas de ressource opérationnelle ou de groupe de ressources dans le cadre des demandes de ressources pour une opération, les ressources applicables peuvent être exécutées à différentes vitesses. Par conséquent, le temps nécessaire pour traiter une opération peut varier. Pour résoudre ce problème, vous pouvez utiliser le champ **Formule** dans la relation d'opération pour spécifier le calcul du temps de traitement. Les options suivantes sont disponibles :

-   **Standard** – option par défaut) Le calcul utilise uniquement les champs de la relation d'opération et multiplie le temps d'exécution spécifié par la quantité de la commande.
-   **Capacité** – Le calcul comprend le champ **Capacité** issu des ressources opérationnelles. Par conséquent, la durée dépend des ressources. La valeur spécifiée pour la ressource opérationnelle est la capacité horaire. Cette valeur est multipliée par la quantité de la commande et la valeur **Facteur** issue de la relation d'opération.
-   **Lot** – Une capacité de lot est calculée à l'aide des informations issues de la relation d'opération. Le nombre de lots et, par conséquent, le temps d'exécution, peuvent ensuite être calculés en fonction de la quantité de la commande.
-   **Lot de ressource** – Cette option est fondamentalement la même que l'option **Lot**. Toutefois, le calcul comprend le champ **Capacité de lot** issu des ressources opérationnelles. Par conséquent, la durée dépend des ressources.

### <a name="set-up-route-groups"></a>Paramétrer des groupes de gammes

Vous pouvez définir des groupes de gammes et le paramétrage pour ces types de gamme ou de tâche sous **Contrôle de la production > Paramétrage > Gammes > Groupes de gammes**. Pour chaque type de gamme/tâche dans le groupe de gammes, vous pouvez activer ou désactiver les options suivantes :

- **Activation** : sélectionnez cette option pour activer les calculs et la planification du type de tâche sélectionné et de recevoir des commentaires sur les tâches lorsque vous exécutez la planification des tâches. Vous devez sélectionner cette option pour activer le type de tâche, puis sélectionner le reste des options pour ce type de tâche. Si l'activation n'est pas sélectionnée, ce type de tâche n'est pas activé, indépendamment de la sélection des autres options. 
- **Gestion des tâches** : sélectionnez cette option pour inclure le type de tâche dans la gestion des tâches lorsque vous exécutez la planification des tâches. 
- **Temps de travail** : sélectionnez cette option pour planifier le type de tâche en fonction du calendrier du temps de travail défini pour la ressource opérationnelle. Sinon, le calendrier grégorien est sélectionné. Le temps de travail peut être planifié selon le calendrier grégorien ou le calendrier du temps de travail défini. Si vous sélectionnez cette option, la planification est basée sur le calendrier du temps de travail défini. En outre, la tâche du type de tâche est planifiée à partir minuit à la date définie comme date de début de la tâche.
- **Capacité** : sélectionnez cette option pour réserver la capacité pour le type de tâche lorsque vous exécutez la planification des tâches. So vous sélectionnez cette option, la capacité est réservée lorsque vous exécutez la planification pour le type de tâche sélectionné. Cela donne une vue d'ensemble des types de tâches dans chaque groupe de gammes qui utilisent les ressources opérationnelles. Par exemple, dans une situation dans laquelle les ressources de séchage sont des ressources critiques (goulot d'étranglement), ces ressources doivent être spécifiées comme critiques. Les opérations de séchage affectées aux types de tâches de temps d'attente réserveront les ressources de séchage. 

Pour chacun des types de tâches, vous devez déabord l'activer ou le désactiver. Lorsqu'il est désactivé, aucun des autres paramétrages (gestion des tâches, temps de travail et capacité) ne sera pris en compte, car le type de tâche n'est pas actif. 

Parmi les types de tâches, vous trouvez le Chevauchement. Le chevauchement permet de réaliser simultanément différentes tâches. Lorsque les tâches se chevauchent, les ressources peuvent être utilisées mais ne peuvent pas être réservées pour des tâches spécifiques.
Par conséquent, lorsque l'activation est activée pour le chevauchement, le reste des paramètres (gestion des tâches, temps de travail et capacité) n'ont aucun impact sur le groupe de gammes. 

> [!NOTE]
> Lorsque vous mettez des versions à niveau, vous pouvez rencontrer l'erreur suivante : **Une erreur CLR s'est produite lors de l'appel du moteur de planification**. Si vous recevez cette erreur, accédez à la page **Groupes de gammes** et, pour toutes les gammes pour lesquelles vous avez activé le **Chevauchement**, désactivez les options **Gestion des tâches**, **Temps de travail** et **Capacité**. 

## <a name="additional-resources"></a>Ressources supplémentaires

- [Nomenclatures et formules](bill-of-material-bom.md)

- [Catégories de coûts utilisées dans les gammes de production](../cost-management/cost-categories-used-production-routings.md)

- [Capacités de ressources](resource-capabilities.md)

- [Vue d'ensemble de la signature électronique](../../fin-and-ops/organization-administration/electronic-signature-overview.md)



