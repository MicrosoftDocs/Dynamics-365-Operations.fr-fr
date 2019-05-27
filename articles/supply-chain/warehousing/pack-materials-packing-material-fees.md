---
title: Matières et taxes d'emballage
description: Des taxes sur les matières d'emballage sont payées à intervalles réguliers à une entreprise de recyclage. Un montant par unité de poids est payé pour chaque matière composant une unité d'emballage. Les taxes sur les matières d'emballage sont calculées et déclarées, mais aucune écriture comptable n'est validée car ces frais ne sont pas considérés comme devant être payés à une administration.
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventPackagingGroup, InventPackagingMaterialCode, InventPackagingMaterialFee, InventPackagingMaterialTrans, InventPackagingMaterialTransPurch, InventPackagingUnit
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2194
ms.assetid: 040b65dc-43c9-4256-b69f-b2d6e736fbe9
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c188651fe8ba3fe3f9678f36ab11ae886ef6f1cf
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546016"
---
# <a name="packing-materials-and-fees"></a>Matières et taxes d'emballage

[!include [banner](../includes/banner.md)]

Des taxes sur les matières d'emballage sont payées à intervalles réguliers à une entreprise de recyclage. Un montant par unité de poids est payé pour chaque matière composant une unité d'emballage. Les taxes sur les matières d'emballage sont calculées et déclarées, mais aucune écriture comptable n'est validée car ces frais ne sont pas considérés comme devant être payés à une administration.

Les poids et les taxes des matières d'emballage sont calculés pour les lignes de commande client et fournisseur.

Vous pouvez définir une ou plusieurs unités d'emballage pour un article, pour un groupe d'articles d'emballage ou pour tous les articles. Une unité d'emballage comprend les différentes matières d'emballage et leur poids, en plus du nombre d'articles inclus dans l'unité d'emballage. Un code matières d'emballage est affecté à chaque type de matières d'emballage définies. Selon le code matières d'emballage, vous pouvez spécifier un prix pour une période spécifiée. Les matières d'emballage sont calculées en fonction de ces informations.

| **Remarque**                                                                                                                                             |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Même si votre société ne paie pas de taxes sur les matières d'emballage, vous pouvez utiliser cette fonctionnalité pour calculer des statistiques sur les poids des matières d'emballage. |

## <a name="setup-requirements-for-packing-material-fees"></a>Exigences de paramétrage pour les taxes sur les matières d'emballage
Avant le calcul du poids et/ou des taxes des matières d'emballage, vous devez créer les données de base suivantes :

-   Groupes d'emballage - Créez des groupes d'emballage à affecter aux articles.
-   Codes matières d'emballage – Créez des codes matières d'emballage pour chaque type de matières d'emballage définies.
-   Unités d'emballage - Spécifiez une unité d'emballage pour un article, un groupe d'emballage ou tous les articles. Pour chaque unité d'emballage, définissez les matières d'emballage à inclure, affectez des poids et, dans le champ Facteur d'unité d'emballage, spécifiez le facteur de conversion de l'unité de stock.
-   Taxes sur les matières d'emballage – Spécifiez les taxes sur les matières d'emballage par code matières d'emballage. Pour chaque type de matériel, définissez la période de validité, le prix par matière, la devise et l'unité.

## <a name="packing-units-on-sales-order-lines"></a>Unités d'emballage sur les lignes de commande client
Lorsque vous créez une ligne de commande client, le système vérifie si des unités d'emballage sont spécifiées pour l'article. Si tel est le cas, le système met à jour la ligne de commande client avec l'unité d'emballage spécifiée et la quantité d'unités d'emballage. La quantité d'unités d'emballage est basée sur la quantité commandée divisée par le nombre d'articles de l'unité d'emballage sélectionnée. Si une unité d'emballage n'a pas été spécifiée, vous pouvez entrer manuellement une unité d'emballage et une quantité d'unités d'emballage sur la ligne de commande client. Vous pouvez également modifier l'unité d'emballage et la quantité d'unités d'emballage lorsque vous validez la ligne de commande client. Cela est pertinent si la ligne de commande client n'est livrée ou facturée que partiellement. Lorsque vous facturez la commande client, des transactions de matières d'emballage sont créées. Les transactions de matières d'emballage contiennent les poids des matières d'emballage pour la ligne de vente. Vous pouvez également modifier les transactions après la facturation et créer des transactions.

## <a name="packing-units-on-purchase-order-lines"></a>Unités d'emballage sur les lignes de commande fournisseur
Les transactions de matières d'emballage d'une ligne de commande fournisseur ne sont pas créées par le système. Vous créez des transactions pour les lignes de commande fournisseur facturées manuellement sur la page **Transactions de matières d'emballage**.

## <a name="set-up-customer-packaging-material-fee-license-numbers"></a>Paramétrage des numéros de licence des frais sur les matières d'emballage des clients
Si les clients paient les taxes sur les matières d'emballage, spécifiez les numéros de licence des taxes sur les matières d'emballage des clients sur la page **Clients**. Quand un numéro de licence a été affecté à un client, les frais sur les matières d'emballage sont calculés automatiquement lors de la facturation des commandes client. Après la facturation, la case **Calculer les frais** est décochée sur la page **Transactions de matières d'emballage** parce que vous n'avez pas besoin de calculer ni d'imprimer un état. Vous pouvez choisir d'imprimer les poids des matières d'emballage sur la facture et d'informer les clients qu'ils paient les taxes. 

Si votre société paie les frais sur les matières d'emballage, ne spécifiez pas les numéros de licence client. Après la facturation, la case **Calculer les frais** est cochée sur la page **Transactions de matières d'emballage**. Cela indique que les frais sont calculés lors de la création d'un état. Vous pouvez imprimer les poids sur la facture, et indiquer que votre société paie les frais.

## <a name="print-packaging-material-weights-on-invoices"></a>Impression du poids des matières d'emballage sur les factures
Vous pouvez imprimer les poids des matières d'emballage sur la facture, et indiquer qui les paie. Les poids sont cumulés par codes matière d'emballage.





