---
title: Génération du fichier d'audit standard pour la France (FEC)
description: Cette rubrique décrit le processus de génération du fichier d'audit standard pour la France (FEC) dans Microsoft Dynamics 365 for Finance and Operations.
author: ShylaThompson
manager: AnnBe
ms.date: 11/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: France
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 931b34b5a88811e359603c1023217951b05f3b57
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852249"
---
# <a name="create-standard-audit-file-for-france-fec"></a>Créer un fichier d'audit standard pour la France (FEC)

[!include [banner](../includes/banner.md)]

Cette procédure vous montre comment générer le fichier d'audit standard (FEC) pour la France dans le format de fichier électronique. L'administration fiscale française a besoin de fichiers d'audit générés au format FEC.

Avant de générer un fichier d'audit FEC, vous devez 
1. Importer la dernière version du **Fichier d'audit FEC français** de la configuration de génération d'états électroniques. Pour plus d'informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
2. Dans la page **Configurations**, développez **Modèle d'exportation des données**, sélectionnez **Mise en correspondance de modèle FEC français**. Définissez **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**

## <a name="generate-the-standard-audit-file-for-france"></a>Génération du fichier d'audit standard pour la France
1. Accédez à **Comptabilité générale** > **Tâches périodiques** > **Exportation de données** pour ouvrir la page **Exportation de données**.
2. Dans le champ **Mise en correspondance des formats**, sélectionnez *Fichier d'audit FEC français*.
3. Cliquez sur **OK**.
4. Dans la page **Paramètres de génération d'états électroniques**, entrez les dates de début et de fin de la période dans les champs **Période - date de début**, **Période - Date de fin** et cliquez sur **OK**.
5. Examinez le fichier généré.
