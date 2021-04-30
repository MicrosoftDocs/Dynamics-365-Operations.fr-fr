---
title: Impossible de créer un environnement dans le centre d’administration Power Apps
description: Cet article explique comment procéder si l’administrateur ne peut pas créer d’environnement dans le Centre d’administration Microsoft Power Apps.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 26a228229a09e74809a048675a3ff90025f2a26c
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892225"
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