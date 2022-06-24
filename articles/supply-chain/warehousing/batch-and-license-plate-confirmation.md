---
title: Confirmation du contenant et du lot
description: Cet article décrit comment vous paramétrez et appliquez la confirmation du contenant et du lot d’un périphérique mobile.
author: Mirzaab
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef0d528d23c1ee9424e35e29d39121d42ba548e5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903722"
---
# <a name="batch-and-license-plate-confirmation"></a>Confirmation du contenant et du lot

[!include [banner](../includes/banner.md)]

La confirmation du lot vous permet de confirmer que le lot approprié est prélevé du périphérique mobile. Lors du prélèvement initial du travail pour les articles *Batch-above\[location\]*, où « batch-above » (lot au-dessus) indique que le lot est placé plus haut que l’emplacement dans la hiérarchie de recherche, vous devez vérifier que le lot sélectionné correspond au lot de la ligne de travail.

La confirmation du contenant vous permet de confirmer que le contenant approprié est prélevé du périphérique mobile. Lors du travail de prélèvement d’un emplacement intermédiaire, vous devez vérifier que le contenant qui est prélevé correspond au contenant associé au travail. Si le travail est lancé en analysant un contenant, cette étape de confirmation sera ignorée.

## <a name="where-it-applies"></a>Dans ce cas

La confirmation s’applique dans les scénarios suivants :

- La confirmation de lot s’applique aux prélèvements d’origine du travail des éléments au-dessus.
- La confirmation de contenant s’applique aux prélèvements à partir des emplacements intermédiaires.

> [!IMPORTANT]
> Le réapprovisionnement n’est pas pris en charge pour la confirmation de contenant. Lors de l’exécution du travail de réapprovisionnement, aucune étape de confirmation de contenant n’est créée.

## <a name="set-up-batch-and-license-plate-confirmation"></a>Configurer la confirmation du contenant et du lot

Vous pouvez configurer la confirmation du lot et du contenant à l’aide des options de menu du périphérique mobile.

1. Dans les options de menu de l’appareil mobile, accédez à Paramétrage de la confirmation du travail.  
1. Permet de sélectionner l’option pour la confirmation du lot ou du contenant. Les deux options sont disponibles pour les prélèvements de type travail qui n’ont pas la confirmation automatique activée.  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
