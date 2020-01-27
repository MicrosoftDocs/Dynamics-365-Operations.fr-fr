---
title: Déclarer comme terminé à un emplacement qui ne fait pas l'objet d'un contrôle de contenant depuis le périphérique pour le bon de travail
description: Cette rubrique décrit le processus pour compléter les produits finis sur un ordre de fabrication dans le stock lorsqu'un contenant contrôle l'emplacement.
author: johanhoffmann
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: 63073035941cd2ef343c65364536fe76a9b71430
ms.sourcegitcommit: af36eb17b36092a3101bbfc96486b25036676558
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2020
ms.locfileid: "2935120"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a>Déclarer comme terminé à un emplacement qui ne fait pas l'objet d'un contrôle de contenant depuis le périphérique pour le bon de travail 

Le processus nommé Déclaration de fin complète des produits finis sur un ordre de fabrication au stock. Si le produit fini est activé pour les processus avancés d'entrepôt, le produit est déclaré comme fini à un emplacement appelé l'emplacement de sortie de production. Pour plus d'informations sur le paramétrage de l'emplacement de sortie de production, voir [Emplacement de sortie de production](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).

Si l'emplacement de sortie de production est contrôlé par le contenant, un contenant doit être fourni lors du signalement comme terminé. Le champ **Contenant** est visible sous l'invite **Saisie de l'avancement** sur la page **Périphérique des bons de travail**. Le champ n'est visible que sur l'invite **Signaler les progrès** lorsque vous créez un rapport sur la dernière opération de l'ordre de fabrication et que l'article de l'ordre de fabrication est activé pour les processus de gestion de l'entrepôt. 

Il existe deux options pour fournir le contenant
- L'utilisateur sélectionne un contenant existant dans le champ de contenant.
- Le contenant est automatiquement généré à partir d'une souche de numéros et par défaut dans le champ du contenant.

L'option de génération automatique de contenant est configurée en sélectionnant l'option **Générer un contenant** sur la page **Configurer le bon de travail pour les périphériques**.
