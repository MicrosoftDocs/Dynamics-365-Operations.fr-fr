---
title: Examiner l'état d'une expérience
description: Cette rubrique explique l'état d'une expérience dans le cycle de vie de l'expérimentation dans Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 5ae29fe5ac49d92c261c59d115664b50e87880a0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965100"
---
# <a name="review-the-status-of-an-experiment"></a>Examiner l'état d'une expérience
La configuration et l’exécution d’une expérience dans Dynamics 365 Commerce comportent de nombreuses étapes. Pour plus d'informations sur le cycle de vie de l'expérimentation, consultez [Expérimentation dans Dynamics 365 Commerce](experimentation-overview.md).

Pour savoir où se situe une expérience dans le cycle de vie, dans le générateur de site Commerce, sélectionnez **Expériences** dans le volet de navigation de gauche. Une liste des expériences s'affiche et indique l'état de chaque expérience dans Commerce et dans le service tiers utilisé pour permettre la création des expériences, attribuer des variantes et analyser les données.

Dans la colonne **État de Commerce**, les valeurs suivantes peuvent être affichées. 
- **Brouillon** - L'expérience est connectée à une page ou à un fragment dans Commerce et est en cours de modification.
- **Publié** - Les variantes de l'expérience sont prêtes à être affichées sur votre site web. Si l'expérience est en cours d'exécution dans le service tiers, les utilisateurs du site web verront une variante de la page ou du fragment sélectionné par le service tiers.
- **Non publié** - L'expérience n'est plus disponible sur votre site web. Les utilisateurs du site web ne verront que la version par défaut de la page ou du fragment, même si l'expérience est exécutée dans le service tiers.
- **Terminé** - L'expérience est terminée et une variante a été promue et mise en ligne pour tous les utilisateurs du site web.

De même, dans la colonne **État du tiers**, les valeurs suivantes peuvent être affichées pour indiquer l'état des expériences dans le service tiers.
- **Brouillon** - L'expérience est configurée dans le service tiers mais n'a pas été lancée.
- **En cours** - L'expérience a été lancée dans le service tiers et collecte des données.
- **Suspendu** - L'expérience est suspendue et ne collecte pas de données. Vous devez reprendre l'expérience pour qu'elle collecte à nouveau des données.
- **Archivé** - L'expérience est terminée et a été ajoutée au catalogue dans le service tiers à titre de référence.

Le diagramme ci-dessous montre les deux ensembles d'états et leurs liens.

[ ![États de l'expérimentation](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)


[!INCLUDE[footer-include](../includes/footer-banner.md)]