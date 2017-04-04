---
title: "Amortissement dérogatoire pour la France"
description: "Cet article fournit des informations sur l&quot;amortissement dérogatoire et la manière de le paramétrer. Dans l&quot;amortissement dérogatoire, un montant d&quot;amortissement supplémentaire est calculé comme étant la différence entre le montant d&quot;amortissement du modèle de valeur de taxe et le montant d&quot;amortissement du modèle de valeur comptable pendant la durée de vie d&quot;une immobilisation."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30321
ms.assetid: be90464e-2cce-445c-b95b-79ec559b411e
ms.search.region: France
ms.author: anasyash
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 81bc0eed25bff53e4a239d66effe9be5921342a0
ms.lasthandoff: 03/31/2017


---

# <a name="derogatory-depreciation-for-france"></a>Amortissement dérogatoire pour la France

Cet article fournit des informations sur l'amortissement dérogatoire et la manière de le paramétrer. Dans l'amortissement dérogatoire, un montant d'amortissement supplémentaire est calculé comme étant la différence entre le montant d'amortissement du modèle de valeur de taxe et le montant d'amortissement du modèle de valeur comptable pendant la durée de vie d'une immobilisation.

Dans l'amortissement dérogatoire, un montant d'amortissement supplémentaire est calculé comme étant la différence entre le montant d'amortissement du modèle de valeur de taxe et le montant d'amortissement du modèle de valeur comptable pendant la durée de vie d'une immobilisation. Ce montant d'amortissement supplémentaire est validé en tant que type de transaction **Augmentation dérogatoire** dans le modèle de valeur comptable si le montant d'amortissement du modèle de valeur de taxe est supérieur au montant d'amortissement du modèle de valeur comptable. Ce montant d'amortissement supplémentaire est également validé en tant que type de transaction **Diminution dérogatoire**. Par exemple, une immobilisation avec un montant d'acquisition de 1 000 EUR est amortie dans le modèle de valeur comptable sur cinq ans et dans le modèle de valeur de taxe sur trois ans. Au cours de la première année, l'amortissement comptable est de 200 EUR (1 000 ÷ 5), et l'amortissement fiscal est de 333,33 EUR (1 000 ÷ 3). Par conséquent, le montant supplémentaire est EUR 133,33 (3 ÷ 5 ÷\]\]\[1.000 – \[1.000, soit 333,33 – 200,00) et validé comme augmentation dérogatoire. Après la troisième année du cycle de vie, l'amortissement comptable est de 200 EUR (1 000 ÷ 5), et l'amortissement fiscal est de 0 (zéro). Par conséquent, le montant supplémentaire est EUR 200 (0,00 – 5 ÷\]\[1.000, soit 0,00 – 200,00) et validé comme une baisse dérogatoire. Pour utiliser l'amortissement dérogatoire, commencez par créer et paramétrer des modèles de valeur comptable et des modèles de valeur de taxe dérogatoire, puis affectez-les à une immobilisation. Pour le modèle dérogatoire, activez le champ **Modèle dérogatoire** dans la page **Modèles de valeur**. Pour le modèle comptable, sélectionnez le modèle dérogatoire dans le champ **Calcul dérogatoire**. Les conditions suivantes doivent être remplies :

-   Le champ **Amortissement **doit être activé pour les deux modèles de valeur.
-   **Accepter la valeur nette négative** est désactivé dans les deux modèles de valeur.
-   Les deux modèles de valeur ont la même valeur dans le champ **Calendrier**.
-   Les deux modèles de valeur doivent avoir la même couche de validation définie sur** Actuel**.
-   L'amortissement complet doit être activé sur le profil d'amortissement sélectionné dans le modèle dérogatoire si la méthode d'amortissement est de type **Dégressif**.
-   Les profils d'amortissement sélectionnés pour les deux modèles de valeur doivent utiliser les mêmes paramètres pour **Année d'amortissement** et **Fréquence**.
-   Les deux modèles de valeur doivent avoir le même paramètre dans le champ **Convention d'amortissement** de la page **Groupe d'immobilisations/modèle de valeur**.
-   Les dates** Mis en service** doivent être les mêmes dans les deux modèles de valeur à partir du moment où les modèles sont affectés à une immobilisation spécifique.

Dans la page **Profils de validation d'immobilisation**, paramétrez les comptes généraux pour les transactions **Augmentation dérogatoire** et **Diminution dérogatoire** dans le modèle de valeur comptable. Dans la page **Paramètres de cession**, vous pouvez effectuer le paramétrage pour valider les montants d'augmentation dérogatoire ou de diminution dérogatoire dans des comptes généraux spécifiques durant la cession. Vous pouvez consulter les montants d'amortissement dérogatoire pour le modèle de valeur comptable dans la page **Soldes d'immobilisation**, l'état **Note d'immobilisation** ou l'état **Mouvements d'immobilisations**.


