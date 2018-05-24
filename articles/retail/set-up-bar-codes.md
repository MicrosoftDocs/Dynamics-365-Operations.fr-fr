---
title: "Paramétrer les codes-barres"
description: "Cet article décrit l'utilisation des codes-barres dans Microsoft Dynamics 365 for Retail."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e4ad8c2a984229b96cc5b81c0fd505a264ba58f0
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="set-up-bar-codes"></a>Paramétrer les codes-barres

[!include [banner](includes/banner.md)]

Cet article décrit l'utilisation des codes-barres dans Microsoft Dynamics 365 for Retail.

Vous pouvez utiliser les codes-barres pour acheter et vendre des articles, des variantes de produit de suivi, et paramétrer les clients et les employés. Vous pouvez également utiliser les codes-barres pour émettre et endosser des coupons, des cartes cadeaux et des avoirs. Vous pouvez paramétrer les produits vendus au détail de façon à ce qu'ils disposent de codes-barres standard ou de codes-barres internes personnalisés. Les produits peuvent avoir plusieurs codes-barres. Par exemple, un produit peut avoir plusieurs codes-barres si celui-ci provient de différents fabricants ou s'il comporte des variantes de taille, de style ou de couleur. Les codes-barres peuvent inclure le poids ou le prix du produit. Les masques de codes-barres sont des modèles qui sont utilisés pour créer des codes-barres. **Remarque :** Si vous attribuez un code-barres unique à chaque combinaison de variantes vous pouvez scanner le code-barres au niveau de la caisse enregistreuse et laisser le programme déterminer quelle variante du produit est vendue. Vous pouvez également obtenir et consulter des statistiques de vente par variante. Chaque groupe de tailles, de couleurs et de styles peut se voir affecter un numéro unique qui identifie ce groupe dans le code-barres. Dynamics 365 for Retail utilise le masque de code-barres pour générer automatiquement des codes-barres pour chaque combinaison de variantes. Cette fonctionnalité peut être utile s'il y a beaucoup de tailles, de couleurs et de styles, car le nombre de combinaisons augmente significativement à l'ajout de chaque nouveau code variante. Si cette fonctionnalité n'est pas utilisée, les codes-barres doivent être affectés manuellement à chaque combinaison représentant une variante de produit. Vous pouvez créer les codes-barres manuellement ou automatiquement. Pour créer des codes-barres, effectuez les tâches suivantes dans l'ordre dans lequel elles sont répertoriées.

1.  [Paramétrage des caractères de masque de code-barres](set-up-bar-code-masks.md).
2.  [Paramétrage de masques de codes-barres](set-up-bar-code-masks.md).
3.  Configurez les paramétrages des codes-barres.
4.  Créez les codes-barres pour les produits spécifiques.


<a name="additional-resources"></a>Ressources supplémentaires
--------

[Paramétrer des masques de codes-barres](set-up-bar-code-masks.md)




