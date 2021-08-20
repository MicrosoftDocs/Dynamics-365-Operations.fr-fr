---
title: Modélisation d’une organisation au plus juste
description: L’article fournit des informations sur les concepts clés de la modélisation d’une organisation au plus juste.
author: cvocph
ms.date: 09/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, KanbanFlowSelection, KanbanFlow
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53141
ms.assetid: 4f272f2f-ec2c-4b0d-a652-00a63b719b9e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f30496540f6493c68d953af6b3d959acc30efbf1faf72f7cbd6de374c30b9c4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738937"
---
# <a name="modeling-a-lean-organization"></a>Modélisation d’une organisation au plus juste

[!include [banner](../includes/banner.md)]

L’article fournit des informations sur les concepts clés de la modélisation d’une organisation au plus juste. 

Un scénario de lean manufacturing est généralement plus qu’un ensemble de règles de kanban ou de stratégies de fourniture de matériel sans lien entre elles. Le flux de matières et de produits dans les cellules de travail et les emplacements pour un scénario spécifique de production ou d’approvisionnement peut être décrit comme une séquence ou un réseau de taille réduite de processus ou d’activités de transfert. Cette séquence ou ce réseau est appelé un flux de production.

## <a name="production-flows-in-lean-manufacturing"></a>Flux de production dans le cadre du concept de lean manufacturing
Dans les scénarios de production basés sur des ordres de fabrication, les matières sont émises en fonction d’un ordre de fabrication spécifique. Lors d’une séquence d’opérations, basée sur une nomenclature et des gammes, les produits sont créés et finalement reçus à l’emplacement indiqué. Le délai d’exécution des ordres de fabrication varie de quelques minutes à des semaines. Tous les coûts associés, les matières et le travail sont cumulés sur l’ordre de fabrication. 

Pour réduire les délais de livraison et le stock excédentaire entre les centres de travail provoqués par la production par lots, le concept de lean manufacturing introduit les réapprovisionnements de kanban et les supermarchés dans la fabrication et le réapprovisionnement d’entrepôt. En général, ces fonctionnalités perturbent la production des cycles de kanban partiellement indépendants. Le réapprovisionnement d’un kanban pour un produit semi-fini n’est plus déclenché par une commande pour un produit fini. 

Pour rétablir un contexte de production et de coût pour les différents scénarios de kanban proposés, les flux de production basés sur l’activité sont présentés comme l’épine dorsale du lean manufacturing. Toutes les règles de kanban se rapportent à cette structure prédéfinie. Le modèle basé sur les activités prend en charge le paramétrage d’un large éventail de scénarios. Toutefois, ce modèle ne complique pas les choses pour les employés de l’atelier, car tous les scénarios utilisent la même interface utilisateur basée sur les activités.

## <a name="semi-finished-products-non-bom-levels"></a>Produits semi-finis (niveaux autres que la nomenclature)
Lean manufacturing intègre des kanbans pour les produits et les produits semi-finis inventoriés en une structure unique, offrant ainsi une expérience utilisateur unifiée pour tous les incidents. En raison de cette architecture, des niveaux supplémentaires de nomenclature n’ont plus besoin d’être entrés pour permettre d’utiliser des kanbans pour les produits semi-finis. Cette architecture permet également de réduire les mouvements de stock à un minimum.

## <a name="products-and-material-in-work-in-progress"></a>Produits et matières dans les travaux en cours
La réduction des tailles de traitements par lots à l’état idéal d’un flux unifié dans le lean manufacturing peut provoquer une augmentation spectaculaire des mouvements de stock si chaque processus de prélèvement ou enregistrement de kanban déclenche des transactions pour les articles consommés. L’architecture de flux de production permet le transfert des matières vers le flux de production avec des kanbans de prélèvement dans les tailles des unités de manutention de stockage ou de transport. La valeur des matières émises est ajoutée au compte de travaux en cours associé au flux de production. Ce comportement ressemble au comportement des matières émises dans un ordre de fabrication. Le même principe peut être appliqué aux produits et aux produits semi-finis. À moins que ces produits soient créés, transférés, ou consommés dans le cadre d’un flux de production, les mouvements de stock sont facultatifs. Une fois les produits validés en stock, le compte des travaux en cours pour le flux de production est réduit par déduction en fonction du coût standard associé.

## <a name="value-streams-and-value-stream-mapping"></a>Chaînes de valeur et mise en correspondance de chaînes de valeur
L’architecture de Lean manufacturing est inspirée des cinq principes formulés par Womack et Jones : Valeur client, chaîne de valeur, flux, tiré et perfection. Une méthode approuvée pour mettre en œuvre des solutions de lean manufacturing dans le monde physique de la fabrication est la mise en correspondance des chaînes de valeur, concept présenté par Rother et Shook dans leur ouvrage « Learning to See » publié par le Lean Manufacturing Institute. 

La chaîne de valeur de l’état futur peut être modélisée en tant que version de flux de production. Tous les processus de la chaîne de valeur sont modélisés en tant qu’activités de processus. Les mouvements ou les transferts peuvent être modélisés en tant qu’activités de transfert si le statut de transfert doit être enregistré ou si une intégration dans les prélèvements de stock ou les expéditions consolidées est requise. 

La chaîne de valeur elle-même est modélisée en tant qu’unité opérationnelle. Par conséquent, la chaîne de valeur peut être utilisée comme dimension financière.

Pour plus d’informations sur les unités opérationnelles, voir [Créer une unité opérationnelle](../../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md).

## <a name="costing-for-lean-manufacturing-based-on-the-production-flow"></a>Évaluation des coûts du lean manufacturing basée sur le flux de production
La consolidation périodique du coût pour un flux de production corrige le compte des travaux en cours associé et permet la détermination des écarts pour les produits fournis par le flux de production.

## <a name="continuous-improvement"></a>Amélioration continue
Pour mieux prendre en charge l’amélioration continue, les flux de production sont mis en œuvre dans les versions qui permettent un gain de temps. Par conséquent, une version de flux de production existante, ainsi que toutes les règles de kanban associées, peut être copiée dans la prochaine version du flux de production. En outre, le flux de production de l’état futur peut être modélisé avant qu’il soit validé et activé pour la production. Pour garantir un flux des matières cohérent à la date de transition et au-delà, les kanbans existants provenant d’anciennes versions de flux de production sont automatiquement associés à la nouvelle version.

## <a name="simplicity"></a>Simplicité
Pour la mise en œuvre de Lean Manufacturing, nous avons choisi l’approche axée sur le flux de production et l’activité, qui autorise la modélisation de scénarios de production simples et complexes dans une architecture évolutive unique. Un examen plus attentif du concept d’activité révèle une nouvelle simplicité pour les utilisateurs qui en ont vraiment besoin : les collaborateurs de l’atelier et de la logistique. En générant des états en fonction des tâches basées sur l’activité au lieu des mouvements de stock, une interface utilisateur unifiée pour toutes les variantes de lean manufacturing transfère la complexité commerciale de l’interface utilisateur vers sa juste place : le flux de production en tant qu’épine dorsale du lean manufacturing.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]