---
title: Tenir à jour la nomenclature d’un modèle de configuration de produit
description: L’exécution de cette procédure nécessite un modèle de configuration de produit existant.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 12eb2d8fcdae5d60efa19e5443a01ab9bd104267
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258801"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a>Tenir à jour la nomenclature d’un modèle de configuration de produit

[!include [banner](../../includes/banner.md)]

L’exécution de cette procédure nécessite un modèle de configuration de produit existant. Cette procédure utilise le modèle de haut-parleur haut de gamme de la société fictive USMF.


## <a name="add-a-bom-line"></a>Ajouter une ligne de nomenclature
1. Cliquez sur Définition du modèle de variante de produit.
2. Cliquez sur Modèles de configuration de produit.
3. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Sélectionnez le Haut-parleur haut de gamme pour cette procédure.  
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Développer la section Lignes de nomenclature.
6. Cliquez sur Ajouter.
7. Tapez une valeur dans le champ Nom.
8. Dans le champ Description, entrez une valeur.
9. Cliquez sur Enregistrer.

## <a name="add-bom-line-details"></a>Ajouter les détails de ligne de nomenclature
1. Cliquez sur Détails de ligne de nomenclature.
2. Entrez ou sélectionnez une valeur dans le champ Numéro d’article.
    * Par exemple, vous pouvez sélectionner l’article M0055.  
    * Pour chaque propriété de ligne de nomenclature, vous pouvez sélectionner si elle prend une valeur fixe ou est mise en correspondance avec un attribut.  
3. Activez la case à cocher Définir.
4. Sélectionnez Oui dans le champ Calcul.
    * Le fait de définir la propriété du calcul sur Oui garantit que la ligne de nomenclature sera incluse dans les calculs de coûts.  
5. Cliquez sur l’onglet Paramétrage.
6. Activez la case à cocher Définir.
7. Dans le champ Quantité, entrer un numéro.
    * Le champ de quantité détermine la quantité d’articles qui sera incluse dans la nomenclature. Cela peut être un candidat idéal pour une mise en correspondance d’attributs.  
8. Cliquez sur l’onglet Dimension.
    * Vérifiez si des dimensions de produit sont actives ; elles doivent donc avoir une valeur ou un attribut affecté.  
9. Cliquez sur OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]