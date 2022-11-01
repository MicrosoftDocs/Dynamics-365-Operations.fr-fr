---
title: Codes de référence d’erreur du module de paiement
description: Cet article décrit les codes de référence d’erreur du module de paiement qui s’affichent dans les messages d’erreur destinés à l’utilisateur dans Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 10/20/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-09-20
ms.openlocfilehash: cd8269a71e56f23dbe3782ec3ffc69ec3ea6b151
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709669"
---
# <a name="checkout-module-error-reference-codes"></a>Codes de référence d’erreur du module de paiement

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cet article décrit les codes d’erreur du module de paiement qui s’affichent dans les messages d’erreur destinés à l’utilisateur dans Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce a introduit des références d’erreur standardisées qui peuvent être incluses dans les erreurs de paiement des canaux en ligne qui sont présentées aux clients en ligne. Dans Commerce version 10.0.31 et versions ultérieures, les messages d’erreur du module de paiement incluent des codes d’erreur et n’affichent pas d’informations inutiles pour le client en ligne. Les codes d’erreur font référence aux erreurs détaillées dans cet article.

En fonction de l’erreur rencontrée, le tableau de cet article inclut les détails suivants :

- Une description de la condition à l’origine de l’erreur ou des détails supplémentaires
- Les informations à prendre en compte dans l’environnement ou les configurations du connecteur de paiement
- Les informations pouvant être référencées dans un dossier de support, si une assistance supplémentaire est requise

## <a name="checkout-module-error-reference-codes"></a>Codes de référence d’erreur du module de paiement

Utilisez le tableau suivant pour obtenir plus de détails sur les références de code d’erreur fournies par les clients ou rencontrées dans le magasin en ligne.

| Code d’erreur | Code d’erreur lié à Dynamics | Description de l’erreur |
| ---------- | ------------------------------ | ----------------- |
| CCR001     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePaymentCardTypeMissingOrNotSupported | Le paiement n’a pas pu être autorisé. L’ID du type de carte dans **TokenizedPaymentCard** est manquant ou l’ID du type de carte fourni n’est pas pris en charge. |
| CCR002     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePayment | Refusé. Le paiement n’a pas pu être autorisé. |
| CCR003     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePaymentCardAdditionalContextRequired | Le paiement n’a pas pu être autorisé. Le client doit fournir des informations supplémentaires. |
| CCR004     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToRetrieveCardPaymentAcceptResult | Désolé mais il semble qu'un problème se soit produit. Nous n’avons pas pu obtenir le résultat de l’acceptation du paiement par carte. Réessayez ou contactez votre administrateur système. |
| CCR005     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentRequiresMerchantProperties | Impossible d’effectuer un paiement à cause de propriétés de paiement de marchand manquantes. Contactez votre administrateur système. |
| CCR006     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidPaymentRequest | Impossible de récupérer le service d’appel d’offres pour l’opération. Vérifiez la configuration de votre mode de paiement pour le type de paiement sélectionné. |
| CCR007     | Microsoft\_Dynamics\_Commerce\_Runtime\_MultipleCustomerAccountPaymentsNotAllowed | Un paiement sur le compte client a déjà été appliqué et un seul paiement est autorisé par transaction. |
| CCR008     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountLimitSignDifferentFromAmountDue | La limite du compte client diffère du montant dû. Essayez un autre mode de paiement ou contactez le service client pour obtenir de l’aide. |
| CCR009     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentExceedsTotalAmountForCarryOutAndReturnItems | Le paiement du compte client dépasse le total dû pour les articles répertoriés. Réessayez ultérieurement ou contactez le service client pour obtenir de l’aide. |
| CCR010     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentUsingUnauthorizedAccount | Le paiement par compte client nécessite son propre compte ou un compte de facturation correspondant sur une ligne de mode de paiement. |
| CCR011     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentExceedsCustomerAccountFloorLimit | Impossible de traiter un paiement du compte client pour l'instant. La valeur limite plancher est dépassée. |
| CCR012     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentForCustomerWithoutAllowOnAccount | Ce client n’est pas autorisé à payer en compte. |
| CCR013     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToCancelPayment | Désolé mais il semble qu'un problème se soit produit. Le paiement n’a pas pu être annulé. Réessayez. |
| CCR014     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToReadCardTokenInfo | Une erreur s’est produite lors du traitement du paiement. Réessayez ultérieurement. |
| CCR015     | Microsoft\_Dynamics\_Commerce\_Runtime\_NotEnoughRewardPoints | Le montant du paiement de fidélité dépasse le montant autorisé pour la carte de fidélité utilisée dans cette transaction. |
| CCR016     | Microsoft\_Dynamics\_Commerce\_Runtime\_RefundAmountMoreThanAllowed | Le montant du remboursement de fidélité dépasse le montant autorisé pour la carte de fidélité utilisée dans cette transaction. |
| CCR017     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidLoyaltyCardNumber | Le numéro de carte de fidélité est introuvable. Activez le numéro de carte de fidélité ou entrez un autre numéro de carte, puis réessayez. |
| CCR018     | Microsoft\_Dynamics\_Commerce\_Runtime\_BlockedLoyaltyCard | Le numéro de carte de fidélité n’est pas disponible. Entrez un autre numéro de carte, puis réessayez. |
| CCR019     | Microsoft\_Dynamics\_Commerce\_Runtime\_NoTenderLoyaltyCard | Cette carte de fidélité ne peut pas rembourser des points de fidélité dans le cadre de cette transaction. |
| CCR020     | Microsoft\_Dynamics\_Commerce\_Runtime\_GiftCardCurrencyMismatch | Le numéro de la carte-cadeau a rencontré une erreur. Essayez une autre carte-cadeau ou contactez le service client pour obtenir de l’aide. |
| CCR021     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentAmountExceedsGiftBalance | Le montant dépasse le solde restant sur la carte-cadeau. Entrez un autre montant, puis réessayez. |
| CCR022     | Microsoft\_Dynamics\_Commerce\_Runtime\_NoMoreThanOneLoyaltyTender | La transaction ne peut pas contenir plusieurs lignes de paiement de fidélité. |
| CCR023     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentAlreadyVoided | Les informations de paiement sont manquantes ou incorrectes. Vérifiez les informations de paiement, puis réessayez. |
| CCR024     | Microsoft\_Dynamics\_Commerce\_Runtime\_FraudRisk | Impossible de traiter la commande pour l’instant. Réessayez ultérieurement. |
| CCR025     | Dépassement du délai frontal pour l’API de paiement | L’opération frontale a expiré. Vérifiez si la commande a été traitée au niveau de Dynamics 365 Commerce headquarters. |
| CCR026     | Montant autorisé d’origine modifié | Le montant de la commande a changé par rapport au montant d’autorisation d’origine traité avec la passerelle de paiement. Cela peut être dû à l’expiration programmée d’un coupon, d’une promotion ou d’une vente. |
| CCR027     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidCartVersion | Une erreur s’est produite lors du traitement d’un paiement. La référence fournie à l’API de chariot a une référence différente de celle attendue (notant une incohérence potentielle lors du processus de paiement). |
| CCR028     | Microsoft\_Dynamics\_Commerce\_Runtime\_MissingRequiredCartTenderLines | Le mode de paiement tenté a rencontré une erreur. Contactez l’assistance pour vérifier les paramètres de votre compte ou réessayez avec un autre mode de paiement. |

## <a name="additional-resources"></a>Ressources supplémentaires

[FAQ Paiements](dev-itpro/payments-retail.md)

[Module Validation](add-checkout-module.md)

[Module Paiement](payment-module.md)
