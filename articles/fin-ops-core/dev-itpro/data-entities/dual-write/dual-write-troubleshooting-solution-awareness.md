---
title: Résoudre les problèmes liés à la prise en charge des solutions
description: Cet article fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés à la prise en charge des solutions.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c70287cb8ec29fb622f3aefff971b884339e4205
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289422"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>Résoudre les problèmes liés à la prise en charge des solutions

[!include [banner](../../includes/banner.md)]





Cet article fournit des informations sur le dépannage de l’intégration de la double-écriture entre les applications de finances et d’opérations et Dataverse. Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés à la prise en charge des solutions.

> [!IMPORTANT]
> Certains des problèmes abordés dans cet article peuvent exiger le rôle d’administrateur système ou les identifiants d’admin client Microsoft Azure Active Directory (Azure AD). La section pour chaque problème explique si un rôle spécifique ou des informations d’identification sont requis.

## <a name="error-on-the-dual-write-page"></a>Erreur sur la page Double écriture

Sur la page **Double écriture**, vous pouvez recevoir un message d’erreur semblable à l’exemple suivant :

*L’entité avec un nom « msdyn \_dualwriteentitymap » avec namemapping=’Logical’ est introuvable dans le MetadataCache.*

Pour résoudre le problème, assurez-vous que la solution principale de double écriture est installée dans Dataverse. La solution principale de double écriture est une condition préalable à la prise en charge des solutions.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
