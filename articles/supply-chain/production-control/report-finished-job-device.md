---
title: Déclarer comme terminé à un emplacement qui ne fait pas l'objet d'un contrôle de contenant depuis le périphérique pour le bon de travail
description: Cette rubrique décrit le processus pour compléter les produits finis sur un ordre de fabrication dans le stock lorsqu'un contenant contrôle l'emplacement.
author: johanhoffmann
manager: AnnBe
ms.date: 09/06/2019
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
ms.openlocfilehash: 35ad27a6b8a52bfd086fbe4fc57b1681ff88fd5b
ms.sourcegitcommit: 58db26b7edf02e7c33aaaf1c934e3263aa74b01f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/11/2019
ms.locfileid: "1995140"
---
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a>Déclarer comme terminé à un emplacement qui ne fait pas l'objet d'un contrôle de contenant depuis le périphérique pour le bon de travail 

Le processus nommé Déclaration de fin complète des produits finis sur un ordre de fabrication au stock. Si le produit fini est activé pour les processus avancés d'entrepôt, le produit est déclaré comme fini à un emplacement appelé l'emplacement de sortie de production. Pour plus d'informations sur le paramétrage de l'emplacement de sortie de production, voir [Emplacement de sortie de production](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).

Vous devez sélectionner un numéro de contenant existant pour effectuer cette tâche. Si l'emplacement de sortie de production est paramétré pour être suivi par contenant, un numéro de contenant doit être inclus lors de la déclaration de l'emplacement de sortie de production comme fini. Le champ **Contenant** est visible sous l'invite **Saisie de l'avancement** sur la page **Périphérique des bons de travail**. Le champ n'est visible que sous l'invite **Saisie de l'avancement** lors de la déclaration de la dernière opération de l'ordre de fabrication. Le champ est affiché uniquement si l'article pour l'ordre de fabrication est activé pour les processus de gestion des entrepôts. 
