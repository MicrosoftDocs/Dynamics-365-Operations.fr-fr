---
title: Contrats de vente
description: "Cet article fournit des informations sur les contrats de vente. Un contrat de vente est un contrat qui engage le client à acheter une certaine quantité ou un certain montant de produit sur une période définie en échange de prix spéciaux et de remises."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesAgreementListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 9554
ms.assetid: c5d55c8d-99f2-44f9-a897-5b0dee85fc81
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4dd1eae27ae33837fbab16f764083168578d0a29
ms.lasthandoff: 03/31/2017


---

# <a name="sales-agreements"></a>Contrats de vente

Cet article fournit des informations sur les contrats de vente. Un contrat de vente est un contrat qui engage le client à acheter une certaine quantité ou un certain montant de produit sur une période définie en échange de prix spéciaux et de remises.

Un contrat de vente est un contrat qui engage le client à acheter une certaine quantité ou un certain montant de produits sur une période définie en échange de prix spéciaux, de remises spéciales et d'autres conditions spéciales, telles que des conditions de paiement et de livraison. Les prix et les remises du contrat de vente sont prioritaires sur les autres prix et remises indiqués dans les contrats commerciaux existants.  

La période de validité d'un contrat de vente est définie par les champs **Date d'effet** et **Date d'expiration** du contrat. Une commande client satisfait aux termes du contrat si la date d'expédition demandée de la commande est comprise dans la période de validité. Toutes les lignes de la commande client liées à un contrat de vente contribuent à l'exécution de ce contrat de vente.  

Vous pouvez créer une commande client directement à partir d'un contrat de vente à l'aide de l'action **Lancer la commande**. Vous pouvez également sélectionner un contrat de vente en vigueur lorsque vous acceptez des commandes (voir la section « Application des contrats de vente dans le processus de commande » de cet article).  

** Remarque : ** Dans les versions précédentes, contrats de vente étaient nommés des commandes client de fractionnement.

## <a name="commitment-types"></a>Types d'engagements
Chaque ligne d'un accord de vente exprime un engagement à vendre quelque chose. En général il existe deux catégories d'engagement :

-   **Engagement sur valeur **– Le client accepte d'acheter des produits pour un montant spécifique.
-   **Engagement à la quantité **– Le client accepte d'acheter une quantité spécifique de produits.

En outre, un contrat peut engager le client à acheter un ou des produits spécifiques dans une catégorie de produit. En combinant ces deux facteurs (valeur et quantité et produits spécifiques et catégories de produits), nous obtenons quatre types d'engagement :

-   **Engagement à la quantité de produits** – Le client accepte d'acheter une quantité spécifique de produits. Les lignes qui utilisent ce type d'engagement sont définies par un numéro d'article et par la quantité et l'unité convenues. Le champ **Montant** n'est pas disponible.
-   **Engagement à la valeur du produit** – Le client accepte d'acheter des produits spécifiques pour un montant spécifique. Les lignes qui utilisent ce type d'engagement sont définies par un numéro d'article et le montant convenu. Les champs **Quantité** et **Unité** ne sont pas disponibles.
-   **Catégorie de produit - Engagement sur valeur** – Le client accepte d'acheter des produits appartenant à une catégorie de vente spécifique pour un montant spécifique. Les lignes qui utilisent ce type d'engagement sont définies par une catégorie de vente dans la hiérarchie de catégories de vente et un montant. Les champs **Quantité** et **Unité** ne sont pas disponibles.
-   **Engagement sur valeur** – Le client accepte d'acheter un ou des produits dans une catégorie d'approvisionnement spécifique pour un montant spécifique. Les champs **Quantité** et **Unité** ne sont pas disponibles.

Les lignes d'un même contrat de vente peuvent avoir différents types d'engagements.

## <a name="pricing-terms-for-sales-agreements"></a>Conditions de tarification pour les contrats de vente
Les conditions de tarification peuvent varier selon le type d'engagement. Dans une commande client liée à un contrat de vente, les conditions de tarification de ce contrat de vente sont prioritaires sur les autres conditions de tarification qui s'appliquent sur la base des accords commerciaux. Le tableau suivant décrit les champs relatifs au prix affectés par chaque type d'engagement. Oui indique que le champ peut être mis à jour sur une ligne de commande.

| Type d'engagement                   | Prix unitaire | Unité de prix | Pourcentage de remise | Montant de l'escompte de règlement |
|-----------------------------------|------------|------------|------------------|----------------------|
| Engagement à la quantité de produits       | Oui        | Oui        | Oui              | Oui                  |
| Engagement à la valeur du produit          |            |            | Oui              |                      |
| Catégorie de produit - Engagement sur valeur |            |            | Oui              |                      |
| Engagement sur valeur                  |            |            | Oui              |                      |

## <a name="policies-for-sales-agreements"></a>Stratégies des contrats de vente
Les stratégies suivantes affectent la manière dont le lien entre un engagement de contrat de vente et les lignes de commande client correspondantes fonctionne :

-   **Le max. est appliqué** : La quantité ou le montant total pour toutes les lignes de commande ne peut pas dépasser la quantité ou le montant spécifié sur l'engagement associé.
-   **Le prix et la remise sont fixes** : le prix d'une ligne de commande et celui de l'engagement associé ne peuvent pas être différents. Si le prix est modifié sur la ligne de commande, le lien vers l'engagement est rompu. Si le lien est rompu, la ligne de commande ne contribue pas à honorer l'engagement.
-   **Montant de lancement minimal** et **Montant de lancement maximal** : si un montant est spécifié, un message s'affiche si vous apportez une modification à une ligne de commande qui rend celle-ci différente de l'engagement associé.

## <a name="fulfillment-calculations-for-sales-agreements"></a>Calculs d'exécution des contrats de vente
L'onglet **Exécution** de l'organisateur **Détails de ligne** de la page **Contrats de vente** affiche les quantités et les montants ayant permis d'honorer la commande.  

Dans la zone **Exécution**, vous pouvez afficher les quantités et les montants totaux de toutes les lignes de commande liées au contrat de vente spécifié. Vous pouvez également afficher la quantité ou le montant restant servant à honorer l'engagement.  

Dans la zone **Accord**, vous pouvez afficher les quantités et les montants du contrat de vente spécifié. Ces quantités et montants sont les quantités et montants totaux qui ont été validés.

## <a name="confirmations-and-version-history-for-sales-agreements"></a>Confirmations et historique de version des contrats de vente
Lorsque vous confirmez un contrat de vente, la version actuelle du contrat de vente est enregistrée dans une table d'historique. Si vous modifiez le contrat de vente, vous pouvez le confirmer de nouveau pour enregistrer une autre version du contrat de vente dans l'historique.  

Si vous ne confirmez pas un contrat de vente, vous pouvez toujours l'utiliser pour créer des commandes client. Toutefois, les informations d'historique pour le contrat de vente ne sont pas enregistrées.  

Vous pouvez prévisualiser ou imprimer toutes les révisions des confirmations. Vous pouvez ensuite partager les révisions avec votre client pour obtenir l'approbation.

## <a name="applying-sales-agreements-during-the-ordering-process"></a>Application des contrats de vente pendant le processus de commande
Si vous ne lancez pas les commandes client directement pour un contrat de vente, vous pouvez toujours lier un contrat de vente à une commande lors du processus de saisie de commande. Lorsque vous créez une commande client et sélectionnez un contrat de vente, les conditions de cet accord, telles que les conditions de paiement, les conditions de livraison et l'adresse de livraison, sont appliquées à l'en-tête de commande, et le lien entre l'accord et la commande est créé. Ensuite, sur les lignes de commande, lorsque vous sélectionnez les produits et les catégories spécifiés dans le contrat de vente, les prix et remises sont copiés à partir de cet accord. La même commande client peut inclure aussi bien des lignes qui ne sont pas associées à un contrat de vente que des lignes associées à un engagement pour un contrat de vente.

## <a name="modifying-sales-orders-that-are-linked-to-sales-agreements"></a>Modification des commandes client liées aux contrats de vente
Si vous avez créé (lancé) une commande client dans le cadre d'un contrat de vente, certains champs de cette commande client peuvent être modifiés uniquement si vous supprimez le lien aux lignes de contrat de vente associées. Le tableau suivant répertorie certains de ces champs.

| Champ                                                             | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|-------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Date d'expédition demandée                                               | Si vous définissez une date d'expédition demandée antérieure à celle de la valeur **Date d'effet** indiquée dans la ligne de contrat de vente, vous devez supprimer le lien avec celle-ci avant d'enregistrer la date d'expédition modifiée. Si vous définissez une date d'expédition demandée postérieure à celle de la valeur **Date d'expiration** indiquée dans la ligne de contrat de vente, vous devez supprimer le lien avec celle-ci avant d'enregistrer la date d'expédition modifiée. |
| Montant CurrencyDiscount, percentDiscountUnit, pricePrice, unitNet | Si vous modifiez la valeur de l'un de ces champs et si la case à cocher **Le prix et la remise sont fixes** est activée dans la ligne de contrat de vente associée, une boîte de dialogue vous invite à en enregistrer la modification. Cliquez sur **Oui** pour supprimer le lien avec la ligne de contrat de vente et recalculer le prix. Cliquez sur **Non** pour supprimer le lien avec la ligne de contrat de vente sans recalculer le prix.                                                                   |
| Montant net                                                        | Si vous spécifiez un montant supérieur à celui indiqué dans une ligne de contrat de vente dont la case à cocher **Le max. est appliqué** est activée, une boîte de dialogue vous invite à enregistrer le montant modifié. Cliquez sur **Oui** pour supprimer le lien avec la ligne de contrat de vente et recalculer le prix. Cliquez sur **Non** pour supprimer le lien avec la ligne de contrat de vente sans recalculer le prix.                                                                 |
| Quantité                                                          | Si vous spécifiez une quantité supérieure à celle indiquée dans une ligne de contrat de vente dont la case à cocher **Le max. est appliqué** est activée, une boîte de dialogue vous invite à enregistrer la quantité modifiée. Cliquez sur **Oui** pour supprimer le lien avec la ligne de contrat de vente et recalculer le prix. Cliquez sur **Non** pour supprimer le lien avec la ligne de contrat de vente sans recalculer le prix.                                                            |

## <a name="returning-an-item-that-was-ordered-from-a-sales-agreement"></a>Retour d'un article commandé à partir d'un contrat de vente
Lorsqu'un client retourne un produit commandé d'un contrat de vente, Microsoft Dynamics 365 pour les opérations peut rechercher et mettre automatiquement l'engagement à jour concerné de contrat de vente pour refléter les modifications apportées à la quantité ou le montant. En créant un ordre de retour basé sur la commande client d'origine liée à un contrat de vente, vous établissez une relation entre l'engagement de contrat de vente, la ligne de commande client et la facture d'ordre de retour.  

Si vous ne souhaitez pas déduire la quantité de l'article retourné de l'engagement de contrat de vente, vous pouvez utiliser le contrôle **Supprimer le lien** dans la page **Ordre de retour** pour supprimer le lien entre l'ordre de retour et l'engagement de contrat de vente. Si vous devez rétablir le lien ultérieurement, cliquez **Créer un lien**.  

**Remarque :** un ordre de retour ne peut être lié qu'à un seul contrat de vente. Si un client retourne plusieurs produits commandés dans le cadre de plusieurs contrats de vente, vous devez créer un ordre de retour pour chaque produit et créer un lien vers le contrat de vente correspondant.

## <a name="automatic-search-for-sales-agreements"></a>Recherche automatique des contrats de vente
Dans certaines situations où les commandes client sont créées indirectement, comme lorsque vous créez un avoir ou des commandes client intersociétés, vous pouvez contrôler si Microsoft Dynamics 365 pour les recherches d'opérations automatique des contrats de vente applicables.

## <a name="financial-dimensions-on-sales-agreements"></a>Dimensions financières sur les contrats de vente
Vous pouvez copier les dimensions financières vers des en-têtes de document ou des lignes individuelles d'un contrat de vente. Vous pouvez modifier les dimensions de l'en-tête ou de la ligne d'accord à tout moment. Dans ce cas, les dimensions sont automatiquement copiées vers l'en-tête ou la ligne de lancement des ordres de lancement.


