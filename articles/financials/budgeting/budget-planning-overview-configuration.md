---
title: Vue d'ensemble de la planification de budget
description: "Cet article présente la planification budgétaire et contient des informations qui vous aident à configurer la planification budgétaire et à paramétrer ses processus."
author: twheeloc
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 17251
ms.assetid: a2e06633-a800-4840-a962-88fed8462104
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: e874d7353e0d9561ca55f313bfb5209299298169
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="budget-planning-overview"></a>Vue d'ensemble de la planification de budget

[!include[banner](../includes/banner.md)]


Cet article présente la planification budgétaire et contient des informations qui vous aident à configurer la planification budgétaire et à paramétrer ses processus.

<a name="overview-of-budget-planning"></a>Vue d'ensemble de la planification budgétaire
---------------------------

Vous procédez à la planification budgétaire lorsque vous préparez les budgets qui seront implémentés par une organisation. Une organisation peut configurer la planification budgétaire, puis paramétrer les processus afférents pour répondre à ses stratégies, procédures et exigences en matière de préparation du budget. 

Lorsque vous comprenez les concepts et la terminologie utilisés dans Microsoft Dynamics 365 for Finance and Operations, vous avez plus de facilité à implémenter la planification budgétaire dans votre organisation.

### <a name="key-terms"></a>Termes clés

-   **Processus de planification budgétaire** : Les processus de planification budgétaire déterminent la manière dont les plans budgétaires peuvent être mis à jour, acheminés, révisés, puis approuvés dans la hiérarchie d'organisation de budgétisation. Un processus de planification budgétaire est lié à un cycle budgétaire et à une organisation via une entité juridique.
-   **Plans budgétaires** : Les plans budgétaires contiennent les données budgétaires pour un cycle budgétaire. Vous pouvez avoir plusieurs plans budgétaires utilisés pour différents objectifs. Par exemple, les plans budgétaires permettent de créer des montants budgétaires pour différentes unités d'organisation ou d'effectuer des comparaisons et prendre des décisions informées.
-   **Scénarios de plan budgétaire** : Les scénarios de plan budgétaire définissent les catégories de données pour les plans budgétaires. Vous définissez des scénarios de plan budgétaire pour prendre en charge des classes monétaires et d'autres classes d'unités de mesure, telles que la quantité. L'année précédente du département et les demandes du département sont des exemples de scénarios de plan budgétaire monétaires. Les appels passés au support de l'année précédente et le comptage équivalent temps plein (ETP) sont des exemples de scénarios de plan budgétaire qui utilisent des quantités.
-   **Stades de planification budgétaire** : Les stades de planification budgétaire définissent les étapes qu'un plan budgétaire suit de son origine à l'approbation finale. Les stades de planification budgétaire sont organisés dans des workflows de planification budgétaire.
-   **Workflows de planification budgétaire** : Les workflows de planification budgétaire sont composés et définissent les phases de planification budgétaire. Les workflows de planification budgétaire sont associés à des workflows de budgétisation. Les workflows de budgétisation sont des processus automatisés et manuels qui font passer les plans budgétaires dans les différents stades de la planification budgétaire.

[![Terminologie relative à la planification budgétaire](./media/budgetplanning-terms-1024x504.png)](./media/budgetplanning-terms.png)

### <a name="common-tasks"></a>Tâches communes

Vous pouvez utiliser la planification budgétaire pour réaliser les tâches suivantes :

-   Créer des plans budgétaires pour définir les produits et dépenses prévus pour un cycle budgétaire.
-   Analyser et mettre à jour des plans budgétaires pour plusieurs scénarios.
-   Transmettre automatiquement les plans budgétaires, ainsi que les feuilles de calcul, les justificatifs et autres pièces jointes pour qu'ils soient révisés et approuvés.
-   Consolider plusieurs plans budgétaires situés à un niveau inférieur dans l'organisation dans un seul plan budgétaire parent situé à un niveau supérieur de l'organisation. Vous pouvez également élaborer un plan budgétaire unique à un niveau supérieur de l'organisation et allouer le budget à des niveaux inférieurs dans l'organisation.

La planification budgétaire est intégrée à d'autres modules Microsoft Dynamics 365 for Finance and Operations. Par conséquent, vous pouvez apporter des informations relatives aux budgets précédents, dépenses réelles, immobilisations et ressources humaines. Étant donné que la planification budgétaire est également intégrée à Microsoft Excel et Microsoft Word, vous pouvez utiliser ces programmes pour exploiter vos données de planification budgétaire. Par exemple, un responsable du budget peut exporter la demande de budget d'un département dans une feuille de calcul Excel à partir d'un scénario de plan budgétaire. Les données peuvent être analysées, mises à jour et importées dans la feuille de calcul, puis publiées de nouveau dans les lignes du plan budgétaire.

## <a name="configuring-budget-planning"></a>Configuration de la planification budgétaire
La page **Configuration de planification budgétaire** contient la plupart des paramètres nécessaires pour paramétrer la planification budgétaire. Les sections suivantes décrivent certains facteurs clé dont vous devez tenir compte lorsque vous configurez la planification budgétaire. Après avoir terminé la configuration, vous paramétrez les processus de planification budgétaire.

### <a name="create-a-budget-planning-schema"></a>Créer un schéma de planification budgétaire

La première étape, facultative mais recommandée, consiste à créer un schéma qui explique la procédure de votre organisation concernant la formulation d'un budget. Vous pouvez utiliser n'importe quelle méthode pour créer ce schéma. L'illustration suivante présente un exemple générique, où des workflows de planification budgétaire distincts sont créés pour différents niveaux de l'organisation. Des stades sont définis dans chaque workflow, et des scénarios spécifiques sont affectés à chaque stade pour contenir les données du budget. Des tâches sont effectuées pour déplacer les données d'un stade au stade suivant. Par exemple, les montants peuvent être affectés ou agrégés pour différents comptes, approbations ou autres révisions. Dans cet exemple, le texte en italique indique un scénario non modifiable lors du stade, ou des données historiques ou approuvées lors d'un stade antérieur et qui ne doivent donc pas être modifiées. 

[![Schéma générique de la planification budgétaire](./media/budgetplanninggenericschema-300x145.png)](./media/budgetplanninggenericschema.png) 

Dans l'exemple suivant, le siège de l'entreprise établit une estimation des montants de base du budget initial et la distribue aux départements des ventes. Les départements des ventes procèdent ensuite à une estimation et soumettent leurs prévisions au siège, où le responsable du budget regroupe et ajuste les prévisions. Enfin, le responsable du budget envoie les montants budgétaires ajustés au directeur financier pour révision, ajustements finaux et approbation. 

[![Exemple de schéma de planification budgétaire](./media/budgetplanningexampleschema-300x145.png)](./media/budgetplanningexampleschema.png)

###  <a name="organization-hierarchy-for-budget-planning"></a>Hiérarchie d'organisation pour la planification budgétaire

Dans la page **Hiérarchie d'organisation**, vous pouvez désigner une hiérarchie d'organisation comme étant la hiérarchie de planification budgétaire pour chaque processus de planification budgétaire. La hiérarchie de planification budgétaire peut être différente de la hiérarchie d'organisation standard utilisée à d'autres fins. Étant donné que cette hiérarchie permet de regrouper et répartir des données, vous pouvez modifier sa structure. Dans l'exemple de schéma, les départements des ventes sont subordonnés au siège, qui comprend les départements Budget et Finances. Cette structure diffère probablement de la structure mise en place pour gérer les opérations pour les départements des ventes. Une seule hiérarchie d'organisation peut être affectée à chaque processus de planification budgétaire. 

Pour plus d'informations sur les hiérarchies d'organisation, voir [Organisations et hiérarchies d'organisation](../../fin-and-ops/organization-administration/organizations-organizational-hierarchies.md).

### <a name="user-security"></a>Sécurité utilisateur

La planification du budget peut suivre l'un des deux modèles de sécurité pour définir les autorisations utilisateur. Pour spécifier le modèle de sécurité, vous définissez un paramètre de planification budgétaire sur la page **Configuration de planification budgétaire**.

### <a name="budget-planning-workflows-stages"></a>Stades de workflow de planification budgétaire

Les workflows de planification budgétaire sont utilisés avec les workflows de budgétisation pour gérer la création et l'évolution des plans budgétaires.

Un workflow de planification budgétaire est composé d'un ensemble ordonné de stades par lesquels un plan budgétaire passe. Chaque workflow de planification budgétaire est associé à un workflow de budgétisation. Les workflows de budgétisation sont l'un des types de workflows utilisés dans Finance and Operations. Le workflow de budgétisation transmet les plans budgétaires, ainsi que les feuilles de calcul, justifications et pièces jointes, au sein de votre organisation pour qu'ils soient révisés et approuvés. 

Vous créez le workflow de planification budgétaire dans la section **Stades de workflow** de la page **Configuration de la planification budgétaire**. Là, vous pouvez sélectionner les stades et le workflow de budgétisation qui sera utilisé, puis configurer également les paramètres supplémentaires. 

Il est judicieux de créer un workflow de planification budgétaire pour chaque niveau d'une hiérarchie de budgétisation. Vous affectez un workflow de budgétisation qui contient les éléments qui correspondent aux stades du workflow de planification budgétaire. Dans l'exemple de schéma donné précédemment, un workflow de planification budgétaire serait créé pour les départements des ventes et un autre serait créé pour les sièges. Un workflow de budgétisation fait progresser les plans budgétaires d'un stade à un autre. 

Vous créez le workflow de budgétisation pour la planification budgétaire dans la page **Workflows de budgétisation**. Le processus est semblable au processus de création d'autres workflows dans Finance and Operations. L'illustration suivante présente un exemple de workflow au niveau du siège. 

[![Workflow de budgétisation pour la planification budgétaire](./media/budgetingworkflowforbudgetplanning-300x300.png)](./media/budgetingworkflowforbudgetplanning.png) 

Le workflow comprend des éléments pour l'allocation aux départements des ventes et l'agrégation de leurs soumissions, la révision par le responsable du budget, l'approbation par le directeur financier et les transitions entre chaque stade. 

Vous affectez le workflow de budgétisation à chaque workflow de planification budgétaire dans la section **Stades de workflow** de la page **Configuration de la planification budgétaire**.

### <a name="parameters-scenarios-and-stages"></a>Paramètres, scénarios et stades

Les paramètres initiaux de la page **Configuration de planification budgétaire** vous permettent de créer certains éléments constitutifs pour les étapes de configuration ultérieures :

-   **Paramètres** : Les paramètres définissent les règles de sécurité que vous souhaitez appliquer aux plans budgétaires et les dimensions financières par défaut qui doivent être utilisés lorsque les utilisateurs explorent les montants de scénario de plan budgétaire.
-   **Scénarios** : Les scénarios englobent les catégories de données que vous choisissez pour les plans budgétaires. Vous définissez des scénarios de plan budgétaire pour prendre en charge des classes monétaires et d'autres classes d'unités de mesure, telles que la quantité. Dans un plan budgétaire, les scénarios représentent une version des données de la planification budgétaire. Les ventes de l'année précédente et les contrats signés sont des exemples de scénarios de plan budgétaire monétaires. Le nombre de visites commerciales et le comptage équivalent temps plein (ETP) sont des exemples de scénarios qui utilisent des quantités.
-   **Stades** : Les stades définissent les étapes qu'un plan budgétaire suit de son origine à l'approbation finale. Le repositionnement HQ, la révision par le directeur financier et la finalisation sont des exemples de stades de planification budgétaire.

### <a name="allocation-schedules"></a>Programmes de répartition

Dans la planification budgétaire, vous pouvez répartir les montants ou les quantités dans les lignes de plan budgétaire d'un scénario à un autre, ou dans un même scénario. Par exemple, vous pouvez décider d'attribuer au même scénario si vous souhaitez appliquer des modifications aux dimensions financières ou aux dates des montants dans ce scénario. Une répartition peut être effectuée dans un plan budgétaire ou d'un plan budgétaire à un autre. 

Les programmes de répartition allouent automatiquement des lignes de plan budgétaire lors du traitement du workflow. Vous pouvez effectuer des répartitions à l'aide de l'une des méthodes suivantes de la liste **Mode de répartition** :

-   **Répartir par le biais de périodes** : une clé de répartition par période permet d'affecter les lignes du plan budgétaire depuis le scénario de plan budgétaire source sur plusieurs périodes du scénario de destination. **Remarque :** Avant de répartir sur plusieurs périodes, vous devez paramétrer des clés de répartition par période dans la page ****Catégories de répartition par période****.
-   **Répartition vers les dimensions** : Les lignes du plan budgétaire sont réparties depuis le scénario de plan budgétaire source sur plusieurs dimensions financières du scénario de destination. **Remarque :** Avant de pouvoir effectuer la répartition sur plusieurs dimensions, vous devez paramétrer les conditions de répartition budgétaire sur la page ****Conditions de répartition budgétaire****.
-   **Regroupement** : Les lignes du plan budgétaire sont regroupées depuis le scénario de plan budgétaire source des plans budgétaires associés vers le scénario de destination du plan budgétaire parent.
-   **Répartir** : Les lignes du plan budgétaire sont réparties depuis le scénario de plan budgétaire source du plan budgétaire parent vers le scénario de destination des plans budgétaires associés.
-   **Utiliser les règles de répartition comptable** : Les lignes de plan budgétaire sont réparties du scénario de plan budgétaire source vers le scénario de destination en fonction de la règle de répartition comptable sélectionnée.
-   **Copier à partir d'un plan budgétaire** : Vous pouvez sélectionner un autre plan budgétaire à utiliser comme source de répartition.

### <a name="stage-allocations"></a>Répartitions de stade

Les répartitions de stades sont utilisées pour répartir automatiquement des lignes de plan budgétaire lors du traitement du workflow. Lorsque les répartitions de stades sont utilisées, les lignes de plan budgétaire du scénario de destination peuvent être créées et modifiées sans l'intervention du préparateur ou du réviseur du plan budgétaire.

Lorsque vous paramétrez une répartition de stades, vous associez le workflow et le stade de planification budgétaire au programme de répartition. Le workflow de planification budgétaire doit être associé à un workflow de budgétisation utilisant la tâche de workflow automatique ****Répartition de stade de planification budgétaire****. Lorsque le workflow atteint le stade spécifié, la répartition s'effectue automatiquement. Cette tâche automatique peut servir à créer des lignes de plan budgétaire dans un nouveau scénario. 

Dans l'exemple de schéma donné précédemment, une répartition est exécutée pour transférer les montants d'un plan budgétaire et de scénarios du stade Référence du siège vers un autre plan budgétaire et d'autres scénarios du stade Estimation du département des ventes. L'illustration suivante montre la section appropriée de l'exemple de schéma.

[![Répartitions de stade](./media/stageallocation-204x300.png)](./media/stageallocation.png) 

En outre, dans l'exemple de schéma, une agrégation est effectuée des plans budgétaires et des scénarios du stade Soumis du département des ventes vers un plan parent du stade repositionnement HQ. L'illustration suivante montre la section appropriée de l'exemple de schéma.

[![Regroupement](./media/aggregation-109x300.png)](./media/aggregation.png)

### <a name="priorities"></a>Priorités

Vous pouvez également utiliser les priorités de plan budgétaire pour définir des catégories et des objectifs pour les plans budgétaires que vous avez paramétrés. Vous pouvez également utiliser des priorités pour organiser, classifier et évaluer plusieurs plans budgétaires. Par exemple, vous pouvez créer une priorité de planification budgétaire pour la santé et la sécurité, puis évaluer les plans budgétaires affectés à cette priorité. Vous pouvez également affecter un numéro pour classer tous les plans budgétaires.

### <a name="columns-and-layouts"></a>Colonnes et les structures

Les chiffres budgétaires apparaissent dans un plan budgétaire, dans des lignes et des colonnes. Vous devez commencer par définir les colonnes, puis vous pouvez créer une mise en page pour définir la présentation des colonnes. 

Pour définir une colonne, sélectionnez un scénario de plan budgétaire. Les montants des lignes de ce scénario apparaissent dans le plan budgétaire. Vous pouvez sélectionner une période pour filtrer le montant, et vous pouvez également appliquer des filtres basés sur le compte général. 

Lorsque vous définissez une mise en page, sélectionnez une dimension comptable définie pour créer les lignes du plan budgétaire à afficher, puis sélectionnez les colonnes comme éléments de mise en page. Vous pouvez créer plusieurs mises en page, afin qu'un plan budgétaire comprenne les données qui vous intéressent à différents stades du processus de planification budgétaire. 

Outre les colonnes des montants budgétaires, vous pouvez définir les colonnes pour les champs de projet, de projet proposé, d'actif et d'actif proposé du plan budgétaire. Vous pouvez également définir une colonne pour les postes budgétés. Cette option est très utile lorsque vous devez analyser les budgets de personnel. 

Pour l'exemple de schéma, vous voudrez peut-être créer des colonnes pour les scénarios Ventes PY, Contrats et Prévisions (l'illustration suivante montre la section appropriée du schéma). Vous pouvez ensuite éclater l'un de ces scénarios ou tous ces scénarios en différentes colonnes pour chaque trimestre de l'exercice, de sorte que le responsable du département Ventes puisse précisément entrer des montants de prévision pour chaque période.

[![Colonnes](./media/columns.png)](./media/columns.png) 

Vous indiquez également si chaque élément de mise en page (colonne) est modifiable, et s'il est disponible dans n'importe quel modèle de feuille de calcul créé pour cette mise en page. Pour l'exemple de schéma, dans la mise en page utilisée pour le stade Estimation, les colonnes de prévision sont modifiables, alors que les colonnes de ventes PY et de contrats sont en lecture seule.

### <a name="templates"></a>Modèles

Dans la section **Mises en page** de la page **Configuration de planification budgétaire**, vous pouvez également générer, afficher ou télécharger des modèles Excel. Ces modèles sont les classeurs qui sont associés à chaque plan budgétaire afin de fournir des fonctionnalités supplémentaires d'analyse, de création de graphiques et de saisie de données. 

Vous pouvez générer, afficher ou télécharger un modèle pour chaque mise en page. Lorsqu'un modèle est généré, la mise en page est verrouillée et ne peut pas être modifiée. Ce verrouillage aide à garantir que le format du modèle correspond à la mise en page du plan budgétaire et qu'il inclut les mêmes données. Une fois le modèle généré, il peut être affiché et modifié. Par exemple, vous pouvez ajouter des graphiques au modèle ou personnaliser davantage son apparence.

> [!NOTE] 
> Le modèle doit être enregistré dans un emplacement auquel l'utilisateur a accès, afin qu'il puisse être chargé vers la mise en page lorsque la modification est terminée. De cette manière, le modèle sera utilisé avec les plans budgétaires qui utilisent la mise en page.

### <a name="descriptions"></a>Description

Les descriptions que vous pouvez affecter dans la section **Mises en page** sont utilisées pour afficher le nom d'une dimension financière incluse dans une mise en page. Par exemple, une organisation peut souhaiter afficher le nom du compte principal en regard du numéro de compte principal dans un plan budgétaire, mais souhaiter omettre les noms d'autres dimensions financières pour éviter d'encombrer l'affichage.

## <a name="setting-up-budget-planning-processes"></a>Paramétrage de processus de planification budgétaire

Après avoir terminé de configurer la planification budgétaire, vous pouvez paramétrer les processus de planification budgétaire dans la page **Processus de planification budgétaire**. Les processus de planification budgétaire sont des ensembles de règles qui déterminent la manière dont les plans budgétaires peuvent être mis à jour, acheminés, révisés, puis approuvés dans la hiérarchie d'organisation de budgétisation. 

Pour chaque processus de planification budgétaire, vous commencez par sélectionner un cycle budgétaire et un compte général. Chaque processus de planification budgétaire est lié à un seul cycle budgétaire et à un compte général. Sélectionnez ensuite la hiérarchie d'organisation budgétaire dans l'organisateur **Administration de processus de planification budgétaire** et affectez un workflow de planification budgétaire à tous les centres de responsabilité de l'organisation qui s'affichent dans la grille. 

Pour affecter ou modifier le workflow de planification budgétaire de centres de responsabilité similaires, cliquez sur **Affecter un workflow**, puis sélectionnez le type d'organisation cible et le workflow de planification budgétaire à utiliser. L'ID de workflow de budgétisation associé à chaque workflow de planification budgétaire est automatiquement ajouté à la grille. 

Lorsque vous définissez les règles et les modèles de stade dans l'organisateur **Règles et mises en page du stade de planification budgétaire**, vous pouvez définir un autre ensemble de règles et de mises en page par défaut pour chaque stade de planification budgétaire. Par exemple, le stade Estimation du département des ventes peut permettre aux utilisateurs de modifier les lignes d'un plan budgétaire, mais interdire aux utilisateurs d'ajouter des lignes. Le stade Soumis peut permettre aux utilisateurs de consulter les lignes, mais ne pas leur permettre d'ajouter ni de modifier des lignes, car, à ce stade, le travail est terminé et les plans budgétaires ne doivent pas être modifiés. Pour sélectionner les mises en page disponibles pour les plans budgétaires, cliquez sur **Autres mises en page**. 

Vous pouvez sélectionner les priorités de planification budgétaire dans l'organisateur **Contraintes de priorité de plan budgétaire**. Les priorités peuvent alors être sélectionnées pour les plans budgétaires. 

L'étape finale consiste à activer le processus de planification budgétaire via le menu **Actions**. Un processus de planification budgétaire ne peut pas être utilisé tant qu'il n'a pas été activé. 

Dans le menu **Actions**, vous pouvez également créer un processus en copiant un processus existant. Cette fonctionnalité est utile pour les organisations qui suivent le même flux de processus à chaque cycle budgétaire, et apportent peu de modifications, voire aucune. 

Une autre commande utile du menu **Actions** est **Afficher le statut de processus budgétaire**. Cette commande affiche graphiquement les plans budgétaires d'un processus, avec les données appropriées, comme le statut de workflow des plans, des synthèses par montant et par unité et la navigation en un clic vers les plans budgétaires.

[![Statut de processus de planification budgétaire](./media/budgetplanningprocessstatus-300x171.png)](./media/budgetplanningprocessstatus.png)




