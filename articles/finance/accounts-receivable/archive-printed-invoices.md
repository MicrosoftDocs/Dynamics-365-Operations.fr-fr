---
title: Archiver les factures client imprimées avec des numéros de hachage
description: Cette rubrique explique comment activer l’archivage afin de stocker des factures client imprimées avec des numéros de hachage.
author: ilkond
ms.date: 09/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 093b1b8c516c0c659e7970d17d3f84b2ed0ccf8f
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500525"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a>Archiver les factures client imprimées avec des numéros de hachage

[!include [banner](../includes/banner.md)]

Dans certains pays, il existe une obligation légale de stocker les numéros de hachage calculés dans le système avec les impressions de certains documents. Les numéros de hachage peuvent être utilisés pour les rapports destinés aux autorités et pendant les audits.

Cette rubrique explique comment configurer l’archivage afin de stocker des factures client imprimées avec des numéros de hachage.

## <a name="prerequisites"></a>Conditions préalables

- Dans l’espace de travail **Gestion des fonctionnalités**, activez la fonctionnalité **Archiver les factures client imprimées avec des numéros de hachage**. Pour plus d’informations, voir [Vue d’ensemble de la gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Configurez les formats imprimables des documents requis dans **Gestion de l’impression**.

Cette fonctionnalité s’applique aux documents suivants.

**Comptabilité client**
- Facture client
- Avoir du client
- Facture financière
- Avoir financier

**Gestion et comptabilité des projets**
- Facture de projet
- Avoir de projet

## <a name="configure-customer-master-data"></a>Configurer les données principales du client
Procédez comme suit pour configurer les données client et activer la possibilité d’enregistrer automatiquement les factures imprimées en tant que pièces jointes.

1. Accédez à **Comptabilité client** > **Tous les clients**. 
2. Sélectionnez un client, et sur le raccourci **Facture et livraison**, dans la section **FACTURE ÉLECTRONIQUE**, dans le champ **Pièce jointe à la facture électronique**, sélectionnez **Oui**.

## <a name="print-invoices"></a>Imprimer les factures
Vous pouvez publier et imprimer n’importe quelle facture financière, facture client et facture de projet ou avoir pour le client configuré dans la procédure précédente.

Ouvrez la page **Pièces jointes** pour la facture imprimée. Sur le raccourci **Pièce jointe**, dans le groupe de champs **Détails supplémentaires**, dans **Numéro de hachage du document**, recherchez le numéro de hachage enregistré calculé pour la facture imprimée.

![Numéro de hachage de la pièce jointe.](media/attach-hash-num.jpg)

