---
title: Nouveautés ou modifications apportées à Dynamics AX 7.0 (février 2016)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics AX 7.0. Cette version contient des fonctions de plateforme et d’application et a été publiée en février 2016.
author: sericks007
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 91243
ms.assetid: 515bc6e7-a85d-4995-95c6-6cab6c8aa0f9
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3c1b63ba623eb1699938476825a77fd40d838142
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4797217"
---
# <a name="whats-new-or-changed-in-dynamics-ax-70-february-2016"></a>Nouveautés ou modifications apportées à Dynamics AX 7.0 (février 2016)

[!include [banner](../includes/banner.md)]

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics AX 7.0. Cette version contient des fonctions de plateforme et d’application et a été publiée en février 2016.

## <a name="cost-management"></a>Gestion des coûts

<table>
<thead>
<tr>
<th>Que pouvez-vous faire ?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Pourquoi est-ce important ?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Obtenez d’un aperçu rapide du solde du stock, des travaux en cours, ainsi que des flux entrants et sortants des travaux en cours pour l’exercice fiscal sélectionné.</td>
<td>Non applicable</td>
<td>L’espace de travail <strong>Administration des coûts</strong> contient une section dans laquelle le relevé de stock ou le relevé de stock des travaux en cours est présenté pour la période fiscale sélectionnée. Le relevé est basé sur un cache du jeu de données qui, par défaut, est mis à jour toutes les 24 heures. Le cache de l’ensemble de données peut être configuré afin que les utilisateurs puissent mettre à jour le manuellement pour la génération d’états en temps réel. La carte <strong>Statut d’actualisation des données</strong> dans l’espace de travail <strong>Administration des coûts</strong> s’affiche lorsque le cache a été mis à jour.</td>
<td>Les contrôleurs de coûts veulent savoir si le solde du relevé du stock ou du stock des travaux en cours augmente ou diminue au fil du temps. En classifiant des événements opérationnels sur le relevé, le contrôleur de coûts peut obtenir une vue d’ensemble de l’écoulement du stock. Si le stock ou le stock de travaux en cours est valorisé par les coûts standard, l’écart global enregistré peut également être considéré.</td>
</tr>
<tr>
<td>Utilisez le module <strong>Gestion des coûts</strong>.</td>
<td>Non applicable</td>
<td>Le module Gestion des coûts est présenté comme une zone de domaine. La configuration et l’analyse associées aux coûts ont été dispersées dans les modules Gestion des stocks, Contrôle de la production et Comptabilité fournisseur.</td>
<td>Étant donné que toutes les tâches associées à la gestion des coûts sont centralisées dans un module, les contrôleurs de coût pourront plus facilement tenir le système à jour.</td>
</tr>
<tr>
<td>Les types de validation liés à la comptabilité de stock et comptabilité de production ont été mis à jour.</td>
<td>Les noms dans les écrans <strong>InventPosting</strong>, <strong>Ressource</strong>, <strong>ResourceGroup</strong> et <strong>ProductionGroup</strong> ne sont pas toujours alignés avec ceux réellement utilisés dans <strong>LedgerPostingType</strong>. Il n’est pas simple de comprendre la terminologie utilisée pour les noms.</td>
<td>Les noms ont été mis à jour afin que les noms dans les pages <strong>InventPosting</strong>, <strong>Ressource</strong>, <strong>ResourceGroup</strong> et <strong>ProductionGroup</strong> soient conformes à ceux réellement utilisés dans <strong>LedgerPostingType</strong>. Tous les noms ont été également renommés afin de correspondre aux événements opérationnels. Notez que la logique réelle de validation n’a pas été modifiée.</td>
<td>Il est plus simple de configurer le système, car les nouveaux noms sont liés aux événements opérationnels qui utilisent ce type de validation.</td>
</tr>
<tr>
<td>Importation/exportation du prix d’achat, du coût ou du prix de vente à partir de Microsoft Excel dans ou à partir d’une version d’évaluation des coûts.</td>
<td>Vous ne pouvez pas correctement importer des prix ou des coûts dans une version d’évaluation des coûts, car le modèle de données nécessite un ID InventDim.</td>
<td>L’introduction des entités de données permet de mettre en œuvre une fonctionnalité d’importation/d’exportation. Cette fonctionnalité permet aux utilisateurs d’importer/d’exporter des prix ou des coûts dans une version d’évaluation des coûts.
<ul>
<li>Importation d’une liste complète des prix d’achat de l’année suivante obtenue à partir du département Achats.</li>
<li>Transmission des coûts et des prix de vente standard depuis le siège vers une ou plusieurs succursales en une seule opération.</li>
</ul></td>
<td>Cela peut faire gagner beaucoup de temps aux contrôleurs de coût lorsqu’ils tiennent le système à jour, en particulier lorsqu’ils doivent tenir à jour des coûts prédéterminés pour l’exercice suivant.</td>
</tr>
<tr>
<td>Obtention d’un aperçu rapide du solde de stock et du coût unitaire moyen d’un objet de coût.</td>
<td>L’utilisateur doit ouvrir l’écran disponible et sélectionner les dimensions de stock qui reflètent l’objet de coût. Il doit par conséquent savoir quelles dimensions de stock étaient marquées pour le stock financier pour le produit spécifique.</td>
<td>Une nouvelle page <strong>Objet de coût</strong> est introduite. Par défaut, cette page affiche tous les objets de coûts liés au produit. La page affiche la quantité en stock, la valeur et le coût unitaire moyen par objet de coût.</td>
<td>Elle permet de supprimer une partie de la complexité et facilite la tâche des contrôleurs de coût.</td>
</tr>
<tr>
<td>Utilisez la nouvelle page <strong>Écritures de coût</strong> au cours du contrôle des stocks.</td>
<td>Il peut s’avérer compliqué d’effectuer la vérification du stock sur les mouvements de stock enregistrés et les règlements associés, car les mêmes transactions peuvent être physiques et financières.</td>
<td>La page <strong>Entrées de coût</strong> offre une nouvelle manière d’afficher les mouvements de stock.
<ul>
<li>Les transactions sont affichées dans l’ordre chronologique.</li>
<li>Seules les transactions qui contribuent aux coûts sont incluses.</li>
<li>Il n’existe aucune notion de coût physique ou de coût financier.</li>
<li>Il n’existe aucune notion de quantité physique ou de quantité financière.</li>
<li>Les coûts sont ajoutés de façon incrémentielle.</li>
</ul></td>
<td>Cela permet de faire gagner beaucoup de temps aux contrôleurs de coût quand ils doivent effectuer la vérification du stock au niveau de la transaction.</td>
</tr>
<tr>
<td>Utilisez la nouvelle boîte de dialogue <strong>Relevé des travaux en cours au niveau de la production</strong> pour afficher une vue de synthèse des coûts cumulés pour un produit spécifique.</td>
<td>Non applicable</td>
<td>Le relevé des travaux en cours présente le solde résumé des travaux en cours de l’ordre de fabrication spécifique, regroupé dans les classifications de coût appropriées. Un graphique affiche, dans l’ordre chronologique, comment les validations opérationnelles ont affecté le solde des travaux en cours.</td>
<td>Cela permet de faire gagner beaucoup de temps aux contrôleurs de coût quand ils doivent connaître le solde actuel des travaux en cours dans un ordre de fabrication spécifique, ou la quantité de matières premières consommées dans la commande.</td>
</tr>
<tr>
<td>Utilisez la fonctionnalité Afficher la comparaison du coût introduite dans les ordres de fabrication. Cette fonctionnalité facilite la comparaison des coûts associés à un ordre de fabrication.</td>
<td>L’utilisateur peut comparer uniquement les coûts estimés et ceux réalisés. Cette comparaison peut être effectuée au niveau le plus bas.</td>
<td>La fonctionnalité de comparaison des coûts permet aux contrôleurs de coûts de comparer les données suivantes :
<ul>
<li>Coût actif comparé aux coûts estimés = Écart de planification</li>
<li>Coût estimé comparé au coût réalisé = Écart de production</li>
<li>Écart de planification + Écart de production = Écart total</li>
</ul>
Cette fonctionnalité fonctionne indépendamment des méthodes d’évaluation des coûts qui sont affectées à l’article produit. Par défaut, un graphique affiche la comparaison des coûts par type de groupe de coûts. Le graphique permet aux utilisateurs d’explorer des niveaux d’analyse détaillés.</td>
<td>Il permet aux contrôleurs de coûts ou aux responsables de production d’analyser l’origine des écarts de production et ce qui les provoque.</td>
</tr>
</tbody>
</table>

## <a name="developer"></a>Développeur

| Que pouvez-vous faire ? | Dynamics AX 2012 | Dynamics AX 7.0 | Pourquoi est-ce important ? |
|------------------|------------------|-----------------|------------------------|
| Possibilité de créer des solutions Web dans le cloud accessibles sur plusieurs périphériques. | Non disponible | La version actuelle de Dynamics AX est basée sur un nouveau client Web et une infrastructure cliente. | Vous pouvez fournir des solutions de deuxième génération à vos utilisateurs finaux. |
| Possibilité d’utiliser Microsoft Visual Studio pour développer vos solutions. | Microsoft MorphX est l’environnement de développement principal, mais certains développements ont lieu dans Visual Studio. | Visual Studio est l’unique environnement de développement intégré. | Il conserve les concepts familiers de Dynamics AX 2012, et les adapte facilement à la structure et aux paradigmes de Visual Studio. Il active l’interopérabilité standard avec d’autres langues et projets .NET. |
| Langage intermédiaire commun (CIL) de compilation pour toutes les fonctionnalités. | X++ compilé en code P. | Le tout nouveau compilateur X++ génère du CIL pour toutes les fonctionnalités. CIL est le même langage intermédiaire que celui utilisé par d’autres langages basés sur .NET. | CIL est plus rapide, il peut référencer efficacement des classes dans les bibliothèques de liens dynamiques gérées (DLL) et peut s’exécuter sur une grande base d’outils d’utilitaires .NET. |
| Intégration de visualisations et de rapports Business Intelligence (BI) dans le client Microsoft Dynamics AX. | Non disponible | Création de visualisations fluides et très intuitives. | Il fournit des analyses de prise de décision basées sur BI. |
| Intégrez avec Microsoft Office. | Non disponible | Les nouvelles fonctionnalités incluent l’application de connecteur de données Excel, la page **Concepteur des classeurs**, l’API d’exportation, et la gestion des documents. | Vous pouvez créer des solutions de productivité pour les utilisateurs finaux. |
| Automatisation de la version, du test et du déploiement. | Partiellement disponible | Déploiement de la topologie pour développeur à l’aide du développeur et de Build VM. Auto-configuration de Build VM pour découvrir, créer des modules à partir de Visual Studio Online (VSO) et exécuter des tests. La compilation et les références de module C\# et X++ sont prises en charge. | Cela augmente la productivité des développeurs en réduisant le coût et les efforts pour les tests et les validations. |
| Personnalisation avec une superposition de couches et des extensions. | Les extensions ne sont pas disponibles. | La version actuelle de Dynamics AX comporte un nouveau modèle de personnalisation. | Vous pouvez personnaliser le code source et les métadonnées des éléments modèles expédiés par Microsoft ou les partenaires Microsoft tiers. |
| Création de contrôles et d’éléments d’interface utilisateur à l’aide de X++ et d’une infrastructure Web moderne. | Les contrôles personnalisés reposent sur les infrastructures externes, notamment Microsoft ActiveX et Windows Presentation Foundation (WPF). | Il est plus simple de créer des contrôles dans la version actuelle. L’infrastructure X++ peut être utilisée pour le comportement et la logique métier de l’application, et un client basé sur HTML/JavaScript autorise des visualisations modernes. | Vos contrôles peuvent être conçus pour ressembler et se comporter exactement comme nos contrôles prêts à l’emploi Dynamics AX. |
| Évaluation et optimisation des performances à l’aide de nouveaux outils. | PerfSDK, l’outil d’extension des données, l’analyseur de suivi WEb et PerfTimer ne sont pas disponibles. | PerfSDK, l’outil d’extension des données, l’analyseur de suivi WEb et PerfTimer sont des nouveautés. | Le kit de développement logiciel (SDK) permet de tester et de valider tous les processus entreprise essentiels pour les performances de l’exécution du test mono-utilisateur et, le cas échéant, multi-utilisateur. L’outil d’extension des données vous permet de développer correctement tous les tests de performances qui doivent avoir des données principales et des données transactionnelles correctement développées. L’analyseur de suivi vous permet de valider l’exécution du test mono-utilisateur ou multi-utilisateur. Le PerfTimer vous permet de voir si une requête ou un appel de méthode spécifique entraîne un problème de performances. Vous n’avez donc pas à effectuer de suivi et analyser tout en détail. |
| Exposition de l’affichage pouvant être mis à jour à l’aide d’OData. | Non disponible | La version actuelle de Dynamics AX contient désormais un point de terminaison de service OData public qui active l’accès aux données de Dynamics AX de façon cohérente entre une large gamme de clients. | Les solutions peuvent interagir avec les services RESTful, partager des données de façon détectable, et activer une large intégration à l’aide du protocole de pile HTTP. |
| Tirez profit du Business Connector pour initier la logique métier et prendre en charge les scénarios d’intégration. | Le Business Connector peut être appelé dans le code X++ à partir du code géré. Il est recommandé de n’utiliser le Business Connector que pour créer de la logique métier dans C\#, pas pour les scénarios d’intégration. | Business Connector n’est plus pris en charge. L’exigence de conception est fournie par le fait que X++ est compilé en code managé. interop est par conséquent plus simple. Les scénarios d’intégration sont effectués à l’aide d’OData. | Dorénavant, vous ne pouvez plus utiliser Business Connector. |
| Choisissez l’échelle (autrement dit, le nombre de décimales) sur de vrais de champs de base de données et des Extended data types (EDT). | 16 est l’échelle par défaut et ne peut pas être modifiée par le développeur. | Les EDT et les champs ont désormais une propriété d’échelle qui peut être appliquée aux champs individuels et aux EDT. La valeur par défaut est de 6, pas de 16. | Les performances avec les tables NCCI (prises en charge en mémoire dans SQL) sont plus rapides par ordres de grandeur lorsqu’une échelle inférieure est utilisée. Modifiez l’échelle en fonction des besoins d’utilisation des différents champs. |

## <a name="financial-management"></a>Gestion financière

<table>
<thead>
<tr>
<th>Que pouvez-vous faire ?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Pourquoi est-ce important ?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Exportez les structures de compte vers Microsoft Excel.</td>
<td>Non disponible</td>
<td>Vous pouvez désormais sélectionner une structure de compte et l’exporter vers Excel.</td>
<td>Plusieurs clients ont demandé la possibilité d’exporter des structures de compte vers Excel pour un filtrage plus simple.</td>
</tr>
<tr>
<td>Affichage des comptes et des structures de règles avancées associées à une structure de compte dans une seule page.</td>
<td> L’utilisateur doit accéder à plusieurs écrans pour afficher la comptabilité et la structure de compte utilisées.</td>
<td>Les récapitulatifs ont été ajoutés à la page de structure de compte.</td>
<td>Il est plus simple d’accéder aux informations importantes lorsque les structures de compte sont définies et modifiées.</td>
</tr>
<tr>
<td>Possibilité d’afficher les comptabilités associées à un plan de comptes sur une seule page.</td>
<td>L’utilisateur doit accéder à chaque société et ouvrir l’écran de comptabilité pour voir le plan de comptes affecté à la comptabilité.</td>
<td>Les récapitulatifs ont été ajoutés à la page <strong>Plan de comptes</strong>.</td>
<td> Il est plus simple d’accéder aux informations importantes lorsqu’un plan de compte est défini et attribué.</td>
</tr>
<tr>
<td>Permet d’afficher la feuille d’ajustements et les transactions de clôture dans des colonnes distinctes dans la page de liste <strong>Balance comptable</strong>.</td>
<td>L’utilisateur peut seulement consulter les deux types de transactions dans une seule colonne.</td>
<td>Un paramètre supplémentaire a été ajouté la page de liste <strong>Balance comptable</strong>.</td>
<td>Il permet d’effectuer une analyse plus sommaire des données et est également requis pour la génération d’états de réglementation dans certains pays/certaines régions.</td>
</tr>
<tr>
<td>Utilisez la nouvelle page <strong>Journaux des opérations diverses globaux</strong>.</td>
<td>Non disponible</td>
<td>Nouvelle page <strong>Journaux des opérations diverses globaux</strong> pour saisir les journaux des opérations diverses. Les privilèges de cette page sont ajoutés au rôle <strong>Comptable</strong>.</td>
<td>Rend possible pour un comptable de service partagé d’entrer des journaux des opérations diverses entre ds sociétés sans avoir à quitter l’écran ni à changer le contexte de la société.</td>
</tr> 
<tr>
<td>Utilisez la nouvelle <strong>Explorateur de comptabilité source</strong>.</td>
<td>Disponible à partir de Dynamics AX 2012 R3 CU10.</td>
<td>Nouvelle page <strong>Explorateur de comptabilité source</strong> et nouvelles actions pour accéder à la page de liste <strong>Balance comptable</strong> et à la page <strong>Pièces comptables</strong>.</td>
<td>Facilite l’affichage d’informations plus détaillées relatives à la source d’une balance comptable ou d’une écriture comptable dans la comptabilité, ou pour une analyse ad-hoc.</td>
</tr>
<tr>
<td>Ajoutez des couches de validation supplémentaires.</td>
<td>L’ajout de couches de validation supplémentaires était une expérience de développeur.</td>
<td>Dix couches de validation sont désormais disponibles.</td>
<td>La plupart des clients ajoutent des couches de validation supplémentaires.</td>
</tr>
<tr>
<td>Utilisez l’option N° document lié.</td>
<td>Non disponible</td>
<td>L’option N° document lié est disponible pour que les utilisateurs affichent le document dans la société de contrepartie lors de la validation des transactions intersociétés. Depuis les n° documents associés, les utilisateurs peuvent cliquer sur les détails et accéder rapidement au document de la société de contrepartie.</td>
<td>Lors de la validation des transactions intersociétés, les utilisateurs n’avaient aucune visibilité ou ni aucun suivi du document qui était validé dans la société de contrepartie.</td>
</tr>
<tr>
<td>Clôture de période comptable en masse</td>
<td>Non disponible</td>
<td>Les utilisateurs peuvent mettre à jour l’accès au module et modifier le statut de la période pour plusieurs sociétés à la fois.</td>
<td>Avant cette fonctionnalité, les utilisateurs devaient modifier la société à laquelle ils étaient connectés, accédez à l’écran du calendrier comptable et mettre à jour manuellement l’accès du module et le statut de la période.</td>
</tr>
<tr>
<td>Avoir des taux de change générés par Oanda.</td>
<td>La configuration du fournisseur de taux de change pour importer les taux de Oanda était une expérience de développeur.</td>
<td>Si les utilisateurs disposent d’une clé pour Oanda, ils peuvent la saisir lors de la configuration du fournisseur de taux de change.</td>
<td>Les utilisateurs peuvent tirer parti des fonctionnalités prêtes à l’emploi en ayant des taux de change générés par Oanda importés de manière planifiée.</td>
</tr>
<tr>
<td>Filtrer les états financiers (Management Reporter) en fonction de dimensions, d’attributs, de dates et de scénarios.</td>
<td> Tous les filtrages des états Management Reporter sont gérés via la création de l’état. Par exemple, si un utilisateur ayant des privilèges d’affichage souhaite afficher un état pour une date différente, un concepteur d’état qui doit effectuer la modification.</td>
<td>Des options de génération d’états ont été ajoutées, de sorte qu’il est possible d’appliquer différents filtres lorsqu’un utilisateur affiche un état. Un nouvel état est ensuite généré à partir de ces filtres.</td>
<td>Les consommateurs d’états financiers peuvent appliquer différents filtres pour les dimensions, les dates, les attributs, les scénarios sans exiger de mises à jour pour déclarer des conceptions.</td>
</tr>
<tr>
<td>Afficher des états financiers (Management Reporter) au sein du client Microsoft Dynamics AX.</td>
<td>Un client Web distinct a été utilisé pour afficher les états de Management Reporter.</td>
<td>Tous les états financiers sont accessibles dans le client Dynamics AX. L’utilisateur sélectionne un état à afficher et celui-ci s’affiche dans le client.</td>
<td>Vous pouvez désormais afficher des états financiers sans avoir à accéder à un client/une candidature différent(e).</td>
</tr>
<tr>
<td>Imprimez des états financiers (Management Reporter) depuis le client Microsoft Dynamics AX.</td>
<td>L’impression d’un état utiliserait les options d’impression du navigateur pour l’impression et n’imprime que ce que l’utilisateur peut voir à l’écran.</td>
<td>L’utilisateur peut choisir le niveau de détail et la mise en page d’un état à l’aide de l’option d’impression de l’état financier dans le client Dynamics AX.</td>
<td>Impression d’états imprimés de la manière souhaitées par les utilisateurs au lieu d’imprimer une page web.</td>
</tr><tr>
<td>Analyser les données financières à l’aide du contenu Power BI « Surveiller les performances financières ».</td>
<td>Non disponible</td>
<td>Dans PowerBI.com, sélectionnez <strong>Obtenir des données</strong>, puis sélectionnez le pack de contenu <strong>Dynamics AX – Performances financières</strong>. Permet d’entrer l’URL de votre point de terminaison Dynamics AX pour afficher vos données répercutées dans le tableau de bord.</td>
<td>En trois à quatre clics, les organisations peuvent déployer un tableau de bord Power BI contenant des données financières importantes. Le contenu peut être personnalisé par l’organisation.</td>
</tr>
<tr>
<td>Suivi des processus de clôture de période comptable.</td>
<td>Non disponible</td>
<td>Les modèles et les programmes de clôture peuvent être créés à l’aide de la configuration de clôture de période comptable. Utilisez l’espace de travail <strong>Fermeture de période financière</strong> pour suivre la progression des programmes de clôture à travers plusieurs sociétés.</td>
<td>Cet espace de travail élimine les systèmes manuels pour définir, planifier, et communiquer les activités de clôture. Par conséquent, le nombre de jours à clôturer est réduit.</td>
</tr>
<tr>
<td>Surveillance de budget par rapport à la réalité, puis création les prévisions de comptabilité à l’aide de l’espace de travail <strong>Budgets comptables et prévisions</strong> et des écrans de recherche supplémentaires.</td>
<td>Non disponible</td>
<td> L’espace de travail peut être consulté via le tableau de bord de Dynamics AX. Il inclut des liens vers plusieurs nouvelles pages de recherche : <strong>Synthèse Réels/Budget</strong>, <strong>Synthèse Statistique du contrôle budgétaire</strong>, <strong>Écritures de registre budgétaires</strong>, et <strong>Plans budgétaires</strong>.</td>
<td>Les nouvelles pages de recherche permettent d’accéder simplement aux informations budgétaires. L’espace de travail combine toutes les tâches de mise à jour et de surveillance de budget dans un emplacement simple à utiliser pour les responsables comptables ou du budget.</td>
</tr>
<tr>
<td>Possibilité de créer des structures pour les plans budgétaires et les prévisions.</td>
<td>Le document <strong>Plan budgétaire</strong> s’affiche sous forme d’une liste de lignes ayant des dates d’effet et des montants pour les combinaisons des dimensions financières. L’utilisateur doit créer et utiliser des modèles Excel pour afficher des données du calendrier budgétaire dans un tableau croisé dynamique.</td>
<td>Un nombre illimité de structures est disponible pour les plans budgétaires et les prévisions. Vous pouvez combiner les dimensions financières sélectionnées, les colonnes définies par l’utilisateur, et d’autres attributs de ligne (tels que les commentaires, les projets, et des actifs) dans la structure. Les utilisateurs peuvent basculer la structure du document du plan budgétaire à la volée et modifier les données à l’aide de n’importe quelle structure sélectionnée. La configuration de la planification de budget est simplifiée en éliminant des contraintes de scénario et en employant des structures pour définir les données qui peuvent être affichées et modifiées à chaque étape du document du plan budgétaire.</td>
<td>Elle donne une certaine flexibilité pour créer et modifier les plans budgétaires à l’aide d’Excel et du client Dynamics AX. Les modèles de classeurs Excel peuvent être générés à l’aide du paramétrage de la structure de plan budgétaire.</td>
</tr>
<tr>
<td>Imprimez l’état <strong>Transactions de factures fournisseur</strong> à l’aide des informations de l’état <strong>Liste détaillée des dates d’échéance</strong>, qui inclut les jours de retard.</td>
<td>Vous devez imprimer deux états différents : <strong>Liste détaillée des dates d’échéance</strong> et <strong>Transactions de factures fournisseur</strong>.</td>
<td>Les informations sur les deux états ont été consolidées dans l’état <strong>Transactions de factures fournisseur</strong>. L’état <strong>Liste détaillée des dates d’échéance</strong> a été abandonné.</td>
<td>Il supprime la nécessité d’imprimer deux rapports distincts mais associés.</td>
</tr>
<tr>
<td>Génération d’états de réglementation directement au format PDF.</td>
<td>Vous devez tout d’abord générer un état de réglementation dans un format et ensuite l’exporter au format PDF.</td>
<td>Le format PDF est le format par défaut pour les états de réglementation.</td>
<td>Il fournit une expérience d’affichage unifiée sur les deux écrans d’ordinateur et une copie papier imprimée.</td>
</tr>
<tr>
<td>Exécution du processus de règlement de la taxe en tant que processus de traitement par lots.</td>
<td>Non disponible</td>
<td>Dans la page <strong>Période de règlement fiscal</strong>, vous pouvez spécifier que le processus de règlement doit être exécuté par lots.</td>
<td>Pour les périodes ayant plusieurs transactions de taxe, le processus de règlement peut être long, puis il peut être préférable d’exécuter le processus en arrière-plan en tant que processus de traitement par lots.</td>
</tr>
</tbody>
</table>

## <a name="foundation"></a>Fondation

<table>
<thead>
<tr>
<th>Que pouvez-vous faire ?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Pourquoi est-ce important ?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Accédez au client n’importe quand, n’importe où.</td>
<td>Le client de bureau AX 2012 fournit un ensemble complet d’écrans, mais il peut s’exécuter uniquement sur les ordinateurs qui exécutent Microsoft Windows et requiert l’installation. Terminal Server est souvent utilisé avec le client de bureau pour activer l’accès sur un réseau étendu (WAN). Le client Web Enterprise Portal fournit un ensemble d’écrans réduit.</td>
<td>Les deux clients AX 2012 ont été remplacés par un seul client Web simple, basé sur les normes, qui fournit l’ensemble complet de fonctionnalités du client de bureau avec la portée du client Enterprise Portal.</td>
<td>Il empêche les efforts de développement de se diviser entre deux plateformes d’IU. À l’aide des interfaces Web standard, cela élimine le besoin de serveur Terminal Server.</td>
</tr>
<tr>
<td>Soyez productif à l’aide du nouvel enregistreur de tâches.</td>
<td>L’enregistreur de tâches d’AX 2012 a besoin d’accès direct à un ordinateur Serveur d’objets d’application (AOS) et des privilèges élevés, et ne fournit pas d’option de modification.</td>
<td>Le nouvel Enregistreur de tâches peut être utilisé à partir du client web. L’accès à l’enregistreur de tâches ne nécessite pas de droits d’administrateur. Les étapes enregistrées peuvent être visualisées en direct lors de l’enregistrement, de nouvelles options de modification ont été introduites, et l’enregistreur de tâches prend en charge plus de scénarios en plus des scénarios Concepteur de processus d’entreprise (BPM) existants.</td>
<td>Le nouvel enregistreur de tâches fournit une expérience profilée et de nouvelles fonctionnalités dans Dynamics AX. Certaines de ces fonctionnalités sont désormais disponibles, d’autres suivront plus tard.</td>
</tr>
<tr>
<td>Aidez les utilisateurs à mieux comprendre leur travail à venir avec des espaces de travail.</td>
<td>Les Aperçus interactifs offrent une vue d’ensemble des informations qui correspondent à la fonction d’un utilisateur dans l’entreprise ou l’organisation.</td>
<td>Les espaces de travail sont un nouveau concept dans Dynamics AX qui sont destinés à remplacer les aperçus interactifs comme le moyen principal d’accéder aux tâches et à des pages spécifiques. Ils fournissent une vue d’ensemble sur une page d’une activité commerciale et permettent aux utilisateurs de comprendre l’état actuel, la charge de travail à venir et les performances du processus et de l’utilisateur. Les espaces de travail sont plus précis que les aperçus interactifs AX 2012, et un utilisateur peut avoir accès à plusieurs espaces de travail.</td>
<td>Les espaces de travail sont conçus pour augmenter la productivité des utilisateurs. Les développeurs devront créer un espace de travail pour chaque « activité » significative prise en charge par le produit. Un aperçu interactif hérité de AX 2012 sera en général remplacé par plusieurs espaces de travail dans la version actuelle de Dynamics AX.</td>
</tr>
<tr>
<td>Rendez les formulaires réactifs à la taille de fenêtre d’affichage du navigateur ou de l’appareil.</td>
<td>Dans AX 2012, le contenu d’un formulaire était disposé de manière rigide à l’aide de colonnes et la hauteur/largeur globale du formulaire était déterminée en grande partie selon les contrôles du formulaire.</td>
<td>Avec la touche MAJ enfoncée sur le web dans la dernière version de Dynamics AX, les dimensions d’un formulaire sont désormais basées sur la taille de fenêtre d’affichage du navigateur ou de l’appareil. Les contrôles et les paramètres de mise en page ont été modifiés ou ajoutés pour mieux répondre aux modifications de la taille de la fenêtre d’affichage.</td>
<td>Le contenu du formulaire doit être plus réactif pour utiliser de manière optimisale la hauteur/largeur disponible du navigateur ou de l’appareil. Devenir réactif peut nécessiter des modifications dans la façon dont un formulaire est modélisé.</td>
</tr>
<tr>
<td>Utilisez des modèles pour une expérience de développement de formulaire améliorée.</td>
<td>Les modèles de formulaire étaient disponibles comme point de départ pour le développement de formulaires dans AX 2012 en fonction d’un style de formulaire. Le correcteur de style de formulaire, complément facultatif, fournissait des informations sur les variations d’un formulaire par rapport à son modèle.</td>
<td>Dans la version actuelle de Dynamics AX, des modèles de formulaire ont été introduits. Les modèles de formulaire représentent une combinaison des modèles de formulaire et du correcteur de style de formulaire étroitement intégrés dans l’environnement de développement. Les modèles ont été définis au niveau du formulaire (par exemple, AX 2012) avec des sous-modèles supplémentaires maintenant disponibles au niveau de la page du groupe et de l’onglet.</td>
<td>Les formulaires conformes aux modèles présentent de nombreux avantages, notamment une interface utilisateur plus cohérente, une expérience de développement plus simple, un chemin d’accès là la mise à niveau du formulaire plus simple et une confiance accrue dans la réactivité de la mise en page de l’écran.</td>
</tr>
</tbody>
</table>

## <a name="help"></a>Affiche l’aide

<table>
<thead>
<tr>
<th>Que pouvez-vous faire ?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Pourquoi est-ce important ?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Accès à l’aide procédurale guidée (guides des tâches) et aux rubriques conceptuelles en cliquant sur <strong>Aide</strong>.</td>
<td>Le système d’aide AX 2012 pointe vers les rubriques HTML qui sont enregistrées sur un serveur Web local. Les partenaires et clients peuvent créer leur propre Aide.</td>
<td>Le système d’aide de la version actuelle de Dynamics AX affiche les guides de tâches qui sont enregistrés dans le BPM Microsoft Dynamics Lifecycle Services (LCS). Le système d’aide affiche également des rubriques à partir du site de documentation Microsoft. Pour en savoir plus, voir <a href="help-overview.md" data-raw-source="[Help system](help-overview.md)">Système d’aide</a> et <a href="new-task-guides-available-february-2016.md" data-raw-source="[New task guides (February 2016)](new-task-guides-available-february-2016.md)">Nouveaux guides de tâches (février 2016)</a>.</td>
<td>Un guide de tâche fournit une expérience contrôlée, guidée, interactive qui vous accompagne le long des étapes d’une tâche ou d’un processus métier. Vous pouvez télécharger et personnaliser les guides de tâches fournis par Microsoft. La rubrique explique un moyen plus rapide et plus souple de créer, de fournir et mettre à jour la documentation du produit. Par conséquent, il aide à garantir que vous avez accès aux dernières informations techniques.</td>
</tr>
</tbody>
</table>

## <a name="human-capital-management"></a>Gestion du capital humain

<table>
<thead>
<tr>
<th>Que pouvez-vous faire ?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Pourquoi est-ce important ?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Transfert de qualifications et de certificats aux stagiaires une fois le cours achevé.</td>
<td>Il s’agit d’un processus manuel.</td>
<td>Lorsqu’un cours est terminé, une nouvelle option devient disponible pour mettre à jour les enregistrements d’un participant avec les nouvelles qualifications et les nouveaux certificats.</td>
<td>Elle fournit une nouvelle manière efficace de mettre à jour les enregistrements d’un employé.</td>
</tr>
<tr>
<td>Vérifier rapidement les emplois.</td>
<td>Il s’agit d’un processus manuel.</td>
<td>Le service des ressources humaines peut rapidement vérifier les emplois à l’aide d’un espace de travail ou de la page de l’employé.</td>
<td>Le service des ressources humaines n’a plus à accéder à plusieurs pages pour vérifier la date de début, le responsable, la durée du poste, et les données de rémunération.</td>
</tr>
<tr>
<td>Possibilité de laisser les employés afficher, mettre à jour, et supprimer des informations dans le système.</td>
<td>Disponible, mais avec des capacités d’affichage et de mise à jour limitées.</td>
<td>Cette fonctionnalité est activée, et permet aux employés et aux fournisseurs d’afficher un large éventail de données personnelles. Le cas échéant, un workflow peut être utilisé lorsque les informations sont créées, mises à jour ou supprimées.</td>
<td>Cela permet aux employés de prendre le contrôle de leurs informations, que cela implique de mettre l’adresse ou les informations de contact à jour, de postuler à un travail, de répondre à un questionnaire, ou de mettre à jour leur image. Lorsqu’un workflow est activé, les informations peuvent être révisées par un approbateur ou être approuvées automatiquement, selon vos processus d’entreprise.</td>
</tr>
<tr>
<td>Les responsables ont la possibilité d’afficher ou de modifier les informations sur les employés.</td>
<td>Disponible, mais avec des capacités d’affichage et de mise à jour limitées.</td>
<td>En fonction des paramètres de configuration et de sécurité, les responsables peuvent afficher ou modifier les informations sur l’employé.</td>
<td>Cela permet aux responsables d’accéder aux données importantes sur l’employé, ils peuvent ainsi prendre de meilleures décisions sur le recrutement, les performances, et le développement de l’employé.</td>
</tr>
<tr>
<td>Tirez parti des fonctionnalités de libre-service de gestionnaire.</td>
<td>Non disponible</td>
<td>Les responsables peuvent désormais envoyer des demandes pour les nouvelles recrues (employés et sous-traitants), les transferts et les fins de contrats (fin de l’emploi). Les gestionnaires peuvent également demander un nouveau poste, étendre une durée d’emploi ou demander des modifications de poste.</td>
<td>Ces scénarios étaient précédemment uniquement exposés aux ressources humaines. L’activation de ces scénarios fournit des outils puissants aux responsables dans une organisation. Des workflows facultatifs peut être activés pour fournir le bon niveau de révision et d’approbation.</td>
</tr>
<tr>
<td>Accès aux résultats du traitement de la rémunération.</td>
<td>Les résultats sont uniquement disponibles au moment du traitement.</td>
<td>Les résultats du traitement de la rémunération peuvent désormais être consultés à tout moment une fois le processus exécuté.</td>
<td>Cela fournit un excellent audit du processus et des résultats du processus. Cela fournit également une vue complète des données avant que les enregistrements d’employé soient mis à jour.</td>
</tr>
<tr>
<td>Accès aux résultats du traitement des avantages.</td>
<td>Les résultats sont uniquement disponibles au moment du traitement.</td>
<td>Les résultats du traitement des avantages peuvent désormais être consultés à tout moment une fois le processus exécuté.</td>
<td>Cela fournit une vue complète des données qui sont mises à jour par l’inscription aux avantages et les modifications de coûts.</td>
</tr>
<tr>
<td>Affichage des modifications du calendrier « Date d’effet ».</td>
<td>Non disponible</td>
<td>Cet outil de comparaison est disponible pour les employés, les postes et les tâches. Il fournit une vue complète des modifications d’une version d’un enregistrement à une autre.</td>
<td>Il vous permet de gagner du temps lorsque vous affichez les modifications qui ont eu lieu dans les enregistrements des employés, des postes et des tâches. Il vous permet de comparer rapidement deux versions d’un enregistrement, ou tous les enregistrements, au fil du temps.</td>
</tr>
<tr>
<td>Affichage des employés par société.</td>
<td>Il s’agit d’un processus manuel qui est effectué via le filtrage.</td>
<td>Les listes des employés et des fournisseurs sont automatiquement filtrées par la société à laquelle vous êtes connecté.</td>
<td>Cela fournit une vue filtrée des employés qui travaillent dans la société connectée. Si vous souhaitez une vue non filtrée de tous les employés et fournisseurs, la liste des collaborateurs est encore disponible. Dans la version actuelle de Dynamics AX, le système ne modifie pas la société en fonction de l’employé sélectionné dans la liste.</td>
</tr>
<tr>
<td>Mise à jour de la liste des participants au cours.</td>
<td>Non disponible</td>
<td>Les participants aux cours peuvent être supprimés de la liste des participants.</td>
<td>Cela fournit une manière unique de mettre à jour les participants aux cours enregistrés par erreur.</td>
</tr>
<tr>
<td>Gestion des événements de rémunération dans un groupe.</td>
<td>Non disponible</td>
<td>Cette fonctionnalité rationalise le traitement des modifications de rémunération pour les employés.</td>
<td>Elle fournit un processus simplifié pour mettre à jour les enregistrements des employés via l’espace de travail de rémunération et les pages associées.</td>
</tr>
</tbody>
</table>

## <a name="inventory-management"></a>Gestion des stocks

Aucune nouvelle fonctionnalité n’a été ajoutée :

## <a name="localization"></a>Localisation

<table>
<thead>
<tr>
<th>Que pouvez-vous faire ?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Pourquoi est-ce important ?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Configuration et génération de documents électroniques pour répondre aux obligations légales dans plusieurs pays/régions.</td>
<td>Les documents électroniques sont codés de manière irréversible en X++ ou en tant que transformations XSLT (Extensible Stylesheet Language Transformations). Tous les ajustements de format requièrent des efforts de développement. L’accès aux données et à la mise en forme n’est pas isolé. Un déploiement ajusté du format nécessite un nouveau correctif logiciel de Microsoft Dynamics AX qui remplace le format existant. Les modifications personnalisées de chaque format doivent être déplacées manuellement vers le code source d’un nouveau correctif logiciel de Microsoft Dynamics AX.</td>
<td>La génération d’états électroniques est un nouvel outil pour configurer et générer des documents électroniques qui visent les utilisateurs professionnels plutôt que les développeurs. Les états électroniques permettent de paramétrer les modèles de données qui sont spécifiques au domaine et indépendants de la base de données Microsoft Dynamics AX comme source de données pour les formats des documents. Un utilisateur professionnel peut configurer les formats, selon ces modèles de données spécifiques au domaine (par exemple, pour les paiements, les états de déclaration d’échanges de biens, ou les déclarations de taxe). L’utilisateur configure les formats à l’aide d’outils visuels simples qui sont similaires à Excel. Les états électroniques prennent en charge la génération de documents électroniques aux formats texte, XML et Excel. Ces documents peuvent être générés simultanément et compressés dans des fichiers zip. Les modèles et les formats de données prennent en charge le contrôle de versions. Les versions de format peuvent avoir des périodes d’effet. Chaque version du modèle de données ou du format est enregistrée dans une configuration distincte et distribuée aux partenaires et aux clients via LCS. Les partenaires et les clients peuvent personnaliser les modèles de données et les formats Microsoft, ou créez les leurs. Les états électroniques enregistrent les modifications apportées à la configuration des partenaires et des clients en tant que deltas aux exigences de Microsoft, ce qui simplifie les mises à niveau des nouvelles versions des configurations Microsoft. Avec LCS, les partenaires peuvent également partager les configurations de format et de modèle de données avec d’autres partenaires et clients, qui peuvent ensuite les personnaliser et les partager. La personnalisation delta et la mise à jour simple sont prises en charge via toute la chaîne de personnalisation.</td>
<td>Les états électroniques simplifient la création, la maintenance, et la mise à niveau des formats des documents électroniques pour répondre aux obligations légales dans plusieurs pays/régions. Les états électroniques rendent le processus de création ou de modification des présentations des documents électroniques plus rapide et plus simple. Ces modifications peuvent être apportées par des utilisateurs professionnels plutôt que des développeurs. Les états électroniques permettent aux partenaires et aux clients de mettre à niveau plus rapidement et plus facilement les personnalisations du format vers de nouvelles versions de format lancées par Microsoft ou d’autres partenaires. Les états électroniques fournissent une façon commune (via LCS) pour Microsoft et les partenaires de distribuer des configurations de document électronique à d’autres partenaires et clients. Les états électroniques permettent également aux partenaires et aux clients de personnaliser, de mettre à niveau et de diffuser facilement des présentations des documents électroniques pour répondre aux exigences métier spécifiques.</td>
</tr>
<tr>
<td>États de réglementation (MEX) Generate Mexican value-added tax (VAT).</td>
<td>Vous devez générer des états <strong>TVA sur ventes et achats</strong> à l’aide de la fonctionnalité TVA non réalisée, afin que les utilisateurs puissent identifier les transactions appartenant aux sections réalisées et non réalisées en fonction du statut.</td>
<td>Les états <strong>TVA sur ventes et achats</strong> ont été modifiés et prennent en compte à présent la fonctionnalité de taxe conditionnelle uniquement à l’aide de périodes de règlement spécifiques pour la définition des codes taxe non réalisés et réalisés.</td>
<td>Des modifications de la configuration de codes taxe sont requises avant que les utilisateurs puissent générer ces états correctement. Une fonctionnalité de taxe conditionnelle est nécessaire, et l’utilisateur doit configurer des périodes de règlement distinctes, non réalisées et réalisées, pour identifier les transactions dans les sections associées.</td>
</tr>
<tr>
<td>(JPN) Gestion du document de déclaration d’amortissement accéléré d’immobilisations japonais.</td>
<td>Non disponible</td>
<td>Les informations de déclaration importantes sont stockées de manière centralisée dans un document unique pour une meilleure mise à jour.</td>
<td>La conformité des documents et la facilité de gestion réduisent les problèmes lors des audits et des examens.</td>
</tr>
<tr>
<td>(JPN) Vérification des caractères JBA sur le compte bancaire.</td>
<td>Non disponible</td>
<td>Vous pouvez vérifier que les champs de nom kana contiennent uniquement les caractères autorisés par le format bancaire JBA.</td>
<td>Cela évite que les utilisateurs soient interrompus lors de la génération du fichier de paiement en raison de caractères non valides.</td>
</tr>
<tr>
<td>(JPN) Rattrapage de la différence minimale d’immobilisation au Japon à la fin de l’exercice.</td>
<td>Non disponible</td>
<td>Dans la page <strong>Paramètres d’immobilisation</strong>, vous pouvez choisir d’effectuer le rattrapage à la fin de la période fiscale ou de l’exercice.</td>
<td>Cela offre davantage de flexibilité pour correspondre aux pratiques locales.</td>
</tr>
<tr>
<td>(JPN) Génération d’une série de 16 tableaux ajoutés à la déclaration de taxe d’entreprise japonaise à un montant récapitulé par type d’immobilisation principal.</td>
<td>Non disponible</td>
<td>Dans les modèles de valeur d’une immobilisation, vous pouvez choisir de résumer par type principal. Par défaut, cette fonctionnalité est utilisée pour les immobilisations nouvellement créées.</td>
<td>Pour les grandes sociétés qui ont des milliers d’immobilisations, les états récapitulés réduisent considérablement la taille de l’état généré.</td>
</tr>
<tr>
<td>(JPN) Début de l’attribution de la réserve d’amortissement spéciale à partir de l’exercice suivant pour les immobilisations au Japon.</td>
<td>Non disponible</td>
<td>Dans les modèles de valeur d’une immobilisation ayant un profil d’amortissement exceptionnel approprié, vous pouvez choisir de commencer la répartition à partir de la période fiscale suivante ou de l’exercice suivant.</td>
<td>Cela offre davantage de flexibilité pour correspondre aux pratiques locales.</td>
</tr>
<tr>
<td>(JPN) Génération d’un état de taxe sur la consommation du Japon incluant les taux de taxe modifiés.</td>
<td>L’état de taxe sur la consommation est disponible pour un taux de taxe de 5 %.</td>
<td>L’état de taxe sur la consommation contient une section pour le taux de taxe modifié (par exemple, 8 %).</td>
<td>Cette disposition a été récemment annoncée par le gouvernement.</td>
</tr>
<tr>
<td>(UE) Configurez les paramètres de l’arrondi de la liste des ventes intracommunautaires.</td>
<td>Les paramètres d’arrondi de la liste des ventes intracommunautaires de différents pays/régions sont codés de manière irréversible dans X++ ou les transformations de documents XSLT (Extensible Stylesheet Language Transformations).</td>
<td>Les paramètres d’arrondi sont ajoutés aux paramètres de commerce extérieur. Vous pouvez configurer la précision de l’arrondi, la méthode, la précision de sortie et le comportement des montants inférieurs à la précision d’arrondi.</td>
<td>Cela permet d’unifier et de simplifier la configuration de la déclaration de la liste des ventes intracommunautaires. Les paramètres d’ajustement de l’arrondi n’exigent plus d’efforts de développement.</td>
</tr>
<tr>
<td>(UE) Configurez les règles d’application de la taxe au preneur.</td>
<td>Les règles d’application de la taxe au preneur sont codées de manière irréversible pour le scénario de taxe au preneur. Le seuil d’application peut être configuré par groupe d’articles. Cette fonctionnalité est disponible pour la Grande-Bretagne uniquement.</td>
<td>Vous pouvez configurer des règles d’application de taxe au preneur par type de document (commande fournisseur/client, facture fournisseur, facture financière, etc.) et un groupe de taxe au preneur qui combine des articles, groupes d’articles et catégories d’achat/de vente. Les règles d’application sont soumises à la date d’effet. Vous pouvez également marquer les codes de taxe individuels dans les groupes de taxe applicables à la taxe au preneur. L’état de facture de vente est ajusté pour représenter les détails de la taxe au preneur appliquée. La fonctionnalité est disponible pour tous les pays/régions d’Europe.</td>
<td>Cette modification unifie la configuration des règles d’application de la taxe au preneur et prend en charge l’adoption des règlements nationaux sur la taxe au preneur par pays/régions d’Europe.</td>
</tr>
<tr>
<td>(DE) Générer le fichier d’audit allemand - GDPdUGoBD</td>
<td>Les utilisateurs peuvent configurer la définition de tables contenant des données financières à exporter dans un format accepté par les autorités et les auditeurs allemands.</td>
<td>La fonctionnalité a été implémentée comme configuration de génération d’états électroniques. Cette fonctionnalité est disponible pour l’Allemagne et l’Autriche.</td>
<td>Cette modification offre à l’utilisateur beaucoup plus de possibilités de formatage des données, de transformations, ainsi que tous les avantages provenant de la gestion du cycle de vie de la configuration des états électroniques, comme l’échange de configuration, le contrôle des versions, etc..</td>
</tr>
<tr>
<td>(FR) État de liste du solde avec comptes de groupe de type total.</td>
<td>L’état Liste du solde avec comptes de groupe de type total est implémentée en tant qu’état SSRS (LedgerAccountSum_FR).</td>
<td>L’état Liste du solde avec comptes de groupe de type total est implémentée en tant qu’état Management Reporter disponible dans le dossier États financiers localisés dans la bibliothèque d’actifs LCS.</td>
<td>Cela permet aux utilisateurs d’obtenir tous les avantages et la liberté des personnalisations de l’utilistaion d’états financiers dans Management Reporter.</td>
</tr>
<tr>
<td>(UE) États des avis de paiement, notes de participation et contrôles pour les paiements.</td>
<td>Tous ces états sont mis en œuvre et états SSRS.</td>
<td>Ces états ont été implémentés en tant que modèles Open XML à utiliser dans Microsoft Excel.</td>
<td>Les configurations de paiement électronique contiennent des modèles et des paramètres de format de fichier de paiement. Cela permet aux utilisateurs d’obtenir tous les avantages et la liberté des personnalisations d’états de l’utilistaion d’états financiers.</td>
</tr>
<tr>
<td>(UE) Configurez les paramètres de l’arrondi de la déclaration d’échanges de biens.</td>
<td>Les paramètres d’arrondi de la déclaration d’échanges de biens de différents pays/régions sont codés de manière irréversible dans X++ ou les transformations de documents XSLT (Extensible Stylesheet Language Transformations).</td>
<td>Les paramètres d’arrondi sont ajoutés aux paramètres de commerce extérieur. Vous pouvez configurer la précision de l’arrondi, la méthode, la précision de sortie et le comportement des montants inférieurs à la précision d’arrondi.</td>
<td>Cela permet d’unifier et de simplifier la configuration de l’état de la déclaration d’échanges de biens. Les paramètres d’ajustement de l’arrondi n’exigent plus d’efforts de développement.</td>
</tr>
<tr>
<td>(UE) Configuration des codes de marchandise de déclaration d’échanges de biens dans les hiérarchies de catégories.</td>
u<td>Les codes de marchandise de la déclaration d’échanges de biens est une liste séparée. Bien qu’il existe une hiérarchie de catégories de type Code de marchandise, ces codes de marchandises pouvaient être affectés par défaut dans Retail HQent et les catégories de ventes.</td>
<td>Une liste distincte des codes de marchandises de la déclaration d’échanges de biens est fusionnée avec la hiérarchie des produits du type Code de marchandise.</td>
<td>Cela unifie l’approche pour affecter des codes de marchandises aux produits lancés et aux catégories dans les documents de vente et d’achat.</td>
</tr>
<tr>
<td>(UE) Déclarez la quantité dans les unités supplémentaires pour la déclaration d’échanges de biens à l’aide du paramètre de conversion d’unité.</td>
<td>Le code de marchandise de la déclaration d’échanges de biens a un champ de texte pour identifier les unités supplémentaires et la carte <strong>Produit</strong> a un champ pour identifier la quantité d’unités supplémentaires en kilogrammes.</td>
<td>Les unités supplémentaires du code de marchandise de la déclaration d’échanges de biens sont choisies dans la liste des unités. La quantité d’unités supplémentaires est calculée au moyen des paramètres de conversion d’unité.</td>
<td>Cela unifie l’approche pour le nouveau calcul d’unités de transaction dans les unités supplémentaires.</td>
</tr>
<tr>
<td>(UE) Affectez la méthode de transport par défaut au mode de livraison.</td>
<td>Non disponible</td>
<td>Un champ pour la méthode de transport par défaut est ajouté au mode de livraison.</td>
<td>Cela simplifie la préparation de la génération de déclaration d’échanges de biens.</td>
</tr>
<tr>
<td>(UE) Marquez le produit lancé à ne pas déclarer dans la déclaration d’échanges de biens.</td>
<td>Non disponible</td>
<td>Une option pour exclure l’article de l’état de la déclaration d’échanges de biens est ajoutée au produit lancé.</td>
<td>Cela simplifie la préparation de la génération de déclaration d’échanges de biens.</td>
</tr>
</tbody>
</table>

## <a name="manufacturing"></a>Fabrication

| Que pouvez-vous faire ? | Dynamics AX 2012 |
|------------------|------------------|
| Effectuez une vérification de la disponibilité des matières premières pour les ordres de fabrication sur une page indépendante ouverte à partir de l’espace de travail **Gestion de l’atelier de production**. | Non disponible |
| Vous pouvez démarrer et déclarer la progression des tâches de production à l’aide de la nouvelle page **Périphérique pour le bon de travail**. | L’écran **Enregistrement de tâche** vise principalement les grands écrans, et la consultation de l’IU se fait généralement par clics de souris. |

## <a name="master-planning-and-forecasting"></a>Planification et prévisions

| Que pouvez-vous faire ? | Dynamics AX 2012 | Dynamics AX 7.0 | Pourquoi est-ce important ? |
|------------------|------------------|-----------------|------------------------|
| Prévenez l’utilisateur si une commande client ou un ordre de fabrication n’est pas prêt pour la livraison à la date prévue. | Les avertissements créés par la planification sont appelés *messages de perspectives*. Un contrat de type *Perspectives* est un contrat entre deux parties pour acheter ou vendre une immobilisation à un prix convenu le jour même (le *prix des perspectives*), bien que la livraison et le paiement se produisent à une date ultérieure (la *date de livraison*). | Les *messages de perspectives* et les *dates à venir* ont été renommés *retards calculés* et *dates retardées*, respectivement. | La terminologie utilisée dans AX 2012 était inexacte et provoquait des traductions incorrectes. |
| Possibilité d’obtenir une analyse rapide du statut d’exécution d’une planification, des ordres prévisionnels urgents, et des ordres prévisionnels qui provoquent des retards. | Les informations sont disponibles, mais elles ont dispersées entre plusieurs écrans. | L’espace de travail **Planification** offre un aperçu de la date de la dernière exécution de la planification, si des erreurs ont eu lieu, quels sont les ordres prévisionnels urgents et quels ordres prévisionnels ont provoqué des retards. | Vous tirez profit de la vue d’ensemble fournie par l’espace de travail. Les informations pertinentes sont rassemblées pour guider la planification et aider à améliorer la productivité. |
| Utilisation d’Excel pour mettre à jour les prévisions de la demande. | Non disponible | Vous pouvez tirer profit de l’intégration transparente dans Excel lorsque vous entrez des prévisions de la demande, que vous effectuez les mises à jour, et que vous supprimez des prévisions de la demande. | Cela permet d’augmenter le rendement et la productivité. |
| Estimez la demande future et de créer des prévisions de la demande en fonction des données de transaction historiques. | Dans Microsoft Dynamics AX 2012 R3, les modèles prévus dans le service d’analyse Microsoft SQL Server sont utilisés pour créer des prévisions de la demande. | Estimation des demande futures à l’aide de la puissance et de l’extensibilité d’un service cloud Microsoft Azure Machine Learning. Il est facile d’utiliser et d’étendre les modèles de prévision dans Machine Learning pour répondre aux exigences des clients. Le service sélectionne le modèle qui concorde le mieux et offre des indicateurs de performance clés (KPI) pouvant servir à calculer l’exactitude de la prévision. | Génération de prévisions plus exactes à l’aide de techniques d’apprentissage automatique. |
| Optimisation de la date et de la quantité de commande, selon une vue d’ensemble des actions associées à partir de l’exécution d’une planification générale. | La vue d’ensemble du graphique des actions est disponible mais affiche toutes les actions associées. Lorsque des actions sont appliquées, elles disparaissent immédiatement de la vue. | Le graphique des actions fournit une meilleure vue d’ensemble. Il inclut les options qui permettent d’afficher uniquement les actions appliquées et des actions directement associées. Lorsque des actions sont appliquées, elles semblent estompées mais sont toujours affichées. Par conséquent, la vue d’ensemble est conservée. Les informations supplémentaires sont ajoutées au plan d’actions pour afficher les données dans une page. | Vous tirez bénéfice de l’amélioration de la productivité, car vous pouvez vous concentrer uniquement sur les actions appropriées. |

## <a name="procurement-and-sourcing"></a>Approvisionnements

| Que pouvez-vous faire ? | Dynamics AX 2012 | Dynamics AX 7.0 | Pourquoi est-ce important ? |
|------------------|------------------|-----------------|------------------------|
| Utilisez l’espace de travail **Préparation des commandes fournisseur** pour obtenir une analyse rapide du statut de commandes fournisseur qui sont préparées. | Non pris en charge | L’espace de travail **Préparation des commandes fournisseur** offre une vue d’ensemble des commandes à partir de la date de leur création en tant que brouillon et de leur suivi, via les états d’approbation de workflow, puis ultérieurement en vue d’une confirmation. | Votre département Achats n’a plus à rechercher des informations sur plusieurs pages mais tire profit de la mise à jour de la vue d’ensemble fournie par l’espace de travail. |
| Utilisez l’espace de travail **Réception et suivi de commande fournisseur** pour obtenir une analyse rapide des commandes fournisseur en attente de réception pour aider au niveau du suivi. | Non pris en charge | L’espace de travail **Réception et suivi de commande fournisseur** offre une vue d’ensemble des commandes fournisseur confirmées qui sont en attente de réception ou d’expédition. L’espace de travail inclut des listes de réceptions en retard et en attente pour aider la révision proactive et le suivi par le fournisseur. L’espace de travail liste également les commandes fournisseur pour lesquelles l’enregistrement d’arrivée a eu lieu dans l’entrepôt, afin de garantir que la réception est validée. Les retours de commande fournisseur qui n’ont pas encore été expédiées sont également disponibles pour révision. | Le département Achats tire bénéfice de la vue d’ensemble fournie par l’espace de travail. Les informations pertinentes sont rassemblées pour guider le suivi et aider à améliorer la productivité. |
| Envoi des commandes fournisseur pour confirmation à un portail fournisseur hébergé dans le client Dynamics AX. Possibilité de laisser le fournisseur confirmer ou rejeter. | Non pris en charge | L’interface du portail fournisseur permet aux fournisseurs de recevoir des commandes fournisseur à confirmer ou à rejeter. Il permet également au fournisseur d’avoir une vue d’ensemble de toutes les commandes fournisseur confirmées pour un compte. L’agent des achats peut soumettre une commande fournisseur nécessitant une confirmation du fournisseur. Le fournisseur doit être un utilisateur AAD enregistré dans Microsoft Azure Active Directory (Azure AD) dans Dynamics AX, une personne à contacter pour le fournisseur et avoir un rôle de sécurité dédié. | Votre département Achats tire bénéfice de la réduction de paperasserie et peut tenir à jour manuellement les réponses sur les commandes fournisseur, car le flux va directement dans le système. Le fait d’avoir une seule source d’informations réduit les malentendus entre le client et le fournisseur. |

## <a name="projects"></a>Projets

| Que pouvez-vous faire ? | Dynamics AX 2012 | Dynamics AX 7.0 | Pourquoi est-ce important ? |
|------------------|------------------|-----------------|------------------------|
| Réservation des collaborateurs comme ressources pour des projets. | Similaires aux ressources, les collaborateurs sont réservés directement dans les projets en plus des ressources. | La table Poste de charge où les ressources pour la fabrication et la production sont enregistrées peut désormais être utilisée pour réserver des collaborateurs en tant que ressources pour un projet. | Lorsque vous réservez des projets, vous devez uniquement réserver les ressources. |

## <a name="retail-sales-marketing-and-customer-service"></a>Ventes au détail, marketing et service client

### <a name="retail-hq"></a>Siège social de Retail

Le siège social de Retail hébergé par Microsoft Azure offre une gestion centralisée et une visibilité complète de tous les aspects des opérations commerciales via un client Web.

<table>
<thead>
<tr>
<th>Que pouvez-vous faire ?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Pourquoi est-ce important ?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Possibilité d’exécuter des opérations de promotion des ventes.</td>
<td>Les utilisateurs doivent accéder à plusieurs écrans pour gérer ces données :
<ul>
<li>Gestion des catégories</li>
<li>Gestion des produits</li>
<li>Attributs de produit de canal</li>
<li>Assortiments</li>
<li>Gestion du catalogue</li>
<li>Kits</li>
<li>Prix et remises</li>
</ul></td>
<td>L’espace de travail <strong>Gestion des catégories et des produits</strong> active les fonctionnalités suivantes :
<ul>
<li>Gestion des assortiments.</li>
<li>Suivi de cycle de vie des assortiments.</li>
<li>Gestion des produits lancés.</li>
</ul>
L’espace de travail <strong>Gestion des remises et des produits</strong> active les fonctionnalités suivantes :
<ul>
<li>Gestion des remises et des produits pour un canal et une catégorie donnés.</li>
<li>Gestion de règles de prix de catégorie.</li>
<li>Priorités des prix et des remises, qui vous permettent d’affecter des priorités aux groupes de prix et aux remises, afin de pouvoir contrôler les commandes auxquelles elles sont appliquées.</li>
<li>Gestion des remises de catalogue et des affiliations.</li>
</ul>
L’espace de travail <strong>Gestion du catalogue</strong> active les fonctionnalités suivantes :
<ul>
<li>Synthèse des catalogues actifs.</li>
<li>Suivi de cycle de vie du catalogue dans un seul emplacement.</li>
</ul></td>
<td><ul>
<li>Les espaces de travail améliorent le rendement et la productivité des collaborateurs en les laissant gérer de façon centralisée leurs tâches et leurs actions associées à la vente.</li>
<li>La fonctionnalité en matière de priorité des prix et des remises donne aux clients plus de contrôle sur la manière dont les prix et les remises sont utilisés. La fonctionnalité active également de nouveaux scénarios dans lesquels les prix les plus élevés en magasin l’emportent sur les prix standard.</li>
</ul></td>
</tr>
<tr>
<td>Gestion des déploiements et des opérations de canal de vente au détail.</td>
<td>L’utilisateur doit accéder à plusieurs écrans pour effectuer les tâches suivantes :
<ul>
<li>Créer et configurer de nouveaux canaux et les entités associées.</li>
<li>Gérer les activités de travail quotidiennes du magasin.</li>
<li>Traitez les transactions de vente au détail dans Microsoft Dynamics AX, générez les relevés de vente au détail et mettez à jour le stock et les finances de Microsoft Dynamics AX.</li>
</ul>
</td>
<td>L’espace de travail <strong>Déploiement de canal</strong> permet d’effectuer les tâches suivantes :
<ul>
<li>Créer de nouveaux canaux et les entités associées.</li>
<li>Suivre la progression de la configuration du magasin de vente au détail.</li>
<li>Faire le nécessaire pour exécuter une tâche ou fournir des informations pour effectuer la tâche.</li>
<li>Suivre le statut des périphériques, puis valider et télécharger directement l’installation du programme Retail Modern POS (MPOS) dans les magasins.</li>
<li>Accéder à toutes les pages associées.</li>
</ul>L’espace de travail 
<strong>Gestion du magasin de vente au détail</strong> permet d’effectuer les tâches suivantes :
<ul>
<li>Gérer les collaborateurs et les autorisations de point de vente (PDV) associées.</li>
<li>Suivre le statut de l’équipe de travail pour un magasin ou un groupe de magasins donnés.</li>
<li>Valider et télécharger directement l’installation du programme MPOS dans les magasins.</li>
<li>Imprimer des états et accéder aux pages associées.</li>
</ul>L’espace de travail 
<strong>Finances du magasin de vente au détail</strong> permet d’effectuer les tâches suivantes :
<ul>
<li>Créer, calculer et valider des relevés pour un canal donné.</li>
<li>Programmer les traitements par lots pour mettre à jour le stock, puis calculer et valider les instructions.</li>
<li>Suivre les relevés en cours.</li>
<li>Suivre le statut de l’équipe de travail pour un magasin ou un groupe de magasins donnés.</li>
<li>Imprimer des états et accéder rapidement à toutes les pages associées.</li>
</ul></td>
<td>Les espaces de travail améliorent le rendement et la productivité des collaborateurs en les laissant gérer de façon centralisée la plupart de leurs tâches et de leurs actions associées au déploiement de canaux, à la gestion de magasin et aux finances.</td>
</tr>
<tr>
<td>Gérer les opérations d’informatique au détail.</td>
<td>L’utilisateur doit accéder à plusieurs écrans.</td>
<td>L’espace de travail <strong>Informatique au détail</strong> active les recherches de Commerce Data Exchange dans un emplacement unique pour un canal donné, afin que vous puissiez effectuer les tâches suivantes :
<ul>
<li>Télécharger des sessions.</li>
<li>Charger des sessions.</li>
<li>Effectuer le suivi des sessions qui ont échoué, et les reprendre ou les exécuter à nouveau.</li>
<li>Afficher ou exécuter les tâches futures.</li>
</ul></td>
<td>Les espaces de travail améliorent le rendement et la productivité des collaborateurs en les laissant gérer de façon centralisée les tâches et les actions associées aux opérations d’informatique au détail.</td>
</tr>
<tr>
<td>Importer/exporter des données à l’aide des entités de données.</td>
<td>AX 2012 prend en charge la migration de Microsoft Dynamics Retail Management System (RMS) prête à l’emploi via l’environnement d’importation/exportation des données.</td>
<td>Les entités de données commercialisées ont été développées pour prendre en charge les données principales et les données de référence associées à la vente au détail. La prise en charge des entités de données a également été améliorée dans toute la solution Dynamics AX.</td>
<td>Les entités de données permettent aux clients d’effectuer des importations et des exportations des données fondées sur les métadonnées. Les entités OData permettent également aux clients d’intégrer Dynamics AX dans les programmes tiers.</td>
</tr>
<tr>
<td>Possibilité d’effectuer des analyses intelligentes à l’aide des états BI de Dynamics Microsoft AX et du client POS.</td>
<td>Plus de 25 états de BackOffice et cinq états côté canal sont disponibles.</td>
<td>Plus de 30 états de BackOffice et 10 états côté canal sont disponibles.</td>
<td>Ces états permettent aux clients d’avoir plus de BI pour prévoir les tendances, pour découvrir des analyses, et pour fonctionner constamment à des pics de performances.</td>
</tr>
<tr>
<td>Possibilité d’analyser des données de ventes du canal de vente au détail à l’aide du contenu Power BI « Surveiller Retail Channel Performance ».</td>
<td>Non disponible</td>
<td>Dans PowerBI.com, sélectionnez <strong>Obtenir des données</strong>, puis sélectionnez le pack de contenu <strong>Dynamics AX – Retail Channel Performance</strong>. Permet d’entrer l’URL de votre point de terminaison Dynamics AX pour afficher vos données répercutées dans le tableau de bord.</td>
<td>En trois à quatre clics, les organisations peuvent déployer un tableau de bord Power BI contenant des données financières importantes. Le contenu peut être personnalisé par l’organisation. En outre, les utilisateurs peuvent incorporer des vignettes de tableau de bord Power BI dans leurs espaces de travail personnalisés dans Dynamics AX, afin de pouvoir ensuite consulter les informations analytiques d’un seul coup d’œil.</td>
</tr>
<tr>
<td>Configurer des autorisations client.</td>
<td>Non disponible</td>
<td>Les clients peuvent choisir si les opérations de PDV sont mises à disposition des consommateurs ou non. Le serveur de vente au détail utilise les autorisations pour les appels de l’API de téléphonie (TAPI).</td>
<td>Il permet de configurer les autorisations au niveau consommateur.</td>
</tr>
<tr>
<td>Possibilité de gérer et de valider des configurations d’entité.</td>
<td>Non disponible</td>
<td>La fonctionnalité de validateur et de gestionnaire de configuration active les fonctions suivantes :
<ul>
<li>Chargement en bloc des données de configuration</li>
<li>Validation de l’entité commerciale</li>
</ul></td>
<td>Cela permet de démarrer la configuration, puis de valider le statut et l’exhaustivité de la configuration pour les divers éléments de configuration.</td>
</tr>
</tbody>
</table>

### <a name="retail-hardware-station"></a>Station matérielle de vente au détail

| Que pouvez-vous faire ? | Dynamics AX 2012 | Dynamics AX 7.0 | Pourquoi est-ce important ? |
|------------------|------------------|-----------------|------------------------|
| Possibilité d’activer les périphériques du PDV pour se connecter à des périphériques tels que des imprimantes, des tiroirs-caisses, ou des appareils de paiement. | Le profil matériel de MPOS permet de spécifier les périphériques utilisés. | Un profil matériel ajouté prend en charge des matériaux plus divers d’une station à l’autre. Un nouveau profil de station matérielle prend en charge un seul ID de terminal pour chaque station matérielle lorsque des transactions de transfert électronique de fonds (TEF) sont traitées. La prise en charge de TEF a été fusionnée dans la station matérielle pour réduire l’implication de MPOS dans le traitement des paiements de TEF. | Cela fournit une plus grande flexibilité pour les implémentations. Cela fournit également une meilleure sécurité et une exposition moindre aux données de carte de crédit. |

### <a name="retail-server-and-data-management"></a>Serveur de vente au détail et gestion des données

Le serveur de vente au détail et la gestion des données permettent aux utilisateurs et aux entreprises de créer une expérience d’achat dans plusieurs canaux en ligne, en magasin et en centres d’appels.

<table>
<thead>
<tr>
<th>Que pouvez-vous faire ?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Pourquoi est-ce important ?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Possibilité de se connecter à une base de données de Commerce Runtime (CRT) qui enregistre les données commerciales pour le canal à l’aide des services CRT.</td>
<td>OData V3 est pris en charge.</td>
<td>OData V4 est pris en charge.</td>
<td>Cela aide les clients à rester à jour avec les normes OData. Cela crée également une expérience fiable dans plusieurs canaux en intégrant des ventes au sein des canaux en ligne, mobiles et en magasin.</td>
</tr>
<tr>
<td>Prise en charge des services de vente au détail en tant qu’ensemble de services pouvant être hébergés.</td>
<td>L’API d’e-commerce n’est pas prise en charge par le serveur de vente au détail.</td>
<td>L’API d’e-commerce est désormais disponible via le serveur de vente au détail pour prendre en charge des scénarios en ligne.</td>
<td>Elle fournit des services hébergés et d’e-commerce évolutifs qui peuvent être utilisés avec des magasins en ligne tiers.</td>
</tr>
<tr>
<td>Déplacez les données entre les services administratifs et les canaux Microsoft Dynamics AX via Commerce Data Exchange.</td>
<td>Commerce Data Exchange est un système qui transfère des données entre Microsoft Dynamics AX et canaux de vente au détail, tels que des magasins en ligne et les magasins traditionnels. Pour plus d’informations, voir <a href="https://technet.microsoft.com/library/dn741440.aspx">Commerce Data Exchange [AX 2012]</a>.</td>
<td>Il y a une parité fonctionnelle avec Microsoft Dynamics AX 2012 CU8. Notez toutefois les informations suivantes :
<ul>
<li>Commerce Data Exchange a été repensé pour le cloud.</li>
<li>Le service Async utilise l’accès direct à la base de données dans la base de données de canal.</li>
<li>Commerce Data Exchange : le service en temps réel est hébergé comme service personnalisé Microsoft Dynamics AX.</li>
<li>MPOS gère la synchronisation entre les bases de données hors connexion et le serveur de vente au détail.</li>
</ul></td>
<td>Commerce Data Exchange a été repensé pour la plateforme du cloud. Il continue à gérer le transfert des données entre Microsoft Dynamics AX et les canaux de vente au détail, tels que des magasins en ligne ou des magasins traditionnels.</td>
</tr>
<tr>
<td>Prise en charge du plug and play, du traitement du paiement inter-canal semi-intégré via le kit de développement logiciel (SDK) du paiement.</td>
<td>AX 2012 fournit les fonctionnalités suivantes :
<ul>
<li>Prise en charge de tous les canaux : PDV, e-commerce et centre d’appels.</li>
<li>Prise en charge de la présence ou non des cartes.</li>
<li>Page pour accepter le paiement.</li>
<li>Prise en charge de périphérique pour LS5300 et MX925 comme exemple de code dans le Kit de développement logiciel (SDK) Retail.</li>
</ul></td>
<td>La version actuelle de Dynamics AX prend en charge toutes les fonctionnalités de carte de crédit/débit Microsoft Dynamics AX pour Retail 2012 existantes et quatre nouvelles améliorations.</td>
<td>Cela permet au client de traiter les transactions par cartes de crédit, cartes de débit pour les paiements.</td>
</tr>
<tr>
<td>Activez les périphériques à l’aide d’un compte Microsoft (Microsoft Azure Active Directory (Azure AD)).</td>
<td>Non disponible</td>
<td>La fonctionnalité suivante est fournie :
<ul>
<li>Sécurité améliorée par l’activation basée sur Azure AD pour le cloud.</li>
<li>Sécurité améliorée pour la gestion de jeton.</li>
<li>Fiabilité, résolution des problèmes et messages d’erreur durant l’activation améliorés</li>
<li>Tâches d’administration informatiques simplifiées liées à l’activation.</li>
<li>Modèle de risque revisité et problèmes de sécurité résolus.</li>
</ul></td>
<td>Cela fournit les avantages suivants :
<ul>
<li>La sécurité est améliorée via Azure AD et le jeton/l’ID de périphérique (appels RS utilisant un jeton, stockage d’application spécifique à un utilisateur).</li>
<li>Elle interrompt l’utilisation distante non-autorisée de MPOS (périphérique physique).</li>
<li>Elle suit des périphériques MPOS à des fins de conformité de PCI.</li>
<li>Elle met en correspondance les périphériques physiques avec une entité commerciale (registre) à l’aide d’un jeton de périphérique.</li>
<li>Elle initialise les paramètres pour la fonctionnalité MPOS lissée (souches de numéros et profils matériels) comme le premier point de contact de MPOS.</li>
<li>Elle signale les informations de périphérique depuis le siège.</li>
</ul></td>
</tr>
<tr>
<td>Gestion du contenu de support riche pour créer et servir via la galerie de supports.</td>
<td>Non disponible</td>
<td><ul>
<li>Prise en charge de chargement d’image, et affichage, gestion et suppression à partir de la galerie de supports à la fois pour les images hébergées en externe et par Retail.</li>
<li>Prise en charge du chargement et de l’affichage d’image à partir des pages d’entité (<strong>Produits</strong>, <strong>Catalogues</strong>, etc.) en liant une image à partir de la galerie et en téléchargeant une image à partir du bureau.</li>
<li>Optimisation des images pour les miniatures, la taille personnalisée et l’original.</li>
<li>Liaison en bloc des entités à l’aide d’un modèle et des travaux d’arrière-plan pour l’association en bloc.</li>
<li>Microsoft Excel remplace les limitations de groupe d’attributs des conventions de dénomination et des chemins prédéfinis.</li>
<li>Prise en charge des images hors connexion et des images sécurisées pour le contenu des informations d’identification personnelle, comme les images des clients et des employés hébergés par Retail.</li>
</ul></td>
<td><ul>
<li>Cela permet de résoudre les points faibles liés aux images hébergées en externe, afin d’éviter d’avoir à naviguer entre les étapes, et permet au lieu de cela une gestion dans un emplacement unique.</li>
<li>Cela fournit une gestion de contenu puissante via la galerie de supports pour les images téléchargées et hébergées en externe, et fournit également un filtrage afin d’aider à trouver des images.</li>
<li>Cela vous permet de créer facilement des associations en bloc entre des images hébergées en externe et des entités telles que des produits et des catalogues.</li>
<li>Cela permet de prendre en charge le stockage hébergé dans Retail pour des images, et l’intégration d’Excel pour les mises à jour faciles.</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="rich-clientele-experience"></a>Expérience client riche

La vente au détail offre des expériences de mobilité immersives n’importe où, tout le temps et dans n’importe quel périphérique. Cette fonctionnalité permet des expériences améliorées d’achat et de stockage entre les canaux.

<table>
<thead>
<tr>
<th>Que pouvez-vous faire ?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Pourquoi est-ce important ?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Recherche ou analyse des produits, ajout des produits dans un panier, acceptation du paiement et contrôle à l’aide d’une expérience utilisateur immersive, riche, conviviale et intuitive sur MPOS.</td>
<td>AX 2012 autorise les fonctions suivantes :
<ul>
<li>Effectuer les ventes, les retours, et les annulations.</li>
<li>Créer, modifier et prendre les commandes client.</li>
<li>Effectuer des opérations en lien avec le tiroir-caisse.</li>
<li>Prendre et recevoir des commandes fournisseur et réaliser des inventaires.</li>
<li>Afficher les états dans un magasin.</li>
</ul></td>
<td>La parité fonctionnelle avec AX 2012 MPOS est fournie. Cela inclut les fonctionnalités suivantes :
<ul>
<li>Recherche de clients dans les magasins/canaux.</li>
<li>Possibilité de créer des commandes client sans accéder au service en temps réel.</li>
<li>Messages d’erreur, statuts et workflows d’activation de périphérique améliorés.</li>
<li>Améliorations d’extensibilité (prise en charge d’activité et de déclencheurs avant/après) pour améliorer la personnalisation.</li>
</ul></td>
<td>Les vendeurs peuvent traiter des transactions de vente et des commandes client, et exécuter des opérations quotidiennes et gérer les stocks, à l’aide des périphériques mobiles n’importe où dans le magasin.</td>
</tr>
<tr>
<td>Possibilité de démarrer le PDV en tant qu’application Web via un PDV Cloud</td>
<td>Non disponible</td>
<td>La parité fonctionnelle avec MPOS est fournie. Cela inclut les fonctionnalités suivantes :
<ul>
<li>Activation du périphérique à l’aide d’AAD</li>
<li>Conception d’une mise en page réactive</li>
<li>Prise en charge des navigateurs Edge, Internet Explorer et Chrome.</li>
</ul></td>
<td>Fourniture d’un PDV d’application Web dont la fonctionnalité est compatible avec MPOS, et qui peut être utilisé dans plusieurs plateformes et navigateurs sans aucun coût de déploiement.</td>
</tr>
<tr>
<td>Intégration avec des systèmes de gestion de contenu pour créer un site Web d’e-commerce dans plusieurs canaux.</td>
<td>Microsoft SharePoint et les vitrines tierces sont pris en charge.</td>
<td>Une plateforme d’e-commerce est fournie et prend en charge les vitrines tierces. Elle inclut les fonctionnalités suivantes :
<ul>
<li>API du consommateur riche.</li>
<li>Intégration de l’authentification dans tous les fournisseurs OpenID tiers.</li>
<li>Intégration du paiement.</li>
</ul></td>
<td>Les clients ont à présent la flexibilité d’utiliser le système de gestion de contenu de leur choix.</td>
</tr>
<tr>
<td>Ciblage des clients via des catalogues de vente par correspondance et simplification des opérations via la saisie de commande rapide, les ventes assistées, et l’exécution à l’aide du centre d’appels.</td>
<td><ul>
<li>Canaux de centre d’appels</li>
<li>Catalogues de vente par correspondance</li>
<li>Saisie de commande rapide et vente assistée</li>
<li>Traitement des commandes amélioré</li>
<li>Service client</li>
<li>Tarification intégrée et promotions/remises</li>
</ul></td>
<td>Parité disponible avec la solution de centre d’appels d’AX 2012 (sauf pour les remplacements des prix).</td>
<td>Les centres d’appel sont un type de canal de vente au détail qui permettent aux collaborateurs de prendre des commandes clients par téléphone et de créer des commandes client.</td>
</tr>
</tbody>
</table>

### <a name="commerce-essentials"></a>Essentiel du commerce

Une option de configuration orientée sur le commerce et la vente au détail aide à simplifier les déploiements spécifiques à la vente au détail.

| Que pouvez-vous faire ? | Dynamics AX 2012 | Dynamics AX 7.0 | Pourquoi est-ce important ? |
|------------------|------------------|-----------------|------------------------|
| Utilisation du tableau de bord Essentiel du commerce. | Une page de zone avec des liens vers les options du menu est disponible. | Le tableau de bord Essentiel du commerce fournit des liens vers les tâches fréquentes, notamment des liens vers des espaces de travail, le contrôle Web Power BI, les favoris, les pages récentes, et les éléments de travail actuels. | Le tableau de bord amélioré responsabilise les collaborateurs en les rendant plus efficaces et en fournissant un point de départ flexible pour toute tâche de vente au détail. |
| Utilisation d’entités de données pour accéder aux modifications de compte. | Les modifications de compte sont exportées vers un dossier sur le système de fichiers. | Les modifications de compte sont accessibles via les entités de données. | Cette fonctionnalité fournit une flexibilité supérieure lors du déplacement des données entre les systèmes disparates. Elle peut aussi être améliorée via des applications OData. |
| Utilisation de Cloud POS et MPOS. | Seul Enterprise POS (EPOS) est pris en charge out-of-the-box. | MPOS et Cloud POS remplacent le client EPOS. Le canal de commerce électronique a également été ajouté à Essentiel du commerce par défaut. | Cette fonctionnalité offre une prise en charge de canal supérieure out-of-box avec des clients du point de vente rapidement déployables. |
| Mise en œuvre et maintient à jour de l’architecture à deux niveaux. | L’infrastructure d’importation/d’exportation de données fournit la capacité de déplacer des données entre AX 2012 et les systèmes tiers. | Des entités de données sont créées pour améliorer la prise en charge de l’architecture à deux niveaux. | Les applications d’entités de données et OData fournissent une couche d’abstraction afin de faciliter les scénarios à deux niveaux pour la mise en œuvre et le tenue à jour. |
| Simplification des écrans. | Le code personnalisé est requis pour simplifier l’IU. | Des extensions d’écran et de menu fournissent une simplification standardisée d’IU. | Cette fonctionnalité fournit une façon plus rapide et plus simple de régler avec précision des écrans selon les besoins du détaillant. |

### <a name="pos-task-recorder"></a>Enregistreur de tâches PDV

<table>
<thead>
<tr>
<th>Que pouvez-vous faire ?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Pourquoi est-ce important ?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Possibilité de créer et de partager des guides et des documents sur les tâches pour le PDV moderne.</td>
<td>Non disponible</td>
<td>L’enregistreur de tâches du PDV prend en charge les fonctionnalités suivantes :
<ul>
<li>Créer des enregistrements de tâches pour différentes tâches effectuées dans MPOS.</li>
<li>Générer un document qui implique des étapes et des captures d’écran, puis les associer à un nœud dans le modèle de processus entreprise.</li>
</ul></td>
<td>Les partenaires, les éditeurs de logiciels indépendants (ISV) peuvent personnaliser MPOS et fournir des documents justificatifs pour former leurs utilisateurs.</td>
</tr>
</tbody>
</table>

### <a name="extensibility"></a>Extensibilité

<table>
<thead>
<tr>
<th>Que pouvez-vous faire ?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Pourquoi est-ce important ?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prise en charge des composants Retail facilement déployables et extensibles entre le siège, les centres d’appels, l’e-commerce et le PDV.</td>
<td>Ces composants peuvent être étendus à l’aide du kit de développement logiciel (SDK) Retail. Aucune capacité d’emballage et de déploiement n’est prise en charge.</td>
<td>Les crochets d’extensibilité sont améliorés entre les différents composants pour améliorer l’isolement et l’utilité de code de support. Voici certaines des fonctionnalités incluses :
<ul>
<li>Workflow, activité et opération.</li>
<li>Pré-déclencheurs et post-déclencheurs qui permettent d’étendre facilement un workflow.</li>
<li>Déclencheurs de candidatures et d’opérations.</li>
</ul>
En outre, une structure est disponible et permet de créer et d’emballer ces composants à l’aide de MSBuild, puis de déployer sans faille votre personnalisation via Microsoft Dynamics Lifecycle Services (LCS).</td>
<td>Les détaillants ont des besoins très spécifiques, selon les marchés verticaux et l’emplacement des opérations. En fournissant une plateforme facilement extensible, nous activons l’utilisation sur plusieurs marchés verticaux. Étant donné que Retail a également une architecture très répartie, la capacité de déployer sans faille améliore considérablement la productivité.</td>
</tr>
</tbody>
</table>

### <a name="lifecycle-management"></a>Gestion du cycle de vie

Lifecycle Services (LCS) fournit un ensemble de services que les clients et les partenaires peuvent utiliser pour gérer le cycle de vie du système entre l’inscription et les opérations quotidiennes.

<table>
<thead>
<tr>
<th>Que pouvez-vous faire ?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Pourquoi est-ce important ?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Gestion du programme via des services de déploiement cloud.</td>
<td>Non disponible</td>
<td>Les topologies suivantes peuvent être déployées dans le cloud :
<ul>
<li>Topologie d’essai Retail 1-box.</li>
<li>Topologie haute-disponibilité Retail multi-box.</li>
<li>Topologie du développeur avec le kit de développement logiciel (SDK) Retail.</li>
</ul>
Installation améliorée du composant client « à faible contact » via l’installation en libre-service :
<ul>
<li>Retail Modern POS.</li>
<li>Retail Hardware Station.</li>
<li>Prise en charge du chargement et de la distribution des packages personnalisés via l’installation en libre-service.</li>
</ul></td>
<td>Les services de déploiement cloud offrent les avantages suivantes :
<ul>
<li>Effort et complexité du déploiement des composants du siège social Retail considérablement réduits.</li>
<li>Déploiement natif dans le cloud public Microsoft Azure.</li>
<li>Installation en libre-service améliorée des composants en magasin pour rendre la configuration plus simple et plus intuitive</li>
</ul></td>
</tr>
<tr>
<td>Surveillance de la santé du système, et diagnostic des erreurs et des problèmes.</td>
<td>Cette fonctionnalité nécessite le <a href="https://www.microsoft.com/download/details.aspx?id=42636">Pack de gestion du centre système 2012 pour Microsoft Dynamics AX 2012 R3 CU8 Retail</a>.</td>
<td>La surveillance et le diagnostic pour les composants Retail sont à présent disponibles via le tableau de bord <strong>Aperçu opérationnel</strong> dans LCS.</td>
<td>Le tableau de bord <strong>Aperçu opérationnel</strong> est un portail de surveillance basé sur le cloud qui remplace la nécessité d’installer l’infrastructure System Center Operations Manager (SCOM).</td>
</tr>
<tr>
<td>Création, configuration, téléchargement et installation de la station matérielle de vente au détail via le libre-service.</td>
<td>À l’aide du package d’installation et d’Enterprise Portal, un utilisateur peut exécuter une installation et une configuration automatiques de tous les composants nécessaires sur un ordinateur spécifique, selon la topologie définie.</td>
<td>Comme il n’existe que deux programmes d’installation (une pour le client MPOS et l’autre pour le composant Station matérielle de vente au détail), le libre-service a réduit la quantité de travail requise à chaque niveau pour installer ces composants clients.</td>
<td>Le libre-service vise à réduire les besoins et à faciliter les installations.</td>
</tr>
</tbody>
</table>

## <a name="sales"></a>Ventes

<table>
<thead>
<tr>
<th>Que pouvez-vous faire ?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Pourquoi est-ce important ?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Obtention d’un aperçu rapide des alternatives de livraison lorsque vous promettez des commandes aux clients.</td>
<td>En cas de contraintes en matière de disponibilité des produits, et si la date de livraison demandée par le client pour un ou plusieurs produits sur la commande ne peut pas être respectée, la tâche liée à la commande devient problématique. Pour rechercher des alternatives pouvant compenser la disponibilité et les problèmes de délai d’expédition afin que la date demandée par le client puisse être respectée, ou pour offrir aux clients une solution de livraison acceptable et fiable, le gestionnaire des commandes peut avoir à ouvrir plusieurs écrans, offrant chacun uniquement un sous-ensemble des informations requises. Un écran affiche par exemple la quantité disponible sur plusieurs sites, un autre écran affiche la quantité disponible dans le paramètre intersociétés, un troisième écran permet aux utilisateurs de calculer la date disponible la plus proche pour un site/une variante à la fois, et un quatrième écran affiche les commandes d’approvisionnement. Par conséquent, les utilisateurs n’ont pas la certitude d’avoir pris en compte toutes les options appropriées au lieu de choisir juste une solution immédiate mais sous-optimale. En outre, les utilisateurs ne se sentent pas efficaces, car de nombreuses interruptions surviennent au cours de la commande lorsqu’ils ouvrent et ferment plusieurs pages, et combinent les analyses et les options.</td>
<td>Selon les algorithmes existants pour le calcul de la date de livraison, la page <strong>Autres modes de livraison </strong>offre une nouvelle expérience utilisateur pour la promesse de commande :
<ul>
<li>Elle consolide les informations pertinentes à partir de plusieurs écrans dans un espace.</li>
<li>Elle offre d’autres packages de livraison « prêts à l’emploi », tels qu’une combinaison site/entreposage/variante/mode de transport, selon le critère de livraison le plus rapide (date disponible la plus proche) que l’utilisateur peut sélectionner.</li>
<li>Elle permet à l’utilisateur de sélectionner des options à partir de l’interface de simulation et de les transférer dans la ligne de commande client.</li>
</ul></td>
<td>Les sociétés qui cherchent à offrir un service client élevé lors de la validation d’une stratégie d’optimisation de stock doivent pouvoir promettre des commandes de manière sûre et compétitive. En effet, l’entreprise de leurs clients requiert aussi que les produits soient disponibles à temps. La page de tâche <strong>Autres modes de livraison</strong> rend la tâche liée à la commande plus rapide, plus simple, et plus systématique en identifiant et en recommandant les meilleures dates de livraison de commande alternatives dans un emplacement interactif.</td>
</tr>
</tbody>
</table>

## <a name="service-management"></a>Gestion des services

Aucune nouvelle fonctionnalité n’a été ajoutée :

## <a name="transportation-management"></a>Gestion du transport

Aucune nouvelle fonctionnalité n’a été ajoutée :

## <a name="travel-and-expense"></a>Déplacements et dépenses

Aucune nouvelle fonctionnalité n’a été ajoutée :

## <a name="warehouse-management"></a>Gestion des entrepôts

| Que pouvez-vous faire ? | Dynamics AX 2012 | Dynamics AX 7.0 | Pourquoi est-ce important ? |
|------------------|------------------|-----------------|------------------------|
| Possibilité de télécharger, d’installer et de configurer le portail des appareils mobiles d’entrepôt. | Vous pouvez télécharger, installer et configurer le portail lors du processus d’installation de Microsoft Dynamics AX, via un paramétrage standard. Il est conçu pour le déploiement et la configuration autonomes sur site. | Vous pouvez télécharger un installateur autonome via une option de menu dans le module gestion des entrepôts. Il est conçu pour le déploiement et la configuration autonomes sur site. | Lorsque vous configurez l’utilisation de la fonctionnalité de périphérique mobile, vous devez installer et configurer le portail des appareils mobiles d’entrepôt localement et obtenir une connexion à Dynamics AX dans le cloud. |

## <a name="additional-resources"></a>Ressources supplémentaires

[Page d’accueil Nouveautés ou modifications dans Finance and Operations](whats-new-changed.md)

[Nouveaux guides des tâches (février 2016)](new-task-guides-available-february-2016.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]