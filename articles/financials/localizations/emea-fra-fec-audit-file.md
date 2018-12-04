---
title: "Génération du fichier d'audit standard pour la France (FEC)"
description: "Cette rubrique décrit le processus de génération du fichier d'audit standard pour la France (FEC) dans Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 11/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: France
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 62e418550d4a8ea5e31c51478574491753b4a481
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="create-standard-audit-file-for-france-fec"></a>Créer un fichier d'audit standard pour la France (FEC)

[!include [banner](../includes/banner.md)]

Cette procédure vous montre comment générer le fichier d'audit standard (FEC) pour la France dans le format de fichier électronique. L'administration fiscale française a besoin de fichiers d'audit générés au format FEC.

Avant de pouvoir générer un fichier FEC, vous devez importer la version la plus récente de la Configuration de la gestion des états électroniques **Importer le fichier XML des données de comptabilité FEC de configuration (FR)**. Pour plus d'informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)

## <a name="generate-the-standard-audit-file-for-france"></a>Génération du fichier d'audit standard pour la France
1.  Accédez à **Comptabilité** > **Recherches et états** > **États de Comptabilité** > **Exportation de données comptables FEC** pour ouvrir la page **Paramètres des états électroniques**.
2.  Entrez la plage de dates du fichier.
3.  Cliquez sur **OK**.

