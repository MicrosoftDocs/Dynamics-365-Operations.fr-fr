---
title: Générer et exécuter les états prêts à l'emploi
description: Utilisez ce guide de tâche pour exécuter des états prêts à l'emploi dans Headquarters à partir de différents espaces de travail et des états Recherches et ventes situés dans Commerce.
author: ashishmsft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailCategoryAndProductWorkspace, RetailOrgHierarchyTreeLookup, SrsReportViewerForm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d3dd941eb4e682e61c8b3d10ef0ccd14239f090c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232711"
---
# <a name="generate-and-run-out-of-box-reports"></a>Générer et exécuter les états prêts à l'emploi

[!include [banner](../includes/banner.md)]

Utilisez ce guide de tâche pour exécuter des états prêts à l'emploi dans Headquarters à partir de différents espaces de travail et des états Recherches et ventes situés dans Commerce.

La société fictive utilisée pour créer cet enregistrement est USRT. Cet enregistrement est destiné au rôle Administrateur système.

## <a name="launch-reports-from-workspaces"></a>Lancer des états à partir des espaces de travail
1. Accédez à Retail et Commerce > Produits et catégories > Gestion des catégories et des produits.
2. Cliquez sur la flèche pour développer ou réduire la section États.
3. Cliquez sur État Principaux produits.
4. Entrez une date dans le champ Date de début.
5. Entrez une date dans le champ Date de fin.
6. Dans le champ Canal, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans l'arborescence, sélectionnez « Contoso Retail\Contoso Retail USA\Central\Houston ».
    * La hiérarchie d'organisation par défaut pour Commerce s'affiche pour la génération d'états.   Accédez à Administration d'organisation > Organisations > Objectifs de la hiérarchie d'organisation et choisissez Génération d'états de Commerce et, sous Hiérarchies affectées, vérifiez le nom de la hiérarchie pour lequel la colonne Valeur par défaut est cochée. Dans le cadre des données de démonstration (utilisées pour cet enregistrement de tâche), vous remarquez que Magasins par région est la hiérarchie d'organisation par défaut pour la génération d'états.     
8. Cliquez sur OK.
9. Dans le champ Afficher, sélectionnez une option.
10. Dans le champ Par, sélectionnez une option.
11. Cliquez sur OK.

## <a name="launch-reports-from-the-inquiries-and-sales-reports"></a>Lancer des rapports à partir des états Recherches et ventes
1. Accédez à Retail et Commerce > Recherches et états > États des ventes > État des ventes par catégorie.
2. Entrez une date dans le champ Date de début.
3. Entrez une date dans le champ Date de fin.
4. Dans le champ Canal, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans l'arborescence, sélectionnez « Contoso Retail\Contoso Retail USA\West\Seattle ».
    * La hiérarchie d'organisation par défaut pour Commerce s'affiche pour la génération d'états. Accédez à Administration d'organisation > Organisations > Objectifs de la hiérarchie d'organisation et choisissez Génération d'états de Commerce et, sous Hiérarchies affectées, vérifiez le nom de la hiérarchie pour lequel la colonne Valeur par défaut est cochée. Dans le cadre des données de démonstration (utilisées pour cet enregistrement de tâche), vous remarquez que Magasins par région est la hiérarchie d'organisation par défaut pour la génération d'états.     
6. Cliquez sur OK.
7. Cliquez sur OK.

## <a name="export-an-hq-reports"></a>Exporter un état HQ
1. Accédez à Retail et Commerce > Recherches et états > États des ventes > État des ventes d'organisation.
2. Entrez une date dans le champ Date de début.
3. Entrez une date dans le champ Date de fin.
4. Cliquez sur OK.
5. Cliquez sur Exporter.
6. Cliquez sur PDF.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]