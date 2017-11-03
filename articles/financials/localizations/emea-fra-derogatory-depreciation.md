---
title: "Amortissement dérogatoire pour la France"
description: "Cet article fournit des informations sur l'amortissement dérogatoire et la manière de le paramétrer. Dans l'amortissement dérogatoire, un montant d'amortissement supplémentaire est calculé comme étant la différence entre le montant d'amortissement du modèle de valeur de taxe et le montant d'amortissement du modèle de valeur comptable pendant la durée de vie d'une immobilisation."
author: Anasyash
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 30321
ms.search.region: France
ms.author: anasyash
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1fd82e773fd159fe716a3761e2a906daadd472fc
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="derogatory-depreciation-for-france"></a>Amortissement dérogatoire pour la France

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur l'amortissement dérogatoire et la manière de le paramétrer. Dans l'amortissement dérogatoire, un montant d'amortissement supplémentaire est calculé comme étant la différence entre le montant d'amortissement du modèle de valeur de taxe et le montant d'amortissement du modèle de valeur comptable pendant la durée de vie d'une immobilisation.

Dans l'amortissement dérogatoire, un montant d'amortissement supplémentaire est calculé comme étant la différence entre le montant d'amortissement du modèle de valeur de taxe et le montant d'amortissement du modèle de valeur comptable pendant la durée de vie d'une immobilisation. Ce montant d'amortissement supplémentaire est validé en tant que type de transaction **Augmentation dérogatoire** dans le modèle de valeur comptable si le montant d'amortissement du modèle de valeur de taxe est supérieur au montant d'amortissement du modèle de valeur comptable. Ce montant d'amortissement supplémentaire est également validé en tant que type de transaction **Diminution dérogatoire**. Par exemple, une immobilisation avec un montant d'acquisition de 1 000 EUR est amortie dans le modèle de valeur comptable sur cinq ans et dans le modèle de valeur de taxe sur trois ans. Au cours de la première année, l'amortissement comptable est de 200 EUR (1 000 ÷ 5), et l'amortissement fiscal est de 333,33 EUR (1 000 ÷ 3). Par conséquent, le montant supplémentaire est de 133,33 EUR (\[1 000 ÷ 3\] – \[1 000 ÷ 5\] ou 333,33 – 200,00) et est validé comme augmentation dérogatoire. Après la troisième année du cycle de vie, l'amortissement comptable est de 200 EUR (1 000 ÷ 5), et l'amortissement fiscal est de 0 (zéro). Par conséquent, le montant supplémentaire est de 200 EUR (0,00 – \[1 000 ÷ 5\] ou 0,00 – 200,00) et est validé comme diminution dérogatoire. Pour utiliser l'amortissement dérogatoire, commencez par créer et paramétrer des modèles de valeur comptable et des modèles de valeur de taxe dérogatoire, puis affectez-les à une immobilisation. Pour le modèle dérogatoire, activez le champ **Modèle dérogatoire** dans la page **Modèles de valeur**. Pour le modèle comptable, sélectionnez le modèle dérogatoire dans le champ **Calcul dérogatoire**. Les conditions suivantes doivent être remplies :

-   Le champ **Amortissement**doit être activé pour les deux modèles de valeur.
-   **Accepter la valeur nette négative** est désactivé dans les deux modèles de valeur.
-   Les deux modèles de valeur ont la même valeur dans le champ **Calendrier**.
-   Les deux modèles de valeur doivent avoir la même couche de validation définie sur**Actuel**.
-   L'amortissement complet doit être activé sur le profil d'amortissement sélectionné dans le modèle dérogatoire si la méthode d'amortissement est de type **Dégressif**.
-   Les profils d'amortissement sélectionnés pour les deux modèles de valeur doivent utiliser les mêmes paramètres pour **Année d'amortissement** et **Fréquence**.
-   Les deux modèles de valeur doivent avoir le même paramètre dans le champ **Convention d'amortissement** de la page **Groupe d'immobilisations/modèle de valeur**.
-   Les dates**Mis en service** doivent être les mêmes dans les deux modèles de valeur à partir du moment où les modèles sont affectés à une immobilisation spécifique.

Dans la page **Profils de validation d'immobilisation**, paramétrez les comptes généraux pour les transactions **Augmentation dérogatoire** et **Diminution dérogatoire** dans le modèle de valeur comptable. Dans la page **Paramètres de cession**, vous pouvez effectuer le paramétrage pour valider les montants d'augmentation dérogatoire ou de diminution dérogatoire dans des comptes généraux spécifiques durant la cession. Vous pouvez consulter les montants d'amortissement dérogatoire pour le modèle de valeur comptable dans la page **Soldes d'immobilisation**, l'état **Note d'immobilisation** ou l'état **Mouvements d'immobilisations**.




