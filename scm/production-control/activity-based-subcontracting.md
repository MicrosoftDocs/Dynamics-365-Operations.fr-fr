---
title: "sous-traitance Activité-basée"
description: "Cette rubrique décrit, en détail, comment utiliser les activités sous-traitées dans un flux de production pour la production au plus juste."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267034
ms.assetid: 15c76a51-fa6d-42d2-994a-c67df6bae6a9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8e57c53ca894aa44b71e15c1f66bd7c722ea8a81
ms.lasthandoff: 03/31/2017


---

# <a name="activity-based-subcontracting"></a>sous-traitance Activité-basée

Cette rubrique décrit, en détail, comment utiliser les activités sous-traitées dans un flux de production pour la production au plus juste.

Dans Microsoft Dynamics 365 pour les opérations, il existe deux approches pour la sous-traitance : ordres de fabrication et production au plus juste. Dans l'approche de production au plus juste, le travail de sous-traitance est modelé en tant que service associé à une activité de flux de production. Un type spécial de type de groupe de coûts nommé ** à externaliser direct ** a été introduit, et services de sous-traitance ne sont plus une partie d'une nomenclature (BOM). Le contrôle de gestion du travail sous-traité est entièrement intégré dans la solution d'évaluation des coûts de production au plus juste.

## <a name="production-flows-that-involve-subcontractors"></a>Flux de production qui impliquent des sous-traitants
Le principe de base d'un flux de production ne change pas lorsque les activités sont sous-traitées. Les matières est transmise toujours entre emplacements, matériel de convertir des activités de processus à des produits, et les activités de transfert déplacent les matières ou les produits d'un emplacement à l'autre. Vous pouvez modéliser des emplacements et des cellules de travail comme fournisseur- gérées en affectant le compte fournisseur à un entrepôt ou une ressource d'un groupe de ressources.  

En fonction de ces fonctionnalités, production au plus juste ne requiert aucune fonctionnalité spécifique afin de prendre en charge le flux des matières et des produits. Tous les scénarios possibles impliquant des fournisseurs comme fournisseur des services de production ou de transport peuvent être modélisés selon l'architecture du flux de production et des activités.  

Par exemple, un sous-traitant établit d'un supermarché situé au sous-traitant. Lorsque les unités de manutention sont purgées le sous-traitant, les cartes kanban sont retournées dans la cellule d'assembly avec la prochaine expédition. Le supermarché le sous-traitant est ensuite réapprovisionné. Les transferts vers et du sous-traitant peuvent être modélisés comme activités de transfert explicites pour prendre en charge un prélèvement et d'expédition. Si un enregistrement explicite n'est pas obligatoire afin de prendre en charge le transport physique, les activités de transfert peuvent être omises.  

Un sous-traitant peut être utilisé pour équilibrer les charges la capacité générale du flux de production. Par exemple, un flux de production est modelé à l'aide de les règles de kanban planifiées. Le planificateur utilise le tableau de planification de kanban pour planifier et charger de niveau les deux cellules de travail à la demande. Le planificateur surveille également le programme consolidé d'approvisionnement pour le supermarché sur ** programme d'approvisionnement ** la page. Les sous-traitants plusieurs peuvent être modélisés dans un ou flux de production multiples, et il peut y avoir des règles de kanban plusieurs qui peuvent être utilisées pour fournir le même produit au même endroit via diverses activités. Le planificateur peut convertir des kanbans à une autre règle de kanban de replanifier un kanban qui a été créé pour la production interne au processus de remplacement. En fait, la nature sous-traitée de la cellule de travail n'a aucune incidence sur le flux de production. Même principe de travail s'applique pour deux cellules de travail internes parallèles ou pour deux cellules sous-traitées.   

Comme une autre activité dans un flux de production, les activités sous-traitées peuvent consommer et fournir les matières inventorié, non inventorié (travaux en cours\]\[de travaux en cours), et semi-fini et produits. Dans tous les cas, les processus de planification et d'exécuter les activités sous-traitées sont identiques. En outre, ils traitent les mêmes que les processus pour le travail interne.

## <a name="purchase-process-for-subcontracted-activities-services"></a>Processus d'achat pour les activités sous-traitées (services)
Le processus d'achat pour les activités sous-traitées est basée sur les flux des matières physique qui est enregistré par progression d'opération kanban, par exemple, début ou complète. Le flux financier, par exemple, Coût de travail sous-traité, est un flux secondaire qui suit le flux physique. En même temps, le processus d'achat est un processus indépendante qui autorise de l'ajustement manuel des documents d'achat à chaque étape. Voici le processus d'achat pour les activités sous-traitées :

1.  Création d'un contrat d'achat. Le contrat d'achat est créé pour le service et connecté à l'activité de flux de production.
2.  Création d'une commande fournisseur. Une commande fournisseur de lancement peut être créée pour le service, en fonction de les tâches de kanban planifiées. Les tâches pour le même service peuvent être regroupées aux lignes de commande fournisseur par jour, semaine, ou mois. Les lignes de commande fournisseur peuvent être créées à tout moment après les opérations kanban créées. Les lignes de commande fournisseur même peuvent être créées après le fait. Cette option est généralement activée si un sous-traitant fournit des services sans préavis supplémentaire, selon les kanbans ou les cartes kanban que le sous-traitant Réception. Dans ce cas, les écarts entre la commande fournisseur et la facture peuvent être réduits.
3.  Générer des cartes kanban, les matières, et prélèvements à envoyer au sous-traitant pour préparer à traiter. Selon la modélisation détaillée du flux de production, préparations est effectuée sur le tableau kanban pour les activités de processus à l'aide de les prélèvements et de la fonction de préparation. Sinon, la préparation est effectuée sur le tableau kanban pour les tâches de transfert à l'aide de les prélèvements et le démarrage ou l'achèvement. Pour le matériel inventorié, les deux processus peuvent être pris en charge par un processus de WMS-prélèvement et d'expédition. Une feuille de chargement peut être créée sur la demande.
4.  Générer des unités de manutention et les cartes kanban de kanban. Après traitement, les cartes sont retournées du sous-traitant. Généralement, les cartes incluent une note de livraison qui spécifie le matériel physique livrée. Référence aux services livrés n'est nécessaire. L'arrivée du matériel ou de produits au client est enregistrée dans le tableau kanban, selon les cartes kanban. (Tableau kanban pour les activités de processus ou le tableau kanban pour les tâches de transfert est utilisé, en fonction de les activités modelées.).
5.  Créez un advisory de réception. L'advisory de réception peut être utilisé pour remplacer un document de bon de livraison pour les services reçus. Les advisories de réception peuvent être générés selon des tâches terminées pour l'activité de sous-traitance pour une période sélectionnée. Pour chaque réception de tâches, les advisories sont créés pour la ligne de commande fournisseur associée. L'advisory de réception peut être imprimé et envoyé au sous-traitant comme confirmation de réception.
6.  Générez une facture.

Le processus prend fin lorsque le sous-traitant est facturé pour une période. Correspondance de facture est effectuée par rapport à les advisories de réception créés. Comme les advisories de réception représentent la réception physique précise du matériel, le rapprochement à trois facteurs est simplifié.

## <a name="configuring-activities-for-subcontracting"></a>Configuration des activités pour la sous-traitance
Les sections suivantes décrivent comment configurer des activités pour la sous-traitance.

### <a name="subcontracted-services"></a>Les services sous-traités

L'article de paiement utilisé dans la sous-traitance activité- basée doit être un produit disposant des propriétés suivantes :

-   ** Type de produit : ** Service
-   ** Groupe de modèles de stock : ** Non stocké

Ce besoin applique l'utilisation effective du premier entré, premier modèle de stock de (FIFO). ** Remarque : ** La calcul du coût des produits requiert que le coût standard du service défini. Un contrat d'achat avec le fournisseur est requis. Sinon, le service ne peut pas être utilisé pour la sous-traitance activité- basée.

### <a name="subcontracted-process-activities"></a>Activités sous-traitées de processus

Pour configurer une activité de processus comme activité sous-traitée, procédez comme suit.

1.  Configuration d'une cellule de travail sous-traitée. Pour configurer une cellule de travail comme sous-traitée, vous devez créer une ressource de ** fournisseur ** la tapez et associez à la cellule de travail (groupe de ressources). Une catégorie de coûts d'exécution ** à externaliser direct ** du type de groupe de coûts doit être affectée à la cellule de travail. Les catégories de coûts pour le paramétrage et la quantité ne sont pas requises.
2.  Après une activité de processus soit créée et associée à une cellule de travail sous-traitée, vous devez configurer un service pour l'activité avant que la version de flux de production puisse être activée. Vous effectuez cette étape dans ** activité ** ** les détails ** page. Pour les activités associées à une cellule de travail sous-traitée, ** des conditions de service ** l'organisateur est affiché. Cet organisateur, ajoutez un service par défaut qui est valide pour tous les articles de sortie. Si des articles spécifiques de sortie nécessitent différents services ou différents paramètres de calcul de service (par exemple, un taux différent de service), vous pouvez ajouter d'autres services à l'activité.

## <a name="subcontracted-transfer-activities"></a>Activités de transfert sous-traitées
Une activité de transfert est configurée comme activité sous-traitée, selon ** ** transporté par le paramètre de l'activité de transfert. Les options suivantes sont disponibles :

-   ** L'expéditeur ** – L'activité est sous-traité si le transfert à partir de l'entrepôt est géré par un fournisseur (comme défini par une propriété de l'entrepôt). Tous les contrats d'achat sélectionnés pour les services doivent avoir le même ID de fournisseur que l'entrepôt.
-   ** Le destinataire ** – L'activité est sous-traité si le transfert vers l'entrepôt est géré par un fournisseur (comme défini par une propriété de l'entrepôt). Tous les contrats d'achat sélectionnés pour les services doivent avoir le même ID de fournisseur que l'entrepôt.
-   ** Le transporteur ** – L'activité est sous-traité à n'importe quel fournisseur qui offre le service. Pour être valide, un transporteur doit être créé pour la gestion des entrepôts et doit avoir un compte fournisseur affecté.

Comme pour les activités de processus, vous devez configurer un service par défaut pour les activités de transfert sous-traitées sur ** des conditions de service ** l'organisateur ** activité ** ** les détails ** page.

## <a name="service-quantity-calculation"></a>Calcul de la quantité de service
Le processus d'achat entière est basé sur une référence d'article pour un service. Cette référence d'article est mesurée en une unité de mesure d'un service. Les services sont généralement mesurés en le numéro de services (unités) ou à temps. Pour calculer la quantité de service, selon l'achèvement enregistré des opérations kanban, vous pouvez utiliser les méthodes suivantes :

-   ** Le calcul qui est basé sur le nombre de tâches ** – Une opération kanban égale des unités de *n* de service, indépendamment de la quantité de produits livrés. Au production au plus juste, une tâche correspond à une unité de manutention. Ce mode de calcul s'applique à tous les services possédant un prix fixe par unité de manutention. Par conséquent, cette méthode s'applique généralement aux activités de transfert. Toutefois, elle peut également s'appliquer pour traiter les activités qui traitent les unités de manutention entières.
-   ** Le calcul basée sur la quantité de produits ** – La quantité de service est lié à la quantité de produits prévue/livrée. Lorsque la quantité de produits livrée est calculée, des quantités erronées peuvent être incluses ou exclues. Cette méthode de calcul applique à tous les cas où le prix de service par unité de produit traité est convenu.
-   ** Calcul basé sur la durée d'activité ** – Les durées d'activité théoriques sont calculés, selon la période de traitement de l'activité, la quantité traitée total, et le taux de débit du produit traité. Ce mode de calcul s'applique aux services qui sont payés à l'heure et ont un écart dans le temps à partir de chaque produit traité.

## <a name="cost-accounting-of-subcontracted-services"></a>Contrôle de gestion des services sous-traités
Lorsque la réception consultative ou un bon de livraison fournisseur dans une commande fournisseur créée pour un flux de production (autrement dit, une commande fournisseur qui était basée sur des opérations kanban générées pour les activités sous-traitées) est validée, la valeur de la réception est de compte dans les comptes de travaux en cours de le flux de production. Les écarts des factures sont également mis compte au flux de production. Une catégorie de coûts pour le travail sous-traité a été introduite. Cette catégorie de coûts permettent de suivre transparent de la valeur du travail sous-traité affecté aux travaux en cours et consommé par période.  

La comptabilité à rebours pour Lean manufacturing à la fin d'une période d'évaluation des coûts calcule les écarts réels des produits qui sont produits du flux de production pendant la période d'évaluation des coûts.

## <a name="modeling-transfers-as-subcontracted-activities"></a>Modélisation les transferts en tant qu'activités sous-traitées
Les personnes souvent à prendre en compte le transport non productives) et pensent qu'il n'ajoute pas de valeur. Toutefois, lorsque le coût de la sous-traitance est comparé au coût de production interne, le coût des activités supplémentaires de transport doit être considéré. Un flux de production qui couvre plusieurs emplacements et nécessite des services de transport doit modéliser le transport tant que coûts comme faisant partie du coût de fournir des produits au client. 

la sous-traitance Activité- basée dans la structure Production au plus juste permet d'intégrer des transporteurs et transporter les fournisseurs qui déplacent le matériel et les produits entre emplacements d'un flux de production. En utilisez une activité de transfert, vous pouvez affecter un transporteur ou un fournisseur. Les activités de transfert/tâches est basée sur un service et un contrat d'achat, et vous pouvez créer des commandes fournisseur et des advisories de réception, en fonction de les tâches réelles de transfert. Cette fonctionnalité est le même que la fonctionnalité pour les activités sous-traitées de processus.  

Par conséquent, Dynamics 365 pour les opérations prend en charge alors le calcul de nomenclature qui inclut les services de transport, la création des commandes fournisseur liées, enregistrement intégré de réception, et l'intégration du service de transport sur les coûts dans l'évaluation des coûts de flux de production.


