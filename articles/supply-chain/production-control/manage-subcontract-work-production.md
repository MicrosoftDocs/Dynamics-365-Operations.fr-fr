---
title: Gestion du travail de sous-traitance en production
description: Cette rubrique explique comment les opérations sous-traitées sont gérées dans Dynamics 365 Supply Chain Management. En d'autres termes, elle explique comment les opérations de production qui sont affectées à une ressource sont gérées par un fournisseur.
author: cvocph
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanDocumentServiceCreation, PlanActivity, ProdBOMVendorListPage, ProdRoute, ProdTable, ProdTableListPage, PurchAgreementSubcontractorLookup, RouteTable, WrkCtrResourceGroup, ProdBOMVendorListPagePreviewPane, ProdBOMVendor
audience: Application User
ms.reviewer: kamaybac
ms.custom: 268174
ms.assetid: fe47c498-4f48-42a2-a0cf-5436c19ab3ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e71fc643b519273e1b3c15b7037c1ec11d4d7192
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007014"
---
# <a name="manage-subcontracting-work-in-production"></a>Gestion du travail de sous-traitance en production

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment les opérations sous-traitées sont gérées dans Dynamics 365 Supply Chain Management. En d'autres termes, elle explique comment les opérations de production qui sont affectées à une ressource sont gérées par un fournisseur.

Dans [processus de production](production-process-overview.md), le travail peut être effectué par les ressources qui sont détenues ou administrées par les fournisseurs. Généralement, les ressources fournisseur sont utilisées pour niveler une demande excédentaire périodique qui dépasse la capacité disponible des propres ressources d'une société. Le fournisseur peut également pouvoir faire une offre de [capacités de ressource](resource-capabilities.md) ou de ressources spécifiques à un prix inférieur.  

En fonction des ressources fournisseur utilisées dans le cadre d'un processus de production, une [gamme](routes-operations.md) offre souvent des besoins logistiques supplémentaires, car le matériel et les produits semi-finis doivent d'abord être transportés vers le site du fournisseur. Puis le résultat de l'opération sous-traitée doit être transporté soit vers l'emplacement affecté à la prochaine opération ou vers un entrepôt de produits finis.  

Lorsque des opérations ou des activités de sous-traitance sont utilisées, elles affectent tous les stades des opérations, la définition des opérations requises pour la production, l'évaluation des coûts, les prévisions, la planification, et lors de la planification, la gestion de la logistique pour les matières, les produits semi-finis et les produits finis. Enfin, les ressources nécessitent leurs propres processus pour la comptabilité et le contrôle des coûts.  

Pour les ressources internes, un taux de coût fixe est généralement affecté pour une période. En revanche, le coût des ressources sous-traitées est basée sur le prix d'achat du service associé. Le service est défini comme une autre produit, et est utilisé pour piloter les processus d'approvisionnement et d'achat pour une opération sous-traitée donnée.  

Actuellement, il n'existe aucun concept explicite des produits semi-finis dans Supply Chain Management. Pour un ordre de fabrication qui requiert une ou plusieurs opérations afin de transformer des matières premières en un produit fini, le produit fini est validé en stock uniquement dans la dernière opération. Les produits semi-finis que les opérations antérieures produisent sont comptabilisés dans les travaux en cours, mais ils ne sont ni affichés ni enregistrés. Même si vous pouvez diviser les gammes et les nomenclatures en plusieurs unités plus petites, cette approche augmente le nombre de produits, de nomenclatures et de gammes qui doivent être gérés.  

Il existe deux méthodes pour modéliser le travail de sous-traitance pour les opérations de production. Ces méthodes diffèrent en ce sens où le processus de sous-traitance peut être modélisé, la manière dont les produits semi-finis sont représentés dans le processus, et la manière à laquelle le contrôle des coûts est géré.

-   Sous-traitance des opérations de gamme dans les ordres de fabrication ou les lots de commandes
    -   Le produit de service doit être un produit stocké, et doit faire partie de la nomenclature.
    -   Cette méthode prend en charge le premier entré, le premier sorti ou le coût standard.
    -   Les produits semi-finis sont représentés par le produit de service dans le processus.
    -   Le contrôle des coûts attribue les coûts associés au travail sous-traité aux coûts matériels.
-   Sous-traitance des activités de flux de production dans un flux de production au plus juste
    -   Le service est un produit de service non-stocké, et ne fait pas partie de la nomenclature.
    -   Cette méthode utilise des contrats d'achat comme accords de service.
    -   Cette méthode utilise la comptabilité à rebours.
    -   Cette méthode permet une acquisition agrégée et asynchrone. (Le flux des matières est indépendant du processus d'approvisionnement).
    -   Le contrôle des coûts répartit le travail sous-traité dans son propre bloc d'analyse des coûts.

## <a name="subcontracting-of-route-operations"></a>Sous-traitance des opérations de gamme
Pour utiliser la sous-traitance des opérations de gamme pour les ordres de fabrication ou les commandes par lots, le produit de service utilisé pour l'acquisition du service doit être défini comme un produit du type **Service**. En outre, il doit avoir un groupe de modèles d'éléments qui a l'option **Produit stocké** sous **Stratégie de stock** définie sur **Oui**. Cette option définit si un produit est comptabilisé en tant que stock sur l'accusé de réception de marchandises (**produit stocké** = **Oui**), ou si le produit est passé en charges sur un compte de profits et pertes (**Produit stocké** = **Non**). Bien que ce comportement puisse sembler contradictoire, il est basé sur le fait que seuls les produits qui ont cette stratégie créeront des transactions de stock qui peuvent être utilisées dans le contrôle des coûts pour calculer le coût planifié et déterminer le coût réel lorsqu'un ordre de fabrication est terminé.  

Pour être pris en compte dans la planification et le calcul des coûts, le service doit être ajouté à la nomenclature. La ligne de nomenclature doit être du type **Vendor** et doit être affectée à l'opération de gamme à laquelle le service est affecté. Cette opération de gamme doit avoir une ressource d'évaluation des coûts et une demande de ressources qui indiquent une ressource de **fournisseur** qui relie l'opération et le service associé au compte fournisseur correspondant.  

Lorsque cette configuration est utilisée, une commande fournisseur est créée pour le produit de service associé, en fonction de l'estimation d'un ordre de fabrication. La commande fournisseur du service est utilisée comme ancrage des opérations sous-traitées. Le travail sous-traité peut être géré via la page de liste **Travail sous-traité** dans Contrôle de la production. Le travail sous-traité est utilisé pour expédier des matières premières et éventuellement un produit semi-fini au fournisseur en prévision de l'opération. Il est également utilisé pour recevoir le produit résultant de l'opération sous-traitée lors de l'arrivée de l'article, où le produit de service est utilisé pour identifier l'arrivée du produit semi-fini. À la réception de l'ordre de fabrication, l'opération de production est mise à jour comme terminée.  

Un ordre de fabrication peut avoir plusieurs opérations, et chaque opération peut être affectée à un autre fournisseur. Par conséquent, un ordre de fabrication de bout en bout peut engendrer des commandes fournisseur.

## <a name="subcontracting-of-production-flow-activities"></a>Sous-traitance des activités de flux de production
La solution [lean manufacturing](lean-manufacturing-overview.md) modélise le travail de sous-traitance comme un service associé à une activité de [flux de production](tasks/create-production-flow-version.md) (rubrique du Guide de tâche). Par conséquent, ce type de sous-traitance est également appelé [Sous-traitance basée sur des activités.](activity-based-subcontracting.md) Un type spécial de groupe de coûts nommé **Externalisation directe** a été introduit, et les services de sous-traitance ne font plus partie d'une nomenclature de biens finis. Lorsque vous utilisez le production au plus juste, toutes les activités sont définies par des kanbans qui peuvent être liés à une ou plusieurs activités de flux de production. Jusqu'à présent, cette explication ressemble à une explication des ordres de fabrication. Toutefois, alors que les ordres de fabrication doivent toujours se terminer par un produit fini, vous pouvez créer des kanbans pour fournir un produit semi-fini. Vous n'avez pas besoin d'entrer un nouveau produit ni un niveau de nomenclature.  

Comme les règles de kanban peuvent être très dynamiques, vous pouvez modéliser des variantes d'approvisionnement pour le même produit dans un flux de production. Lorsque vous utilisez la sous-traitance au plus juste, les flux des matières et le flux financier sont strictement séparés. Tous les flux de matières sont représentés par les activités de kanban. Les commandes fournisseur pour les produits de service et les validations de réception de ces services peuvent être automatiques, selon le statut des opérations kanban dans le flux de production. Les opérations kanban peuvent être démarrées et terminées avant la création des commandes fournisseur. Les documents de sous-traitance (commande fournisseur et réception de l'achat du service) peuvent être regroupés par période et service. Par conséquent, le nombre de documents et de lignes d'achat peut être petit, même dans les opérations très répétitives où les fournisseurs fournissent des services sous-traités dans un seul flux.

### <a name="modeling-subcontracting-in-a-production-flow"></a>Modélisation de la sous-traitance dans un flux de production

Dans un [flux de production au plus juste](lean-manufacturing-modeling-lean-organization.md), une activité de processus peut être définie comme sous-traitée lorsqu'elle est affectée à une cellule de travail (groupe de ressources) ayant une ressource unique en fournisseur. Lorsqu'une cellule de travail est sous-traitée, les activités de processus associées doivent être liées à une ligne de contrat d'achat active qui contient l'article de service et le prix du service. L'accord de service de l'activité définit également le taux de calcul entre la quantité de produits de la tâche de kanban et la quantité de service qui en résulte. Vous pouvez sélectionner si la quantité de service est calculée en fonction du nombre de tâches, la bonne quantité de produits qui est spécifiée sur les tâches, ou la quantité totale de produits (la quantité totale inclut les produits défectueux).  

Les activités de transfert peuvent également être définies comme sous-traitées. Cette définition se produit implicitement lorsque vous sélectionnez la partie responsable de l'expédition dans l'activité de transfert. Lorsque vous sélectionnez **Expéditeur** ou **Destinataire**, si l'entrepôt source ou cible correspondant est un entrepôt géré par un fournisseur, l'activité est considérée comme étant sous-traitée. Lorsque vous sélectionnez **Transporteur**, l'activité est toujours sous-traitée. Comme les activités de processus sous-traitées similaires, une activité de transfert sous-traitée doit être liée à un accord de service avant que le flux de production puisse être activé.

### <a name="backflush-costing"></a>Calcul des coûts de post-consommation

Le contrôle de gestion du travail sous-traité est entièrement intégré dans la solution d'évaluation des coûts pour la solution de lean manufacturing (comptabilité à rebours). Lorsque la réception de commande fournisseur du service est validée, ou lorsque la facturation se produit, le coût du service est affecté au flux de production. Pour la comptabilité à rebours, l'écart des services sous-traités est calculé en compensant le bloc de sous-traitance du coût standard des produits reçus avec les quantités de service réellement reçues et facturées.

## <a name="material-supply-for-subcontracted-operations"></a>Approvisionnement matériel pour les opérations sous-traitées
Les produits semi-finis et les matières associés doivent être transférés vers l'emplacement où le travail est effectué physiquement. Lorsque vous utilisez des opérations et des activités sous-traitées, ce transfert est souvent lié au transport supplémentaire vers un site fournisseur. En allouant du matériel dans la nomenclature à l'opération sous-traitée, vous déclarez que le matériel doit être ajouté à l'emplacement d'entrée du groupe de ressources pour la ressource allouée. La planification ou le réapprovisionnement au plus juste met le matériel en service à cet emplacement.  

Pour modéliser le stock situé sur le site du fournisseur, la meilleure pratique du secteur consiste à définir un entrepôt géré par le fournisseur. Vous pouvez facilement définir un entrepôt géré par le fournisseur en créant un nouvel entrepôt et en affectant le compte fournisseur. Pour documenter que la matière doit être transférée au fournisseur avant qu'une opération puisse être exécutée, vous devez affecter l'entrepôt géré par le fournisseur vers l'entrepôt d'entrée du groupe de ressources qui renferme la ressource.  

Pour réapprovisionner le matériel dans cet entrepôt, vous pouvez utiliser plusieurs stratégies :

-   Ordres de transfert
-   Transférer les journaux
-   Kanbans de prélèvement
-   Achat direct à l'emplacement du fournisseur

Les produits semi-finis sont des exceptions à cette règle. Pour transférer des produits semi-finis, vous êtes limité à ces options :

-   Pour les ordres de fabrication et les traitements par lots, les produits semi-finis ne peuvent être transférés que par voie logique en utilisant le journal de prélèvement à partir de la page **Travail sous-traité**. Ce journal crée un document de note de livraison qui permet de transférer la matière semi-finie et la matière première au fournisseur.
-   Pour les opérations sous-traitées dans les flux de production, le transfert des produits semi-finis est documenté par la réception des kanbans de prélèvement ou de production à l'emplacement fournisseur. Pour modéliser une activité de transfert explicite, vous pouvez terminer un kanban de production avec une activité de transfert supplémentaire.

**Remarque :** Une gamme de production pour un ordre de fabrication unique ne peut pas concerner plusieurs sites. Cette règle s'applique également au travail sous-traité. Par conséquent, les entrepôts et les emplacements de matériels gérés par le fournisseur doivent être définis sur le même site que les ressources internes utilisées dans la gamme. Bien que les flux de production puissent concerner plusieurs sites, ils ne peuvent pas transporter des produits semi-finis d'un site vers un autre, car cette opération implique une modification de contexte de coût.  

Généralement, l'entrepôt de sortie et l'emplacement d'un groupe de ressources sous-traité directement sont répartis dans l'entrepôt et l'emplacement de l'étape suivante de l'opération dans la gamme ou le flux de production. Cette configuration permet de réduire la quantité de rapports de travail qui se produit ou le nombre d'opérations de transfert supplémentaires qui doivent être modélisées.



