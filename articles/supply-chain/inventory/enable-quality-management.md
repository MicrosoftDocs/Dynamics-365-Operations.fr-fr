---
title: Vue d'ensemble de la gestion de la qualité
description: Cette rubrique décrit la manière dont vous pouvez utiliser la gestion de la qualité dans Microsoft Dynamics 365 for Finance and Operations pour vous aider à améliorer la qualité des produits de votre chaîne logistique.
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1630d13437d7e930fdf32ed5fdc61fc62bc33817
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557498"
---
# <a name="quality-management-overview"></a>Vue d'ensemble de la gestion de la qualité

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la manière dont vous pouvez utiliser la gestion de la qualité dans Microsoft Dynamics 365 for Finance and Operations pour vous aider à améliorer la qualité des produits de votre chaîne logistique.

La gestion de la qualité peut vous aider à gérer les délais de rotation lorsque vous traitez des produits non conformes, indépendamment de leur point d'origine. Étant donné que les types de diagnostics sont liés à la génération d'états de correction, Microsoft Dynamics 365 for Finance and Operations peut programmer des tâches afin de corriger les problèmes et les empêcher de se reproduire.

Outre la fonctionnalité de gestion de la non-conformité, la gestion de la qualité inclut la fonctionnalité de suivi des problèmes par type de problème (même les problèmes internes) et d'identification des solutions comme à court terme ou à long terme. Les statistiques concernant les indicateurs clés de performance (KPI) donnent des indications sur l'historique des problèmes de non-conformité antérieurs et sur les solutions qui ont été utilisées pour les corriger. Vous pouvez utiliser les données historiques pour examiner l'efficacité des mesures de qualité antérieures et déterminer les mesures appropriées à utiliser à l'avenir.

Lorsque vous paramétrez une association de qualité, Finance and Operations peut générer des ordres de qualité pour différents processus d'entreprise, événements et conditions. L'association de qualité peut couvrir un article spécifique, un groupe d'articles spécifique, ou tous les articles.

## <a name="examples-of-the-use-of-quality-management"></a>Exemples de l'utilisation de la gestion de la qualité
La gestion de la qualité est flexible et peut être mise en œuvre de différentes manières afin de répondre aux exigences de niveaux spécifiques des opérations de chaîne d'approvisionnement. Les exemples suivants illustrent les utilisations possibles de ces fonctionnalités :

-   Démarrer automatiquement un processus de contrôle qualité, basé sur des critères prédéfinis (lors de l'enregistrement en entrepôt d'une commande fournisseur provenant d'un fournisseur spécifique).
-   Bloquer le stock au cours de l'inspection pour empêcher l'utilisation d'un stock non-approuvé (blocage complet des quantités des commande fournisseur).
-   Utiliser l'échantillonnage d'article dans le cadre d'une association de qualité pour définir la quantité de stock physique actuel qui doit être inspectée. L'échantillonnage peut être basé sur des quantités fixes ou sur un pourcentage.
-   Créez des ordres de qualité pour les réceptions partielles. Pour créer un ordre de qualité basé sur la quantité qui est reçue physiquement avec une commande, vous devez activer la case à cocher **Par quantité mise à jour** sur l'écran **Échantillonnage d'article**.
-   Créer des types de test qui incluent les valeurs minimales, maximales, ainsi que les valeurs de test cibles, et réaliser des tests quantitatifs/qualitatifs ayant des résultats de contrôle prédéfinis.
-   Spécifier un niveau de qualité acceptable pour contrôler les tolérances de la mesure de qualité.
-   Spécifier les ressources qu'une opération d'inspection nécessite, telles qu'une zone de test et des instruments de test.

## <a name="working-with-quality-associations"></a>Utilisation des associations de qualité
Le processus d'entreprise qui utilise une association de qualité peut être associé à diverses documents source, tels que des commandes fournisseur, des commandes client ou des ordres de fabrication.

Chaque enregistrement d'association de qualité définit l'ensemble de tests, le niveau de qualité acceptable et le programme d'échantillonnage qui s'applique aux ordres de qualité générés. Vous devez définir un enregistrement d'association de qualité pour chaque variation d'un processus d'entreprise. Par exemple, vous pouvez paramétrer une association de qualité qui génère un ordre de qualité lorsqu'un accusé de réception de marchandises de commande fournisseur est mis à jour. Selon le paramétrage du plan d'exécution, le processus de déclenchement lui-même peut être bloqué tant qu'il existe un ordre de qualité en cours, ou les processus suivants, tels que la facturation d'une commande fournisseur, peuvent être bloqués.

**Remarque :** tant qu'il existe des ordres de qualité en cours, le lancement des quantités en stock est automatiquement bloqué. En fonction du paramètre **Blocage total** de la page **Échantillonnage d'article**, la quantité est soit la quantité de l'ordre de qualité, soit la quantité de la ligne de document source.

Pour un processus entreprise donné, l'enregistrement d'association de qualité identifie l'événement et les conditions pour lesquels un ordre de qualité est généré. Les conditions peuvent être spécifiques à un site ou à une entité juridique. Un ordre de qualité qui implique des tests destructifs ne peut être généré que si le stock disponible existe pour l'événement.

Les exemples suivants présentent la manière dont un enregistrement d'association de qualité est défini pour les variations de chaque processus entreprise. Pour chaque exemple, le tableau suivant résume les événements et les conditions définis par un enregistrement d'association de qualité.

<table>
<tbody>
<tr>
<th>Type de référence</th>
<th>Type de droit</th>
<th>Exécution</th>
<th>Blocage d'événement</th>
<th>Références du document</th>
</tr>
<tr>
<td>Stock</td>
<td>Non applicable</td>
<td>Non applicable</td>
<td>Aucun(e)</td>
<td>Tout</td>
</tr>
<tr>
<td rowspan="7">Ventes</td>
<td rowspan="4">Le processus de prélèvement est planifié</td>
<td rowspan="4">Avant</td>
<td>Aucun(e)</td>
<td rowspan="22">ID spécifique, Groupe, ou Tous uniquement</td>
</tr>
<tr>
<td>Processus de prélèvement</td>
</tr>
<tr>
<td>Bon de livraison</td>
</tr>
<tr>
<td>Facture</td>
</tr>
<tr>
<td rowspan="3">Bon de livraison</td>
<td rowspan="3">Avant</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Bon de livraison</td>
</tr>
<tr>
<td>Facture</td>
</tr>
<tr>
<td rowspan="15">Achat</td>
<td rowspan="7">Liste de réception</td>
<td rowspan="4">Avant</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Liste de réception</td>
</tr>
<tr>
<td>Accusé de réception de marchandises</td>
</tr>
<tr>
<td>Facture</td>
</tr>
<tr>
<td rowspan="3">Après</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Accusé de réception de marchandises</td>
</tr>
<tr>
<td>Facture</td>
</tr>
<tr>
<td rowspan="3">Enregistrement</td>
<td rowspan="3">Non applicable</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Accusé de réception de marchandises</td>
</tr>
<tr>
<td>Facture</td>
</tr>
<tr>
<td rowspan="5">Accusé de réception de marchandises</td>
<td rowspan="3">Avant</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Accusé de réception de marchandises</td>
</tr>
<tr>
<td>Facture</td>
</tr>
<tr>
<td rowspan="2">Après</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Facture</td>
</tr>
<tr>
<td rowspan="8">Production</td>
<td rowspan="3">Enregistrement</td>
<td rowspan="3">Non applicable</td>
<td>Aucun(e)</td>
<td rowspan="12">Tout</td>
</tr>
<tr>
<td>Déclaration de fin</td>
</tr>
<tr>
<td>Fin</td>
</tr>
<tr>
<td rowspan="5">Déclaration de fin</td>
<td rowspan="3">Avant</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Déclaration de fin</td>
</tr>
<tr>
<td>Fin</td>
</tr>
<tr>
<td rowspan="2">Après</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Fin</td>
</tr>
<tr>
<td rowspan="4">Contrôle</td>
<td rowspan="3">Déclaration de fin</td>
<td rowspan="2">Avant</td>
<td>Déclaration de fin</td>
</tr>
<tr>
<td>Fin</td>
</tr>
<tr>
<td>Après</td>
<td>Fin</td>
</tr>
<tr>
<td>Fin</td>
<td>Avant</td>
<td>Fin</td>
</tr>
<tr>
<td rowspan="3">Opération de gamme</td>
<td rowspan="3">Déclaration de fin</td>
<td rowspan="2">Avant</td>
<td>Aucun(e)</td>
<td rowspan="3">ID spécifique, Groupes ou Tous, et Spécifique à la ressource, Groupe ou Tous</td>
</tr>
<tr>
<td>Déclaration de fin</td>
</tr>
<tr>
<td>Après</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td rowspan="3">Production de coproduits</td>
<td>Enregistrement</td>
<td>Non applicable</td>
<td rowspan="3">Aucun(e)</td>
<td rowspan="3">Tout</td>
</tr>
<tr>
<td rowspan="2">Déclaration de fin</td>
<td>Avant</td>
</tr>
<tr>
<td>Après</td>
</tr>
</tbody>
</table>

Le tableau suivant fournit plus d'informations sur la manière dont les ordres de qualité peuvent être générés pour des types de processus spécifiques.
<div class="tableSection">

<table>
<tbody>
<tr>
<th>Type de processus</th>
<th>Lorsque des ordres de qualité peuvent être automatiquement générés</th>
<th>Lorsque des ordres de qualité peuvent être générés si les tests destructifs sont requis</th>
<th>Informations de condition</th>
<th>Informations de génération manuelle</th>
</tr>
<tr>
<td>Commande fournisseur</td>
<td>Avant ou après la validation d'une liste de réceptions ou d'un accusé de réception de marchandises reçu pour les matières</td>
<td>Après la validation de l'accusé de réception de marchandises pour les matières reçu, car les matières doivent être disponibles pour les tests destructifs</td>
<td>La nécessité d'établir un ordre de qualité peut refléter un site, un article ou un vendeur spécifique ou une combinaison de ces conditions.</td>
<td>Un ordre de qualité généré manuellement qui fait référence à une commande fournisseur peut utiliser les informations dans un enregistrement d'association de qualité, telles que le programme d'échantillonnage de test.</td>
</tr>
<tr>
<td>Ordre de contrôle</td>
<td>Avant ou après la déclaration de fin de l'ordre de contrôle</td>
<td>Les ordres de qualité nécessitant des tests destructifs ne peuvent pas être générés. On suppose que la fonctionnalité d'ordre de contrôle gère l'élimination des matières détruites.</td>
<td>La nécessité d'établir un ordre de qualité peut refléter un site, un article ou un vendeur spécifique ou une combinaison de ces conditions.</td>
<td>Un ordre de qualité généré manuellement qui fait référence à un ordre de contrôle peut utiliser les informations dans un enregistrement d'association de qualité, telles que le programme d'échantillonnage de test.</td>
</tr>
<tr>
<td>Commande client</td>
<td>Avant la mise à jour d'un processus de prélèvement planifié ou d'un bon de livraison pour les articles qui sont expédiés</td>
<td>À toute étape</td>
<td>La nécessité d'établir un ordre de qualité peut refléter un site, un article ou un client spécifique ou une combinaison de ces conditions.</td>
<td>Un ordre de qualité généré manuellement qui fait référence à une commande client peut utiliser les informations dans un enregistrement d'association de qualité, telles que le programme d'échantillonnage de test.</td>
</tr>
<tr>
<td>Ordre de fabrication</td>
<td>Avant ou après la déclaration de la quantité terminée pour l'ordre de fabrication</td>
<td>Après la déclaration de la quantité terminée pour l'ordre de fabrication</td>
<td>La nécessité d'établir un ordre de qualité peut refléter un site, un article ou un client spécifique ou une combinaison de ces conditions.</td>
<td>Un ordre de qualité généré manuellement qui fait référence à un ordre de fabrication peut utiliser les informations dans un enregistrement d'association de qualité, telles que le programme d'échantillonnage de test.</td>
</tr>
<tr>
<td>Ordre de fabrication qui a une opération de gamme</td>
<td>Avant ou après la fin de l'état pour une opération</td>
<td>Après la déclaration de fin de production pour la dernière opération</td>
<td>La nécessité d'établir un ordre de qualité peut refléter un site, un article ou d'une ressource opérationnelle, ou une combinaison de ces conditions.</td>
<td>Un ordre de qualité généré manuellement qui fait référence à une opération de gamme peut utiliser les informations dans un enregistrement d'association de qualité, telles que le programme d'échantillonnage de test.</td>
</tr>
<tr>
<td>Stock</td>
<td>Un ordre de qualité ne peut pas être automatiquement généré pour une transaction dans un journal de stock ou pour des transactions d'ordre de transfert</td>
<td></td>
<td></td>
<td>Un ordre de qualité doit être créé manuellement pour la quantité de stock d'un article. Le stock physique disponible est exigé.</td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a>Pages Gestion de la qualité
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Page</th>
<th>Description</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Associations de qualité</td>
<td>Voir les sections précédentes de cet article.</td>
<td>Une association de qualité définit toutes les informations suivantes pour un ordre de qualité qui est généré :
<ul>
<li>L'événement de transaction</li>
<li>L'ensemble des tests qui doivent être exécutés sur les articles</li>
<li>Le niveau de qualité acceptable</li>
<li>Le programme d'échantillonnage</li>
</ul>
Vous devez définir une association de qualité pour chaque variation dans un processus d'entreprise qui requiert la génération automatique d'ordres de qualité. Par exemple, un ordre de qualité peut être généré dans le processus d'entreprise pour les commandes fournisseur, les ordres de contrôle,, les commandes client et les ordres de fabrication.</td>
</tr>
<tr class="even">
<td>Tests</td>
<td>Cette page permet de définir et d'afficher les tests individuels qui déterminent si vos produits correspondent aux spécifications de qualité. Vous pouvez affecter un ou plusieurs tests à un groupe de tests. Dans ce cas, vous pouvez également spécifier des informations spécifiques aux tests, telles que les valeurs de mesures acceptables. Celles-ci sont utilisées dans le cadre des tests quantitatifs et les variables de test sont utilisées lors des tests qualitatifs.
<ul>
<li>Un test quantitatif est associé à un type de test <strong>Entier</strong> ou <strong>Fraction</strong>, et est également doté d'une unité de mesure spécifiée. Les spécifications de qualité et les résultats des tests peuvent être exprimés sous forme de nombres.</li>
<li>Le test qualitatif possède le type de test <strong>Option</strong>. Les tests qualitatifs exigent des informations supplémentaires sur la variable de test mesurée et la liste de ses options. Les spécifications de qualité et les résultats des tests peuvent être exprimés sous forme de résultat.</li>
</ul></td>
<td>Une société de fabrication réalise deux tests sur du matériel acheté : un test quantitatif concernant la qualité du matériel et un test qualitatif concernant la solidité de l'emballage. Elle définit des informations supplémentaires concernant le test qualitatif afin d'identifier la variable de test (solidité de l'emballage) et ses résultats. Elle utilise la page <strong>Groupes de test</strong> pour affecter les deux tests à un groupe de test et spécifier les informations spécifiques aux tests. Le groupe de tests est affecté à un ordre de qualité, de sorte que la société puisse générer un état à partir des résultats des deux tests.</td>
</tr>
<tr class="odd">
<td>Groupes de test</td>
<td>Cette page permet de paramétrer, de modifier et d'afficher des groupes de test et des tests individuels affectés à un groupe de test. Le volet supérieur affiche les groupes de test et le volet inférieur affiche les tests affectés à un groupe de test sélectionné. Vous affectez plusieurs stratégies à un groupe de test, notamment un programme d'échantillonnage, un niveau de qualité acceptable et la demande de tests destructifs. Lorsque vous affectez un test individuel à un groupe de test, vous définissez des informations supplémentaires, telles que l'ordre, les documents et les dates de validité Pour un test quantitatif; les informations que vous définissez incluent également les valeurs de mesures acceptables. Pour un test qualitatif, ces informations incluent la variable de test et le résultat par défaut. Le groupe de test affecté à un ordre de qualité définit l'ensemble des tests par défaut devant être exécutés sur l'article spécifié. Toutefois, vous pouvez ajouter, supprimer ou modifier les tests pour un ordre de qualité. Les résultats de test sont reportés pour chaque test sur un ordre de qualité.</td>
<td>Une société de fabrication définit un groupe de tests pour chaque variation de ses directives qualité. Les groupes de test reflètent les différences entre les programmes d'échantillonnage, les ensembles de tests devant être exécutés simultanément, le niveau de qualité acceptable, ainsi que d'autres facteurs. Pour les tests quantitatifs, il existe également des différences entre les valeurs de mesures acceptables. Pour appliquer ses directives qualité, la société affecte un groupe de test à chaque règle pour la génération automatique d'ordres de qualité sur la page <strong>Associations de qualité</strong>, et affecte également un groupe de test aux ordres de qualité créés manuellement.</td>
</tr>
<tr class="even">
<td>Groupes de qualité d'article</td>
<td>Cette page permet de paramétrer, de modifier et d'afficher les articles affectés à un groupe de qualité ou les groupes de qualité affectés à un article. Un groupe de qualité représente des besoins de test communs pour les articles. Une fois que vous avez défini les besoins de test sur la page <strong>Groupes de test</strong>, vous pouvez définir les règles de génération automatique des ordres de qualité. Pour simplifier le processus, vous ne définissez pas de règles pour des articles individuels. Au lieu de cela, vous définissez des règles pour un groupe de qualité, par l'intermédiaire de la page <strong>Associations de qualité</strong>. Vous pouvez également utiliser la page <strong>Groupes de qualité d'article</strong> pour un groupe de qualité sélectionné afin d'affecter les articles pertinents à ce groupe. Vous pouvez également utiliser la page <strong>Groupes de qualité d'article</strong> pour un article sélectionné afin d'affecter les groupes de qualité pertinents à cet article.</td>
<td>Une société de fabrication achète diverses matières premières présentant les mêmes besoins de test pour l'inspection à venir. La société définit un groupe de qualité, puis affecte les numéros d'articles associés aux matières premières à ce groupe. Ensuite, la société achète un nouveau type de matières premières ayant les mêmes besoins de test. Au lieu de paramétrer de nouveaux besoins de test pour les nouvelles matières, la société ajoute le numéro d'article pour la nouvelle matière au groupe de qualité existant. La même société de fabrication produit également des articles ayant les mêmes besoins de test de production et expédie les articles dotés des mêmes besoins en tests de pré-expédition. La société définit deux groupes de qualité supplémentaires, puis affecte les numéros d'articles pertinents à chaque groupe.</td>
</tr>
<tr class="odd">
<td>Variables de test</td>
<td>Cette page vous permet de définir et d'afficher les variables associées à un test qualitatif. Pour chaque variable, vous définissez les résultats énumérés qui représentent les options possibles. Vous définissez des tests sur la page <strong>Tests</strong>. Pour les tests qualitatifs, vous devez définir le type de test à <strong>Option</strong>. La page <strong>Groupes de test</strong> vous permet d'affecter une variable de test à un test individuel.</td>
<td>Une société de fabrication de biscuits utilise un test d'inspection pour le produit fini. Ce test d'inspection comporte plusieurs variables. L'une des variables est le goût et les résultats possibles pour cette variable sont Bon et Mauvais. Une deuxième variable est la couleur et les résultats possibles sont Trop foncé, Trop clair et Correct.</td>
</tr>
<tr class="even">
<td>Résultats de la variable de test</td>
<td>Cette page permet de paramétrer, de modifier et d'afficher les résultats de tests possibles pour une variable de test associée à un test qualitatif. Pour chaque résultat, vous affectez un statut <strong>Réussite</strong> ou <strong>Échec</strong>. Vous devez définir une variable et ses résultats pour chaque test qualitatif défini sur la page <strong>Tests</strong>. (Pour les tests qualitatifs, le type de test est défini sur <strong>Option</strong> dans la page <strong>Tests</strong>.) La page <strong>Groupes de tests</strong> permet d'affecter une variable de test et le résultat par défaut à un test qualitatif individuel.</td>
<td>Une société de fabrication de biscuits utilise un test d'inspection pour le produit fini. Ce test d'inspection comporte plusieurs variables. L'une des variables est le goût et les résultats possibles pour cette variable sont Bon et Mauvais. Une deuxième variable est la couleur et les résultats possibles sont Trop foncé, Trop clair et Correct. Un statut <strong>Réussite</strong> ou <strong>Échec</strong> est affecté à chaque résultat. Au cours du test d'inspection effectué pour chaque variable, l'inspecteur présente le résultat du test en sélectionnant l'un des résultats.</td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a>Ressources supplémentaires
--------

[Processus de gestion de la qualité](quality-management-processes.md)

[Activation de la gestion de non-conformité](enable-nonconformance-management.md)
