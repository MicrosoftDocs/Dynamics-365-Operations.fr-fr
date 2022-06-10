---
title: Prix fixe de réception
description: Cette rubrique explique comment configurer et utiliser des prix fixes de réception dans Microsoft Dynamics 365 Supply Chain Management.
author: raprofit
ms.date: 04/25/2022
ms.topic: article
ms.search.form: InventPosting, InventItemGroup, InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-04-25
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 8e26d84ddc309249d8bd6e54987ad3ae8eed68f0
ms.sourcegitcommit: 2b4ee1fe05792332904396b5f495d74f2a217250
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2022
ms.locfileid: "8770298"
---
# <a name="fixed-receipt-price"></a>Prix fixe de réception

[!include [banner](../includes/banner.md)]

**Prix fixe de réception** est une option que vous pouvez sélectionner sur un groupe de modèles d’articles lorsque vous utilisez un modèle de stock autre que *Coût standard* ou *Moyenne pondérée*. Dans les premières versions de Microsoft Dynamics AX, cette option s’appelait **Coût standard**. Elle a été renommée **Prix fixe de réception** lorsque le nouveau modèle de stock de coût standard a été introduit dans Dynamics AX 2012. Cette rubrique explique comment configurer et utiliser des prix fixes de réception dans Dynamics 365 Supply Chain Management.

## <a name="about-fixed-receipt-prices"></a>À propos des prix fixes de réception

Lorsque vous sélectionnez la case à cocher **Prix fixe de réception** sur la page **Groupe de modèles d’article** pour un article, le système utilise le prix de réception comme coût standard pour la réception de stock. Si le prix d’achat et le prix de revient de l’article par défaut configurés pour un produit diffèrent, la différence est imputée au compte **Profit sur prix fixe de réception** ou **Perte sur prix fixe de réception** et déduite du compte **Contrepartie de prix fixe de réception** que vous spécifiez sur la page **Profil de validation de stock**.

Comme l’option **Prix fixe de réception** est utilisée en conjonction avec différents modèles de stock (tels que premier entré, premier sorti (FIFO), dernier entré, premier sorti (LIFO) et moyenne pondérée), le processus *Clôture et ajustement des stocks* créera toujours des règlements et des ajustements selon le principe de stock que vous sélectionnez sur la page **Groupe de modèles d’article**. Cependant, les ajustements ne sont apportés qu’aux sorties de stock.

Par exemple, vous avez configuré un produit avec un groupe de modèles d’articles où le champ **Modèle de stock** est défini sur *FIFO* et l’option **Prix fixe de réception** est sélectionnée. Lorsque vous recevez du stock par le biais d’un bon de commande, la valeur du stock est définie sur la valeur du prix de revient par défaut de l’article au moment de la réception du produit. Lorsque vous facturez le bon de commande, si le prix facturé est différent, le système comptabilise le prix de revient par défaut du produit lancé sur le compte de stock. Il comptabilise la différence dans le compte des pertes ou de profit sur prix fixe de réception. Plus tard, lorsque vous vendez ou consommez le produit, le système utilise le coût moyen en vigueur de l’article au moment où la facture de la commande client a été validée (sauf si vous utilisez le marquage).

Lorsque vous exécutez le processus *Clôture et ajustement des stocks*, le système crée un règlement où la première réception correspond à la première sortie. La différence entre le prix du ticket de caisse qui a été utilisé sur le ticket de caisse et le coût moyen en vigueur qui a été utilisé sur la sortie est validée dans un nouveau justificatif.

## <a name="enable-fixed-receipt-prices"></a>Activer des prix fixes de réception

Pour activer les prix fixes de réception pour un article, procédez comme suit.

1. Allez dans **Gestion des stocks \> Paramétrage \> Stock \> Groupes de modèles d’article**.
2. Créez un nouveau groupe de modèles d’articles ou sélectionnez un groupe de modèles existant.
3. Sur le raccourci **Méthode d’évaluation des coûts et constatation du coût**, sélectionnez la case à cocher **Prix fixe de réception**.

    > [!NOTE]
    > Vous ne pouvez pas sélectionner la case à cocher **Prix fixe de réception** si le champ **Modèle de stock** est défini sur *Coût standard* ou *Moyenne mobile*.

4. Fermez la page.

Après avoir activé l’option **Prix fixe de réception**, vous devez mettre à jour votre profil de validation de stock en suivant ces étapes.

1. Accédez à **Gestion des stocks \> Paramétrage \> Validation \> Validation**.
1. Sur l’onglet **Bon de commande**, dans la colonne **Sélectionner**, sélectionnez **Profit sur prix fixe de réception**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Paramétrez la nouvelle ligne de sorte qu’elle s’applique au groupe de modèles d’article pour lequel vous avez activé la tarification de réception fixe et spécifiez le compte principal utilisé pour enregistrer les bénéfices sur le prix de réception fixe pour les bons de commande. Configurez d’autres paramètres selon vos besoins.
1. Dans la colonne **Sélectionner**, sélectionnez **Perte sur prix fixe de réception**. Ajoutez une nouvelle ligne qui s’applique au groupe de modèles d’article pour lequel vous avez activé la tarification de réception fixe et spécifiez le compte principal utilisé pour enregistrer les pertes sur le prix de réception fixe pour les bons de commande. Configurez d’autres paramètres selon vos besoins.
1. Dans la colonne **Sélectionner**, sélectionnez **Contrepartie de prix fixe de réception**. Ajoutez une nouvelle ligne qui s’applique au groupe de modèles d’article pour lequel vous avez activé la tarification de réception fixe et spécifiez le compte principal utilisé pour enregistrer les contreparties sur le prix de réception fixe pour les bons de commande. Configurez d’autres paramètres selon vos besoins.
1. Sur l’onglet **Stock**, dans la colonne **Sélectionner**, sélectionnez **Profit sur prix fixe de réception**. Ajoutez une nouvelle ligne qui s’applique au groupe de modèles d’article pour lequel vous avez activé la tarification de réception fixe et spécifiez le compte principal utilisé pour enregistrer les profits sur le prix de réception fixe pour le stock. Configurez d’autres paramètres selon vos besoins.
1. Dans la colonne **Sélectionner**, sélectionnez **Perte sur prix fixe de réception**. Ajoutez une nouvelle ligne qui s’applique au groupe de modèles d’article pour lequel vous avez activé la tarification de réception fixe et spécifiez le compte principal utilisé pour enregistrer les pertes sur le prix de réception fixe pour le stock. Configurez d’autres paramètres selon vos besoins.

> [!NOTE]
> Nous recommandons généralement que les champs **Profit sur prix fixe de réception** et **Perte sur prix fixe de réception** utilisent le même compte principal pour les bons de commande et le stock.

> [!IMPORTANT]
> Lorsque vous modifiez la valeur dans le champ **Prix** sur le raccourci **Gérer les coûts** de la page **Produits lancés**, le système ne réévalue pas automatiquement le stock disponible. Comme solution de contournement manuelle, ouvrez la page **Clôture et ajustement** et sélectionnez **Ajustement \> Disponible** dans le volet Actions. Sélectionnez ensuite les articles disponibles et ajustez-les au prix actuel. L’un des avantages évidents de l’utilisation du modèle de stock de coût standard est qu’il amène le système à réévaluer automatiquement le stock disponible.
