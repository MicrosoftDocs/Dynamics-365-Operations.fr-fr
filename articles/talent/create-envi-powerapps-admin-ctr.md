---
title: Impossible de créer un environnement dans le Centre d'administration PowerApps
description: Cette rubrique explique comment procéder si l'administrateur ne peut pas créer d'environnement dans le Centre d'administration Microsoft PowerApps.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 96119ca869cbbb15ed8d8d5d0fe3b0f94b5f36cc
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742840"
---
# <a name="cant-create-an-environment-in-the-powerapps-admin-center"></a>Impossible de créer un environnement dans le centre d'administration de PowerApps

[!include [banner](includes/banner.md)]

**Problème**

- Le client/administrateur d'environnement ne peut pas créer d'environnement dans le Centre d'administration Microsoft PowerApps.
- Une licence qui offre aux utilisateurs le droit d'effectuer l'étape de création d'environnement n'a pas été affectée directement à l'utilisateur qui effectue cette étape.

**Solution**

Assurez-vous que l'administrateur de client a affecté une licence PowerApps P2 valide directement à l'utilisateur qui effectuera l'étape de création d'environnement. Voici les plans de service Microsoft Dynamics qui fournissent ce droit.

| Unité de gestion de stock (SKU) de produit général       | Plan de service PowerApps P2  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | PowerApps pour Dynamics 365 |
| Microsoft Dynamics 365 Plan Enterprise Edition | PowerApps pour Dynamics 365 |

Notez que différents SKU Microsoft Office fournissent également le droit, ainsi que les UGS PowerApps Plan 2 autonomes. L'aspect important est que l'une de ces UGS doit être présente.

1. Atteindre [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Créez les environnements en suivant les instructions dans [Mettre en service Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).
