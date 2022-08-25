---
title: Paramétrer les codes-barres
description: Cet article décrit l’utilisation des codes-barres dans Dynamics 365 Commerce.
author: josaw1
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.industry: Retail
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
ms.openlocfilehash: 5771ada4a9bba92fb32155ae425f08d6429b46e6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271794"
---
# <a name="set-up-bar-codes"></a>Paramétrer les codes-barres

[!include [banner](includes/banner.md)]

Cet article décrit l’utilisation des codes-barres dans Dynamics 365 Commerce.

Vous pouvez utiliser les codes-barres pour acheter et vendre des articles, des variantes de produit de suivi, et paramétrer les clients et les employés. Vous pouvez également utiliser les codes-barres pour émettre et endosser des coupons, des cartes cadeaux et des avoirs. Vous pouvez paramétrer les produits de façon à ce qu’ils disposent de codes-barres standard ou de codes-barres internes personnalisés. Les produits peuvent avoir plusieurs codes-barres. Par exemple, un produit peut avoir plusieurs codes-barres si celui-ci provient de différents fabricants ou s’il comporte des variantes de taille, de style ou de couleur. Les codes-barres peuvent inclure le poids ou le prix du produit. Les masques de codes-barres sont des modèles qui sont utilisés pour créer des codes-barres.

> [!NOTE]
> Si vous attribuez un code-barres unique à chaque combinaison de variantes vous pouvez scanner le code-barres au niveau de la caisse enregistreuse et laisser le programme déterminer quelle variante du produit est vendue. Vous pouvez également obtenir et consulter des statistiques de vente par variante. Chaque groupe de tailles, de couleurs et de styles peut se voir affecter un numéro unique qui identifie ce groupe dans le code-barres. Commerce utilise le masque de code-barres pour générer automatiquement des codes-barres pour chaque combinaison de variantes. Cette fonctionnalité peut être utile s’il y a beaucoup de tailles, de couleurs et de styles, car le nombre de combinaisons augmente significativement à l’ajout de chaque nouveau code variante. Si cette fonctionnalité n’est pas utilisée, les codes-barres doivent être affectés manuellement à chaque combinaison représentant une variante de produit.

Vous pouvez créer les codes-barres manuellement ou automatiquement. Pour créer des codes-barres, effectuez les tâches suivantes dans l’ordre dans lequel elles sont répertoriées.

1. [Paramétrage des caractères de masque de code-barres](set-up-bar-code-masks.md).
2. [Paramétrage de masques de codes-barres](set-up-bar-code-masks.md).
3. Configurez les paramétrages des codes-barres.
4. [Créer les codes-barres pour les produits spécifiques](../supply-chain/pim/tasks/create-bar-code-product.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Paramétrer des masques de codes-barres](set-up-bar-code-masks.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
