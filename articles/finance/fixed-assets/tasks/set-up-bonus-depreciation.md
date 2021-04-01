---
title: Paramétrage de l’amortissement de la prime
description: Cette procédure indique comment créer une provision spéciale pour amortissement et l’associer à un registre d’immobilisations.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6627e7fa9a1eb1a9131ec7e2c3cc823b49b286cc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257559"
---
# <a name="set-up-bonus-depreciation"></a>Paramétrage de l’amortissement de la prime

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment créer une provision spéciale pour amortissement et l’associer à un registre d’immobilisations. Elle utilise le rôle de comptable et les données de démonstration de l’entité juridique USMF.


## <a name="create-a-special-depreciation-allowance"></a>Créer une provision spéciale pour amortissement
1. Accédez à Immobilisations > Paramétrage > Provision spéciale pour amortissement.
2. Cliquez sur Nouveau.
3. Entrez une valeur dans le champ Provision spéciale pour amortissement.
4. Dans le champ Description, entrez une valeur.
5. Entrez un nombre dans le champ Pourcentage.
    * Si un pourcentage n’est pas affiché, définissez un montant.  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a>Associer une provision spéciale pour amortissement au registre d’un groupe d’immobilisations
1. Accédez à Immobilisations > Paramétrage > Groupes d’immobilisations.
2. Dans la liste, sélectionnez le groupe d’immobilisations à associer à la provision spéciale pour amortissement.
3. Cliquez sur Registres.
4. Dans la liste, sélectionnez le registre associé à la provision spéciale pour amortissement.
5. Cliquez sur Provision spéciale pour amortissement.
6. Cliquez sur Nouveau.
7. Dans le champ Provision spéciale pour amortissement, entrez ou sélectionnez une valeur.
    * La valeur par défaut du pourcentage ou du montant provient du paramétrage de la provision spéciale pour amortissement.  
8. Dans le champ Priorité, entrer un numéro.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]