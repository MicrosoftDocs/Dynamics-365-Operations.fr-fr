---
title: Acomptes dans Dynamics 365 Commerce
description: Cet article fournit une vue d’ensemble du traitement des transactions d’acompte dans Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2021-06-28
ms.openlocfilehash: 8262470f83481ef8840857a52948c0833d8b278e
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780359"
---
# <a name="prepayments-in-dynamics-365-commerce"></a>Acomptes dans Dynamics 365 Commerce

[!include[banner](../includes/banner.md)]

Cet article fournit une vue d’ensemble du traitement des transactions d’acompte dans Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce traite les transactions d’acompte pour les types de paiement suivants qui sont utilisés dans Comptabilité client ou Commerce :

- **Paiement relatif au dépôt sur compte client** : un client verse un acompte au point de vente (PDV). Commerce traite le paiement de dépôt comme une transaction d’acompte. Lorsque vous validez la transaction, un journal des paiements est créé et validé sur la page **N° document de journal** dans Commerce Headquarters. La case **N° document du journal des acomptes** est automatiquement cochée dans l’onglet **Paiement** pour le journal des paiements. Pour plus d’informations, notamment sur les acomptes et les informations spécifiques aux taxes applicables à la région cible, voir [Ressources de globalisation - Rubriques d’aide spécifiques à un pays/une région](/dynamics365/fin-ops-core/dev-itpro/lcs-solutions/country-region?context=%2Fdynamics365%2Fcontext%2Ffinance#countryregion-specific-help-content).
- **Commande client avec dépôt** : un client crée une commande client au PDV. Le client peut verser un dépôt pour la commande, en fonction du pourcentage de dépôt par défaut configuré sur la page **Commandes client** dans Commerce Headquarters (**Paramètres de Commerce \> Commandes client**). Commerce traite le paiement de dépôt pour la commande client comme une transaction d’acompte. Lorsque vous validez la transaction, un journal des paiements est créé et validé sur la page **N° document de journal**. La case **N° document du journal des acomptes** est automatiquement cochée dans l’onglet **Paiement** pour le journal des paiements. Le paiement est réglé et la facture client est automatiquement émise lors de l’enlèvement ou de la livraison de la commande.
- **Commande client du centre d’appels** : un représentant du service client du centre d’appels crée une commande client pour le compte d’un client et l’attribut **Acompte** est défini sur **Oui** lors de la saisie du paiement.

Commerce effectue les tâches suivantes pour traiter un acompte :

- **Traiter un paiement de dépôt de compte client** : un paiement de dépôt effectué par un client est transféré dans Commerce à l’aide d’un service qui synchronise les données. Commerce crée une transaction de paiement de vente de détail pour le paiement. Lorsque vous validez la transaction de vente au détail, un journal de caisse ou un journal des paiements client est validé. La case **N° document du journal des acomptes** est automatiquement cochée dans l’onglet **Paiement** de la page **N° document de journal** dans Commerce Headquarters pour le journal des paiements. Les acomptes ne peuvent pas être traités si le montant du paiement est négatif.
- **Traiter une commande client ou une commande client avec dépôt** : un client paie un dépôt requis pour une commande client en utilisant Commerce Data Exchange : Real-time Service. Commerce crée soit un journal des paiements client, soit un journal de caisse, selon le mode de paiement utilisé par le client. La case **N° document du journal des acomptes** est automatiquement cochée dans l’onglet **Paiement** de la page **N° document de journal** dans Commerce Headquarters pour le journal. Si un client utilise plusieurs modes de paiement pour effectuer des paiements partiels, Commerce traite chaque paiement partiel en fonction du mode de paiement utilisé.

Pour les cartes de crédit et les portefeuilles numériques qui ont des modes de paiement par carte de crédit sous-jacents, Commerce envoie une demande de « capture » après l’autorisation réussie. (Les fonds sont capturés avant que la commande client ne soit facturée.)

Si vous annulez une commande client, le montant de l’acompte est remboursé et un journal des remboursements est enregistré pour le montant du dépôt. Le montant du remboursement est calculé et validé en fonction du mode de paiement que vous avez spécifié lorsque vous avez validé le paiement du remboursement. Commerce peut appliquer des frais d’annulation, en fonction du pourcentage que vous définissez sur la page **Paramètres de Commerce** dans Commerce Headquarters.

Si vous retournez une commande client, un ordre de retour et un journal des remboursements sont créés. Lorsque vous validez l’ordre de retour, Commerce crée soit un journal des paiements client, soit un journal de caisse, selon le mode de paiement utilisé par le client pour la transaction d’origine.
