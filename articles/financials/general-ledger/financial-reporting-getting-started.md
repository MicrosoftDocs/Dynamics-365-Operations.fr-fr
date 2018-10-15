---
title: "États financiers"
description: "Cette rubrique explique où accéder aux états financiers dans Microsoft Dynamics 365 for Finance and Operations et comment utiliser les fonctionnalités de génération d'états financiers. Elle inclut une description des états financiers par défaut fournis."
author: aprilolson
manager: AnnBe
ms.date: 09/26/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a128f326cb89ab00e69be40801553c0ac551446e
ms.openlocfilehash: c6d504a7b0640f45de4aa9f8fb60d2b1d37818bb
ms.contentlocale: fr-fr
ms.lasthandoff: 09/27/2018

---

# <a name="financial-reporting"></a>États financiers

[!include [banner](../includes/banner.md)]

Cette rubrique explique où accéder aux états financiers dans Microsoft Dynamics 365 for Finance and Operations et comment utiliser les fonctionnalités de génération d'états financiers. Elle inclut une description des états financiers par défaut fournis.

<a name="accessing-financial-reporting"></a>Accès à la génération d'états financiers
-----------------------------

Vous trouverez le menu **États financiers** dans les emplacements suivants de Finance and Operations :

-   **Comptabilité** &gt; **Recherches et états**
-   **Budget** &gt; **Recherches et états** &gt; **Budget de base**
-   **Budget** &gt; **Recherches et états** &gt; **Planification budgétaire**
-   **Budget** &gt; **Recherches et états** &gt; **Contrôle budgétaire**
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
| Tenir à jour les états financiers            | Tenir à jour les états financiers            | Gestionnaire comptable, chef comptable, contrôleur financier, responsable du budget |
| Générer les états financiers            | Générer les états financiers            | PDG, directeur financier, comptable                                                            |
| Afficher les états financiers                | Examiner les performances financières          | Aucun affecté                                                                   |

Une fois qu'un utilisateur a été ajouté ou qu'un rôle a été modifié, il doit pouvoir accéder aux états financiers en quelques minutes. **Remarque :** le rôle sysadmin est ajouté à tous les rôles de la génération d'états financiers.

## <a name="default-reports"></a>États par défaut
Les états financiers fournissent 22 états financiers par défaut. Chaque état utilise les catégories de compte principal par défaut dans Finance and Operations. Vous pouvez utiliser ces états tels quels ou en tant que point de départ pour vos besoins en matière d'états financiers. Outre les tableaux d'analyse traditionnels, tels que le rapport de revenus et le bilan de résultats, ces états par défaut incluent des états qui indiquent les différents types d'états financiers que vous pouvez créer. 

<!--Each report in the following table links to an Office Mix presentation about the report.-->

| État par défaut                                                                                         | Description                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Relevé des revenus sur 12 mois roulants à une seule colonne – Par défaut | Permet d'afficher la rentabilité d'une organisation pour les 12 derniers mois dans une colonne unique.                                                                                                                                                                                                                                      |
| Relevé des revenus, tendance sur 12 mois – Par défaut                 | Permet d'afficher la rentabilité d'une organisation pour chacun des 12 derniers mois. Ces 12 mois peuvent couvrir plus d'un exercice.                                                                                                                                                                                             |
| Comparatif Réel/Budget – Par défaut                                | Permet d'afficher les informations détaillées sur le solde pour tous les comptes pour le budget d'origine, et de comparer le budget révisé aux valeurs réelles présentant un écart.                                                                                                                                                                          |
| Détails d'audit – Par défaut                                  | Permet d'afficher les informations détaillées du solde pour tous les comptes. Cet état indique les soldes de débit et de crédit dans la devise de déclaration et la devise locale, ainsi que les informations des transactions supplémentaires, telles que l'ID utilisateur, l'utilisateur ayant modifié les données en dernier, la date de la dernière modification et l'ID de journal. |
| Liste de solde – Par défaut                                   | Permet d'afficher les informations détaillées du solde pour tous les comptes. Cet état indique les soldes d'ouverture et de clôture, et les soldes de débit et de crédit pour la période actuelle et l'année jusqu'à présent, ainsi que les informations des transactions supplémentaires, telles que le N° document.                                                                    |
| Bilan – Par défaut                                   | Permet d'afficher la position financière de l'organisation pour l'année.                                                                                                                                                                                                                                                             |
| Bilan et relevé des revenus côte à côte – Par défaut | Permet d'afficher la position financière et la rentabilité de l'organisation pour l'année, côte à côte.                                                                                                                                                                                                                              |
| Flux de trésorerie – Par défaut                                       | Renseigne sur la trésorerie entrante et sortante de l'organisation.                                                                                                                                                                                                                                   |
| Révision détaillée JE et TB – Par défaut                      | Permet d'afficher le solde d'ouverture et les informations d'activité pour tous les comptes.                                                                                                                                                                                                                                                      |
| Balance comptable détaillée – Par défaut                         | Permet d'afficher les informations de solde pour tous les comptes ayant des soldes de débit et de crédit, et le net de ces soldes, avec la date de la transaction, le N° document et la description de journal.                                                                                                                                  |
| Tendance des dépenses trimestrielles sur trois ans – Par défaut             | Renseigne sur les dépenses pour les 12 derniers trimestres des trois années précédentes.                                                                                                                                                                                                                                   |
| Révision JE et TB des légendes financières – Par défaut            | Donne la vue d'ensemble des soldes et de l'activité pour les légendes financières des immobilisations, du passif, des capitaux propres, du produit, des dépenses, des bénéfices, ou des pertes.                                                                                                                                                                           |
| Relevé des revenus – Par défaut                                | Permet d'afficher la rentabilité de l'organisation pour la période actuelle et l'année jusqu'à ce jour.                                                                                                                                                                                                                                   |
| Liste des écritures comptables – Par défaut                        | Permet d'afficher les informations détaillées du solde pour tous les comptes. Cet état affiche les soldes de débit et de crédit, ainsi que les informations de transaction supplémentaires, telles que la date de la transaction, le numéro de journal, le N° document, le type de validation et le numéro de suivi.                                                                            |
| Taux – Par défaut                                          | Permet d'afficher la solvabilité, la rentabilité et les taux de rendement de l'organisation pour l'année.                                                                                                                                                                                                                           |
| Dépenses sur 12 mois roulants – Défaut                       | Renseigne sur les dépenses de chacun des 12 derniers mois. Ces 12 mois peuvent couvrir plus d'un exercice.                                                                                                                                                                                                       |
| Relevé des revenus trimestriels roulants – Par défaut               | Permet d'afficher la rentabilité de l'organisation par trimestre, pour la dernière année et l'année jusqu'à ce jour.                                                                                                                                                                                                                   |
| Bilan côte à côte bilan – Par défaut                      | Permet d'afficher la position financière de l'organisation pour l'année. Cet état affiche les actifs et passifs et les capitaux propres des actionnaires côte à côte.                                                                                                                                                                                |
| Synthèse de balance comptable– Par défaut                          | Permet d'afficher les informations du solde pour tous les comptes ayant des soldes d'ouverture et de clôture, et les soldes de débit et de crédit ensemble avec leur différence nette.                                                                                                                                                                  |
| Synthèse de balance comptable d'une année à l'autre – Par défaut           | Permet d'afficher les informations du solde pour tous les comptes ayant des soldes d'ouverture et de clôture, et les soldes de débit et de crédit ensemble avec leur différence nette pour l'année courante et l'année précédente.                                                                                                                           |
| Ventes et remises hebdomadaires - Par défaut                     | renseigne sur les ventes et les remises de chaque semaine d'un mois. Cet état inclut un total sur quatre semaines.                                                                                                                                                                                                              |
| Fonds budgétaires disponibles - Par défaut                         | Permet d'afficher une comparaison détaillée du budget révisé, des dépenses réelles, des réservations budgétaires et des fonds budgétaires disponibles pour tous les comptes                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Ouverture d'états financiers
Lorsque vous cliquez sur le menu **États financiers**, la liste des états financiers par défaut pour la société s'affiche. Vous pouvez ensuite ouvrir ou modifier un état. Pour ouvrir un des états par défaut, sélectionnez le nom de l'état. La première fois que l'état est ouvert, il est automatiquement généré pour le mois précédent. Par exemple, si vous ouvrez un état pour la première fois en août 2016, l'état est généré pour le 31 juillet 2016. Après l’ouverture d’un état, vous pouvez démarrer l'exploration en accédant à des ensembles de données spécifiques et en modifiant les options d'état.

## <a name="creating-and-modifying-financial-reports"></a>Création et modification d'états financiers
Dans la liste des états financiers, vous pouvez créer un nouvel état ou modifier un état existant. Si vous disposez des autorisations appropriées, vous pouvez créer un état financier en cliquant sur **Nouveau** dans le volet Actions. Un programme de concepteur d'états est téléchargé sur votre périphérique. Une fois que le concepteur d'états démarre, vous pouvez créer l'état. Après avoir enregistré le nouvel état, il apparaît dans la liste des états financiers. La liste affiche uniquement les états créés pour la société utilisés dans Finance and Operations. 

> [!NOTE] 
> La version 4.6.2 de Microsoft .NET Framework doit être installée sur l'ordinateur sur lequel vous téléchargez le client Concepteur d'états. Cette version de Microsoft .NET Framework peut être téléchargée et installée à partir du [Centre de téléchargement Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=53345). Si vous utilisez Chrome, vous devez installer une extension ClickOnce afin de télécharger le client Concepteur d'états. Si vous utilisez le mode incognito, vérifiez que l'extension ClickOnce est activée pour le mode incognito. Vous pouvez également modifier un état qui apparaît dans la liste des états financiers. Lorsque la zone autour du nom de l'état est activée, cliquez sur **Édition** dans le Volet Actions. Le programme de concepteur d'état démarre.

## <a name="additional-resources"></a>Ressources supplémentaires
- [Afficher les états financiers](view-financial-reports.md)




