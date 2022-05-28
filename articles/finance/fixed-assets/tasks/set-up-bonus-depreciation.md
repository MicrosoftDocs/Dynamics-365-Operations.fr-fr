---
title: Paramétrage de l’amortissement de la prime
description: Cette procédure indique comment créer une provision spéciale pour amortissement et l’associer à un registre d’immobilisations.
author: moaamer
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7bc768e6b470f8f49b23bf7ce0c8e5a080043281
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725875"
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
