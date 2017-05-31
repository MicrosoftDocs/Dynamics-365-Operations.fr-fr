---
title: Collaboration fournisseur avec des fournisseurs externes
description: "Cette rubrique décrit comment les agents des achats peuvent collaborer avec des fournisseurs externes pour échanger des informations sur les commandes fournisseur et le stock de consignation."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b141ed78306504949eae641377b5c5a2b0599572
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="vendor-collaboration-with-external-vendors"></a>Collaboration fournisseur avec des fournisseurs externes

[!include[banner](../includes/banner.md)]


Cette rubrique décrit comment les agents des achats peuvent collaborer avec des fournisseurs externes pour échanger des informations sur les commandes fournisseur et le stock de consignation.

Le module **Collaboration fournisseur** est destiné aux fournisseurs qui n'ont pas l'intégration d'échange de données informatisé (EDI) avec Microsoft Dynamics 365 for Operations. Il permet aux fournisseurs d'utiliser les informations sur la commande fournisseur, la facture, et le stock de consignation. Cette rubrique décrit comment vous pouvez collaborer avec des fournisseurs externes qui utilisent l'interface de collaboration fournisseur pour utiliser des CF et le stock de consignation. Elle décrit également comment autoriser un fournisseur spécifique à utiliser la collaboration fournisseur, et comment définir les informations que tous les fournisseurs verront lorsqu'ils répondent à une commande fournisseur. Pour plus d'informations sur ce que les fournisseurs externes peuvent effectuer dans l'interface de collaboration fournisseur, voir [Collaboration fournisseur avec des clients](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Pour plus d'informations sur la manière dont les fournisseurs peuvent utiliser la collaboration fournisseur dans les processus de facturation, voir [Espace de travail de facturation de collaboration fournisseur](/dynamics365/operations/financials/accounts-payable/vendor-portal-invoicing-workspace). Pour plus d'informations sur la mise en service de nouveaux utilisateurs de la collaboration fournisseur, voir [Gérer les utilisateurs de la fonctionnalité de collaboration du fournisseur](manage-vendor-collaboration-users.md).

## <a name="define-the-information-shown-to-vendors-when-they-respond-to-pos"></a>Définir les informations affichées pour les fournisseurs lorsqu'ils répondent aux commandes fournisseur
Lorsque les fournisseurs répondent à une commande fournisseur que vous leur envoyez, ils affichent une boîte de dialogue sur laquelle ils doivent confirmer s'ils souhaitent accepter, refuser, ou accepter la CF avec des modifications. Les informations qui doit être affichées pour le fournisseur à ce stade peuvent être spécifiques à votre entreprise, vous pouvez donc spécifier le texte qui s'affiche sur chacun des trois messages de confirmation. Par exemple, le texte peut informer le fournisseur des prochaines étapes du processus, ou des conditions générales.  

Pour définir le texte affiché dans la réponse à une CF :

1.  Ouvrez la page **Informations pour les fournisseurs qui répondent aux CF**.
2.  Sélectionner l'une des réponses suivantes.
3.  Cliquez sur **Modifier.**
4.  Entrez les informations que vous souhaitez que les fournisseurs affichent dans la zone **Message d'information**.

Si vous devez ajouter des messages dans plusieurs langues, créez des messages distincts avec des codes de langues appropriés. Le fournisseur verra s'afficher le message dans la langue qu'il utilise.

## <a name="set-the-vendor-collaboration-options-for-a-specific-vendor"></a>Définir les options de collaboration fournisseur pour un fournisseur spécifique
Les paramètres généraux pour la collaboration fournisseur dans Dynamics 365 for Operations sont configurés par un administrateur. Par exemple, ils déterminent les rôles de sécurité disponibles pour tous les fournisseurs avec lesquels vous collaborez. Il existe aussi des paramètres qui peuvent être différent pour chaque compte fournisseur, que vous devez définir :

-   Activez la collaboration fournisseur.
-   Indiquez si vous souhaitez que le fournisseur affiche les informations de prix.

### <a name="enable-vendor-collaboration"></a>Activer la collaboration fournisseur

Avant que les comptes d'utilisateur puissent être créés pour un fournisseur externe, vous devez configurer le compte fournisseur pour leur permettre d'utiliser la collaboration fournisseur. Pour celà, définissez le champ **Activation de la collaboration** sur actif sous l'onglet **Général** de la page **Fournisseurs**. Il existe deux options que vous pouvez sélectionner :

-   **Actif (la CF est confirmée automatiquement)**- Les commandes fournisseur sont automatiquement confirmées lorsque le fournisseur les accepte sans modifications.
-   **Actif (la CF n'est pas confirmée automatiquement)**- Les commandes fournisseur doivent être confirmées manuellement par votre organisation, après que le fournisseur les a acceptées.

### <a name="decide-whether-you-want-the-vendor-to-see-price-information"></a>Indiquer si vous souhaitez que le fournisseur affiche les informations de prix

Si vous souhaitez partager des informations sur les prix telles que les prix, les remises, et les frais sur l'interface de collaboration, vous devez définir l'option **Prix/montant de la commande fournisseur** sur **Oui** sur le compte fournisseur. Cette option est disponible sous l'onglet **Valeurs par défaut des commandes fournisseur**.

## <a name="work-with-pos-when-using-vendor-collaboration"></a>Utiliser des CF lors de l'utilisation de la collaboration fournisseur
### <a name="sending-a-po-to-the-vendor"></a>Envoi d'une CF à un fournisseur

Les commandes fournisseur sont préparées dans Dynamics 365 for Operations. Lorsque la CF a le statut **Approuvé**, vous l'envoyez au fournisseur à l'aide de l'action **Envoyer pour confirmation **de la page **Commande fournisseur**. Le statut de la CF passe à **En cours de révision externe**. Une fois la CF soumise, le fournisseur peut la voir sur la page **Commandes fournisseur pour examen** dans l'interface de collaboration fournisseur, dans laquelle ils peuvent accepter, refuser ou proposer des modifications à la commande. Le fournisseur peut également ajouter des commentaires pour communiquer des informations telles que des modifications à la CF. Si vous souhaitez attirer l'attention du fournisseur sur une nouvelle CF, vous pouvez également utiliser le système de gestion de l'impression pour l'envoyer par courrier électronique.

### <a name="confirmation-and-acceptance-of-the-po-by-the-vendor"></a>Confirmation et acceptation de la CF par le fournisseur

Lorsqu'un fournisseur a accepté une commande fournisseur, celle-ci peut être automatiquement confirmée, ou elle peut devoir être manuellement confirmée. Cela varie selon que le champ **Activation du fournisseur **est défini sur **Actif (la CF est confirmée automatiquement)**pour le fournisseur, ou sur **Actif (la CF n'est pas confirmée automatiquement)**.  

Le tableau suivant présente l'échange d'informations classique, selon la réaction du fournisseur lorsque vous envoyez une CF pour confirmation.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Réponse du fournisseur</strong></td>
<td><strong>Résultat</strong></td>
</tr>
<tr class="even">
<td>Le fournisseur <strong>accepte</strong> la commande. Dynamics 365 for Operations est configuré pour confirmer automatiquement les CF lors de l'accord du fournisseur.</td>
<td>Le statut de la commande est mis à jour sur <strong>Confirmé</strong>. Si un événement empêche la commande d'être mise à jour, la réponse du fournisseur est toujours enregistrée comme <strong>Accepté</strong>, mais le statut de la CF reste dans l'état <strong>En cours de Révision externe</strong>.</td>
</tr>
<tr class="odd">
<td>Le fournisseur <strong>accepte</strong> la commande. Dynamics 365 for Operations n'est pas configuré pour confirmer automatiquement les CF lors de l'accord du fournisseur.</td>
<td>La réponse du fournisseur est enregistrée comme <strong>Accepté</strong>, mais le statut de la CF reste dans l'état <strong>En cours de révision externe</strong>.</td>
</tr>
<tr class="even">
<td>Le fournisseur <strong>rejette</strong> la commande.</td>
<td>La réponse du fournisseur est enregistrée comme <strong>Rejeté</strong> et le statut de la CF reste dans l'état <strong>En cours de révision externe</strong>. Le rejet est reçu avec la note du fournisseur.</td>
</tr>
<tr class="odd">
<td>Le fournisseur <strong>accepte la commande avec des modifications</strong>. Les modifications sont suggérées au niveau de la ligne. Il est possible d'accepter ou de rejeter des lignes. D'autres modifications possibles sont les suivantes :
<ul>
<li>Modification des dates ou des quantités.</li>
<li>Fractionnement des lignes pour différentes dates de livraison ou quantités.</li>
<li>Remplacement d'un article.</li>
</ul>
Les informations sur les prix et les frais ne peuvent pas être modifiées par le fournisseur. Les suggestions de modifications de celles-ci peuvent être faites en utilisant des notes.</td>
<td>La réponse du fournisseur est enregistrée comme <strong>Accepté avec des modifications</strong>, <strong></strong> mais le statut de la CF reste dans l'état <strong>En cours de révision externe</strong>.</td>
</tr>
</tbody>
</table>

Vous pouvez utiliser l'espace de travail **Préparation de** **la commande fournisseur** pour surveiller les CF auxquelles le fournisseur a répondu. Cet espace de travail contient deux listes contenant les commandes fournisseur ayant le statut **En cours de révision externe**:

-   Action requise pour « Fait l'objet d'une révision externe ».
-   Dans la révision externe en attente de réponse du fournisseur.

### <a name="changing-a-po"></a>Modification d'une CF

Lorsque vous devez modifier une CF ayant déjà reçu une réponse, vous devez envoyer une nouvelle version de la CF au fournisseur. La nouvelle CF aura un suffixe de version pour indiquer qu'il s'agit d'une version modifiée d'une CF qui a été précédemment communiquée. La page **Historique des confirmations de commandes fournisseur** vous permet, ainsi que vos fournisseurs, de suivre l'historique de chaque commande. La version précédemment confirmée de la CF demeure dans la liste des CF confirmées jusqu'à ce qu'une nouvelle CF soit confirmée

### <a name="cancelling-a-po"></a>Annuler une CF

Lorsque vous annulez une CF, le statut passe à **Approuvé**. Vous devez retransmettre la CF au fournisseur via le portail Fournisseur afin qu'il puisse confirmer ou rejeter l'annulation. Une fois l'annulation confirmée, la CF apparaît dans la liste des CF confirmées du fournisseur avec le statut **Annulé**.

### <a name="adding-attachments-to-a-po"></a>Ajouter des pièces jointes à une CF

Vous pouvez ajouter des pièces jointes telles que des fichiers, des images, et des notes à la CF à l'aide de le système de gestion des documents. Les pièces jointes ajoutées à la restriction du type **Externe** sont visibles pour le fournisseur lorsque vous lui envoyez la CF.

## <a name="purchase-order-statuses-and-versions"></a>Statuts et versions de commande fournisseur
Cette section décrit les différents statuts qu'une CF peut comporter jusqu'au moment où elle est confirmée, et à quel moment de nouvelles versions de la CF sont rendues disponibles pour le fournisseur. Il existe des différences, selon que vous utilisez la gestion des modifications pour les commandes fournisseur. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Versions et statuts si vous n'utilisez pas la gestion des modifications

Le tableau suivant présente un exemple des modifications de statut et de version qui peuvent s'appliquer à une CF.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Action**                                                               | **Statut et version**                                                                                                                                       |
| La première version de la CF est créée dans Dynamics 365 for Operations. | Le statut est **Approuvé**.                                                                                                                                  |
| La CF est envoyée au fournisseur.                                            | Une version est enregistrée dans l'interface de collaboration fournisseur et le statut devient **En cours de révision externe**.                                          |
| Le fournisseur envoie une réponse **Acceptée avec des modifications**.                  | Le statut est toujours **En cours de révision externe**.                                                                                                                  |
| Vous apportez certaines modifications qui sont requises par le fournisseur.                  | Le statut passe à **Approuvée**.                                                                                                                        |
| Vous envoyez la nouvelle version de la CF au fournisseur.                        | Une nouvelle version est enregistrée dans l'interface de collaboration fournisseur et le statut devient **En cours de révision externe**.                                      |
| Le fournisseur accepte la nouvelle version de la CF.                            | Le statut est toujours **En cours de révision externe**à moins que le compte fournisseur soit configuré pour définir automatiquement la CF sur un état **Confirmée** lorsqu'il l'accepte. |

Les fournisseurs ne doivent pas confirmer la CF à l'ide de l'interface de collaboration fournisseur. Ils peuvent également envoyer un message électronique ou communiquer leur acceptation d'une CF via autres canaux. Vous pouvez ensuite confirmer la commande manuellement dans Dynamics 365 for Operations. Dans ce cas, vous recevez un avertissement indiquant que la commande est confirmée même s'il n'y a aucune réponse du fournisseur. La CF apparaît alors dans l'historique de confirmation sous la forme d'une commande confirmée en cours qui n'a pas de réponse. Le fournisseur n'aura plus l'option de confirmer ou de rejeter la CF.  

**Remarque :** La version de CF disponible pour d'autres processus dans Dynamics 365 for Operations est toujours la version la plus récente, même si cette version n'a pas encore été enregistrée dans l'interface de collaboration fournisseur.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Versions et statuts si vous utilisez la gestion des modifications

Si la gestion des modifications est activée pour les CF, la CF passe par un workflow d'approbation pour atteindre le statut **Approuvé**. Ce processus n'est pas visible au fournisseur.  

Le tableau suivant présente un exemple des modifications de statut et de version qui peuvent s'appliquer à une CF lorsque la gestion des modifications est activée. La version est enregistrée lorsque la CF est approuvée et non lorsque la CF est envoyée au fournisseur ou confirmée.

|                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Action**                                                                                                    | **Statut et version**                                                                                                                                                                                                                                                                                                                                                                      |
| La première version de la CF est créée dans Dynamics 365 for Operations.                                      | Le statut est **Brouillon**.                                                                                                                                                                                                                                                                                                                                                                    |
| La CF est soumise au processus d'approbation. (Il s'agit d'un processus interne dans lequel le fournisseur n'est pas impliqué.) | Le statut passe de **Brouillon** à **En cours de révision** à **Approuvé** si la CF n'est pas rejetée au cours du processus d'approbation. La CF approuvée est enregistrée comme une version.                                                                                                                                                                                                                     |
| La CF est envoyée au fournisseur                                                                                  | La version est enregistrée dans l'interface de collaboration fournisseur et le statut devient **En cours de révision externe**.                                                                                                                                                                                                                                                                       |
| Vous apportez certaines modifications qui sont requises par le fournisseur.                                                       | Le statut redevient **Brouillon**.                                                                                                                                                                                                                                                                                                                                                    |
| La CF est à nouveau soumise au processus d'approbation.                                                            | Le statut passe de **Brouillon** à **En cours de révision** à **Approuvé** si la CF n'est pas rejetée au cours du processus d'approbation. Sinon, le système peut être configuré de sorte que des modifications de champ spécifiques ne nécessitent pas de nouvelle approbation. Dans ce cas, le statut est d'abord modifié en **Brouillon** avant d'être automatiquement mis à jour sur **Approuvé**. La CF approuvée est enregistrée comme une nouvelle version. |
| Vous envoyez la nouvelle version de la CF au fournisseur.                                                             | La nouvelle version est enregistrée dans l'interface de collaboration fournisseur et le statut devient **En cours de révision externe**.                                                                                                                                                                                                                                                                   |
| Le fournisseur approuve la nouvelle version de la CF.                                                                | Le statut devient **Confirmé**automatiquement ou lorsque vous recevez la réponse du fournisseur, puis vous confirmez la CF.                                                                                                                                                                                                                                                     |

## <a name="share-information-about-consignment-inventory"></a>Partager des informations sur le stock de consignation
Si vous utilisez le stock de consignation, les fournisseurs peuvent utiliser l'interface de collaboration fournisseur pour afficher les informations sur les pages suivantes :

-   **Commandes fournisseur consommant le stock de consignation** - Les commandes fournisseur pour le stock de consignation sont générées lorsque la propriété du stock passe du fournisseur à votre société. Un accusé de réception de marchandises est validé en même temps. Ces commandes fournisseur de consignation sont affichées uniquement sur la page **Commandes fournisseur consommant le stock de consignation**. Elles ne sont pas incluses sur la page **Toutes les commandes fournisseur confirmées** du module **Collaboration fournisseur**.
-   **Produits reçus du stock de consignation** - Cette page affiche la liste de toutes les transactions dont la propriété des produits a été transférée du fournisseur à votre société. Les fournisseurs peuvent utiliser ces informations pour facturer le client.
-   **Stock de consignation disponible** - Cette page affiche le stock de consignation disponible appartenant au fournisseur qui a été reçu dans votre entrepôt.





