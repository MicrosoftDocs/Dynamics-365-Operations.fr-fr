---
title: "États financiers"
description: "Cette rubrique décrit dans lequel accéder aux états financiers dans Microsoft Dynamics 365 pour les opérations et comment utiliser les fonctionnalités de rapports financiers. Elle inclut une description des états financiers par défaut fournis."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d13747f17b5f382b3a530b1f166681eeec0b9d73
ms.lasthandoff: 03/31/2017


---

# <a name="financial-reporting"></a>États financiers

Cette rubrique décrit dans lequel accéder aux états financiers dans Microsoft Dynamics 365 pour les opérations et comment utiliser les fonctionnalités de rapports financiers. Elle inclut une description des états financiers par défaut fournis.

<a name="accessing-financial-reporting"></a>Accès à la génération d'états financiers
-----------------------------

Vous pouvez trouver ** des états financiers ** le menu dans les emplacements suivants dans Dynamics 365 pour les opérations :

-   ** Comptabilité ** &gt; ** recherches et états **
-   ** Économisant ** &gt; ** s'enquiert et états ** &gt; ** la budgétisation de base **
-   ** ** ** &gt; Recherches et états de budgétisation ** &gt; ** planification budgétaire **
-   ** ** ** &gt; Recherches et états de budgétisation ** &gt; ** contrôle budgétaire **
-   Consolidations

Pour créer et générer des états financiers pour une entité juridique, vous devez paramétrer les informations suivantes pour cette entité juridique :

-   Calendrier fiscal
-   Comptabilité
-   Plan de comptes
-   Devise

Les fonctions de génération d'états financiers sont disponibles aux utilisateurs ayant les droits et les devoirs appropriés par l'intermédiaire de leurs rôles de sécurité. Les sections suivantes décrivent ces privilèges et responsabilités, ainsi que les rôles associés.

### <a name="duties"></a>Droits

| Nom de la responsabilité                            | Description                                                             | Nom d'AOA                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Tenir à jour la sécurité des états financiers | Tenir à jour la sécurité des états financiers et exécuter des tâches d'administration. | FinancialReportsSecurityMaintain |
| Tenir à jour les états financiers            | Créer et tenir à jour les états financiers.                                  | FinancialReportsMaintain         |
| Générer les états financiers            | Générer et actualiser les états financiers.                                 | FinancialReportsGenerate         |
| Examiner les performances financières          | Examiner et analyser les performances financières.                               | FinancialReportsPerfReview       |

### <a name="privileges"></a>Privilèges

| Nom du privilège                       | Description                                                             | Nom d'AOA                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Tenir à jour la sécurité des états financiers | Tenir à jour la sécurité des états financiers et exécuter des tâches d'administration. | FinancialReportsSecurityMaintain |
| Tenir à jour les états financiers            | Créer et tenir à jour les états financiers.                                  | FinancialReportsMaintainReports  |
| Générer les états financiers            | Générer et actualiser les états financiers.                                 | FinancialReportsGenerateReports  |
| Afficher les états financiers                | Afficher les états financiers.                                                 | FinancialReportsView             |

### <a name="roles"></a>Rôles

| Nom du privilège                       | Responsabilité                                  | Rôles                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Tenir à jour la sécurité des états financiers | Tenir à jour la sécurité des états financiers | Administrateur sécurité                                                          |
| Tenir à jour les états financiers            | Tenir à jour les états financiers            | Responsable comptabilité, superviseur comptable, contrôleur financier, responsable du budget |
| Générer les états financiers            | Générer les états financiers            | PDG, CFO, comptable                                                            |
| Afficher les états financiers                | Examiner les performances financières          | Aucun affecté                                                                   |

Une fois qu'un utilisateur a été ajouté ou qu'un rôle a été modifié, il doit pouvoir accéder aux états financiers en quelques minutes. ** Remarque : ** Le rôle sysadmin est ajouté à Tous les rôles dans les états financiers.

## <a name="default-reports"></a>États par défaut
Les états financiers fournissent 22 états financiers par défaut. Chaque rapport utilise les catégories de compte principal par défaut dans Dynamics 365 pour les opérations. Vous pouvez utiliser ces états tels quels ou en tant que point de départ pour vos besoins en matière d'états financiers. Outre les tableaux d'analyse traditionnels, tels que le rapport de revenus et le bilan de résultats, ces états par défaut incluent des états qui indiquent les différents types d'états financiers que vous pouvez créer. Chaque rapport les liens suivants de table à une présentation combinées Office sur l'état.

| État par défaut                                                                                         | description ;                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [12 Month Rolling Single Column Income Statement – Default](https://mix.office.com/watch/76kc7bm3wnt1) | Permet d'afficher la rentabilité d'une organisation pour les 12 derniers mois dans une colonne unique.                                                                                                                                                                                                                                      |
| [12 Month Trend Income Statement – Default](https://mix.office.com/watch/12brmfge5p8r)                 | Permet d'afficher la rentabilité d'une organisation pour chacun des 12 derniers mois. Ces 12 mois peuvent couvrir plus d'un exercice.                                                                                                                                                                                             |
| [Actual vs Budget – Default](https://mix.office.com/watch/fi439lkwr0no)                                | Permet d'afficher les informations détaillées sur le solde pour tous les comptes pour le budget d'origine, et de comparer le budget révisé aux valeurs réelles présentant un écart.                                                                                                                                                                          |
| [Audit Details – Default](https://mix.office.com/watch/1i15nzd3nwkyh)                                  | Permet d'afficher les informations détaillées du solde pour tous les comptes. Cet état indique les soldes de débit et de crédit dans la devise de déclaration et la devise locale, ainsi que les informations des transactions supplémentaires, telles que l'ID utilisateur, l'utilisateur ayant modifié les données en dernier, la date de la dernière modification et l'ID de journal. |
| [Balance List – Default](https://mix.office.com/watch/1kezwu2a10fq4)                                   | Permet d'afficher les informations détaillées du solde pour tous les comptes. Cet état indique les soldes d'ouverture et de clôture, et les soldes de débit et de crédit pour la période actuelle et l'année jusqu'à présent, ainsi que les informations des transactions supplémentaires, telles que le N° document.                                                                    |
| [Balance Sheet – Default](https://mix.office.com/watch/zkgq0u7visw9)                                   | Permet d'afficher la position financière de l'organisation pour l'année.                                                                                                                                                                                                                                                             |
| [Balance Sheet and Income Statement Side by Side - Default](https://mix.office.com/watch/zkgq0u7visw9) | Permet d'afficher la position financière et la rentabilité de l'organisation pour l'année, côte à côte.                                                                                                                                                                                                                              |
| [Cash Flow – Default](https://mix.office.com/watch/jd3go9pz6390)                                       | Renseigne sur la trésorerie entrante et sortante de l'organisation.                                                                                                                                                                                                                                   |
| [Detailed JE and TB Review – Default](https://mix.office.com/watch/1sw9fmtwgjb1f)                      | Permet d'afficher le solde d'ouverture et les informations d'activité pour tous les comptes.                                                                                                                                                                                                                                                      |
| [Detailed Trial Balance - Default](https://mix.office.com/watch/1ewwgbpv0iwrl)                         | Permet d'afficher les informations de solde pour tous les comptes ayant des soldes de débit et de crédit, et le net de ces soldes, avec la date de la transaction, le N° document et la description de journal.                                                                                                                                  |
| [Expenses Three Year Quarterly Trend – Default](https://mix.office.com/watch/gwm4zu7tmtj8)             | Renseigne sur les dépenses pour les 12 derniers trimestres des trois années précédentes.                                                                                                                                                                                                                                   |
| [Financial Captions JE and TB Review – Default](https://mix.office.com/watch/1sw9fmtwgjb1f)            | Donne la vue d'ensemble des soldes et de l'activité pour les légendes financières des immobilisations, du passif, des capitaux propres, du produit, des dépenses, des bénéfices, ou des pertes.                                                                                                                                                                           |
| [Income Statement – Default](https://mix.office.com/watch/sbuhgl5hzuhi)                                | Permet d'afficher la rentabilité de l'organisation pour la période actuelle et l'année jusqu'à ce jour.                                                                                                                                                                                                                                   |
| [Ledger Transaction List – Default](https://mix.office.com/watch/19h9v2rmh48vy)                        | Permet d'afficher les informations détaillées du solde pour tous les comptes. Cet état affiche les soldes de débit et de crédit, ainsi que les informations de transaction supplémentaires, telles que la date de la transaction, le numéro de journal, le N° document, le type de validation et le numéro de suivi.                                                                            |
| [Ratios – Default](https://mix.office.com/watch/b08hfc5h92me)                                          | Permet d'afficher la solvabilité, la rentabilité et les taux de rendement de l'organisation pour l'année.                                                                                                                                                                                                                           |
| [Rolling 12 Month Expenses – Default](https://mix.office.com/watch/iywod5qmqhz7)                       | Renseigne sur les dépenses de chacun des 12 derniers mois. Ces 12 mois peuvent couvrir plus d'un exercice.                                                                                                                                                                                                       |
| [Rolling Quarter Income Statement – Default](https://mix.office.com/watch/1k4yl6a6oyxqc)               | Permet d'afficher la rentabilité de l'organisation chaque trimestre pour la dernière année et Année en cours.                                                                                                                                                                                                                   |
| [Side by Side Balance Sheet – Default](https://mix.office.com/watch/zkgq0u7visw9)                      | Permet d'afficher la position financière de l'organisation pour l'année. Cet état affiche les actifs et passifs et les capitaux propres des actionnaires côte à côte.                                                                                                                                                                                |
| [Summary Trial Balance – Default](https://mix.office.com/watch/1ewwgbpv0iwrl)                          | Permet d'afficher les informations du solde pour tous les comptes ayant des soldes d'ouverture et de clôture, et les soldes de débit et de crédit ensemble avec leur différence nette.                                                                                                                                                                  |
| [Summary Trial Balance Year Over Year – Default](https://mix.office.com/watch/1ewwgbpv0iwrl)           | Affichez les informations de solde pour tous les comptes avec l'ouverture et les soldes de clôture, et débit et soldes créditeurs ainsi que leur différence nette de l'année en cours et la dernière année.                                                                                                                           |
| [Weekly Sales and Discounts - Default](https://mix.office.com/watch/112ng0hy5de0j)                     | renseigne sur les ventes et les remises de chaque semaine d'un mois. Cet état inclut un total sur quatre semaines.                                                                                                                                                                                                              |
| [Les fonds budgétaires disponibles - Valeur par défaut (https://mix.office.com/watch/15hcpezcbx7tv)]                         | Permet d'afficher une comparaison détaillée du budget révisé, des dépenses réelles, des réservations budgétaires, et des fonds budgétaires disponibles pour tous les comptes                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Ouverture d'états financiers
Lorsque vous cliquez sur le menu **États financiers**, la liste des états financiers par défaut pour la société s'affiche. Vous pouvez ensuite ouvrir ou modifier un état. Pour ouvrir un des états par défaut, sélectionnez le nom de l'état. La première fois que l'état est ouvert, il est automatiquement généré pour le mois précédent. Par exemple, si vous ouvrez un rapport pour la première fois en août 2016, l'état est généré pour le 31 juillet 2016. Après l’ouverture d’un état, vous pouvez démarrer l'exploration en accédant à des ensembles de données spécifiques et en modifiant les options d'état.

## <a name="creating-and-modifying-financial-reports"></a>Création et modification d'états financiers
Dans la liste des états financiers, vous pouvez créer un nouvel état ou modifier un état existant. Si vous disposez des autorisations requises, vous pouvez créer un rapport financier en cliquant sur ** nouveau ** du volet Actions. Programme Concepteur de rapports téléchargé dans votre périphérique. Une fois le Concepteur de rapports commence vous pouvez ensuite créer le nouveau générez un rapport. Après avoir enregistré le nouvel état, il apparaît dans la liste des états financiers. Les états liste affiche uniquement créées pour la société que vous utilisez dans Dynamics 365 pour les opérations. Pour plus d'informations sur le processus de créer et de modifier des rapports financiers dans Dynamics 365 pour les opérations, reportez-vous à ces [validations de blog] (https://blogs.msdn.microsoft.com/dynamics_financial_reporting/tag/learning/) du blog d'états financiers de Dynamics. ** Remarque : ** L'ordinateur que vous chargez le client du Concepteur de rapports en fonction doit disposer de la version 4.6.2 de la zone Microsoft .NET installé dans celui-ci. Cette version de la zone Microsoft .NET peut être chargée et installée à partir de ici [] (https://www.microsoft.com/en-us/download/details.aspx?id=53345). Si vous utilisez chrome, vous devez installer une extension de ClickOnce afin de télécharger le client du Concepteur de rapports. Si vous exécutez en mode incognito, vérifiez que l'extension de ClickOnce est activée pour le mode incognito. Vous pouvez également modifier un état qui apparaît dans la liste des états financiers. Lorsque la zone autour du nom de l'état est activée, cliquez sur **Édition** dans le Volet Actions. Le programme de concepteur d'état démarre.

<a name="see-also"></a>Voir également :
--------

[View financial reports](view-financial-reports.md)

[États financiers Dynamics (blog)](http://blogs.msdn.com/b/dynamics_financial_reporting/)


