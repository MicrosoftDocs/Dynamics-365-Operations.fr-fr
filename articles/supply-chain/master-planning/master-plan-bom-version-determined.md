---
title: Déterminer la version de nomenclature
description: Lors de l’éclatement d’une demande, si le type d’ordre par défaut d’un article est défini sur Production, le moteur de planification détecte une version de nomenclature valide dans le site.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6f1f1656f0ef04799b1ce6b397dac0f829e41c9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251935"
---
# <a name="determine-the-bom-version"></a>Déterminer la version de nomenclature

[!include [banner](../includes/banner.md)]

Lors de l’éclatement d’une demande, si le type d’ordre par défaut d’un article est défini sur Production, le moteur de planification détecte une version de nomenclature valide dans le site. 

La dimension du site est toujours identifiée et indiquée dans la transaction de demande. Le processus suivant permet de déterminer la version de nomenclature à utiliser :

-   Si une version de nomenclature est définie pour l’article dans le site de la demande, la nomenclature spécifique au site est utilisée.
-   Si aucune version de nomenclature n’est définie pour l’article dans le site de la demande, une nomenclature générale est utilisée. Une telle nomenclature n’indique pas de site et est valide pour plusieurs sites. Si une nomenclature générale existe, elle est utilisée.
-   S’il n’y a aucune version de nomenclature à utiliser, l’éclatement de la demande est arrêté à ce stade.

Une version de nomenclature valide (spécifique au site ou générale) doit satisfaire aux critères requis de date et de quantité.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]