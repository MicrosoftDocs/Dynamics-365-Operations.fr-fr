---
title: Prélever le lot le plus ancien sur un appareil mobile
description: Cette rubrique décrit comment vous paramétrez et appliquez les options de prélèvement du lot le plus ancien à partir d’un appareil mobile.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eb0012689cc814daaf8f685c81d4630164b6e0c5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810436"
---
# <a name="pick-oldest-batch-on-a-mobile-device"></a>Prélever le lot le plus ancien sur un appareil mobile

[!include [banner](../includes/banner.md)]

Vous pouvez accéder à la configuration **Prélever le traitement par lots le plus ancien** via le menu d’un appareil mobile qui vous permet de forcer ou d’avertir des collaborateurs de l’entrepôt pour qu’ils prélèvent le lot le plus ancien de son emplacement actuel.  

## <a name="where-it-applies"></a>Dans ce cas
Le prélèvement du lot le plus ancien est configuré sur les options du menu de l’appareil mobile et applique le prélèvement pour les articles du lot ci-dessous.

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a>Comment définir la configuration du prélèvement du lot le plus ancien 
Pour les articles définis pour utiliser le travail existant, **Prélever le traitement par lots le plus ancien** peut être défini sur **Aucun**, **Avertir** ou **Forcer** du menu d’un appareil mobile.

**Aucun** : Les collaborateurs ne recevront aucun message et ils seront autorisés à prélever n’importe quel lot dans leur emplacement.

**Avertir** et **Forcer** : Une liste des lots avec la date d’expiration la plus ancienne sera affichée au-dessus du contrôle du lot lorsque le collaborateur sélectionne un lot. Si l’emplacement est contrôlé par le contenant, une liste des contenants avec le lot le plus ancien sera affichée au-dessus du contrôle du contenant. 
-   **Avertir** : Si un collaborateur choisit un contenant ou un lot qui ne s’affiche pas dans la liste, le contrôle sera grisé et un avertissement indiquera qu’il existe un lot plus ancien à sélectionner. Pour pouvoir poursuivre le travail, le collaborateur peut resélectionner le même contenant ou lot.  
-   **Forcer** : Les collaborateurs continueront à recevoir le message qu’il existe un lot plus ancien à prélever.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]