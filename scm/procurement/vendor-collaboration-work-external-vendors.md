---
title: Collaboration fournisseur avec des fournisseurs externes
description: "Cette rubrique décrit comment les agents des achats peuvent collaborer avec des fournisseurs externes pour échanger des informations sur les commandes fournisseur et le stock de consignation."
author: BibiSp
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: cbd099403f48b502ca74bcb38ae12decedb8f2da
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---

# <a name="vendor-collaboration-with-external-vendors"></a>Collaboration fournisseur avec des fournisseurs externes

[!include[banner](../includes/banner.md)]


Cette rubrique décrit comment les agents des achats peuvent collaborer avec des fournisseurs externes pour échanger des informations sur les commandes fournisseur et le stock de consignation.

Le module **Collaboration fournisseur** est destiné aux fournisseurs qui n'ont pas l'intégration d'échange de données informatisé (EDI) avec Microsoft Dynamics 365 for Finance and Operations. Il permet aux fournisseurs d'utiliser les informations sur la commande fournisseur, la facture, et le stock de consignation. Cette rubrique décrit comment vous pouvez collaborer avec des fournisseurs externes qui utilisent l'interface de collaboration fournisseur pour utiliser des CF et le stock de consignation. Elle décrit également comment autoriser un fournisseur spécifique à utiliser la collaboration fournisseur, et comment définir les informations que tous les fournisseurs verront lorsqu'ils répondent à une commande fournisseur. Pour plus d'informations sur ce que les fournisseurs externes peuvent effectuer dans l'interface de collaboration fournisseur, voir [Collaboration fournisseur avec des clients](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Pour plus d'informations sur la manière dont les fournisseurs peuvent utiliser la collaboration fournisseur dans les processus de facturation, voir [Espace de travail de facturation de collaboration fournisseur](/dynamics365/unified-operations/financials/accounts-payable/vendor-portal-invoicing-workspace). Pour plus d'informations sur la mise en service de nouveaux utilisateurs de la collaboration fournisseur, voir [Gérer les utilisateurs de la fonctionnalité de collaboration du fournisseur](manage-vendor-collaboration-users.md).

Pour plus d'informations sur la manière dont les fournisseurs peuvent utiliser la collaboration fournisseur dans les processus de facturation, voir [Espace de travail de facturation de collaboration fournisseur](/dynamics365/unified-operations/financials/accounts-payable/vendor-portal-invoicing-workspace). 

Pour plus d'informations sur la mise en service de nouveaux utilisateurs de la collaboration fournisseur, voir [Gérer les utilisateurs de la fonctionnalité de collaboration du fournisseur](manage-vendor-collaboration-users.md).

## <a name="define-the-information-that-is-shown-to-vendors-when-they-respond-to-pos"></a>Définir les informations affichées pour les fournisseurs lorsqu'ils répondent aux commandes fournisseur
Lorsque les fournisseurs répondent à une commande fournisseur que vous leur envoyez, ils affichent une zone de message dans laquelle ils doivent confirmer s'ils souhaitent accepter la CF, la refuser ou l'accepter avec des modifications. Comme les informations qui doivent être affichées pour le fournisseur à ce stade peuvent être spécifiques à votre entreprise, vous pouvez donc spécifier le texte qui s'affiche dans chacun des trois messages de confirmation. Par exemple, le texte peut informer le fournisseur des prochaines étapes du processus, ou des conditions générales.  

Pour définir le texte affiché dans la réponse à une CF :

1.  Ouvrez la page **Informations pour les fournisseurs qui répondent aux CF**.
2.  Sélectionner l'une des réponses suivantes.
3.  Cliquez sur **Modifier**.
4.  Entrez les informations que vous souhaitez que les fournisseurs affichent dans la zone **Message d'information**.

Si vous devez ajouter des messages dans plusieurs langues, créez des messages distincts et spécifiez les codes de langue appropriés pour chacun d'eux. Le message que verra le fournisseur s'affichera dans la langue qu'il utilise.

## <a name="set-the-vendor-collaboration-options-for-a-specific-vendor"></a>Définir les options de collaboration fournisseur pour un fournisseur spécifique
Les paramètres généraux pour la collaboration fournisseur dans Finance and Operations sont configurés par un administrateur. Par exemple, un administrateur détermine les rôles de sécurité disponibles pour tous les fournisseurs avec lesquels vous collaborez. Il existe aussi des paramètres qui peuvent être différents pour chaque compte fournisseur, que vous devez définir :
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

Les commandes fournisseur sont préparées dans Finance and Operations. Lorsque la CF a le statut **Approuvée**, vous l'envoyez au fournisseur à l'aide de l'action **Envoyer pour confirmation** sur la page **Commande fournisseur**. Le statut de la CF passe à **En cours de révision externe**. Une fois la CF soumise, le fournisseur peut la voir sur la page **Commandes fournisseur pour examen** dans l'interface de collaboration fournisseur. Le fournisseur peut alors accepter la commande, la refuser ou proposer des modifications. Le fournisseur peut également ajouter des commentaires pour communiquer des informations telles que des modifications à la CF. Si vous souhaitez attirer l'attention du fournisseur sur une nouvelle CF, vous pouvez également utiliser le système de gestion de l'impression pour l'envoyer par courrier électronique.

### <a name="confirmation-and-acceptance-of-the-po-by-the-vendor"></a>Confirmation et acceptation de la CF par le fournisseur

Lorsqu'un fournisseur a accepté une commande fournisseur, celle-ci peut être automatiquement confirmée, ou elle peut devoir être manuellement confirmée. Cela varie selon que le champ **Activation du fournisseur** est défini sur **Actif (la CF est confirmée automatiquement)** ou sur **Actif (la CF n'est pas confirmée automatiquement)** pour le fournisseur.  

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
<td>Le fournisseur <strong>accepte</strong> la commande. Finance and Operations est configuré pour confirmer automatiquement les CF lors de l'accord du fournisseur.</td>

<td>Le statut de la commande est mis à jour sur <strong>Confirmé</strong>. Si un événement empêche la commande d'être mise à jour, la réponse du fournisseur est toujours enregistrée comme <strong>Accepté</strong>, mais le statut de la CF reste dans l'état <strong>En cours de Révision externe</strong>. 

La CF envoyée au fournisseur avec le statut **En cours de révision externe** est mise à jour avec les dates de livraison confirmées sur les lignes. La mise à jour lance une nouvelle version qui est automatiquement mise à jour sur le statut **Confirmé**. Une fois la CF confirmée, elle apparaît dans l'interface de collaboration du fournisseur.</td>
</tr>
<tr class="odd">
<td>Le fournisseur <strong>accepte</strong> la commande. Finance and Operations n'est pas configuré pour confirmer automatiquement les CF lors de l'accord du fournisseur.</td>
<td>La réponse du fournisseur est enregistrée comme <strong>Accepté</strong>, mais le statut de la CF reste dans l'état <strong>En cours de révision externe</strong>.

La CF envoyée au fournisseur avec le statut **En cours de révision externe** est mise à jour avec les dates de livraison confirmées sur les lignes. La mise à jour lance une nouvelle version qui est définie sur le statut **En cours de révision externe**. Vous pourrez ensuite confirmer manuellement la CF.</td>

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
<td>La réponse du fournisseur est enregistrée comme <strong>Accepté avec des modifications</strong>, mais le statut de la CF reste <strong>En cours de révision externe</strong>. Les statuts indiquent les types de modifications suggérées par le fournisseur. Pour plus d'informations sur la consommation automatique des modifications, consultez la section ci-dessous sur la mise à jour de la CF lorsqu'un fournisseur propose des modifications. </td>
</tr>
</tbody>
</table>

Vous pouvez utiliser l'espace de travail **Préparation de** **la commande fournisseur** pour surveiller les CF auxquelles le fournisseur a répondu. Cet espace de travail contient deux listes contenant les commandes fournisseur ayant le statut **En cours de révision externe**:

-   Action requise pour « Fait l'objet d'une révision externe ».
-   Dans la révision externe en attente de réponse du fournisseur.

### <a name="changing-a-po"></a>Modification d'une CF

Pour modifier une CF ayant déjà reçu une réponse, vous devez envoyer une nouvelle version de la CF au fournisseur. La nouvelle CF aura un suffixe de version pour indiquer qu'il s'agit d'une version modifiée d'une CF qui a été précédemment communiquée. La page **Historique des confirmations de commandes fournisseur** vous permet, ainsi que vos fournisseurs, de suivre l'historique de chaque commande. La version précédemment confirmée d'une CF demeure dans la liste des CF confirmées jusqu'à ce qu'une nouvelle CF soit confirmée.

### <a name="cancelling-a-po"></a>Annuler une CF

Lorsque vous annulez une CF, le statut passe à **Approuvé**. Vous devez retransmettre la CF au fournisseur via le portail Fournisseur afin qu'il puisse confirmer ou rejeter l'annulation. Une fois l'annulation confirmée, la CF apparaît dans la liste des CF confirmées du fournisseur avec le statut **Annulé**.

### <a name="adding-attachments-to-a-po"></a>Ajouter des pièces jointes à une CF

Vous pouvez ajouter des pièces jointes telles que des fichiers, des images, et des notes à la CF à l'aide du système de gestion des documents. Les pièces jointes du type **Externe** sont visibles par le fournisseur lorsque vous envoyez la CF.

## <a name="update-the-po-when-a-vendor-suggests-changes"></a>Mettre à jour la CF lorsqu'un fournisseur propose des modifications
Lorsqu'un fournisseur a répondu à la CF et proposé des modifications, l'étape suivante consiste à traiter la réponse.
Dans l'espace de travail **Préparation des commandes fournisseur**, dans la liste Action requise pour « Fait l'objet d'une révision externe », vous pouvez identifier une CF à laquelle un fournisseur a répondu comme étant acceptée avec des modifications. Dans la liste Action requise pour « Fait l'objet d'une révision externe », vous pouvez également accéder à la réponse du fournisseur. Dans une réponse, un fournisseur peut modifier les informations suivantes sur l'en-tête.
 
-   Référence du document du fournisseur
-   Mode de livraison
-   Conditions de livraison
-   Date de livraison confirmée

Le fournisseur peut également ajouter une note ou une pièce jointe

Sur les lignes, le fournisseur peut modifier la quantité et les dates de livraison, ajouter des notes et des pièces jointes, refuser une ligne, remplacer une ligne par un autre produit qui est entré comme du texte et fractionner une ligne en plusieurs livraisons. En fonction des modifications suggérées par le fournisseur, la ligne aura différents statuts :
    
-   **Accepter avec les modifications**
-   **Rejeté**
-   **Remplacé** - Dans ce cas, une ligne supplémentaire sera ajoutée avec le statut **Remplacer**.
-   **Confirmé** Fractionner en plan de livraison - Dans ce cas, des lignes supplémentaires seront ajoutées avec le statut **Lignes de plan de livraison**.

Si une ligne n'est pas modifiée, son statut est **Accepté**.

Dans la réponse, les statuts de ligne précédemment mentionnés indiquent les types de modifications effectuées par le fournisseur. En outre, tous les champs modifiés s'affichent en gras pour vous aider à identifier les modifications.

Vous pouvez mettre à jour une CF en cliquant sur l'action **Traiter la mise à jour de la CF** dans la réponse ou sur une ligne à la fois. Un indicateur, **La mise à jour de la CF a-t-elle été réalisée ?**, dans l'en-tête et les lignes vous permet de voir si le système a traité l'en-tête ou les lignes pour mettre à jour la CF avec les modifications potentielles provenant de la réponse. Vous pouvez exécuter le processus **Traiter la mise à jour de la CF** une seule fois par en-tête ou ligne.

Toutes les modifications proposées ne peuvent pas être mises à jour sur une CF. Seules les mises à jour sur l'en-tête et les mises à jour des dates et des quantités sur les lignes peuvent être automatiquement mises à jour sur la CF. Pour les autres modifications, vous devez mettre à jour manuellement la CF. Dans ce cas, l'indicateur **La mise à jour de la CF a-t-elle été traitée ?** affiche **Mise à jour manuelle**. Un exemple de modification qui doit être traitée manuellement serait lorsqu'un fournisseur propose de fractionner une ligne en plan de livraison.

Une ligne avec le statut **Accepté** aura une date de livraison confirmée qui sera mise à jour sur la CF lorsque vous exécutez l'action **Traiter la mise à jour de la CF**. Les notes et les pièces jointes ne seront pas automatiquement transférées vers la CF actuelle. Notez que lorsque vous mettez à jour la CF actuelle via l'action **Traiter la mise à jour de la CF**, les accords commerciaux ne seront pas réévalués sur les lignes de la CF.


## <a name="po-statuses-and-versions"></a>Statuts et versions de la CF
Cette section décrit les différents statuts d'une CF jusqu'au moment où elle est confirmée. Elle décrit également dans quelle mesure les nouvelles versions de la CF sont accessibles au fournisseur. Le comportement varie, selon que vous utilisez la gestion des modifications pour les CF. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Versions et statuts si vous n'utilisez pas la gestion des modifications

Le tableau suivant présente un exemple des modifications de statut et de version qui peuvent s'appliquer à une CF.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Action**                                                               | **Statut et version**                                                                                                                                       |
| La première version de la CF est créée dans Finance and Operations. | Le statut est **Approuvé**.                                                                                                                                  |
| La CF est envoyée au fournisseur.                                            | Une version est enregistrée dans l'interface de collaboration fournisseur et le statut devient **En cours de révision externe**.                                          |
| Le fournisseur envoie une réponse **Acceptée avec des modifications**.                  | Le statut est toujours **En cours de révision externe**.                                                                                                                  |
| Vous apportez certaines modifications qui sont requises par le fournisseur.                  | Le statut passe à **Approuvée**.                                                                                                                        |
| Vous envoyez la nouvelle version de la CF au fournisseur.                        | Une nouvelle version est enregistrée dans l'interface de collaboration fournisseur et le statut devient **En cours de révision externe**.                                      |
| Le fournisseur accepte la nouvelle version de la CF.                            | Le statut est toujours **En cours de révision externe** à moins que le compte fournisseur soit configuré pour définir automatiquement la CF sur un état **Confirmée** lorsqu'il l'accepte. |


Les fournisseurs ne doivent pas confirmer la CF à l'aide de l'interface de collaboration fournisseur. Ils peuvent également envoyer un message électronique ou communiquer leur acceptation d'une CF via autres canaux. Vous pouvez ensuite confirmer la commande manuellement dans Finance and Operations. Dans ce cas, vous recevrez un avertissement indiquant que la commande est confirmée même s'il n'y a aucune réponse du fournisseur. La CF apparaît alors dans l'historique de confirmation sous la forme d'une commande confirmée en cours qui n'a pas de réponse. Le fournisseur n'aura plus l'option de confirmer ou de rejeter la CF.  


>[!NOTE]
>La version de CF disponible pour d'autres processus dans Dynamics 365 for Finance and Operations est toujours la version la plus récente, même si cette version n'a pas encore été enregistrée dans l'interface de collaboration fournisseur.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Versions et statuts si vous utilisez la gestion des modifications

Si la gestion des modifications est activée pour les CF, la CF passe par un workflow d'approbation pour atteindre le statut **Approuvé**. Ce processus n'est pas visible au fournisseur.  

Le tableau suivant présente un exemple des modifications de statut et de version qui peuvent s'appliquer à une CF lorsque la gestion des modifications est activée. La version est enregistrée lorsque la CF est approuvée et non lorsque la CF est envoyée au fournisseur ou confirmée.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Action**                                                               | **Statut et version**                                                                                                                                       |
| La première version de la CF est créée dans Finance and Operations.      | Le statut est **Brouillon**.  |
| La CF est soumise au processus d'approbation. (Il s'agit d'un processus interne dans lequel le fournisseur n'est pas impliqué.)                                                           | Le statut passe de **Brouillon** à **En cours de révision** à **Approuvé** si la CF n'est pas rejetée au cours du processus d'approbation. La CF approuvée est enregistrée comme une version.           | 
| La CF est envoyée au fournisseur                                                            | La version est enregistrée dans l'interface de collaboration fournisseur et le statut devient **En cours de révision externe**.      |
| Vous effectuez les modifications demandées par le fournisseur, manuellement ou à l'aide de l'action dans la réponse pour mettre à jour la CF.                                                            | Le statut redevient **Brouillon**.     |
|La CF est à nouveau soumise au processus d'approbation.                                                |  Le statut passe de **Brouillon** à **En cours de révision** à **Approuvé** si la CF n'est pas rejetée au cours du processus d'approbation. Sinon, le système peut être configuré de sorte que des modifications de champ spécifiques ne nécessitent pas de nouvelle approbation. Dans ce cas, le statut est d'abord modifié en **Brouillon** avant d'être automatiquement mis à jour sur **Approuvé**. La CF approuvée est enregistrée comme une nouvelle version.                                         |
|Vous envoyez la nouvelle version de la CF au fournisseur.                                                |  La nouvelle version est enregistrée dans l'interface de collaboration fournisseur et le statut devient **En cours de révision externe**.                                         |
|Le fournisseur approuve la nouvelle version de la CF.                                                |  Le statut devient **Confirmé** automatiquement ou lorsque vous recevez la réponse du fournisseur, puis vous confirmez la CF. |

## <a name="share-information-about-consignment-inventory"></a>Partager des informations sur le stock de consignation
Si vous utilisez le stock de consignation, les fournisseurs peuvent utiliser l'interface de collaboration fournisseur pour afficher les informations sur les pages suivantes :

-   **Commandes fournisseur consommant le stock de consignation** - Les commandes fournisseur pour le stock de consignation sont générées lorsque la propriété du stock passe du fournisseur à votre société. Un accusé de réception de marchandises est validé en même temps. Ces commandes fournisseur de consignation sont affichées uniquement sur la page **Commandes fournisseur consommant le stock de consignation**. Elles ne sont pas incluses sur la page **Toutes les commandes fournisseur confirmées** du module **Collaboration fournisseur**.
-   **Produits reçus du stock de consignation** - Cette page affiche la liste de toutes les transactions dont la propriété des produits a été transférée du fournisseur à votre société. Les fournisseurs peuvent utiliser ces informations pour facturer le client.
-   **Stock de consignation disponible** - Cette page affiche le stock de consignation disponible appartenant au fournisseur qui a été reçu dans votre entrepôt.





