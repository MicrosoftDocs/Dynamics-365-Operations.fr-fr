---
title: Mise à jour collective des immobilisations
description: Si vous utilisez des registres, vous pouvez modifier les conventions d'amortissement pour les groupes d'immobilisations faisant partie du même registre.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3521
ms.assetid: 50207ffb-6b89-4fb9-92e9-928bc0729489
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 30b9aaaabcac09c9147c350422924a23f785c0ce
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177703"
---
# <a name="fixed-asset-mass-update"></a>Mise à jour collective des immobilisations

[!include [banner](../includes/banner.md)]

Si vous utilisez des registres, vous pouvez modifier les conventions d'amortissement pour les groupes d'immobilisations faisant partie du même registre.

Par exemple, si vous vous trouvez aux États-Unis et que vous placez plus de 40 pour cent de vos immobilisations en service durant le quatrième trimestre de l'année, vous devez utiliser la convention d'amortissement à mi-trimestre. Vous pouvez utiliser le processus pour effectuer une mise à jour collective afin de modifier toutes les immobilisations nécessitant la nouvelle convention d'amortissement. 

Lorsque vous mettez à jour la convention d'amortissement pour les actifs, vous supprimez toutes les transactions d'amortissement qui existent pour ces actifs. Vous supprimez également toutes les transactions d'ajustement de l'amortissement, les transactions d'amortissement de la prime et les transactions d'amortissement exceptionnel pour ces actifs. 

Pour mettre à jour la convention d'amortissement pour des immobilisations déjà cédées, vous devez commencer par supprimer les transaction de cession existantes. Vous devez également supprimer toutes les transactions générées en raison du processus de cession. 

Une fois la convention d'amortissement mise à jour pour les immobilisations, vous pouvez traiter l'amortissement et un amortissement exceptionnel pour chaque immobilisation. Vous pouvez également opérer des ajustements d'amortissement manuels si nécessaire.





