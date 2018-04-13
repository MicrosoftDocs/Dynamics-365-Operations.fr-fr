---
title: Approuver et confirmer des commandes fournisseur
description: "Cet article décrit les statuts par lesquels passe une commande fournisseur (CF) après qu'elle a été créée et les conséquences de l’activation de la gestion des modifications sur les CF."
author: FrankDahl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, Retail
ms.custom: 93143
ms.assetid: cd12a944-c52c-4579-a301-7abe1d237c72
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 325807509601d02bad079e5ac60576e1f708e5cd
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="approve-and-confirm-purchase-orders"></a>Approuver et confirmer des commandes fournisseur

[!INCLUDE [banner](../includes/banner.md)]

[!INCLUDE [retail name](../includes/retail-name.md)]

Cet article décrit les statuts par lesquels passe une commande fournisseur (CF) après qu'elle a été créée et les conséquences de l’activation de la gestion des modifications sur les CF.

Après avoir créé une commande fournisseur (CF), celle-ci peut devoir passer par un processus d’approbation. Une fois que le fournisseur a accepté la commande, la CF passe au statut **Confirmée**.

## <a name="approval-of-purchase-orders"></a>Approbation de commandes fournisseur
Les CF qui n’utilisent pas la gestion des modifications ont un statut **Approuvée** dès qu’elles sont créées, les CF qui utilisent la gestion des modifications ont un statut **Brouillon** lorsqu’elles sont créées. Une commande fournisseur qui a été créée lors de la confirmation d'un ordre prévisionnel de la planification est toujours définie sur **Approuvée**, quels que soient les paramètres de gestion des modifications. Une CF crée des mouvements de stock uniquement lorsqu’elle atteint le statut **Approuvée**. Par conséquent, ce stock n’apparaît pas comme disponible pour la réservation ou le marquage tant que la commande n'est pas acceptée.  

Vous activez la gestion des modifications pour les CF en définissant l'option **Activer la gestion des modifications** sur la page **Paramètres d’approvisionnement**. Lorsque la gestion des modifications est activée, les CF doivent passer par un workflow d’approbation après avoir été terminées. Microsoft Dynamics 365 for Finance and Operations a un éditeur de processus de workflow dans lequel vous pouvez définir un workflow pour représenter votre processus d’approbation. Ce workflow peut inclure des règles d’approbation automatique, des règles qui déterminent qui sera affecté pour approuver certaines CF et les règles de transmission d’un workflow qui a été en attente d’approbation pendant une longue période. Vous pouvez activer le processus de gestion des modifications pour tous les fournisseurs ou pour des fournisseurs spécifiques. Vous pouvez également définir le processus de sorte qu’il puisse être substitué pour des CF individuelles.  

Lorsque de la gestion des modifications est activée, les CF passent par six statuts d’approbation, de **Brouillon** à **Finalisée**. Une fois une commande approuvée, les utilisateurs qui souhaitent la modifier doivent utiliser l'action **Demander une modification**.

| Statut d'approbation | Description                                                                      | La demande de modification est activée. |
|-----------------|----------------------------------------------------------------------------------|---------------------------|
| Brouillon           | La CF est un brouillon et n’a pas été soumise pour approbation dans le workflow de CF.     | Non                        |
| En cours de révision       | La CF a été soumise pour approbation dans le workflow de CF. L'approbation est en attente.       | Non                        |
| Rejeté(e)        | La CF a été rejetée lors du processus d'approbation.                                 | Non                        |
| Approuvé(e)        | La CF a été approuvée.                                                             | Oui                       |
| Confirmé       | La CF a été confirmée. Une CF ne peut pas être confirmée tant qu'elle n'a pas été approuvée.        | Oui                       |
| Finalisé       | La CF a été finalisée. Elle est financièrement clôturée et ne peut plus être modifiée. | Non                        |

## <a name="confirming-purchase-orders"></a>Confirmation des commandes fournisseur
Les CF qui ont un statut d’approbation **Approuvée** peuvent passer par des étapes supplémentaires avant d'être confirmées. Par exemple, vous devrez peut-être envoyer une demande de renseignements sur les achats au fournisseur pour obtenir des informations sur les prix, les escomptes ou les dates de livraison. Dans ce cas, vous pouvez définir la CF sur le statut **Fait l'objet d'une révision externe** à l’aide de l'action **Demande de renseignements sur les achats**.  

Les fournisseurs qui sont configurés pour utiliser le portail fournisseur peuvent consulter les commandes sur le portail et les approuver ou les refuser. Au cours de ce processus de révision, la CF a le statut **Fait l'objet d'une révision externe**. Le portail fournisseur peut être configuré de sorte qu'une confirmation du fournisseur confirme automatiquement la commande dans Finance and Operations. Vous pouvez également confirmer manuellement une CF après avoir reçu la confirmation du fournisseur. Si un fournisseur refuse une CF, le refus est reçu avec le motif du rejet et des propositions de modifications. Dans ce cas, le statut de la CF reste **Fait l'objet d'une révision externe**.  

Il existe également une option pour générer une confirmation pro forma pour une commande avant le traitement de la confirmation réelle. Cette option crée simplement un état que vous pouvez partager avec le fournisseur. Elle ne crée pas d'informations de journal.  

Une fois que le fournisseur a accepté la commande, l’étape suivante consiste à enregistrer la CF comme validée. Vous pouvez effectuer cette étape en utilisant l'action **Confirmation** ou l'action **Confirmer**. Ces deux actions définissent le statut d’approbation de la commande sur **Confirmée**. La confirmation d’une commande lance deux processus supplémentaires :

-   Un journal est créé pour stocker une copie exacte de ce qui a été confirmé dans le système. Parfois, les commandes nécessitent des modifications et des journaux supplémentaires sont créés une fois la mise à jour de la commande confirmée. Ces journaux permettent d’afficher l’historique des différentes versions de la commande qui ont été confirmées.
-   Des répartitions comptables sont créées et des vérifications de commander et de budget se produisent si cette fonctionnalité a été activée. Si une vérification échoue, vous recevez un message d’erreur indiquant que des modifications doivent être apportées à la CF avant de pouvoir la confirmer à nouveau.

Un fournisseur peut demander une sorte de garantie que le paiement sera effectué pour un achat. Il existe différents moyens pour fournir cette garantie dans les processus de la comptabilité fournisseur. Par exemple, l'action **Acompte** réserve des fonds pour la CF, et ce paiement anticipé est enregistré sur la CF.

## <a name="changing-purchase-orders"></a>Modification des commandes fournisseur
Dans certaines situations, vous devrez peut-être modifier une CF après qu’elle ait atteint un statut d’approbation **Approuvée** ou **Confirmée**.  

Si la CF a été créée à l’aide d’un processus de gestion des changements, vous pouvez la modifier en rappelant la commande ou, si la commande a déjà été approuvée, à l’aide de l'action **Demande la modification**. Dans ce cas, le statut d’approbation est redéfini sur **Brouillon**, et vous pouvez ensuite modifier la commande. Une fois que vous avez terminé vos modifications, vous devez envoyer la CF pour une nouvelle approbation. Vous pouvez configurer les types de modifications qui nécessitent une nouvelle approbation à l’aide d’une règle de stratégie **Règle de nouvelle approbation pour les commandes fournisseur** sur la page **Stratégies d’achat**.  

Si une partie de la quantité commandée d'une ligne de CF a été livrée, vous ne pouvez pas modifier la quantité commandée. Toutefois, vous pouvez modifier la quantité **Livrer quantité restante** sur la ligne. Vous pouvez ensuite utiliser l'action **Finaliser** pour annuler les lignes et empêcher un traitement supplémentaire. 

Une fois qu'une commande a été confirmée, vous ne pouvez plus la supprimer. Toutefois, vous pouvez annuler la quantité totale ou la quantité restante d’une commande, sous réserve que la quantité n’a pas été reçue ou facturée.

<a name="see-also"></a>Voir également :
--------

[Présentation des commandes fournisseur](purchase-order-overview.md)

[Création de commandes fournisseur](purchase-order-creation.md)

[Accusé de réception de marchandises et commandes fournisseur](product-receipt-against-purchase-orders.md)

[Vue d'ensemble des factures fournisseur](../../financials/accounts-payable/vendor-invoices-overview.md)




