---
title: Impossible de créer un environnement dans le centre d'administration Power Apps
description: Cette rubrique explique comment procéder si l'administrateur ne peut pas créer d'environnement dans le Centre d'administration Microsoft Power Apps.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 50a5aac71ec8ed850cfad32bdb1b8d589eb2885a
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413559"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>Impossible de créer un environnement dans le centre d’administration Power Apps

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Sortie**

- Le client/administrateur d’environnement ne peut pas créer d’environnement dans le Centre d’administration Microsoft Power Apps.
- L’utilisateur n’a pas de licence qui donne le droit de créer des environnements.

**Solution**

Assurez-vous que l’administrateur du client a attribué une Licence P2 Power Apps à l’utilisateur créant l’environnement. Les plans de service Microsoft Dynamics suivants fournissent des autorisations pour créer des environnements :

| Unité de gestion de stock (SKU) de produit général       | Plan de services Power Apps P2  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | Power Apps pour Dynamics 365 |
| Microsoft Dynamics 365 Plan Enterprise Edition | Power Apps pour Dynamics 365 |

Notez que différentes références Microsoft Office fournissent également le droit, ainsi que les références Power Apps Plan 2 autonomes. L’aspect important est que l’une de ces UGS doit être présente.

1. Atteindre [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Créez les environnements en suivant les instructions dans [Mettre en service Human Resources](/dynamics365/unified-operations/talent/provisioning-talent).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
