---
title: Saisie d’un supplément à une immobilisation
description: Cette procédure décrit comment ajouter un supplément à une immobilisation existante.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetAddition
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 35e447ff9652861de4f7f310f68e8180a69589b4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209996"
---
# <a name="enter-an-addition-to-a-fixed-asset"></a>Saisie d’un supplément à une immobilisation

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment ajouter un supplément à une immobilisation existante. L’objectif des ajouts d’immobilisations est de suivre les suppléments, la maintenance, ou les améliorations d’un actif, à titre indicatif uniquement. Toutes les modifications de la valeur ou de la durée de vie de l’immobilisation doivent être apportées séparément.   

La procédure utilise le rôle de comptable et les données de démonstration pour l’entité juridique USMF.

1. Dans le volet de navigation, accédez à **Modules > Immobilisations > Immobilisations > Immobilisations**.
2. Dans la liste, recherchez et sélectionnez l’immobilisation à ajouter.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Dans le volet Actions, cliquez sur **Immobilisation**.
5. Cliquez sur **Ajouts d’immobilisations**.
6. Cliquez sur **Nouveau**.
7. Tapez une valeur dans le champ **Nom**.
8. Dans le champ **Date d’acquisition**, définissez la date de l’achat ou du service en supplément.
9. Dans le champ **Coût unitaire**, entrez le coût de l’article, de la maintenance ou de toute autre amélioration de l’actif.
10. Entrez un nombre dans le champ **Quantité**. Le coût total n’aura pas d’impact sur la valeur de l’immobilisation. Il sert uniquement pour le suivi et à titre indicatif. Si le coût est ensuite capitalisé, une transaction d’augmentation doit être validée séparément.  
11. Cliquez sur l’onglet **Général**.

    * Définissez **Augmente la durée de vie** sur **Oui** si le supplément augmente la durée de vie de l’actif.  
    * Ce champ est fourni uniquement à titre indicatif. Pour augmenter la durée de vie, modifiez la durée de vie sur les modèles de valeur et/ou les registres des amortissements pour l’actif.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]