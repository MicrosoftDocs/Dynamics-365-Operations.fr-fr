---
title: Résoudre les problèmes liés à la prise en charge des solutions
description: Cette rubrique fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés à la prise en charge des solutions.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: aa5ba0cfb127f20012237774fe948c23731eb56f8680d9fa23309e189683dbf3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736348"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>Résoudre les problèmes liés à la prise en charge des solutions

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Cette rubrique fournit des informations sur la résolution des problèmes de l’intégration de la double écriture entre les applications Finance and Operations et Dataverse. Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés à la prise en charge des solutions.

> [!IMPORTANT]
> Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d’administrateur système ou les identifiants d’admin client Microsoft Azure Active Directory (Azure AD). La section pour chaque problème explique si un rôle spécifique ou des informations d’identification sont requis.

## <a name="error-on-the-dual-write-page"></a>Erreur sur la page Double écriture

Sur la page **Double écriture**, vous pouvez recevoir un message d’erreur semblable à l’exemple suivant :

*L’entité avec un nom « msdyn \_dualwriteentitymap » avec namemapping=’Logical’ est introuvable dans le MetadataCache.*

Pour résoudre le problème, assurez-vous que la solution principale de double écriture est installée dans Dataverse. La solution principale de double écriture est une condition préalable à la prise en charge des solutions.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]