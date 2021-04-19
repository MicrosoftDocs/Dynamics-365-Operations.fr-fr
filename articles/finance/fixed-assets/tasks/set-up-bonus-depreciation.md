---
title: Paramétrage de l’amortissement de la prime
description: Cette procédure indique comment créer une provision spéciale pour amortissement et l’associer à un registre d’immobilisations.
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ad1b7f584d2b2a63dba5f8519ada9d89d6265e7b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815618"
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