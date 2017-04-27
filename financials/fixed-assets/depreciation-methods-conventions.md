---
title: "Méthodes et conventions d&quot;amortissement"
description: "Cet article fournit une vue d&quot;ensemble des conventions d&quot;amortissement et des méthodes d&quot;amortissement prises en charge par Microsoft Dynamics AX."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 51c053e6c130d20258e02284d097431a18bb38cb
ms.lasthandoff: 03/31/2017


---

# <a name="depreciation-methods-and-conventions"></a>Méthodes et conventions d'amortissement

[!include[banner](../includes/banner.md)]


Cet article fournit une vue d'ensemble des conventions d'amortissement et des méthodes d'amortissement prises en charge par Microsoft Dynamics AX.

Vous pouvez sélectionner diverses méthodes et conventions d'amortissement. L'objet des méthodes est l'attribution de la valeur amortissable de l'immobilisation dans des périodes fiscales. La valeur amortissable de l'immobilisation correspond au prix d'acquisition, moins la valeur de mise au rebut, le cas échéant. 

Si vous utilisez des conventions d'amortissement et que vous modifiez la dernière date d'exécution de l'amortissement pour une immobilisation, ce qui fait que certains amortissements ne sont pas pris en compte, l'amortissement de l'année précédente peut être supérieur ou inférieur aux prévisions. L'amortissement est ajusté du nombre de périodes d'amortissement affectées par la modification de la dernière date d'exécution de l'amortissement.

Par exemple, si vous utilisez la convention d'amortissement semestrielle sur trois ans, l'amortissement dure normalement 3 ans 1/2. Si vous modifiez la dernière date d'exécution de l'amortissement au cours des 3 ans 1/2, la dernière année d'amortissement se déplace sur le nombre de périodes affectées. Si vous déplacez la date de trois mois, la dernière année aura neuf mois d'amortissement, contre six normalement.

Vous pouvez choisir parmi les conventions d'amortissement suivantes.


-   Semestre
-   Mois complet
-   Mi-trimestre
-   Mi-mois (1er du mois)
-   Mi-mois (15 du mois)
-   Semestre (début d'exercice)
-   Semestre (exercice suivant)

Vous pouvez choisir parmi les méthodes d'amortissement suivantes.
-   Durée de vie linéaire
-   Dégressif
-   Manuel
-   Facteur
-   Consommation
-   Durée de vie linéaire restante
-   Amortissement dégressif de 200 %
-   Amortissement dégressif de 175 %
-   Amortissement dégressif de 150 %
-   Amortissement dégressif de 125 %

 



<a name="see-also"></a>Voir également :
--------

[Amortissement des immobilisations](fixed-asset-depreciation.md)

[Amortissement linéaire sur la durée de vie](Straight-line-service-life-depreciation.md)

[Amortissement dégressif](reduce-balance-depreciation.md)

[Amortissement manuel](manual-depreciation.md)

[Amortissement paramétrable](factor-depreciation.md)

[Amortissement de consommation](consumption-depreciation.md)

[Amortissement linéaire sur la durée de vie restante](straight-line-life-remaining-depreciation.md)

[Amortissement dégressif de 125 %](125-percent-reducing-balance-depreciation.md)

[Amortissement dégressif de 150 %](150-percent-reducing-balance-depreciation.md)

[Amortissement dégressif de 175 %](175-percent-reducing-balance-depreciation.md)

[Amortissement dégressif de 200 %](200-percent-reducing-balance-depreciation.md)



