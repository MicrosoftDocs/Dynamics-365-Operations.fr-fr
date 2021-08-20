---
title: Tenir à jour la nomenclature d’un modèle de configuration de produit
description: L’exécution de cette procédure nécessite un modèle de configuration de produit existant.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 173022d40a5c1354cbe05c171a8921e733d908d065b10889f9cbe0e87f3e98fa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781463"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a>Tenir à jour la nomenclature d’un modèle de configuration de produit

[!include [banner](../../includes/banner.md)]

L’exécution de cette procédure nécessite un modèle de configuration de produit existant. Cette procédure utilise le modèle de haut-parleur haut de gamme de la société fictive USMF.

## <a name="add-a-bom-line"></a>Ajouter une ligne de nomenclature

1. Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.
1. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez le Haut-parleur haut de gamme pour cette procédure.  
1. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
1. Développer la section **Lignes de nomenclature**.
1. Sélectionnez **Ajouter**.
1. Tapez une valeur dans le champ **Nom**.
1. Tapez une valeur dans le champ **Description**.
1. Sélectionnez **Enregistrer**.

## <a name="add-bom-line-details"></a>Ajouter les détails de ligne de nomenclature

1. Sélectionnez **Détails de la ligne de nomenclature**.
2. Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.
    * Par exemple, vous pouvez sélectionner l’article M0055.  
    * Pour chaque propriété de ligne de nomenclature, vous pouvez sélectionner si elle prend une valeur fixe ou est mise en correspondance avec un attribut.  
3. Activez la case à cocher **Définir**.
4. Sélectionnez *Oui* dans le champ **Calcul**.
    * Le fait de définir la propriété du champ **Calcul** sur *Oui* garantit que la ligne de nomenclature sera incluse dans les calculs de coûts.  
5. Sélectionnez l’onglet **Paramétrage**.
6. Activez la case à cocher **Définir**.
7. Entrez un nombre dans le champ **Quantité**.
    * Le champ de quantité détermine la quantité d’articles qui sera incluse dans la nomenclature. Cela peut être un candidat idéal pour une mise en correspondance d’attributs.  
8. Cliquez sur l’onglet **Dimension**.
    * Vérifiez si des dimensions de produit sont actives ; elles doivent donc avoir une valeur ou un attribut affecté.  
9. Cliquez sur **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]