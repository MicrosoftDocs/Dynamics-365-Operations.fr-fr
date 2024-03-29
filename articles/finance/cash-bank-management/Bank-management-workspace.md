---
title: Espace de travail de la gestion des banques
description: Cet article fournit des informations sur l’espace de travail Gestion des banques. Cet espace de travail affiche des informations concernant les comptes bancaires de la société.
author: angelad116
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: f9880928281e704edcd24a75f99d4562761b7c82
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151549"
---
# <a name="bank-management-workspace"></a>Espace de travail de la gestion des banques

[!include [banner](../includes/banner.md)]

L’espace de travail **Gestion des banques** affichent des informations concernant les comptes bancaires de la société. Cet espace de travail contient une vue **Synthèse** et une page **Analyses**. La vue **Synthèse** affiche des vignettes de synthèse, des informations sur les comptes bancaires, un graphique du solde et des informations associées. La page **Analyses** utilise les fonctionnalités de Microsoft Power BI pour afficher les éléments visuels associés aux soldes de comptes bancaires.

## <a name="summary-view"></a>Vue Synthèse

### <a name="summary"></a>Synthèse

Les vignettes dans la section **Synthèse** fournissent une vue d’ensemble de vos comptes bancaires et fournissent un accès rapide aux pages que vous devez utiliser le plus souvent. Les informations de rapprochement bancaire sont spécifiques à la fonction de rapprochement bancaire avancée. Les informations ne concernent que les comptes bancaires dont l’option **Rapprochement bancaire avancé** est définie sur **Oui** sur la page **Compte bancaire**. Dans la section **Synthèse**, vous pouvez importer les fichiers bancaires électroniques des comptes bancaires de toutes les entités juridiques.

### <a name="bank-accounts"></a>Comptes bancaires

Chaque compte bancaire de l’entité juridique est représenté par une carte dans la section **Comptes bancaires**. Le solde actuel est affiché, et vous pouvez accéder aux transactions composant ce montant du solde de synthèse. Le montant **Transactions d’attente** permet également d’accéder aux transactions composant ce montant de synthèse. Les transactions d’attente sont toutes les transactions en attente qui ont été validées à l’aide de la fonctionnalité Transition, mais qui n’ont pas encore été effacées. Le montant **Solde en suspens** est le solde actuel moins les transactions en transition ou en attente.

La carte indique également le moment où le compte bancaire a fait l’objet d’un rapprochement pour la dernière fois. Ces informations ne sont affichées que si le rapprochement bancaire avancé est activé pour le compte bancaire.

### <a name="balance"></a>Bilan

Le graphique **Solde** affiche, soit les informations sur l’historique du solde du compte bancaire sélectionné dans la section **Comptes bancaires**, soit une synthèse de l’historique du solde de tous les comptes bancaires de l’entité juridique. Ces informations sont disponibles pour des périodes différentes : la semaine en cours, le mois en cours, l’année en cours, les cinq dernières années, et toutes les périodes (historique complet du compte bancaire). 

Si vous consultez le graphique **Solde** d’un seul compte bancaire, l’historique des soldes est affiché dans la devise du compte bancaire. Si vous consultez le graphique de tous les comptes de l’entité juridique, l’historique des soldes est affiché dans la devise comptable.

Les informations relatives au moment où les données ont été mises à jour pour la dernière fois s’affichent en haut du graphique. Vous pouvez mettre à jour les données comme vous le souhaitez.

### <a name="related-information"></a>Informations associées

Dans la section **Informations associées**, vous pouvez ouvrir la page **Journal des opérations diverses** pour effectuer des transferts bancaires. Vous pouvez également ouvrir rapidement les pages **Transactions bancaires** et **Transactions d’attente**.

## <a name="analytics-view"></a>Vue Analyses

La page **Analyses** fournit des mesures importantes sur les comptes bancaires de la société actuelle. Les visualisation suivantes sont disponibles dans la page :

-   Solde bancaire total dans la devise du système
-   Solde par entité juridique
-   Le solde actuel par rapport au solde prévisionnel dans la devise du compte bancaire
-   Solde par compte bancaire
-   Solde par devise

Vous pouvez afficher les analyses bancaires de toutes les sociétés à partir de l’espace de travail **Aperçu de la trésorerie – toutes les sociétés**. Pour plus d’informations, voir [Contenu Power BI – Vue d’ensemble des disponibilités](Cash-Overview-Power-BI-content.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
