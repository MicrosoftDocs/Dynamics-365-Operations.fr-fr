---
title: Gestion du travail de sous-traitance dans la production
description: "Cette rubrique explique comment les opérations sous-traitées sont gérées dans Microsoft Dynamics 365 pour les opérations. En d&quot;autres termes, elle explique comment les opérations de production qui sont affectées à une ressource sont gérées par un fournisseur."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LeanDocumentServiceCreation, PlanActivity, ProdBOMVendorListPage, ProdRoute, ProdTable, ProdTableListPage, PurchAgreementSubcontractorLookup, RouteTable, WrkCtrResourceGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268174
ms.assetid: fe47c498-4f48-42a2-a0cf-5436c19ab3ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 79430358bebd93fd96f1169d22737d3537dbfc08
ms.lasthandoff: 03/31/2017


---

# <a name="manage-subcontracting-work-in-production"></a>Gestion du travail de sous-traitance dans la production

Cette rubrique explique comment les opérations sous-traitées sont gérées dans Microsoft Dynamics 365 pour les opérations. En d'autres termes, elle explique comment les opérations de production qui sont affectées à une ressource sont gérées par un fournisseur.

Dans [processus de production] (production-process-overview.md), le travail peut être effectué par les ressources qui sont détenues ou administrées par les fournisseurs. Généralement, les ressources fournisseur sont utilisées pour niveler une demande excédentaire périodique qui dépasse la capacité disponible des propres ressources d'une société. Le fournisseur peut également pouvoir proposer au détail [capacités de ressource] (resource-capabilities.md) ou les ressources à un prix inférieur.  

Selon les ressources fournisseur utilisées dans le cadre d'un processus de production, une gamme [] (routes-operations.md) est souvent les besoins logistiques supplémentaires, car le matériel et des produits semi-finis doivent d'abord être transportés au site du fournisseur. Puis le résultat de l'opération sous-traitée doit être transporté l'une à l'emplacement affecté à la prochaine opération ou à un entrepôt de produit fini.  

Lorsque des opérations ou des activités de sous-traitance sont utilisées, elles affectent tous les stades des opérations, la définition des opérations requises la production, l'évaluation des coûts, les prévisions, la planification, et lors de la planification, la gestion de la logistique pour les matières, les produits semi-finis, et du produit fini. Enfin, les ressources nécessitent leurs propres processus pour la comptabilité et le contrôle des coûts.  

Pour les ressources internes, un taux de coût fixe est généralement affecté pour une période. En revanche, le coût des ressources sous-traitées est basée sur le prix d'achat du service associé. Le service est défini comme une autre produit, est utilisé pour piloter l'approvisionnement et d'achat de processus pour une opération sous-traitée donnée.  

Actuellement, il n'existe aucun concept explicite des produits semi-finis dans Microsoft Dynamics 365 pour les opérations. Pour un ordre de fabrication qu'une ou de plusieurs opérations afin de transformer des matières premières dans un produit fini, le produit fini est validé en stock uniquement dans la dernière opération. Les produits semi-finis que le produit premier d'opérations sont comptabilisé dans les travaux en cours (WIP), mais elles ne sont pas validés ou ne sont pas suivis dans le stock. Même si vous pouvez diviser les gammes et les nomenclatures (BOMs) en plus petites multiples, augmentations de cette approche le nombre de produits, nomenclatures, et gammes à gérer.  

Il existe deux méthodes pour modéliser le travail de sous-traitance pour les opérations de production. Ces méthodes diffèrent de sens que le processus de sous-traitance peut être modelé, la manière dont les produits semi-finis sont représenté en cours, et la manière à ce que le contrôle des coûts est géré.

-   Sous-traitance des opérations de gamme dans les ordres de fabrication ou les lots de commandes
    -   Le produit de service doit être un produit stocké, et ce doit faire partie de la nomenclature.
    -   Cette la méthode prend en charge premier entré, premier (FIFO) ou coût standard.
    -   Les produits semi-finis sont représentés par le produit de service en cours.
    -   Le contrôle des coûts affecte les coûts associés au travail sous-traité aux coûts du matériel.
-   Sous-traitance des activités de flux de production dans un flux de production au plus juste
    -   Le service est un article non stocké de service, et ce n'est pas partie de la nomenclature.
    -   Cette méthode utilise des contrats d'achat comme accords de service.
    -   Cette méthode utilise la comptabilité à rebours.
    -   Cette méthode est ainsi possible de l'approvisionnement associée et asynchrone. (L'flux des matières est indépendant du processus d'approvisionnement.)
    -   Le contrôle des coûts répartit le travail sous-traité dans son propre bloc d'analyse des coûts.

## <a name="subcontracting-of-route-operations"></a>Sous-traitance des opérations de gamme
Pour utiliser la sous-traitance des opérations de gamme pour la production ou les lots de commandes, le produit de service qui est utilisé pour l'approvisionnement du service doit être défini comme produit ** ** service de type. En outre, il doit avoir un groupe de modèles d'article qui a ** produit stocké ** Option le défini sous ** stratégie de stock ** ** Oui **. Cette option définit si un produit est comptabilisé tant que stock sur l'accusé de réception de marchandises (** produit stocké ** = ** Oui **), ou si le produit sur Internal un compte de résultat (** produit stocké ** = ** aucun **). Bien que ce comportement peut apparaître conflictuels, il a selon le fait que seuls les produits dont cette stratégie créer les mouvements de stock qui peuvent être utilisés dans le contrôle des coûts pour calculer le coût planifié et pour déterminer le coût réel lorsqu'un ordre de fabrication est terminé.  

Pour être pris en compte dans la planification et le calcul des coûts, le service doit être ajouté à la nomenclature. La ligne de nomenclature doit être de ** fournisseur ** type, et il doit affecter à l'opération de gamme que le service est réparti sur. Cette opération de gamme doit avoir une ressource d'évaluation des coûts et demande de ressources qui indiquent une ressource de ** fournisseur ** tapez reliant les opérations et le service associé au compte fournisseur correspondant.  

Lorsque cette configuration est utilisée, une commande fournisseur est créée pour le produit associé de service, selon estimation d'un ordre de fabrication. La commande fournisseur du service est utilisée comme point d'associer des opérations sous-traitées. Le travail sous-traité peut être géré via ** travail sous-traité ** la page de liste dans Contrôle de la production. Le travail sous-traité est utilisé à la matière première d'expédition et, éventuellement, à un produit semi-fini au fournisseur {{en:in_preparation_for}} {{vue:in_preparation_for}} de l'opération. Il permet également de recevoir le produit résultant de l'opération sous-traitée dans l'arrivée d'articles, où le produit de service est utilisé pour identifier l'arrivée de produit semi-fini. Lorsque la ligne de commande fournisseur, l'opération de production est mise à jour comme terminée.  

Un ordre de fabrication peut avoir plusieurs opérations, et chaque opération peut être affectée à un autre fournisseur. Par conséquent, un ordre de fabrication de bout en bout peut engendrer des commandes fournisseur.

## <a name="subcontracting-of-production-flow-activities"></a>Sous-traitance des activités de flux de production
[Production au plus juste] () lean-manufacturing-overview.md la solution modèle le travail de sous-traitance en tant que service associé à une activité d'une [flux de production] (http://ax.help.dynamics.com/en/wiki/create-a-production-flow-version/) (rubrique du Guide de tâche). Par conséquent, ce type de sous-traitance est également conditionné par [sous-traitance activité- basée.] (activity-based-subcontracting.md) Type spécial de groupe de coûts, ** à externaliser direct **, a été introduit, et services de sous-traitance ne font pas partie de la nomenclature du produit fini. Lorsque vous utilisez le production au plus juste, toutes les activités sont définies par des kanbans qui peuvent être liés à un ou des activités de flux de production multiples. Arrondi ici, cette explication ressemble juste de présente une explication des ordres de fabrication. Toutefois, alors que les ordres de fabrication doivent toujours se terminer par un produit fini, vous pouvez créer des kanbans pour fournir un produit semi-fini. Vous ne devez pas entrer un nouveau produit et niveau de nomenclature.  

Comme les règles de kanban peuvent être très dynamiques, vous pouvez modéliser des variantes d'approvisionnement pour le même produit dans un flux de production. Lorsque vous utilisez la sous-traitance plus juste, les flux des matières et le flux financier sont strictement séparés. Tous les flux des matières est représenté par les activités de kanban. Les commandes fournisseur pour les produits de service et les validations de réception de ces services peuvent être automatiques, selon le statut des opérations kanban dans le flux de production. Les opérations kanban peuvent être démarrées et complétées même avant que les commandes fournisseur sont créées. Les documents de sous-traitance (commande fournisseur et réception de l'achat du service) peuvent être regroupés par période et service. Par conséquent, le nombre de documents et des lignes d'achat peut être tenue petit, même dans les opérations très répétitives laquelle les fournisseurs fournissent des services sous-traités dans un flux de tiers une pièce.

### <a name="modeling-subcontracting-in-a-production-flow"></a>Modélisation de la sous-traitance dans un flux de production

Dans a [flux de production au plus juste] (lean-manufacturing-modeling-lean-organization.md), une activité de processus peut être définie comme sous-traité lorsqu'elle a affecté à une cellule de travail (groupe de ressources) ayant une ressource unique en fournisseur. Lorsqu'une cellule de travail est sous-traitée, les activités associées de processus doivent être liées à une ligne de contrat d'achat active qui contient l'article de service et le prix du service. L'accord de service de l'activité définit également le taux de calcul à la quantité de produits de l'opération kanban de la quantité qui en résulte de service. Vous pouvez sélectionner si la quantité de service est calculée en fonction de le nombre de tâches, la bonne quantité de produit qui est spécifiée sur les tâches, ou la quantité de produit total (la quantité totale inclut les produits mis).  

Les activités de transfert peuvent également être définies comme sous-traitées. Cette définition se produit implicitement lorsque vous sélectionnez la partie responsable de l'expédition dans l'activité de transfert. Lorsque vous sélectionnez ** expéditeur ** ou ** destinataire **, si l'entrepôt correspondant de source ou de cible est un entrepôt fournisseur- géré, l'activité est considéré sous-traité. Lorsque vous sélectionnez ** transporteur **, l'activité est toujours sous-traitée. Les activités sous-traitées similaires de processus, une activité de transfert sous-traitée doivent être liées à un accord de service avant que le flux de production puisse être activé.

### <a name="backflush-costing"></a>Calcul des coûts de post-consommation

Le contrôle de gestion du travail sous-traité est complètement intégré dans l'évaluation des coûts pour la solution de production au plus juste (comptabilité à rebours). Lorsque la réception de commande fournisseur du service est validée, ou lorsque la facturation cas, le coût du service est affecté au flux de production. Pour la comptabilité à rebours, l'écart des services sous-traités est calculé en compensant le bloc de sous-traitance du coût standard des produits reçus avec les quantités reçues et facturées réelles de service.

## <a name="material-supply-for-subcontracted-operations"></a>Approvisionnement matériel pour les opérations sous-traitées
Les produits semi-finis et les documents associés doivent être transférés vers l'emplacement de début du travail est effectué physiquement. Lorsque vous utilisez des opérations et des activités sous-traitées, ce transfert est souvent lié au transport supplémentaire à un site fournisseur- opéré. Lors de l'affectation les matières dans la nomenclature à l'opération sous-traitée, vous déclarez que la matière doit être présentée à l'emplacement d'entrée du groupe de ressources pour la ressource affectée. La planification ou le réapprovisionnement au plus juste met le matériel en service à cet emplacement.  

Pour modéliser le stock situé sur le site du fournisseur, il est une pratique dans le secteur de définir un entrepôt fournisseur- géré. Vous pouvez facilement définir un entrepôt fournisseur-géré en créant un nouvel entrepôt et en affectant le compte fournisseur. Pour documenter que la matière doit être transféré au fournisseur avant qu'une opération puisse être exécutée, vous devez affecter l'entrepôt fournisseur- géré vers l'entrepôt d'entrée du groupe de ressources qui tient la ressource.  

Pour réapprovisionner le matériel à cet entrepôt, vous pouvez utiliser des stratégies plusieurs :

-   Ordres de transfert
-   Transférer les journaux
-   Kanbans de prélèvement
-   Livraison directe l'achat à l'emplacement fournisseur

Les produits semi-finis sont des exceptions à cette règle. Pour transférer des produits semi-finis, vous êtes limité à ces options :

-   Pour la production et les lots de commandes, des produits semi-finis ne peuvent être transférés logiquement via le journal des prélèvements ** travail sous-traité ** de la page de liste. Ce journal crée un document de note de livraison qui permet de transférer semi-fini et la matière première au fournisseur.
-   Pour les opérations sous-traitées dans les flux de production, le transfert des produits semi-finis est documenté par la réception des kanbans de prélèvement ou de production à l'emplacement fournisseur. Pour modéliser une activité de transfert explicite, vous pouvez terminer un kanban de production avec une activité de transfert supplémentaire.

** Remarque : ** Une gamme de production pour un ordre de fabrication unique ne peut pas effectuer plusieurs sites. Cette règle s'applique également au travail sous-traité. Par conséquent, les entrepôts et les emplacements matériels fournisseur- gérés doivent être définis dans le même site que les ressources internes utilisées dans la gamme. Bien que les flux de production puissent effectuer des sites, ils ne peuvent pas transporter des produits semi-finis d'un site vers une autre, car cette opération implique une modification de contexte de coût.  

Généralement, l'entrepôt de sortie et l'emplacement d'un groupe de ressources sous-traité directement sont répartis dans l'entrepôt et l'emplacement de l'étape suivante de l'opération dans la gamme ou le flux de production. Cela vous aide paramétrées diminuent le montant de la déclaration de la tâche qui se produit ou opérations supplémentaires de transfert de numéros qui doivent être modelées.


