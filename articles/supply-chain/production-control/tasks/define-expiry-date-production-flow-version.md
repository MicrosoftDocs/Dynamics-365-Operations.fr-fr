--- 
title: "Définir une date d'expiration pour une version de flux de production"
description: "Pour terminer la validité et le traitement d'une version de flux de production à une date donnée, entier ou pour planifier le remplacement d'une version active par une nouvelle version, vous devez définir la date d'expiration de la version."
author: cvocph
manager: AnnBe
ms.date: 10/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6fabeb31720a60bf97d08dabf8ed87ac6af7cbf7
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a>Définir une date d'expiration pour une version de flux de production

[!include [task guide banner](../../includes/task-guide-banner.md)]

Pour terminer la validité et le traitement d'une version de flux de production à une date donnée, entier ou pour planifier le remplacement d'une version active par une nouvelle version, vous devez définir la date d'expiration de la version. Il n'est pas nécessaire de désactiver la version.


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a>Définir une date d'expiration pour mettre fin à une version de flux de production
1. Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez un flux de production qui a une version déjà définie.  
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Cliquez sur Modifier.
5. Dans la liste, marquez la ligne sélectionnée.
6. Entrez une date et une heure dans le champ Date d'expiration.
    * Pour la date d'expiration, une nouvelle version ne démarre pas ni n'est activée. Il n'est également plus possible de créer ou de démarrer des tâches pour ce flux de production. Vous pouvez toujours exécuter les tâches commencées après la date d'expiration.  


