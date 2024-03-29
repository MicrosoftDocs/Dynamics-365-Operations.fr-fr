---
title: Intégration pour les accords de service et les projets
description: Lorsque vous utilisez des accords de service et des lignes d’accord de service, vous utilisez les données paramétrées dans les zones du module Gestion et comptabilité des projets.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7252de08b40aa0668d3ce801b4cbd6f3a53ef12f
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673576"
---
# <a name="integration-for-service-agreements-and-projects"></a>Intégration pour les accords de service et les projets 

[!include [banner](../includes/banner.md)]


Lorsque vous utilisez des accords de service et des lignes d’accord de service, vous utilisez les données paramétrées dans les zones suivantes du module **Gestion et comptabilité des projets**.

## <a name="project-prices"></a>Prix du projet

Les prix de revient et de vente d’une transaction d’accord de service sont issus du paramétrage du prix de revient qui s’applique au projet associé à l’accord de service. Vous pouvez les paramétrer par projet, employé ou catégorie. 

## <a name="project-validation"></a>Contrôle de projet

Les projets, employés et catégories disponibles sur une ligne d’accord de service peuvent être limités par le paramétrage de contrôle dans **Gestion et comptabilité des projets**. À l’aide de ce paramétrage, vous pouvez combiner des employés, des projets et des catégories pour l’accès de contrôle. 

## <a name="project-line-properties"></a>Propriétés de ligne de projet

Une propriété de ligne est entrée automatiquement pour une ligne d’accord de service.

Les propriétés de ligne sont créées dans l’écran **Propriétés de ligne** dans **Gestion et comptabilité des projets**. La propriété de ligne entrée sur un accord de service est associée au projet sélectionné pour l’accord de service et par conséquent héritée par la ligne d’accord de service. 

## <a name="default-offset-accounts"></a>Comptes de contrepartie par défaut

Si vous entrez une transaction de dépense, un compte de contrepartie par défaut pour la dépense est sélectionné automatiquement pour cette transaction. Le compte de dépenses par défaut est paramétré pour le projet associé à l’accord de service en cours.

## <a name="project-categories"></a>Catégories du projet

Les catégories disponibles pour les lignes d’accord de service sont paramétrées dans l’écran **Catégories de projets** dans **Gestion et comptabilité des projets**. 

> [!NOTE]
> <P>Les catégories dont la case à cocher <STRONG>Actif/active dans les journaux</STRONG> est activée sous l’onglet <STRONG>Projet</STRONG> de l’écran <STRONG>Catégories de projets</STRONG> sont disponibles pour sélection. Toutefois, si la case à cocher <STRONG>Catégories inactives</STRONG> est activée sous l’onglet <STRONG>Journaux</STRONG> de l’écran <STRONG>Paramètres de gestion et comptabilité des projets</STRONG>, toutes les catégories sont disponibles pour sélection.</P>

## <a name="project-parameters"></a>Paramètres de projet

Si le champ **Collaborateurs dont le contrat est terminé** sous l’onglet **Journaux** de l’écran **Paramètres de gestion et comptabilité des projets** est sélectionné, vous pouvez sélectionner des employés inactifs et des employés actifs dans les écrans **Accords de service** et **Commandes de service**.

Vous pouvez également activer les champs **Date de début** et **Date de fin** sous l’onglet **Projet** de l’écran **Commandes de service** pour entrer les heures de début et de fin dans les lignes de commande de service.

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a>Activation de la fonctionnalité d’heures de début et de fin pour les commandes de service

1.  Cliquez sur **Gestion et comptabilité des projets** \> **Paramétrage** \> **Paramètres de gestion et comptabilité des projets**.

2.  Cliquez sur l’onglet **Journaux**, puis activez la case à cocher **Afficher les heures de début/fin**.

3.  Cliquez sur **Gestion et comptabilité des projets** \> **Paramétrage** \> **Journaux** \> **Noms de journal**.

4.  Sélectionnez le nom de journal associé à la commande de service.

5.  Cliquez sur l’onglet **Général**, puis activez la case à cocher **Afficher les heures de début/fin**.


> [!NOTE]
> <P>Sélectionnez le nom de journal pour la commande de service dans le champ <STRONG>Heure</STRONG> sous l’onglet <STRONG>Journaux</STRONG> de l’écran <STRONG>Paramètres de gestion des services</STRONG>.</P>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]