---
title: État Récupération d’immobilisations
description: Cette rubrique explique comment utiliser l’état Récupération d’immobilisations.
author: saraschi2
manager: ''
ms.date: 01/08/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-12-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 9374f4ae75d321d82a7c6e8be0770f766afef90e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257655"
---
# <a name="fixed-assets-roll-forward-report"></a>État Récupération d’immobilisations

[!include [banner](../includes/banner.md)]

L’état **Récupération d’immobilisations** fournit, dans un format Microsoft Excel facile à lire, des données détaillées sur les immobilisations qui sont nécessaires pour la clôture de période, les tableaux d’analyse et la déclaration de taxe. L’état inclut les soldes de début et de fin des immobilisations, ainsi que les mouvements d’évaluation pour la période et les nouvelles acquisitions et cessions d’immobilisation au cours de la période. Les données sont fournies pour des immobilisations individuelles, et les valeurs sont également résumées pour les groupes d’immobilisations et l’entité juridique.

L’état **Récupération d’immobilisations** utilise la structure de gestion des états électroniques. Avant d’exécuter l’état, les configurations Modèle d’immobilisations et Récupération d’immobilisations doivent être importées depuis Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’instructions, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs)

Cet état est disponible dans Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3, ou comme correctif pour Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (juillet 2017). Trois correctifs doivent être appliqués aux environnements de la version de juillet 2017 :

- **KB 4041754 :** la configuration des états électroniques ne peut pas être téléchargée à partir de LCS, car elle n’est pas applicable pour la version actuelle après application du package de mise à jour de la plateforme
- **KB 4056107 :** mise à jour cumulative 5 pour les états électroniques
- **KB 4056353 :** les états Relevé et note d’immobilisations ne répondent pas aux exigences de GAAP et IFRS

Le tableau suivant décrit les champs disponibles dans l’état.


|                    Champ                    |                                                                                                                                Description                                                                                                                                |
|---------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              Soldes : ouverture              |                                                                                           Valeur nette de l’immobilisation à compter de la date de début spécifiée dans l’état.                                                                                           |
|              Soldes : clôture              |                                                                                            Valeur nette de l’immobilisation à compter de la date de fin spécifiée dans l’état.                                                                                            |
|         Acquisitions : valeur d’ouverture         |                                                 Somme de toutes les transactions de type <strong>Acquisition</strong> et <strong>Ajustement d’acquisition</strong> à la date de début spécifiée dans l’état.                                                  |
|      Acquisitions : acquisitions sur la période      |                                                 Somme de toutes les transactions de type <strong>Acquisition</strong> et <strong>Ajustement d’acquisition</strong> qui ont été validées au cours de la période pour l’état.                                                  |
|       Acquisitions : cessions sur la période        |                                                                        Somme de toutes les contrepassations d’acquisition validées avec une transaction de cession au cours de la période pour l’état.                                                                        |
|         Acquisitions : valeur de clôture         |                                                  Somme de toutes les transactions de type <strong>Acquisition</strong> et <strong>Ajustement d’acquisition</strong> à la date de fin spécifiée dans l’état.                                                   |
|        Amortissements : valeur d’ouverture         | Somme de toutes les transactions de type <strong>Amortissement</strong>, <strong>Ajustement de l’amortissement</strong>, <strong>Provision spéciale pour amortissement</strong> et <strong>Amortissement exceptionnel</strong> à la date de début spécifiée dans l’état. |
|     Amortissements : amortissements sur la période     |                         Somme de toutes les transactions de type <strong>Amortissement</strong>, <strong>Ajustement de l’amortissement</strong> et <strong>Amortissement exceptionnel</strong> qui ont été validées au cours de la période pour l’état.                          |
| Amortissements : amortissements exceptionnels sur la période |                                                              Somme de toutes les transactions de type <strong>Provision spéciale pour amortissement</strong> qui ont été validées au cours de la période pour l’état.                                                               |
|       Amortissements : cessions sur la période       |                                                                       Somme de toutes les contrepassations d’amortissement validées avec une transaction de cession au cours de la période pour l’état.                                                                        |
|        Amortissements : valeur de clôture         |  Somme de toutes les transactions de type <strong>Amortissement</strong>, <strong>Ajustement de l’amortissement</strong>, <strong>Provision spéciale pour amortissement</strong> et <strong>Amortissement exceptionnel</strong> à la date de fin spécifiée dans l’état.  |
|    Revalorisations/dévalorisations : valeur d’ouverture     |                              Somme de toutes les transactions de type <strong>Augmentations</strong>, <strong>Diminutions</strong> et <strong>Réévaluation</strong> à la date de début spécifiée dans l’état.                               |
|   Revalorisations/dévalorisations : revalorisations sur la période   |                                                                    Somme de toutes les transactions de type <strong>Augmentations</strong> qui ont été validées au cours de la période pour l’état.                                                                    |
|  Revalorisations/dévalorisations : dévalorisations sur la période  |                                                                   Somme de toutes les transactions de type <strong>Diminutions</strong> qui ont été validées au cours de la période pour l’état.                                                                   |
| Revalorisations/dévalorisations : réévaluations sur la période  |                                                                        Somme de toutes les transactions de type <strong>Réévaluation</strong> qui ont été validées au cours de la période pour l’état.                                                                        |
|   Revalorisations/dévalorisations : cessions sur la période   |                                                           Somme de toutes les contrepassations de revalorisation, de dévalorisation et de réévaluation validées avec une transaction de cession au cours de la période pour l’état.                                                           |
|    Revalorisations/dévalorisations : valeur de clôture     |                               Somme de toutes les transactions de type <strong>Augmentations</strong>, <strong>Diminutions</strong> et <strong>Réévaluation</strong> à la date de fin spécifiée dans l’état.                                |
|          Cessions : date de cession           |                                                                                                                Date de cession pour le registre des immobilisations.                                                                                                                |
|    Cessions : valeur nette à la cession    |                                                                                                    Valeur nette du registre des immobilisations au moment de la cession.                                                                                                    |
|            Cessions : valeur de vente            |                                                                                               Valeur de vente pour le registre des immobilisations avec une cession (transaction de vente).                                                                                                |
|           Cessions : valeur de mise au rebut            |                                                                                               Valeur de mise au rebut pour le registre des immobilisations avec une cession (transaction de mise au rebut).                                                                                               |
|           Cessions : résultat            |                                                                                 Valeur du résultat qui est calculée dans le cadre de la transaction de cession pour le registre des immobilisations.                                                                                 |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]