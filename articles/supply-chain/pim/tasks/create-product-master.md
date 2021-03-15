---
title: Créer un produit générique
description: Créez un produit générique pour les variantes prédéfinies.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 612f83f2df0ca3e66aa38defa27ec34315b4b2ce
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001722"
---
# <a name="create-a-product-master"></a>Créer un produit générique

[!include [banner](../../includes/banner.md)]

Créez un produit générique pour les variantes prédéfinies. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au concepteur de produit.


## <a name="create-a-new-product-master"></a>Créer un produit générique
1. Accédez au **volet Navigation > Modules > Gestion d'informations sur les produits > Produits > Produits génériques**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Numéro du produit**, saisissez une valeur. Le nombre doit être unique. Il est possible de définir une séquence de nombres pour le champ **Numéro du produit**. Dans ce cas, il n'est pas nécessaire que l'utilisateur entre de valeur.
4. Dans le champ **Nom du produit**, saisissez une valeur. Saisissez un nom décrivant le produit. Par défaut, la valeur utilisée correspond au nom de recherche, mais il peut être modifié par l'utilisateur.
5. Dans le champ **Groupe de dimensions de produit**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche. Le groupe Dimension du produit détermine les dimensions pouvant être utilisées pour créer des variantes du produit. Cet exemple utilise un groupe avec la couleur et la taille.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée. La **technologie de configuration** par défaut est Variante prédéfinie. Elle est utilisée pour cet exemple.
8. Cliquez sur **OK**.

## <a name="select-product-dimension-groups"></a>Sélectionner des groupes de dimensions de produit
1. Dans le champ **Groupe de couleurs**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Dans le champ **Groupe de tailles**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

## <a name="add-dimension-groups"></a>Ajouter des groupes de dimensions
1. Dans le volet **Actions**, cliquez sur **Produit**.
2. Cliquez sur **Groupes de dimensions** pour ouvrir la boîte de dialogue.
3. Dans le champ **Groupe de dimensions de stockage**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche. Les dimensions de stockage facilitent le contrôle du mode de stockage et de prélèvement sur le stock. Par exemple, une dimension de stockage peut inclure le site et l'entrepôt.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Dans le champ **Groupe de dimensions de suivi**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche. Le groupe de dimensions de suivi détermine les dimensions de suivi que vous pouvez ajouter à un produit. Par exemple, le numéro de lot et le numéro de série sont utilisés pour suivre les articles en stock.
7. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Cliquez sur **OK**.
10. Cliquez sur **Enregistrer**.
11. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]