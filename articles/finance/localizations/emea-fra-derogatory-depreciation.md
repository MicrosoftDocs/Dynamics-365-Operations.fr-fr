---
title: Amortissement dérogatoire pour la France
description: Cet article fournit des informations sur l'amortissement dérogatoire et la manière de le paramétrer. Dans l'amortissement dérogatoire, un montant d'amortissement supplémentaire est calculé comme étant la différence entre le montant d'amortissement du modèle de valeur de taxe et le montant d'amortissement du modèle de valeur comptable pendant la durée de vie d'une immobilisation.
author: Anasyash
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetPosting, AssetBook, AssetBookTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 30321
ms.search.region: France
ms.author: anasyash
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cb23008f7c2cfc90cd67550607fcc1c396e3bd2d
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773467"
---
# <a name="derogatory-depreciation-for-france"></a>Amortissement dérogatoire pour la France

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur l'amortissement dérogatoire et la manière de le paramétrer. Dans l'amortissement dérogatoire, un montant d'amortissement supplémentaire est calculé comme étant la différence entre le montant d'amortissement du Registre des taxes et le montant d'amortissement du livre comptable pendant la durée de vie d'une immobilisation.

Ce montant d'amortissement supplémentaire est validé en tant que type de transaction **Augmentation dérogatoire** dans le livre comptable si le montant d'amortissement du registre des taxes est supérieur au montant d'amortissement du livre comptable. Ce montant d'amortissement supplémentaire est également validé en tant que type de transaction **Diminution dérogatoire**. Par exemple, une immobilisation avec un montant d'acquisition de 1 000 EUR est amortie dans le livre comptable sur cinq ans et dans le registre des taxes sur trois ans. Au cours de la première année, l'amortissement comptable est de 200 EUR (1 000 ÷ 5), et l'amortissement fiscal est de 333,33 EUR (1 000 ÷ 3). Par conséquent, le montant supplémentaire est de 133,33 EUR (\[1 000 ÷ 3\] – \[1 000 ÷ 5\] ou 333,33 – 200,00) et est validé comme augmentation dérogatoire. Après la troisième année du cycle de vie, l'amortissement comptable est de 200 EUR (1 000 ÷ 5), et l'amortissement fiscal est de 0 (zéro). Par conséquent, le montant supplémentaire est de 200 EUR (0,00 – \[1 000 ÷ 5\] ou 0,00 – 200,00) et est validé comme diminution dérogatoire. Pour utiliser l'amortissement dérogatoire, commencez par créer et paramétrer des modèles de valeur comptable et des registres des taxes dérogatoires, puis affectez-les à une immobilisation. Pour le modèle dérogatoire, activez le champ **Modèle dérogatoire** dans la page **Registres**. Pour le modèle comptable, sélectionnez le modèle dérogatoire dans le champ **Calcul dérogatoire**. Les conditions suivantes doivent être remplies :

-   Ces deux registres doivent avoir le champ **Amortissement** activé.
-   **Accepter la valeur nette négative** est désactivé dans les deux registres.
-   Ces deux registres ont la même valeur dans le champ **Calendrier**.
-   Les deux registres doivent avoir la même couche de validation définie sur **Actuel**.
-   L'amortissement complet doit être activé sur le profil d'amortissement sélectionné dans le registre dérogatoire si la méthode d'amortissement est de type **Dégressif**.
-   Les profils d'amortissement sélectionnés pour les deux modèles de valeur doivent utiliser les mêmes paramètres pour **Année d'amortissement** et **Fréquence**.
-   Les deux registres doivent avoir le même paramètre dans le champ **Convention d'amortissement** sur la page **Registres** (**Immobilisations** > **Immobilisations** > **Immobilisations** > sélectionnez une immobilisation, puis cliquez sur **Registres**).
-   Les dates **Mis en service** doivent être les mêmes dans les deux registres à partir du moment où les registres sont affectés à une immobilisation spécifique.

Dans la page **Profils de validation d'immobilisation**, paramétrez les comptes généraux pour les transactions **Augmentation dérogatoire** et **Diminution dérogatoire** dans le livre comptable. Dans la page **Paramètres de cession**, vous pouvez effectuer le paramétrage pour valider les montants d'augmentation dérogatoire ou de diminution dérogatoire dans des comptes généraux spécifiques durant la cession. Vous pouvez consulter les montants d'amortissement dérogatoire pour le livre comptable dans la page **Soldes d'immobilisation**, l'état **Note d'immobilisation** ou l'état **Mouvements d'immobilisations**.


## <a name="additional-resources"></a>Ressources supplémentaires

- [Fusion du modèle de la valeur d'immobilisation et du registre d'amortissement](../fixed-assets/fixed-asset-value-model-depreciation-book-merge.md)
