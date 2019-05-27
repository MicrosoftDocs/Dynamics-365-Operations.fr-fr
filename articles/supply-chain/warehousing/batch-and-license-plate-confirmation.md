---
title: Confirmation du contenant et du lot
description: Cette rubrique décrit comment vous paramétrez et appliquez la confirmation du contenant et du lot d'un périphérique mobile.
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: efab5b11782fd2344fb5f532272007d187c1465b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563900"
---
# <a name="batch-and-license-plate-confirmation"></a>Confirmation du contenant et du lot

[!include [banner](../includes/banner.md)]

La confirmation du lot vous permet de confirmer que le lot approprié est prélevé du périphérique mobile. Lors du prélèvement initial du travail pour les éléments au-dessus uniquement, où lot au-dessus indique que le lot dépasse l'emplacement dans la hiérarchie de recherche, vous devez vérifier que le lot sélectionné correspond au lot de la ligne de travail. 

La confirmation du contenant vous permet de confirmer que le contenant approprié est prélevé du périphérique mobile. Lors du travail de prélèvement d'un emplacement intermédiaire, vous devez vérifier que le contenant qui est prélevé correspond au contenant associé au travail. Si le travail est lancé en analysant un contenant, cette étape de confirmation sera ignorée.

## <a name="where-it-applies"></a>Dans ce cas
La confirmation s'applique dans les scénarios suivants :

- La confirmation de lot s'applique aux prélèvements d'origine du travail des éléments au-dessus.
- La confirmation de contenant s'applique aux prélèvements à partir des emplacements intermédiaires.

## <a name="set-up-batch-and-license-plate-confirmation"></a>Configurer la confirmation du contenant et du lot
Vous pouvez configurer la confirmation du lot et du contenant à l'aide des options de menu du périphérique mobile.  
1.  Dans les options de menu de l'appareil mobile, accédez à Paramétrage de la confirmation du travail.  
2.  Permet de sélectionner l'option pour la confirmation du lot ou du contenant. Les deux options sont disponibles pour les prélèvements de type travail qui n'ont pas la confirmation automatique activée.  
