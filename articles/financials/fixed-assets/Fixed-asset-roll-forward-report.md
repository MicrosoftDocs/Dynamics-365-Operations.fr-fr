---
title: "État Récupération d'immobilisations"
description: "Cette rubrique explique comment utiliser l'état Récupération d'immobilisations."
author: saraschi2
manager: 
ms.date: 01/08/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-12-20
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 7a81697a8e90fb6b0695a02db0868f5708fdbddf
ms.contentlocale: fr-fr
ms.lasthandoff: 02/07/2018

---
# <a name="fixed-assets-roll-forward-report"></a>État Récupération d'immobilisations

[!include[banner](../includes/banner.md)]

L'état **Récupération d'immobilisations** fournit, dans un format Microsoft Excel facile à lire, des données détaillées sur les immobilisations qui sont nécessaires pour la clôture de période, les tableaux d'analyse et la déclaration de taxe. L'état inclut les soldes de début et de fin des immobilisations, ainsi que les mouvements d'évaluation pour la période et les nouvelles acquisitions et cessions d'immobilisation au cours de la période. Les données sont fournies pour des immobilisations individuelles, et les valeurs sont également résumées pour les groupes d'immobilisations et l'entité juridique.

L'état **Récupération d'immobilisations** utilise la structure de gestion des états électroniques. Avant d'exécuter l'état, les configurations Modèle d'immobilisations et Récupération d'immobilisations doivent être importées depuis Microsoft Dynamics Lifecycle Services (LCS). Pour plus d'instructions, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs)

Cet état est disponible dans Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3, ou en tant que correctif pour Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (juillet 2017). Trois correctifs doivent être appliqués aux environnements de la version de juillet 2017 :

- **KB 4041754 :** la configuration des états électroniques ne peut pas être téléchargée à partir de LCS, car elle n'est pas applicable pour la version actuelle de l'application après application du package de mise à jour de la plateforme
- **KB 4056107 :** mise à jour cumulative 5 pour les états électroniques
- **KB 4056353 :** les états Relevé et note d'immobilisations ne répondent pas aux exigences de GAAP et IFRS

Le tableau suivant décrit les champs disponibles dans l'état.

| Champ                                       | Description  |
|---------------------------------------------|-------------|
| Soldes : ouverture                           | Valeur nette de l'immobilisation à compter de la date de début spécifiée dans l'état. |
| Soldes : clôture                           | Valeur nette de l'immobilisation à compter de la date de fin spécifiée dans l'état. |
| Acquisitions : valeur d'ouverture                 | Somme de toutes les transactions de type **Acquisition** et **Ajustement d'acquisition** à la date de début spécifiée dans l'état. |
| Acquisitions : acquisitions sur la période           | Somme de toutes les transactions de type **Acquisition** et **Ajustement d'acquisition** qui ont été validées au cours de la période pour l'état. |
| Acquisitions : cessions sur la période              | Somme de toutes les contrepassations d'acquisition validées avec une transaction de cession au cours de la période pour l'état. |
| Acquisitions : valeur de clôture                 | Somme de toutes les transactions de type **Acquisition** et **Ajustement d'acquisition** à la date de fin spécifiée dans l'état. |
| Amortissements : valeur d'ouverture                | Somme de toutes les transactions de type **Amortissement**, **Ajustement de l'amortissement**, **Provision spéciale pour amortissement** et **Amortissement exceptionnel** à la date de début spécifiée dans l'état. |
| Amortissements : amortissements sur la période         | Somme de toutes les transactions de type **Amortissement**, **Ajustement de l'amortissement** et **Amortissement exceptionnel** qui ont été validées au cours de la période pour l'état. |
| Amortissements : amortissements exceptionnels sur la période | Somme de toutes les transactions de type **Provision spéciale pour amortissement** qui ont été validées au cours de la période pour l'état. |
| Amortissements : cessions sur la période             | Somme de toutes les contrepassations d'amortissement validées avec une transaction de cession au cours de la période pour l'état. |
| Amortissements : valeur de clôture                | Somme de toutes les transactions de type **Amortissement**, **Ajustement de l'amortissement**, **Provision spéciale pour amortissement** et **Amortissement exceptionnel** à la date de fin spécifiée dans l'état. |
| Revalorisations/dévalorisations : valeur d'ouverture        | Somme de toutes les transactions de type **Augmentations**, **Diminutions** et **Réévaluation** à la date de début spécifiée dans l'état. |
| Revalorisations/dévalorisations : revalorisations sur la période     | Somme de toutes les transactions de type **Augmentations** qui ont été validées au cours de la période pour l'état. |
| Revalorisations/dévalorisations : dévalorisations sur la période   | Somme de toutes les transactions de type **Diminutions** qui ont été validées au cours de la période pour l'état. |
| Revalorisations/dévalorisations : réévaluations sur la période  | Somme de toutes les transactions de type **Réévaluation** qui ont été validées au cours de la période pour l'état. |
| Revalorisations/dévalorisations : cessions sur la période     | Somme de toutes les contrepassations de revalorisation, de dévalorisation et de réévaluation validées avec une transaction de cession au cours de la période pour l'état. |
| Revalorisations/dévalorisations : valeur de clôture        | Somme de toutes les transactions de type **Augmentations**, **Diminutions** et **Réévaluation** à la date de fin spécifiée dans l'état. |
| Cessions : date de cession                    | Date de cession pour le registre des immobilisations. |
| Cessions : valeur nette à la cession       | Valeur nette du registre des immobilisations au moment de la cession. |
| Cessions : valeur de vente                       | Valeur de vente pour le registre des immobilisations avec une cession (transaction de vente). |
| Cessions : valeur de mise au rebut                      | Valeur de mise au rebut pour le registre des immobilisations avec une cession (transaction de mise au rebut). |
| Cessions : résultat                      | Valeur du résultat qui est calculée dans le cadre de la transaction de cession pour le registre des immobilisations. |

