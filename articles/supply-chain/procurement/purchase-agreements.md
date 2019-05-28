---
title: Contrats d'achat
description: Cet article fournit des informations sur les contrats d'achat. Un contrat d'achat est un contrat par lequel une organisation s'engage à acheter une quantité ou un montant spécifique au moyen de plusieurs commandes fournisseur sur une certaine période. En échange de cet engagement, l'acheteur a droit à des prix spéciaux et des remises.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AgreementClassification, AgreementLine, AgreementLinePrompt, PurchAgreement, PurchAgreementCreate, PurchAgreementGenerateReleaseOrder, PurchAgreementHistory, PurchAgreementInvoiceJournal
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 11634
ms.assetid: 8ac20adf-7412-4929-be8c-aaedf23a76ad
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7024104dfc76a33735199ad0871fe7ce29f8e011
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570386"
---
# <a name="purchase-agreements"></a>Contrats d'achat

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur les contrats d'achat. Un contrat d'achat est un contrat par lequel une organisation s'engage à acheter une quantité ou un montant spécifique au moyen de plusieurs commandes fournisseur sur une certaine période. En échange de cet engagement, l'acheteur a droit à des prix spéciaux et des remises. 

Les contrats d'achat peuvent s'appliquer à une quantité spécifique d'un produit, à un montant en devise spécifique d'un produit ou à un montant en devise spécifique de produits d'une catégorie d'approvisionnement. Les prix et les remises du contrat d'achat sont prioritaires sur tous les autres prix et remises indiqués dans les autres contrats commerciaux pouvant exister.  

Sur la page **Contrats d'achat**, vous pouvez créer, appliquer et suivre les contrats d'achat qui existent entre votre organisation et vos fournisseurs. Par exemple, après avoir créé un contrat d'achat, vous pouvez l'utiliser directement pour passer vos commandes. Pour chaque contrat d'achat, une période de validité est définie par la personne à l'origine de la création. La date de livraison d'un achat doit être comprise dans les dates de validité de cette période de validité.  

Après avoir créé un contrat d'achat, vous devez l'activer pour qu'il prenne effet. Pour activer un contrat d'achat, définissez l'option **Marquer l'accord comme effectif** sur **Oui**.

## <a name="commitment-types"></a>Types d'engagements
Chaque ligne d'un accord d'achat exprime un engagement à acheter quelque chose. Vous pouvez utiliser les lignes de plusieurs commandes fournisseur pour honorer l'engagement. Il existe quatre types d'engagements :

-   **Engagement à la quantité de produits** : Vous achetez une quantité spécifique d'un produit.
-   **Engagement à la valeur du produit** : Vous achetez un montant en devise spécifique d'un produit.
-   **Catégorie de produit - Engagement sur valeur** : Vous achetez un montant en devise spécifique dans une catégorie d'approvisionnement. Le montant peut concerner un article du catalogue ou un article hors catalogue.
-   **Engagement sur valeur** : Vous achetez un montant en devise spécifique d'un produit ou d'une catégorie d'approvisionnement.

## <a name="pricing-terms-for-purchase-agreements"></a>Conditions de tarification pour les contrats d'achat
Les conditions de tarification peuvent varier selon le type d'engagement. Les conditions de tarification des contrats d'achat remplacent les autres conditions de tarification paramétrées pour les accords commerciaux. Le tableau suivant décrit les champs relatifs au prix affectés par chaque type d'engagement. Les champs contenant **Oui** peuvent être mis à jour sur une ligne de commande.

| Type d'engagement                   | Prix unitaire | Unité de prix | Pourcentage de remise | Montant de l'escompte de règlement |
|-----------------------------------|------------|------------|------------------|----------------------|
| Engagement à la quantité de produits       | Oui        | Oui        | Oui              | Oui                  |
| Engagement à la valeur du produit          |            |            | Oui              |                      |
| Catégorie de produit - Engagement sur valeur |            |            | Oui              |                      |
| Engagement sur valeur                  |            |            | Oui              |                      |

## <a name="policies-for-purchase-agreements"></a>Stratégies des contrats d'achat
Les stratégies suivantes affectent la manière dont le lien entre un engagement de contrat d'achat et les lignes de commande fournisseur correspondantes fonctionne :

-   **Le max. est appliqué** : La quantité ou le montant total pour toutes les lignes de commande ne peut pas dépasser la quantité ou le montant spécifié sur l'engagement associé.
-   **Le prix et la remise sont fixes** : Le prix d'une ligne de commande et celui de l'engagement associé ne peuvent pas être différents. Si le prix est modifié sur la ligne de commande, le lien vers l'engagement est rompu. Si le lien est rompu, la ligne de commande ne contribue pas à honorer l'engagement.
-   **Montant de lancement minimal et Montant de lancement maximal** : Si un montant est spécifié, un message s'affiche si vous apportez une modification à une ligne de commande qui rend celle-ci différente de l'engagement associé.

## <a name="fulfillment-calculations-for-purchase-agreements"></a>Calculs d'exécution des contrats d'achat
Les quantités et les montants ayant permis d'honorer la commande sont affichés dans l'onglet **Expédition** de l'organisateur **Détails de ligne** de la page **Contrats d'achat**.  

La zone **Expédition** indique la quantité ou le montant restant servant à honorer l'engagement.  

La zone **Accord** indique la quantité totale ou le montant total pour lequel la ligne de contrat de vente est valide.  

Vous pouvez accéder aux lignes de CF et aux lignes de facture qui contribuent au calcul du traitement en sélectionnant l'action **Informations associées** dans les lignes ou l'en-tête d'un contrat d'achat.

## <a name="confirmations-and-version-history-for-purchase-agreements"></a>Confirmations et historique de version des contrats d'achat
Lorsque vous confirmez un contrat d'achat, la version actuelle du contrat d'achat est enregistrée dans une table historique. Si vous modifiez le contrat d'achat, vous pouvez le confirmer de nouveau pour enregistrer une autre version du contrat d'achat dans l'historique. Si vous ne confirmez pas un contrat d'achat, vous pouvez toujours l'utiliser pour créer des commandes fournisseur. Toutefois, les informations historiques pour le contrat d'achat ne sont pas enregistrées. Vous pouvez prévisualiser ou imprimer toutes les versions de l'accord. Vous pouvez ensuite partager les révisions avec votre fournisseur pour obtenir l'approbation.

## <a name="applying-purchase-agreements-in-the-ordering-process"></a>Application des contrats d'achat dans le processus de commande
Lorsque vous créez un CF, vous pouvez y appliquer un contrat d'achat. Les informations des termes de l'accord, telles que les conditions de paiement, les conditions de livraison, ainsi que l'adresse de livraison, sont ensuite copiées dans l'en-tête du CF. Si le CF contient une ou plusieurs lignes pour les produits ou les catégories qui sont couvertes par le contrat d'achat, les prix et les remises du contrat d'achat sont utilisés pour ces lignes. Le montant ou la quantité de la ligne de commande est stocké sur l'engagement et contribue à l'exécution de l'engagement dans le contrat d'achat. La même commande fournisseur peut inclure aussi bien des lignes qui ne sont pas associées à un contrat d'achat que des lignes associées à un engagement pour un contrat d'achat.  

Vous pouvez sélectionner un contrat d'achat uniquement lorsque vous créez un CF. Vous ne pouvez pas sélectionner de contrat d'achat une fois que la CF est créée.  
Dans certains cas où les commandes fournisseur sont créées indirectement, vous pouvez contrôler si Finance and Operations doit lancer une recherche automatique des contrats d'achat applicables. Par exemple, vous pouvez procéder ainsi lorsque vous confirmez automatiquement des commandes fournisseur prévisionnelles ou lorsque vous créez des commandes fournisseur basées sur les commandes client.

## <a name="purchase-agreements-and-intercompany-trade"></a>Contrats d'achat et suivi intersociétés
Les relations commerciales intersociétés peuvent être créées entre les comptes fournisseur et les comptes client appartenant à différentes entités juridiques. Lorsqu'une commande client ou une commande fournisseur est créée pour une des parties, une chaîne de commandes intersociétés est créée. Dans la chaîne de commande, la commande client et la commande fournisseur sont créées dans les entités juridiques appropriées.  

Vous pouvez créer un contrat d'achat ou un contrat de vente pour un des partenaires commerciaux intersociétés. Vous pouvez ensuite générer le contrat de vente ou le contrat d'achat correspondant pour l'autre partenaire commercial intersociétés dans l'autre entité juridique.  

Si vous créez une commande fournisseur intersociétés qui utilise le contrat d'achat intersociétés dans une entité juridique, la commande client intersociétés correspondante utilise le contrat de vente intersociétés correspondant dans l'autre entité juridique. L'exécution des engagements de contrat de vente et l'exécution des contrats d'achat sont synchronisées, de même que la commande client intersociétés et la commande fournisseur intersociétés.

## <a name="financial-dimensions-on-purchase-agreements"></a>Dimensions financières sur les contrats d'achat
Vous pouvez copier les dimensions financières vers des en-têtes de document ou des lignes individuelles d'un contrat d'achat. Si vous modifiez les dimensions dans l'en-tête ou la ligne de l'accord, la modification n'affecte aucune commande lancée, mais elle sera reflétée sur toutes les nouvelles commandes.

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Créer un contrat d'achat (guide de tâche)](tasks/create-purchase-agreement.md)

[Création d'un ordre de lancement d'achat à partir d'un contrat d'achat (guide de tâche)](tasks/create-purchase-release-order-purchase-agreement.md)



