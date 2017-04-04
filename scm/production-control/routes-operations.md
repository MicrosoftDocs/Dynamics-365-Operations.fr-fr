---
title: "Gammes et opérations"
description: "Cette rubrique fournit des informations sur les gammes et les opérations. Une gamme définit le processus de fabrication d&quot;un produit ou une variante de produit. Elle décrit chaque étape (opération) dans le processus de production et l&quot;ordre dans lequel ces étapes doivent être effectuées dans. Pour chaque étape, la gamme définit également les ressources opérationnelles requises, le temps de réglage requis et le temps d&quot;exécution, et la manière dont le coût doit être calculé."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMDesigner, BOMDesignerRouteVersion, Route, RouteInventProd, RouteOpr, RouteOprTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268124
ms.assetid: f78d5836-3e71-42b7-a5d1-41f19228d9d2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 556b9859d0b162b11f0bcbfc6552f6fd9a900596
ms.lasthandoff: 03/31/2017


---

# <a name="routes-and-operations"></a>Gammes et opérations

Cette rubrique fournit des informations sur les gammes et les opérations. Une gamme définit le processus de fabrication d'un produit ou une variante de produit. Elle décrit chaque étape (opération) dans le processus de production et l'ordre dans lequel ces étapes doivent être effectuées dans. Pour chaque étape, la gamme définit également les ressources opérationnelles requises, le temps de réglage requis et le temps d'exécution, et la manière dont le coût doit être calculé.

<a name="overview"></a>Vue d'ensemble
--------

Une gamme décrit l'ordre des opérations nécessaire pour produire un produit ou une variante de produit. Pour chaque opération, la gamme définit également les ressources opérationnelles requises, le temps nécessaire pour paramétrer et exécuter l'opération, et la manière dont le coût doit être calculé. Vous pouvez utiliser la même gamme pour produire les plusieurs produits, ou vous pouvez définir une seule gamme pour chaque produit ou variante de produit. Vous pouvez même avoir des gammes pur le même produit. Dans ce cas, la gamme utilisée varie, en fonction de les facteurs tels que la quantité qui doit être produite. La définition d'une gamme dans Microsoft Dynamics 365 pour les opérations se compose de quatre éléments distincts qui, ensemble, décrivent le processus de production :

-   ** La gamme ** – Une gamme définit la structure du processus de production. Autrement dit, il définit l'ordre des opérations.
-   ** L'opération ** – Une opération identifie une étape nommée dans une gamme, par exemple ** assembly **. La même opération peut se produire dans les gammes plusieurs et peut avoir plusieurs numéros d'opération.
-   ** La relation d'opération ** – Une relation d'opération définit les propriétés opérationnelles d'une opération, telles que le temps de réglage et le temps d'exécution, des catégories de coûts, les paramètres de consommation, et les demandes de ressources. La relation d'opération permet aux propriétés opérationnelles d'une opération pour varier, selon la gamme que l'opération est utilisée ou les produits qui sont produits.
-   ** La version de gamme ** – Une version de gamme définit la gamme utilisée pour produire un produit ou une variante de produit. Les versions de gamme proposer des gammes à réutiliser entre plusieurs produits ou modifiées dans le temps. Elles permettent également les gammes à utiliser pour produire le même produit. Dans ce cas, la gamme utilisée dépend de facteurs tels que l'emplacement ou la quantité qui doivent être produits.

## <a name="routes"></a>Gammes
Une gamme décrit l'ordre des opérations utilisé pour fabriquer un produit ou une variante de produit. Chaque opération est associée à un numéro d'opération et une opération du successeur. L'ordre d'écrans d'opérations un réseau de gammes qui peut être représenté par un graphique dirigé incluant un ou plusieurs points de départ et un point de terminaison particulier. Dans Dynamics 365 pour les opérations, des gammes sont distinguées selon le type de structure. Les deux types de gammes sont les gammes et les réseaux de gammes simples. Dans les paramètres de contrôle de la production, vous pouvez spécifier si seuls des gammes simples peuvent être utilisées, ou si les réseaux de gammes plus complexes peuvent être utilisés.

### <a name="simple-routes"></a>Gammes simples

Une seule gamme est séquentielle, et il n'existe qu'un point de départ pour la gamme.  

[seule gamme![] (. /media/routes-and-operations-1-simple-route.png)](. /media/routes-and-operations-1-simple-route.png)  

Si vous activez uniquement les gammes simples dans les paramètres de contrôle de la production, Dynamics 365 pour les opérations génère automatiquement les numéros d'opération (10, 20, 30, etc.) lorsque vous définissez la gamme.

### <a name="route-networks"></a>Réseaux de gammes

Si vous activez des réseaux de gammes plus complexes dans les paramètres de contrôle de la production, vous pouvez définir des gammes qui ont des points de départ et les plusieurs opérations pouvant être exécutés en parallèle.  

[![Route network](./media/routes-and-operations-2-route-network.png)](./media/routes-and-operations-2-route-network.png)  

**Remarques :**

-   Chaque opération peut avoir qu'une opération du successeur, et la gamme entière doit se terminer en une seule opération.
-   Il n'existe aucune garantir que les plusieurs opérations qui ont la même opération de successeur (par exemple, opérations 30 et 40 dans l'illustration précédente) sont exécutées réellement en parallèle. La disponibilité et la capacité de ressources peuvent mettre des contraintes au chemin que les opérations sont planifiées.
-   Vous ne pouvez pas utiliser 0 (zéro) comme numéro d'opération. Le numéro est réservé et permet d'indiquer que la dernière opération de la gamme n'a aucune opération du successeur.

### <a name="parallel-operations"></a>Opérations parallèles

Parfois, une combinaison des ressources opérationnelles plusieurs qui ont des spécifications différentes sont requises pour l'exécution d'une opération. Par exemple, une opération d'assembly peut exiger d'une machine, d'un outil, et d'un travailleur pour chaque deux machines contrôlent l'opération. Cet exemple peut être modelé à l'aide de opérations parallèles, lorsqu'une opération est désignée comme opération principale et d'autres sont secondaires.  

[gamme![ayant des opérations principales et secondaires] (. /media/routes-and-operations-3-parallel-operations.png)](. /media/routes-and-operations-3-parallel-operations.png)  

Généralement, l'opération principale représente la ressource critique et dicte le temps d'exécution pour les opérations secondaires. Toutefois, lors de la planification qui implique une capacité finie, les ressources pour lequel sont planifiés l'opération principale et les opérations secondaires doit être disponible et que la capacité libre simultanément.  

L'opération principale et les opérations secondaires doivent avoir le même numéro d'opération (30 dans l'illustration précédente).  

Dans l'exemple précédent, la demande de ressources pour l'opération principale (30) est la machine, alors que les demandes de ressources pour les opérations secondaires (30 "et "30 ") sont l " outil et le travailleur. Il s'agit d'une charge de cinquante- pourcentage garantissent que le travailleur prévu peut contrôler deux machines simultanément.

### <a name="approval-of-routes"></a>Approbation des gammes

Une gamme doit être approuvée pour pouvoir être utilisée dans la planification ou le processus de fabrication. L'approbation indique que la conception de gamme est terminée. Le même produit lancé ou variante de produit lancé peut avoir les gammes approuvées multiples. Généralement, l'approbation d'une gamme se produit lorsque la première version de gamme concernée est approuvée. Toutefois, dans certains scénarios métier, l'approbation de la gamme et la version de gamme sont des activités distinctes qui peut impliquer des propriétaires de processus.  

Chaque gamme peut être approuvée ou non approuvée séparément. Toutefois, notez que, lorsqu'une gamme est la désapprobation, toutes les versions de gamme associées sont également non approuvées. Dans les paramètres de contrôle de la production, vous pouvez spécifier si les gammes peuvent être approuvées, et si les gammes approuvées peuvent être modifiées.  

Si vous devez conserver un journal qui les enregistrements qui approuve chaque gamme, vous pouvez demander des signatures électroniques pour l'approbation de gamme. Les utilisateurs doivent ensuite confirmer leur identité à l'aide de l'signature électronique [] (/dynamics365/operations/organization-administration/electronic-signature-overview).

## <a name="operations"></a>Opérations
Une opération est une étape du processus de production. Dans Dynamics 365 pour les opérations, chaque opération a un ID et une description unique. Les exemples courantes de tableau suivant de tables des opérations d'un atelier de construction mécanique.

| Opération  | description ;        |
|------------|--------------------|
| PipeCut    | Couper de tuyau       |
| TIGweld    | Soudage de CHAT        |
| JigAssy    | Assemblage de modèle       |
| Inspection | Inspection de qualité |

Les propriétés opérationnelles de l'opération, telles que le temps de réglage et le temps d'exécution, les demandes de ressources, évaluer les informations de coût, et le calcul de consommation, sont spécifiées dans la relation d'opération. (Pour plus d'informations sur les relations d'opération, voir la section suivante.)

## <a name="operation-relations"></a>Groupes d'opérations
Les propriétés opérationnelles suivantes d'une opération sont conservées sur la relation d'opération :

-   Catégories de coûts
-   Paramètres de consommation
-   Temps de traitement
-   Traitement des quantités
-   Demandes de ressources
-   Notes et instructions

Vous pouvez définir des relations plusieurs d'opération pour la même opération. Toutefois, chaque relation d'opération est spécifique à une opération, et enregistre les propriétés spécifiques à une gamme, à un produit lancé, ou un ensemble de produits lancés associés à un groupe d'articles. Par conséquent, la même opération peut être utilisée dans les gammes plusieurs qui ont différentes propriétés opérationnelles. En outre, vous ne pouvez plus facilement maintenir vos données principales si vous utilisez des opérations standard qui ont les mêmes propriétés opérationnelles, indépendamment de la gamme utilisée et du produit fabriqué. La portée de la relation d'opération est définie via ** code article **, ** relation d'article **, ** code gamme ** et ** relation de gamme ** les propriétés, comme indiqué dans le tableau suivant.

| Article - valide pour | Relation d'article         | Gamme - valide pour | Gamme - numéro ou groupe   | Portée de la relation d'opération                                                                                                                                                                                                                                                                              |
|-----------|-----------------------|------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Enregistrement     | &lt;ID article&gt;       | Gamme      | &lt;ID route&gt; | Les propriétés opérationnelles d'une opération lorsqu'elle l'a utilisé dans l'ID gamme=de gamme où **&lt;numéro de gamme **&gt; produire le produit lancé dans lequel ** numéro d'article ** ID&lt;article=&gt;.                                                                                                                        |
| Enregistrement     | &lt;ID article&gt;       | Tout        |                  | Les propriétés opérationnelles par défaut d'une opération lorsqu'elle survenue le produit lancé dans lequel ** numéro d'article ** ID&lt;article=&gt;. En d'autres termes, ces propriétés opérationnelles s'appliquent lorsqu'il n'y a aucun lien gamme- spécifique d'opération pour le produit lancé.                                     |
| Regrouper     | &lt;Identification du groupe d'article&gt; | Gamme      | &lt;ID route&gt; | Les propriétés opérationnelles d'une opération lorsqu'il a utilisé dans l'ID gamme=de gamme où **&lt;numéro de gamme **&gt; produire les produits lancés associés à l'ID &lt;groupe d'articles&gt;de groupe d'articles, à moins qu'il y a une relation gamme- spécifique d'opération pour le produit lancé.                         |
| Regrouper     | &lt;Identification du groupe d'article&gt; | Tout        |                  | Les propriétés opérationnelles par défaut d'une opération lorsque la survenue les produits lancés associés à l'ID &lt;groupe d'articles&gt;de groupe d'articles, à moins qu'une relation plus spécifique d'opération existe.                                                                                                  |
| Tout       |                       | Gamme      | &lt;ID route&gt; | Les propriétés opérationnelles par défaut de l'opération lorsqu'elle l'a utilisé dans la gamme où ** numéro de gamme ** ID&lt;gamme=&gt;. En d'autres termes, ces propriétés opérationnelles s'appliquent lorsqu'il n'existe aucune relation d'opération pour cette gamme spécifiques au produit lancé ou à son groupe d'articles associé. |
| Tout       |                       | Tout        |                  | Les propriétés opérationnelles par défaut d'une opération. Ces propriétés opérationnelles s'appliquent lorsqu'une relation plus spécifique d'opération n'existe pas.                                                                                                                                                                |

Vous pouvez également spécifier qu'une relation d'opération est spécifique à un site. Ainsi, les propriétés opérationnelles d'une opération peuvent varier, selon l'emplacement (autrement dit, le site) où l'opération. Pour les produits configurés, vous pouvez également spécifier plusieurs propriétés opérationnelles pour chaque configuration de produit.  

Les relations d'opération vous donnent un bon nombre de flexibilité lorsque vous définissez vos gammes. En outre, la capacité de définir les applications d'assistance par défaut de propriétés diminuent le montant de données principales que vous devez maintenir. Toutefois, cette flexibilité signifie également que vous devez tenir compte du contexte que vous modifiez une relation d'opération dans.  

** Remarque : ** Comme les propriétés opérationnelles sont des relations en fonction enregistrées par opération par gamme, toutes les occurrences de la même opération (par exemple, assembly) ont le même temps de réglage, le temps d'exécution, demandes de ressources, et ainsi de suite. Par conséquent, si deux occurrences d'une opération doivent se produire dans la même gamme mais avoir des temps d'exécution, vous devez créer deux opérations distinctes, telles qu'Assembly1 et Assembly2.

### <a name="modifying-product-specific-routes"></a>Modifier les gammes de spécifiques à un produit

Lorsque vous ouvrez ** gamme ** la page ** des détails des produits lancés ** de la page, les versions de gamme associées au produit lancé sélectionné sont affichées. Dans ce contexte, pour chaque opération, Dynamics 365 pour les élements opérations les propriétés opérationnelles de la relation d'opération ce mieux adapté à votre sélection la version de gamme. Vous remarquerez que la liste des opérations inclut ** code article ** et ** code gamme ** les propriétés de la relation d'opération. Par conséquent, vous pouvez déterminer que la relation d'opération s'affiche.  

Sous ** gamme ** la page, vous pouvez modifier les propriétés opérationnelles de l'opération, telles que le temps d'exécution ou les catégories de coûts. Vos modifications sont enregistrées sur la relation d'opération spécifique à la gamme et au produit lancé référencés dans la version de gamme actuelle. Si la relation d'opération qui est affichée n'est pas spécifiques à la gamme et au produit lancé, avant que les modifications soient enregistrées, le système crée une copie de la relation d'opération. Ce détail de *is* de copie à la gamme et au produit lancé. Par conséquent, les modifications n'affecteront pas d'autres gammes ou produits lancés. Pour vérifier que la relation d'opération est modifié dans ** gamme ** la page, examinez ** code article ** et ** le code gamme ** des champs.  

Vous pouvez également créer manuellement une opération spécifique à une gamme et à un produit lancé en utilisant ** copiez et de modifier la relation ** de la fonction.  

** Remarque : ** Si vous ajoutez une opération à une gamme sur ** gamme ** la page, une relation d'opération est créée uniquement pour le produit lancé actuel. Par conséquent, si la gamme est également utilisée pour produire d'autres produits lancés, aucune relation applicable d'opération n'existe pour ces produits lancés, et la gamme ne peut plus être utilisée pour ces produits lancés.

### <a name="maintaining-operation-relations-per-route"></a>Mise à jour des relations d'opération par gamme

Lorsque vous ouvrez ** la gamme détaille ** la page ** des gammes ** de la page de liste, une liste de toutes les relations d'opération qui s'appliquent à la gamme sélectionnée s'affiche. Par conséquent, vous pouvez facilement vérifier qu'il utilise des propriétés opérationnelles pour lesquelles des produits. Vous pouvez modifier les deux valeurs de propriété par défaut et valeurs de propriété de spécifiques à un produit.  

Si vous relation d'ajouter une nouvelle opération dans la gamme ** détaille ** la page, ** code gamme ** le champ est automatiquement défini ** gamme **, et ** relation de gamme ** le champ est défini au numéro de la gamme actuelle.

### <a name="maintaining-operation-relations-per-operation"></a>Mise à jour des relations d'opération par opération

** Les opérations ** de la page, vous pouvez ouvrir ** des relations d'opération ** la page. Dans cette page, vous pouvez modifier toutes les relations pour une opération spécifique. Vous pouvez même modifier les relations d'opération qui contiennent des valeurs par défaut.  

Si votre société utilise des opérations standard, et si les paramètres opérationnels sont les mêmes pour l'ensemble des produits et processus, ** des relations d'opération ** la page inclut une méthode pratique de maintenir les propriétés opérationnelles par défaut de ces opérations.

### <a name="applying-operation-relations"></a>Application des relations d'opération

Dans certains cas, Dynamics 365 pour les opérations doit trouver les propriétés opérationnelles pour une opération. Par exemple, lorsqu'une commande fournisseur est créée, les propriétés opérationnelles de chaque opération qui doivent être copiées des relations d'opération à la gamme de production. Dans ce cas, Dynamics 365 pour les opérations recherche les relations d'opération correspondantes de la combinaison la moins spécifique à la combinaison la moins spécifique.  

Lorsque Dynamics 365 pour les recherches d'opérations de la relation d'opération la plus appropriée pour un produit lancé, une relation d'opération qui correspond à l'ID article du produit lancé est préféré sur une relation d'opération qui correspond à l'ID groupe d'articles. Consécutivement, une relation d'opération qui correspond à l'ID groupe d'articles est conseillée qui dépassent la relation d'opération par défaut. La recherche est effectuée dans l'ordre suivant :

1.  ** Code article **=** table ** et ** relation d'article ** ID&lt;article=&gt;
2.  ** Code article **=** groupe ** et ** relation d'article ** ID&lt;groupe d'article=&gt;
3.  ** Code article **=** tous **
4.  ** Code de gamme **=** gamme ** et ** relation de gamme ** ID&lt;gamme=&gt;
5.  ** Code de gamme **=** tous **
6.  ** Configuration ** ID&lt;de configuration de=&gt;
7.  **Configuration**=
8.  ** Site ** ID site&lt;d'=&gt;
9.  **Site**=

Par conséquent, une opération doit être utilisée qu'une seule fois pour chaque gamme. Si l'opération est effectuée la plusieurs fois dans la même gamme, toutes les occurrences de cette opération ont la même relation d'opération, et vous ne pouvez pas avoir plusieurs propriétés (par exemple, les temps d'exécution) pour chaque occurrence.

## <a name="route-versions"></a>Versions de gamme
Les versions de gamme permettent de tenir compte de variations dans la production des produits ou de mieux contrôler le processus de production. Ils définissent de la gamme doit être utilisé lorsqu'un produit lancé ou une variante spécifique de produit lancé est produit. Vous pouvez utiliser les contraintes suivantes pour indiquer que la gamme est utilisé pour un produit lancé :

-   Dimensions de produit (taille, de couleur, style, ou configuration)
-   Quantité de production
-   Site de production
-   Date de production

Lorsque vous générez le produit à un site, dans une quantité spécifique, ou dans une période donnée, vous pouvez indiquer une version de gamme spécifique comme version de gamme par défaut. Toutefois, notez autorisé qu'une gamme active pour un produit lancé donné et un ensemble donné Contraintes.  

Dans les paramètres de contrôle de la production, vous pouvez exiger que la période de validité d'une version de gamme soit toujours spécifiée.

### <a name="approval-of-route-versions"></a>Approbation des versions de gamme

Avant qu'une version de gamme puisse être utilisée dans la planification ou le processus de fabrication, elle doit être approuvée. Lorsque vous approuvez une version de gamme, vous pouvez également approuver la gamme associée. Toutefois, remarquez qu'une version de gamme peuvent être approuvées que si la gamme associée est également approuvée.

### <a name="activating-the-default-route-version"></a>Activer la version de gamme par défaut

Lorsque vous activez une version de gamme, vous pointez comme version de gamme par défaut que la planification utilise, ou qui sera utilisée pour créer des ordres de fabrication. Vous pouvez avoir qu'une version de gamme active pour un ensemble donné de contraintes (par exemple, la période, le site, ou quantité). Si la version que vous tentez d'activer les conflits avec une version déjà active, vous recevez un message d'erreur. Pour empêcher activation ambiguïté une, vous devez ensuite désactiver la version conflictuels ou modifier les contraintes (généralement la période) de la version de gamme.

### <a name="electronic-signatures"></a>Signatures électroniques

Si vous devez conserver un journal qui enregistre qui approuve et active chaque version de gamme, vous pouvez demander des signatures électroniques pour ces tâches. Les utilisateurs qui approuver et activer des versions de gamme doivent ensuite confirmer leur identité à l'aide de l'signature électronique [] (/dynamics365/operations/organization-administration/electronic-signature-overview).

### <a name="product-change-that-uses-case-management"></a>Modification du produit qui utilise la gestion des incidents

Le cas de modification de produit pour l'approbation et l'activation des gammes et des versions de gamme nouvelles ou modifiées vous donne un moyen aisé de afficher une vue d'ensemble des contraintes de version de gamme. Vous pouvez également approuver et activer toutes les gammes liées à un changement spécifique d'une opération et documenter les résultats dans le produit de modifier l'incident.

## <a name="maintaining-routes"></a>Mise à jour des gammes
Selon vos exigences métier, vous pouvez en réduire le nombre requis afin de maintenir vos définitions de processus.

### <a name="making-routes-independent-of-resources"></a>Faire indépendamment de gammes des ressources

Dans de nombreux système, la ressource opérationnelle ou le groupe de ressources qui doivent effectuer une opération doit être spécifiée dans la gamme. Toutefois, dans Dynamics 365 pour les opérations, vous pouvez définir un ensemble d'exigences auxquelles une ressource opérationnelle doit répondre à appliquer pour l'opération. Par conséquent, la ressource opérationnelle ou le groupe de ressources spécifique qui doivent être utilisés ne doit pas être déterminée jusqu'à ce que l'opération puisse être planifiée en réalité. Cette fonctionnalité est particulièrement utile si vous avez de nombreux travailleurs ou de machines qui peuvent exécuter la même opération.  

Par exemple, vous spécifiez qu'une opération requiert une ressource opérationnelle du ** machine ** type pour lequel l'** emboutissant ** capacité de 20 tonne. Le moteur de planification résoudra ensuite ces besoins à une ressource opérationnelle ou à un groupe de ressources lorsque l'opération est planifiée. Comme vous pouvez donc définir ces qualifications au lieu de lier l'opération à une machine spécifique, vous devez mener plus de flexibilité. En outre, la mise à jour est plus facile lorsque des ressources sont déplacées ou de nouvelles ressources sont ajoutées.  

Pour plus d'informations sur les différents types de demandes de ressources et leur utilisation, voir les demandes de ressources opérationnelles et [capacités de ressource] (resource-capabilities.md).

### <a name="sharing-routes-across-sites"></a>Partage de gammes entre plusieurs sites

Si vous produisez le même produit à plusieurs sites de production, et si les étapes pour la fabrication d'un produit sont identiques à tous les sites, vous pouvez souvent créer une gamme partagée utilisée dans tous les sites de production. Pour créer une gamme partagée, ne spécifiez pas de site de la gamme elle-même. Toutefois, vous devez toujours créer une version de gamme qui associe la gamme partagée avec le produit à chaque site.  

Vous devez également s'assurer que les demandes de ressources pour chaque opération de la gamme n'exigent pas les ressources opérationnelles ou groupes de ressources spécifiques, mais qui sont à la place exprimé en termes de spécifications des ressources requises. Le moteur de planification peut ensuite affecter les ressources opérationnelles pertinentes du site que la production est planifiée en fonction. Par exemple, s'il existe des petites différences dans le temps d'exécution, ou si le temps de réglage pour une certaine opération est spécifique au site, vous pouvez spécifier ces informations en ajoutant une relation supplémentaire d'opération pour ce site.  

Pour bénéficier des avantages des gammes partagées, vous devez également utiliser la consommation de ressources dans la nomenclature correspondante (BOM). Lorsque vous définissez l'indicateur pour la consommation de ressources pour la ligne de nomenclature, l'entrepôt et l'emplacement que des matières premières doivent être consommées duquel est inféré de la ressource opérationnelle que l'opération est planifiée en fonction. Par conséquent, l'entrepôt et l'emplacement ne doivent pas être déterminés tant que la production est planifiée en réalité. De cette manière, vous pouvez faire la nomenclature et indépendamment de gamme de l'emplacement physique laquelle le produit est produit.

### <a name="standard-operation-relations"></a>Relations d'opération standard

Si votre société utilise des opérations standardisées dans la production, et s'il existe un nombre restreint ou non de variation dans le temps de réglage, le temps d'exécution, le calcul de la consommation, le calcul des coûts, etc., vous pouvez tirer bénéfice de créer des relations d'opération par défaut pour toutes les opérations. Dans ce cas, évitez de créer des relations d'opération qui sont spécifiques à toute gamme ou produit lancé.  

Si vous Expriment également les demandes de ressources en termes de qualifications et aptitudes, et consultez les gammes au site indépendantes, vous pouvez permettre de conserver la maintenance de vos processus entreprise au minimum.  

Lorsque vous utilisez cette approche, ** des relations d'opération ** la page devient votre principale destination pour la mise à jour des temps d'exécution et d'autres propriétés.

### <a name="resource-specific-process-times"></a>temps d'exécution Ressource-spécifiques

Si vous ne spécifiez pas de ressource opérationnelle ou un groupe de ressources dans le cadre de les demandes de ressources pour une opération, les ressources applicables peuvent être exécutés à différentes langues. Par conséquent, le temps nécessaire pour traiter une opération peut varier. Pour résoudre ce problème, vous pouvez utiliser ** formule ** le champ sur la relation d'opération pour spécifier la manière dont le temps d'exécution est calculé. Les options suivantes sont disponibles :

-   ** La norme ** – (option par défaut) Le calcul utilise uniquement les champs de la relation d'opération et multiplie le temps d'exécution spécifié par la quantité de la commande.
-   ** La capacité ** – Le calcul comprend ** capacité ** le champ de la ressource opérationnelle. Par conséquent, la durée est ressource- personne à charge. La valeur spécifiée pour la ressource opérationnelle est capacité horaire. Cette valeur est multipliée par la quantité de la commande et ** facteur ** la valeur de la relation d'opération.
-   ** Le lot ** – Une capacité du traitement par lots est calculé à l'aide de les informations de la relation d'opération. Le numéro de lots et, par conséquent, le temps d'exécution peuvent ensuite être calculés selon la quantité de la commande.
-   ** Lot de ressource ** – Cette option est fondamentalement la même que ** lot ** l'option. Toutefois, le calcul comprend ** capacité du traitement par lots ** le champ de la ressource opérationnelle. Par conséquent, la durée est ressource- personne à charge.


<a name="see-also"></a>Voir également :
--------

[Bills of materials and formulas](bill-of-material-bom.md)

[Cost categories used in production routing](../cost-management/cost-categories-used-production-routings.md)

[Resource capabilities](resource-capabilities.md)

[Electronic signature overview](/dynamics365/operations/organization-administration/electronic-signature-overview)


