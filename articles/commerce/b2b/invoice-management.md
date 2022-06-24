---
title: Gestion des factures pour les sites e-commerce B2B
description: Cet article décrit les fonctionnalités de gestion des factures des sites e-commerce interentreprises (B2B)Microsoft Dynamics 365 Commerce.
author: shajain
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: fa6b81187481a6b7f47ea02291e5a581052d6c7b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854924"
---
# <a name="invoice-management-for-b2b-e-commerce-websites"></a>Gestion des factures pour les sites e-commerce B2B

[!include [banner](../../includes/banner.md)]

Cet article décrit les fonctionnalités de gestion des factures des sites e-commerce interentreprises (B2B)Microsoft Dynamics 365 Commerce.

C’est une pratique courante pour les entreprises qui gèrent des transactions B2B d’accepter des commandes à crédit client, puis d’envoyer une facture aux clients après avoir exécuté la commande. Les conditions de paiement sont définies pour les clients, et il peut y avoir des remises pour inciter les clients à payer à temps ou avant l’heure. Pour aider à augmenter la probabilité que les paiements soient reçus à temps, les sites e-commerce B2B permettent aux clients de consulter toutes leurs factures. Le client peut facilement filtrer les factures pour afficher les factures payées, impayées et partiellement payées avec les dates d’échéance.

![Page de factures sur un site Web B2B.](../media/ViewInvoices.png)

> [!NOTE]
> Un utilisateur connecté ne peut consulter et payer que ses propres factures. Si un compte d’organisation est configuré dans le menu déroulant **Compte de facturation** via le raccourci **Facture et livraison** du dossier client dans Commerce Headquarters, l’utilisateur pourra afficher et payer les factures du compte de l’organisation.

Sur la page **Factures** d’un site Web B2B, un utilisateur peut sélectionner une facture impayée ou partiellement payée, puis sélectionnez **Payer sa commande**. La facture sélectionnée est ajoutée au panier et l’utilisateur peut procéder au paiement. L’utilisateur peut alors décider de payer le montant total de la facture ou un montant partiel. L’utilisateur ne peut pas utiliser le mode de paiement sur compte pour régler des factures.

> [!NOTE]
> Les factures peuvent être ajoutées au panier uniquement si aucun article ne s’y trouve actuellement. Inversement, les articles ne peuvent être ajoutés au panier que si aucune facture ne s’y trouve actuellement. Microsoft prévoit de supprimer cette restriction dans les futures versions de Commerce.

![Page de panier sur un site Web B2B.](../media/PayInvoice.png)

Sur la page **Factures**, un utilisateur peut également sélectionner **Demander la facture** en regard d’une facture. De cette manière, l’utilisateur peut demander à ce que les détails de la facture soient envoyés à son adresse e-mail enregistrée.

![Boîte de dialogue de demande de facture.](../media/RequestInvoice2.png)

Lorsqu’un utilisateur demande une facture, la demande est déplacée vers la section **Requêtes B2B** de la page **Mon compte**. Puis, après l’exécution des tâches **P-0001** et **Synchroniser les commandes et les demandes de canal** dans Commerce Headquarters, l’e-mail de facturation est déclenché et le statut de la demande B2B est marqué comme terminé.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
