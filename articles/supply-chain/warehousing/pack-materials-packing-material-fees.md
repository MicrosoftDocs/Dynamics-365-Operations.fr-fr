---
title: Matières d'emballage et frais
description: Cette rubrique donne des informations sur les taxes sur les matières d'emballage qui sont payées aux entreprises de recyclage à des intervalles spécifiques.
author: MarkusFogelberg
manager: tfehr
ms.date: 02/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventPackagingGroup, InventPackagingMaterialCode, InventPackagingMaterialFee, InventPackagingMaterialTrans, InventPackagingMaterialTransPurch, InventPackagingUnit
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2194
ms.assetid: 040b65dc-43c9-4256-b69f-b2d6e736fbe9
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2020-02-19
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e5364336c5336cbb91caf3c03564f68371273079
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973633"
---
# <a name="packing-materials-and-fees"></a>Matières d'emballage et frais

[!include [banner](../includes/banner.md)]

Des taxes sur les matières d'emballage sont payées à des intervalles spécifiques à une entreprise de recyclage. Un montant par unité de poids est payé pour chaque matière composant une unité d'emballage. Bien que les taxes sur les matières d'emballage soient calculées et déclarées, aucune écriture comptable n'est validée, car ces taxes ne sont pas considérées comme devant être payés à une administration.

Les poids et les taxes des matières d'emballage sont calculés pour les lignes de commande client et fournisseur.

Vous pouvez définir une ou plusieurs unités d'emballage pour un article, un groupe d'articles (groupe d'emballage) ou tous les articles. Une unité d'emballage comprend les différentes matières d'emballage et leur poids, en plus du nombre d'articles inclus dans l'unité d'emballage. Un code matières d'emballage est affecté à chaque type de matières d'emballage définies. Selon le code matière d'emballage, vous pouvez spécifier un prix pour une période spécifique. Les matières d'emballage sont calculées en fonction de ces informations.

> [!NOTE]
> Même si votre société ne paie pas de taxes sur les matières d'emballage, vous pouvez utiliser cette fonctionnalité pour calculer des statistiques sur les poids des matières d'emballage.

## <a name="set-up-packing-material-allocation"></a><a name="allocations"></a>Configurer l'affectation de matières d'emballage

Avant de pouvoir calculer les poids et/ou les taxes des matières d'emballage, vous devez activer le calcul et définir quelles matières et quelles taxes s'appliquent à quels articles.

1. Allez dans **Gestion des stocks \> Configuration \> Paramètres de gestion des stocks et des entrepôts**.
1. Sous l'onglet **Général**, dans la section **Matières d'emballage**, définissez l'option **Calculer les taxes sur les matières d'emballage** sur **Oui**.
1. Allez dans **Gestion des stocks \> Configuration \> Matières d'emballage \> Groupes d'emballage** et créez tous les groupes d'emballage que vous utilisez. Tous les articles d'un groupe d'emballage utiliseront la même affectation de matières d'emballage. Si vous n'utilisez pas de groupes d'emballage, vous pouvez ignorer cette étape.

    > [!TIP]
    > Après avoir créé vos groupes d'emballage, vous pouvez affecter un groupe à chaque produit selon vos besoins. Allez dans **Gestion des informations sur les produits \> Produits \> Produits lancés**, sélectionnez un produit, puis, dans le raccourci **Gérer le stock**, dans le champ **Groupe d'emballage**, sélectionnez le groupe d'emballage approprié.

1. Allez dans **Gestion des stocks \> Configuration \> Matières d'emballage \> Codes matières d'emballage**, définissez chaque type de matière d'emballage que vous utilisez et spécifiez l'unité dans laquelle la matière d'emballage est consommée lors de la préparation des expéditions.
1. Allez dans **Gestion des stocks \> Configuration \> Matières d'emballage \> Taxes sur les matières d'emballage** et définissez une taxe pour chaque type de matière d'emballage que vous venez de définir. Les taxes sont calculées en fonction du prix unitaire consommé.
1. Pour affecter des matières d'emballage aux articles, accédez à **Gestion des stocks \> Configuration \> Matières d'emballage \> Affectation de matières d'emballage** et créez des affectations. Vous pouvez créer autant d'affectations que nécessaire. Vous pouvez affecter des matières d'emballage pour des articles individuels, des groupes d'articles (groupes d'emballage) ou tous les articles, selon le niveau de détail de vos affectations.

    Pour chaque affectation que vous créez, procédez comme suit.

    1. Dans l'organisateur **Général**, définissez les champs suivants :

        - **Code article** : permet de sélectionner la portée de l'affectation :

            - **Table** : permet de créer une affectation pour un article spécifique.
            - **Groupe** : permet de créer une affectation pour tous les articles appartenant à un groupe d'emballage défini sur la page **Groupes d'emballage**.
            - **Tous** : permet de créer une affectation pour tous les articles.

            > [!NOTE]
            > Généralement, vous devez créer toutes vos affectations au même niveau (**Table**, **Groupe** ou **Tous**). Si vous utilisez plusieurs niveaux, l'affectation correspondante la plus spécifique sera utilisée pour chaque article. (Le niveau **Table** est prioritaire sur le niveau **Groupe**, et ces deux niveaux sont prioritaires sur le niveau **Tous**.)

        - **Relation d'article** : si vous créez une affectation pour un article, sélectionnez-le. Si vous créez une affectation pour un groupe d'articles, sélectionnez le groupe d'emballage. Si vous créez une affectation pour tous les articles, laissez ce champ vide.
        - **Configuration**, **Taille**, **Couleur** et **Style** : entrez des valeurs pour ces dimensions selon vos besoins, pour définir davantage l'article pour lequel vous créez une affectation.
        - **Unité d'emballage** : sélectionnez l'unité d'emballage de l'article lorsque la matière d'emballage est utilisée. Cette unité peut différer de l'unité d'achat et de stockage de l'article.
        - **Facteur d'unité d'emballage** : entrez le facteur de conversion utilisé pour la conversion de l'unité de stock en unité d'emballage. (La conversion utilise la formule *Unités d'emballage* = *Unités d'article* × *Facteur d'unité d'emballage*.)

    1. Dans le raccourci **Matières d'emballage**, ajoutez une ligne pour chaque matière d'emballage requise pour l'affectation actuelle. Sur chaque ligne, spécifiez le type de matière (tel que défini sur la page **Codes matières d'emballage**) et la quantité consommée pour chaque unité expédiée de l'article actuel.

## <a name="packing-units-on-sales-order-lines"></a>Unités d'emballage sur les lignes de commande client

Après avoir [activé le calcul des taxes sur les matières d'emballage et configuré vos affectations](#allocations), le système vérifie que les unités d'emballage sont spécifiées pour chaque article ajouté à une commande client. Il calcule ensuite toutes les taxes requises. Lorsqu'un article est ajouté à une commande client, l'une des étapes suivantes se produit :

- **Si une affectation de matières d'emballage s'applique à l'article** : le système met à jour la ligne de commande client avec l'unité d'emballage spécifiée et la quantité d'unités d'emballage. (La quantité d'unités d'emballage est calculée à l'aide de la formule *Quantité d'unités d'emballage* = *Quantité commandée* ÷ *Nombre d'articles dans l'unité d'emballage sélectionnée*).
- **Si aucune affectation de matières d'emballage ne s'applique à l'article** : vous pouvez entrer manuellement une unité d'emballage et une quantité d'unités d'emballage sur la ligne de commande client.

Vous pouvez également modifier l'unité d'emballage et la quantité d'unités d'emballage lorsque vous validez la ligne de commande client. Cette fonctionnalité est pertinente si la ligne de commande client n'est livrée ou facturée que partiellement.

Lorsque vous facturez la commande client, le système crée des transactions de matières d'emballage. Les transactions de matières d'emballage contiennent les poids des matières d'emballage pour la ligne de vente. Vous pouvez modifier les transactions une fois facturées. Vous pouvez ensuite créer de nouvelles transactions.

## <a name="packing-units-on-purchase-order-lines"></a>Unités d'emballage sur les lignes de commande fournisseur

Le système ne crée pas de transactions de matières d'emballage pou les lignes de commande fournisseur. À la place, vous créez manuellement des transactions pour les lignes de commande fournisseur facturées sur la page **Transactions de matières d'emballage**.

## <a name="set-up-license-numbers-for-customers-that-are-charged-packing-material-fees"></a>Définir des numéros de licence pour les clients devant payer des taxes sur les matières d'emballage

Si les commandes client pour un client spécifique doivent inclure des taxes sur les matières d'emballage utilisées pour chaque commande, procédez comme suit.

1. Allez dans **Comptabilité client \> Clients \> Tous les clients**.
1. Sélectionnez le client devant être facturé pour les matières d'emballage.
1. Dans le raccourci **Facture et livraison**, définissez les champs suivants :

    - Dans la section **Taxe**, dans le champ **Numéro de licence de droits de douane emballages**, entrez le numéro de licence de la société.
    - Dans la section **Taxe sur les matières d'emballage**, dans le champ **Numéro de licence**, entrez le numéro de licence de la société.

Maintenant, lorsque vous créez et facturez une commande client incluant un ou plusieurs articles qui utilisent des matières d'emballage, la facture affichera les taxes sur les matières d'emballage.

Pour les clients qui ne doivent pas payer de taxes sur les matières d'emballage, suivez les mêmes étapes, mais effacez les numéros de licence des champs **Numéro de licence de droits de douane emballages** et **Numéro de licence**. Les factures des clients qui ne paient pas de taxes sur les matières d'emballage affichent les poids des matières d'emballage, mais elles n'indiquent pas les taxes.

Pour générer un rapport indiquant toutes les taxes sur les matières d'emballage dus par votre société pour une période spécifique, accédez à **Gestion des stocks \> Recherches et états \> États sur les matières d'emballage \> Calcul de la taxe sur les matières d'emballage**, spécifiez une plage de dates, puis cliquez sur **OK**.

## <a name="print-packing-material-weights-on-invoices"></a>Imprimer le poids des matières d'emballage sur les factures

Vous pouvez imprimer le poids des matières d'emballage sur une facture, et indiquer qui paie les taxes associées. Les poids sont cumulés par codes matière d'emballage.

1. Accédez à **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.
1. Dans l'onglet **Mises à jour**, dans le raccourci **Facture**, définissez l'option **Imprimer le poids des matières d'emballage** sur **Oui**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]