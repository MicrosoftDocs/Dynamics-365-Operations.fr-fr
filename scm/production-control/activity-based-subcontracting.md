---
title: "Sous-traitance basée sur des activités"
description: "Cette rubrique décrit, en détail, comment utiliser les activités sous-traitées dans un flux de production pour le lean manufacturing."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4cf93c861345ad11b995ac2fe50c9a94dddcbd56
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="activity-based-subcontracting"></a>Sous-traitance basée sur des activités

[!include[banner](../includes/banner.md)]


Cette rubrique décrit, en détail, comment utiliser les activités sous-traitées dans un flux de production pour le lean manufacturing.

Dans Microsoft Dynamics 365 for Operations, il existe deux approches de sous-traitance : les ordres de fabrication et le lean manufacturing. Dans l'approche du lean manufacturing, le travail de sous-traitance est modélisé comme un service associé à une activité de flux de production. Un type spécial de groupe de coûts nommé **Externalisation directe** a été introduit, et les services de sous-traitance ne font plus partie d'une nomenclature. Le contrôle de gestion du travail sous-traité est entièrement intégré dans la solution d'évaluation des coûts pour le lean manufacturing.

## <a name="production-flows-that-involve-subcontractors"></a>Flux de production impliquant des sous-traitants
Le principe de base d'un flux de production ne change pas lorsque les activités sont sous-traitées. Les matières circulent toujours entre des emplacements, les activités de processus convertissent les matières en produits et les activités de transfert déplacent les matières ou les produits d'un emplacement à un autre. Vous pouvez modéliser les emplacements et les cellules de travail de manière à ce qu'ils soient gérés par un fournisseur en affectant le compte fournisseur à un entrepôt ou à une ressource d'un groupe de ressources.  

Sur la base de ces fonctionnalités, le lean manufacturing ne requiert pas de fonctionnalités spécifiques pour prendre en charge le flux de matières et de produits. Tous les scénarios possibles impliquant des fournisseurs comme fournisseurs de services de production ou de transport peuvent être modélisés selon l'architecture du flux de production et des activités.  

Par exemple, un sous-traitant travaille dans un supermarché situé chez le sous-traitant. Lorsque les unités de manutention sont vidées chez le sous-traitant, les cartes kanban sont renvoyées vers la cellule d'assembly avec la prochaine expédition. Le supermarché du sous-traitant est ensuite réapprovisionné. Les transferts vers et depuis le sous-traitant peuvent être modélisés comme des activités de transfert explicites pour prendre en charge un processus de prélèvement et d'expédition. Si un enregistrement explicite n'est pas nécessaire pour prendre en charge le transport physique, les activités de transfert peuvent être omises.  

Un sous-traitant peut être utilisé pour équilibrer la charge de la capacité globale du flux de production. Par exemple, un flux de production est modélisé à l'aide de règles de kanban planifiées. Le planificateur utilise le tableau de planification de kanban pour planifier et équilibrer la charge des deux cellules de travail à la demande. Le planificateur surveille également le programme d'approvisionnement consolidé pour le supermarché dans la page **Programme d'approvisionnement**. Plusieurs sous-traitants peuvent être modélisés dans un ou plusieurs flux de production, et plusieurs règles de kanban peuvent être utilisées pour fournir le même produit au même emplacement via diverses activités. Le planificateur peut convertir des kanbans en une autre règle de kanban afin de replanifier un kanban initialement créé pour la production interne dans un autre processus. En fait, la nature sous-traitée de la cellule de travail n'a aucune incidence sur le flux de production. Le même principe de fonctionnement s'applique pour deux cellules de travail internes parallèles ou pour deux cellules sous-traitées.   

Comme toute autre activité dans un flux de production, les activités sous-traitées peuvent utiliser et fournir des matières et des produits inventoriés, non inventoriés (travail en cours \[WIP\]) et semi-finis. Dans tous les cas, les processus de planification et d'exécution des activités sous-traitées sont identiques. En outre, ils fonctionnent de la même manière que les processus de travail interne.

## <a name="purchase-process-for-subcontracted-activities-services"></a>Processus d'achat pour les activités sous-traitées (services)
Le processus d'achat pour les activités sous-traitées est basé sur le flux de matières physiques qui est enregistré par la progression des tâches de kanban, par exemple, Démarrer ou Terminer. Le flux financier, par exemple, le coût du travail sous-traité, est un flux secondaire qui suit le flux physique. En même temps, le processus d'achat est un processus indépendant qui permet l'ajustement manuel des documents d'achat à chaque étape. Voici le processus d'achat pour les activités sous-traitées :

1.  Créez un contrat d'achat. Le contrat d'achat est créé pour le service et connecté à l'activité du flux de production.
2.  Création d'une commande fournisseur. Une commande fournisseur de lancement peut être créée pour le service, selon les tâches de kanban planifiées. Les tâches pour le même service peuvent être regroupées en lignes de commande fournisseur par jour, semaine ou mois. Les lignes de commande fournisseur peuvent être créées à tout moment après la création des tâches de kanban. Les lignes de commande fournisseur peuvent même être créées après le fait. Cette option est généralement sélectionnée lorsqu'un sous-traitant fournit des services sans notification supplémentaire, en fonction des kanbans ou des cartes kanban reçus par le sous-traitant. Dans ce cas, les écarts entre la commande fournisseur et la facture peuvent être réduits.
3.  Générez des cartes kanban, des matières et des prélèvements à envoyer au sous-traitant pour préparer le traitement. Selon la modélisation détaillée du flux de production, la préparation est effectuée sur le tableau kanban pour les activités de processus à l'aide des prélèvements et de la fonction de préparation. La préparation peut également être effectuée sur le tableau kanban pour les tâches de transfert à l'aide des prélèvements et du démarrage ou de la fin. Pour les matières inventoriées, les deux processus peuvent être pris en charge par un processus de prélèvement WMS et d'expédition. Une feuille de chargement peut être créée à la demande.
4.  Générez des unités de manutention de kanban et des cartes de kanban. Après traitement, les cartes sont renvoyées à partir du sous-traitant. Généralement, les cartes incluent une note de livraison qui spécifie les matières physiques livrées. Une référence aux services fournis n'est pas nécessaire. L'arrivée des matières ou produits chez le client est enregistrée dans le tableau kanban, selon les cartes kanban. (Le tableau kanban pour les activités de processus ou le tableau kanban pour les tâches de transfert est utilisé, selon les activités modélisées).
5.  Créez un avis de réception. L'avis de réception peut être utilisé pour remplacer un document de bon de livraison pour les services reçus. Les avis de réception peuvent être générés en fonction des tâches de kanban terminées pour l'activité de sous-traitance pour une période sélectionnée. Pour chaque réception de tâche, les avis sont créés pour la ligne de commande fournisseur associée. L'avis de réception peut être imprimé et envoyé au sous-traitant comme confirmation de réception.
6.  Générez une facture.

Le processus prend fin lorsque le sous-traitant est facturé pour une période. La facture est mise en correspondance avec les avis de réception créés. Comme les avis de réception représentent la réception physique exacte des matières, le rapprochement à trois facteurs est simplifié.

## <a name="configuring-activities-for-subcontracting"></a>Configuration d'activités pour la sous-traitance
Les sections suivantes décrivent comment configurer des activités pour la sous-traitance.

### <a name="subcontracted-services"></a>Services sous-traités

L'article de paiement utilisé dans la sous-traitance basée sur des activités doit être un produit présentant les propriétés suivantes :

-   **Type de produit :** service
-   **Groupe de modèles de stock :** non stocké

Cette exigence applique l'utilisation du modèle de stock « premier entré/premier sorti » (FIFO). **Remarque :** le calcul du coût des produits requiert que le coût standard du service soit défini. Un contrat d'achat avec le fournisseur est requis. Sinon, le service ne peut pas être utilisé pour la sous-traitance basée sur des activités.

### <a name="subcontracted-process-activities"></a>Activités de processus sous-traitées

Pour configurer une activité de processus comme activité sous-traitée, procédez comme suit.

1.  Configurez une cellule de travail sous-traitée. Pour configurer une cellule de travail comme une cellule sous-traitée, vous devez créer une ressource de type **Fournisseur** et l'associer à la cellule de travail (groupe de ressources). Une catégorie de coûts d'exécution du type de groupe de coûts **Externalisation directe** doit être affectée à la cellule de travail. Les catégories de coûts pour le paramétrage et la quantité ne sont pas requises.
2.  Une fois qu'une activité de processus est créée et associée à une cellule de travail sous-traitée, vous devez configurer un service pour l'activité avant que la version du flux de production puisse être activée. Vous effectuez cette étape dans la page **Détails de** **l'activité**. Pour les activités associées à une cellule de travail sous-traitée, l'organisateur **Conditions de service** est affiché. Dans cet organisateur, ajoutez un service par défaut qui est valide pour tous les articles de sortie. Si des articles de sortie spécifiques nécessitent différents services ou différents paramètres de calcul de service (par exemple, un taux de service différent), vous pouvez ajouter d'autres services à l'activité.

## <a name="subcontracted-transfer-activities"></a>Activités de transfert sous-traitées
Une activité de transfert est configurée comme une activité sous-traitée, selon le paramètre **Transporté par**de l'activité de transfert. Les options suivantes sont disponibles :

-   **Expéditeur** : l'activité est sous-traitée si le transfert à partir de l'entrepôt est géré par un fournisseur (comme défini par une propriété de l'entrepôt). Tous les contrats d'achat sélectionnés pour les services doivent avoir le même ID de fournisseur que l'entrepôt.
-   **Destinataire** : l'activité est sous-traitée si le transfert vers l'entrepôt est géré par un fournisseur (comme défini par une propriété de l'entrepôt). Tous les contrats d'achat sélectionnés pour les services doivent avoir le même ID de fournisseur que l'entrepôt.
-   **Transporteur** : l'activité est sous-traitée à un fournisseur qui fournit le service. Pour être valide, un transporteur doit être créé pour la gestion des entrepôts et un compte fournisseur doit lui être affecté.

Comme pour les activités de processus, vous devez configurer un service par défaut pour les activités de transfert sous-traitées dans l'organisateur **Conditions de service** de la page **Détails de** **l'activité**.

## <a name="service-quantity-calculation"></a>Calcul de la quantité de service
L'ensemble du processus d'achat est basé sur une référence d'article pour un service. Cette référence d'article est mesurée dans l'unité de mesure d'un service. Les services sont généralement mesurés en nombre de services (unités) ou en temps. Pour calculer la quantité de service, selon l'achèvement enregistré des tâches de kanban, vous pouvez utiliser les méthodes suivantes :

-   **Calcul basé sur le nombre de tâches** : une tâche de kanban est égale à *n* unités de service, indépendamment de la quantité de produit fournie. Dans le lean manufacturing, une tâche correspond à une unité de manutention. Ce mode de calcul s'applique à tous les services ayant un prix fixe par unité de manutention. Par conséquent, cette méthode s'applique généralement aux activités de transfert. Toutefois, elle peut également s'appliquer aux activités de processus qui traitent des unités de manutention entières.
-   **Calcul basé sur la quantité de produit** : la quantité de service est basée sur la quantité de produit prévue/fournie. Lorsque la quantité de produit fournie est calculée, des quantités erronées peuvent être incluses ou exclues. Ce mode de calcul s'applique à tous les cas où le prix du service par unité de produit traité est convenu.
-   **Calcul basé sur la durée de l'activité** : les durées d'activité théoriques sont calculées, selon la durée de traitement de l'activité, la quantité totale traitée et le taux de débit du produit traité. Ce mode de calcul s'applique aux services payés à l'heure qui présentent un écart de temps par produit traité.

## <a name="cost-accounting-of-subcontracted-services"></a>Contrôle de gestion des services sous-traités
Lorsque l'avis de réception ou un bon de livraison fournisseur pour une commande fournisseur créée pour un flux de production (autrement dit, une commande fournisseur générée en fonction des tâches de kanban pour les activités sous-traitées) est validé, la valeur de la réception est comptabilisée dans les comptes de travaux en cours du flux de production. Les écarts de factures sont également comptabilisés dans le flux de production. Une catégorie de coûts pour le travail sous-traité a été introduite. Cette catégorie de coûts permet le suivi transparent de la valeur du travail sous-traité qui est affectée aux travaux en cours et utilisée par période.  

La comptabilité à rebours pour le lean manufacturing à la fin d'une période d'évaluation des coûts calcule les écarts réels des produits issus du flux de production pendant la période d'évaluation des coûts.

## <a name="modeling-transfers-as-subcontracted-activities"></a>Modélisation des transferts comme activités sous-traitées
Les gens considèrent souvent le transport comme une activité non productive et sans valeur ajoutée. Toutefois, lorsque le coût de la sous-traitance est comparé au coût de production interne, le coût des activités de transport supplémentaires doit être pris en compte. Un flux de production qui couvre plusieurs emplacements et nécessite des services de transport doit modéliser le coût de transport dans le cadre du coût de fourniture des produits au client. 

La sous-traitance basée sur des activités dans le lean manufacturing permet d'intégrer les transporteurs et les fournisseurs de transport qui déplacent des matières et des produits entre les emplacements d'un flux de production. En modélisant une activité de transfert, vous pouvez affecter un transporteur ou un fournisseur. Les activités ou tâches de transfert sont basées sur un contrat de service et d'achat, et vous pouvez créer des commandes fournisseur et des avis de réception, en fonction des tâches de transfert réelles. Cette fonctionnalité est la même que celle pour les activités de processus sous-traitées.  

Par conséquent, Dynamics 365 for Operations prend désormais en charge le calcul de nomenclature qui inclut les services de transport, la création des commandes fournisseur associées, l'enregistrement intégré des réceptions et l'intégration des coûts du service de transport dans l'évaluation des coûts du flux de production.




