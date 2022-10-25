---
title: Tableau de bord de la solution Invoice Capture
description: Cet article décrit le tableau de bord de la solution Invoice Capture.
author: sunfzam
ms.date: 10/15/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4c9000039488c1290f4ab992d7fe79b8ccac7b19
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690120"
---
# <a name="invoice-capture-solution-dashboard"></a>Tableau de bord de la solution Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Dans Invoice Capture, le tableau de bord inclut les graphiques qui offrent une vue d’ensemble des factures importées. Ces graphiques peuvent aider le responsable des comptes fournisseurs à analyser les performances du processus de génération de factures. Le responsable de la comptabilité fournisseur peut voir l’état du processus de génération de facture et, en appliquant différents filtres, peut également afficher les détails.

## <a name="available-charts"></a>Graphiques disponibles

Les graphiques suivants sont disponibles sur le tableau de bord :

- **Toutes les factures capturées par statut** : ce graphique présente les statuts suivants pour une facture capturée. En sélectionnant un statut, les utilisateurs peuvent filtrer les factures capturées dans la liste détaillée.

    - Capturé
    - Terminer
    - En cours de révision
    - Obsolète

- **Volume total de facture capturée** : ce graphique montre le nombre de factures capturées par période. Les utilisateurs peuvent modifier la période à l’aide de la liste déroulante.
- **Factures capturées à partir de principaux fournisseurs** : ce graphique montre le nombre total de factures par fournisseur. Les fournisseurs qui ont le plus de factures apparaissent en haut.
- **Jours à terminer par facture avec des exceptions** : ce graphique montre le nombre moyen de jours nécessaires pour saisir une facture. Ces informations peuvent aider le responsable de comptabilité fournisseur à analyser le temps de traitement d’une facture lorsqu’une intervention manuelle est requise. S’il y a une tendance à la hausse, les utilisateurs peuvent revoir les détails du processus et ajuster les paramètres pour aider à réduire le nombre de jours nécessaires.
- **Factures incomplètes par temps d’attente** : ce graphique indique le nombre de jours pendant lesquels une facture capturée n’a pas été générée dans le système de planification des ressources d’entreprise. Plus le nombre de jours en attente est élevé, plus le processus de génération de facture est long. Le responsable de la comptabilité fournisseur peut explorer les factures capturées détaillées et générer des factures dans le système ERP.
