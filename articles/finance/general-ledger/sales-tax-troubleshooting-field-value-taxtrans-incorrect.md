---
title: Valeur de champ incorrecte dans TaxTrans
description: Cette rubrique fournit des informations sur la résolution des problèmes de valeurs de champ incorrectes dans TaxTrans.
author: bijian
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 488ff54f1dd99208db940024a2fe8b2d25861f44
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020161"
---
# <a name="incorrect-field-value-in-taxtrans"></a>Valeur de champ incorrecte dans TaxTrans

[!include [banner](../includes/banner.md)]

Si une valeur de champ est incorrecte dans **TaxTrans**, utilisez les informations de cette rubrique pour essayer de résoudre le problème.

## <a name="overview-of-values"></a>Aperçu des valeurs
La liste suivante montre que **TaxTrans**, **TaxUncommitted** et **TmpTaxWorkTrans** sont des ensembles de données similaires, mais fonctionnent différemment.

  - **TaxTrans** est le résultat final de la transaction fiscale affiché et conservé dans la base de données.
  - **TaxUncommitted** est le résultat de taxe calculé intermédiaire conservé dans la base de données (le cas échéant), qui sera utilisé plus tard lors de la comptabilisation.
  - **TmpTaxWorkTrans** est le résultat de taxe calculé temporaire dans la table en mémoire (Type de table = InMemory).

Si vous trouvez la cause première d'une colonne **TaxTrans** incorrecte, vous avez également trouvé la cause première d'une colonne **TaxUncommitted** ou **TmpTaxWorkTrans** incorrecte. En effet, les trois colonnes sont copiées les unes des autres.

En règle générale, lors du calcul de la taxe, **TmpTaxWorkTrans** est généré, puis, le cas échéant, **TaxUncommitted** est généré. Lors de la validation de la taxe, **TaxTrans** est généré.


## <a name="add-breakpoints"></a>Ajouter des points d'arrêt
Procédez comme suit pour ajouter des points d'arrêt : 

1. Ajoutez des extensions et des points d'arrêt dans *insérer()* et *mettre à jour()* dans les extensions comme indiqué ci-dessous.

     - **TaxTrans**

        ```x++
        [ExtensionOf(tableStr(TaxTrans))]
        public final class TaxTrans_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TaxUncommitted**

        ```x++
        [ExtensionOf(tableStr(TaxUncommitted))]
        public final class TaxUncommitted_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TmpTaxWorkTrans**

        ```x++
        [ExtensionOf(tableStr(TmpTaxWorkTrans))]
        public final class TmpTaxWorkTrans_Extension
        {
            public void insert(boolean _ignoreCalculatedSalesTax)
            {
                next insert(_ignoreCalculatedSalesTax);
            }
        
            public void update(boolean _ignoreCalculatedSalesTax)
            {
                next update(_ignoreCalculatedSalesTax);
            }
        
        }
        
        ```

2. Vous pouvez également ajouter des points d'arrêt directement lorsque **TaxUncommitted** n'est pas inclus.

     - *TaxTrans.insert()*, *TaxTrans.update()*
     - *TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*

## <a name="reproduce-and-debug"></a>Reproduire et déboguer

Une fois les points d'arrêt définis, chaque modification de la persistance des données est visible pendant le débogage. Pour trouver la cause première d'une colonne incorrecte de **TaxTrans**, **TaxUncommitted** ou **TmpTaxWorkTrans**, passez en revue et notez les éléments suivants :

- Le dernier point d'arrêt où la colonne est correcte.
- Le premier point d'arrêt où la colonne est incorrecte.
- Ce qu'il se passe entre ces deux points.

## <a name="determine-whether-customization-exists"></a>Déterminer si la personnalisation existe
Si vous avez terminé les étapes des sections précédentes mais que vous n'avez pu résoudre le problème, déterminez s'il existe une personnalisation. Si aucune personnalisation n'existe, contactez le support Microsoft pour obtenir de l'aide.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

