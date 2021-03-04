---
title: L'utilisateur peut accéder à Ressources humaines mais pas à Onboard ou Attract
description: 'Cette rubrique explique comment résoudre le problème suivant : un utilisateur peut accéder à Microsoft Dynamics 365 Talent - Ressources humaines mais pas à Attract ou Onboard.'
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
ms.openlocfilehash: 6c384d9a7100982eabd201d910e1bea14355dc1f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461145"
---
# <a name="user-can-access-human-resources-but-not-onboard-or-attract"></a>L'utilisateur peut accéder à Ressources humaines mais pas à Onboard ou Attract

[!include [banner](includes/banner.md)]

**Détails de l'environnement**

- Le déploiement de Microsoft Dynamics Lifecycle Services (LCS) a été effectué par l'utilisateur A.
- L'utilisateur A a ajouté l'utilisateur B comme utilisateur de Microsoft Dynamics 365 Human Resources.

**Sortie**

L'utilisateur B peut accéder à Ressources humaines mais ne peut pas accéder à l'application Talent - Attract ou à l'application Talent - Onboard. Lorsque l'utilisateur essaie d'accéder à **Applications d'expérience**, il est dirigé vers un environnement de test à la place.

**Solution**

L'utilisateur B doit se voir octroyer les droits d'afficher l'environnement Microsoft Power Apps que l'utilisateur A a créé lors du processus de mise en service.

Pour plus d'informations, voir la section « Octroi d'accès à l'environnement » dans [Mise en service de Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

**Solution à long terme**

Microsoft envisage d'affecter automatiquement les droits appropriés vers Onboard et Attract lorsqu'un utilisateur est ajouté à Ressources humaines.


[!INCLUDE[footer-include](../includes/footer-banner.md)]