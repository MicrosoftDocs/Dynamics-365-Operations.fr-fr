---
title: Configurer la taxe pour les commandes en ligne
description: Cette rubrique fournit une vue d’ensemble de la sélection du groupe de taxes pour différents types de commande en ligne dans Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 5801bbfb5b5850cb4c9ae06140bff5adca9b368febdc06d69c538fc49f9ee40a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772959"
---
# <a name="configure-sales-tax-for-online-orders"></a>Configurer la taxe pour les commandes en ligne

[!include [banner](includes/banner.md)]

Cette rubrique fournit une vue d’ensemble de la sélection du groupe de taxes pour différents types de commande en ligne à l’aide des paramètres de taxe basés sur la destination ou sur le compte client. 

Vous pouvez souhaiter que votre canal de commerce électronique puisse prendre en charge des options telles que la livraison ou le retrait des commandes en ligne. L’applicabilité de la taxe est basée sur l’option sélectionnée par vos clients en ligne. 

## <a name="destination-based-taxes-for-online-orders"></a>Taxes basées sur la destination pour les commandes en ligne

En général, les taxes pour les commandes en ligne expédiées aux adresses des clients sont définies par la destination. Chaque groupe de taxes a une configuration de taxe basée sur la destination de vente au détail dans laquelle votre entreprise peut définir des détails de destination, tels que le pays ou la région, l’état, le département et la ville, sous une forme hiérarchique.

### <a name="orders-delivered-to-customer-address"></a>Commandes livrées à une adresse client

Lorsqu’une commande en ligne est passée, le moteur de taxe de Commerce utilise l’adresse de livraison de chaque élément de ligne de la commande et recherche les groupes de taxes avec les critères de taxe correspondant à la destination. Par exemple, pour une commande en ligne avec une adresse de livraison d’élément de campagne à San Francisco, Californie, le moteur de taxe trouvera le groupe de taxes et le code de taxe pour la Californie, puis calculera la taxe pour chaque élément de ligne en conséquence.

### <a name="order-pick-up-in-store"></a>Retrait de commande en magasin

Pour les lignes de commande avec retrait en magasin ou retrait à un point-relais spécifié, le groupe de taxes du magasin de retrait sélectionné sera appliqué. Pour plus d’informations sur la configuration des taxes pour un magasin donné, voir [Définir d’autres options fiscales pour les magasins](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

## <a name="customer-account-based-taxes-for-online-orders"></a>Taxes basées sur le compte client pour les commandes en ligne

Il peut se trouver un scénario d’entreprise dans lequel vous souhaitez configurer un groupe de taxes sur un compte client spécifique dans Commerce Headquarters. Il y a deux endroits dans Commerce Headquarters où vous pouvez configurer la taxe sur un compte client. Pour y accéder, vous devez d’abord accéder à une page de détails du client en accédant à **Retail et Commerce \> Clients \> Tous les clients**, puis en sélectionnant un client.

Les deux endroits où vous pouvez configurer la taxe pour un compte client sont les suivants :

- **Groupe de taxes** dans le raccourci **Facture et livraison** de la page des détails du client. 
- **Taxes** dans le raccourci **Général** de la page **Gérer les adresses**. Pour y accéder à partir de la page des détails du client, sélectionnez une adresse spécifique sous le raccourci **Adresses**, puis sélectionnez **Avancé**.

> [!TIP]
> Pour les commandes clients en ligne, si vous souhaitez uniquement appliquer les taxes basées sur la destination et éviter les taxes basées sur le compte client, assurez-vous que le champ **Groupe de taxes** est vide dans le raccourci **Facture et livraison** de la page des détails du client. Pour vous assurer que les nouveaux clients qui s’inscrivent via le canal en ligne n’héritent pas des paramètres du groupe de taxes des paramètres de client ou de groupe de clients par défaut, assurez-vous que le champ **Groupe de taxes** est également vide pour les paramètres client et les paramètres de groupe de clients par défaut du canal en ligne (**Retail et Commerce \> Clients \> Groupes de clients**).

## <a name="determine-destination-based-tax-or-customer-account-based-tax-applicability"></a>Déterminer l’applicabilité de la taxe basée sur la destination ou de la taxe basée sur le compte client 

Le tableau suivant explique si les taxes basées sur la destination ou les taxes basées sur le compte client sont appliquées aux commandes en ligne. 

| Type de client | Adresse d’expédition                   | Client > Facture et livraison> Groupe de taxes ? | Adresse sur le compte client dans Commerce Headquarters ? | Adresse client > Avancé > Général> Groupe de taxes ?                                              | Groupe de taxes appliqué      |
|---------------|------------------------------------|-----------------------------------------------------|-----------------------------------|--------------------------------------------------------------------------------------------------------|------------------------------|
| Invité         | Manhattan, NY                      | Non (vide)                                                | Non (vide)                              | Non (vide)                                                                                                   | NY (taxes basées sur la destination) |
| Connecté     | Austin, Texas                          | Non (vide)                                             | Oui                               | None<br/><br/>Nouvelle adresse ajoutée via le canal en ligne.                                                            | Texas (taxes basées sur la destination) |
| Connecté     | San Francisco, CA (Retrait en magasin) | Oui (NY)                                            | Non applicable                              | Non applicable                                                                                                    | Californie (taxes basées sur la destination) |
| Connecté     | Houston, Texas                         | Oui (NY)                                            | Oui                               | Oui (NY)<br/><br/>Nouvelle adresse ajoutée via le canal en ligne et groupe de taxes hérité du compte client. | NY (taxes basées sur le compte client)  |
| Connecté     | Austin, Texas                          | Oui (NY)                                            | Oui                               | Oui (NY)<br/><br/>Nouvelle adresse ajoutée via le canal en ligne et groupe de taxes hérité du compte client. | NY (taxes basées sur le compte client)  |
| Connecté     | Sarasota, Floride                       | Oui (NY)                                            | Oui                               | Oui (WA)<br/><br/>Défini manuellement sur WA.                                                                          | WA (taxes basées sur le compte client)  |
| Connecté     | Sarasota, Floride                       | Non (vide)                                                | Oui                               | Oui (WA)<br/><br/>Défini manuellement sur WA.                                                                          | WA (taxes basées sur le compte client)  |

## <a name="additional-resources"></a>Ressources supplémentaires

[Paramétrer des taxes pour les magasins en ligne en fonction de la destination](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination)

[Vue d’ensemble des taxes](../finance/general-ledger/indirect-taxes-overview.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Modes de calcul des taxes dans le champ Origine](../finance/general-ledger/sales-tax-calculation-methods-origin-field.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Affectation et remplacement des taxes](../supply-chain/procurement/tasks/sales-tax-assignment-overrides.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Options de calcul montant entier et intervalle pour les codes taxe](../finance/general-ledger/whole-amount-interval-options-sales-tax-codes.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Calcul de l’exonération fiscale](tax-exempt-price-inclusive.md) 



[!INCLUDE[footer-include](../includes/footer-banner.md)]