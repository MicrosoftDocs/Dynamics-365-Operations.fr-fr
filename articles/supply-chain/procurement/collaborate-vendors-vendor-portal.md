---
title: Collaborer avec des fournisseurs à l'aide du portail Fournisseur
description: Cette rubrique décrit comment les agents des achats peuvent utiliser le portail Fournisseur pour collaborer avec des fournisseurs externes lors du processus de confirmation de commande fournisseur. Ces informations ne s'appliquent qu'aux versions de février 2016 &amp; de mai 2016 de Dynamics AX.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 07fbc5fea1fd44769a29bcc40297ffd02812a1e5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555154"
---
# <a name="collaborate-with-vendors-by-using-the-vendor-portal"></a>Collaborer avec des fournisseurs à l'aide du portail Fournisseur

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment les agents des achats peuvent utiliser le portail Fournisseur pour collaborer avec des fournisseurs externes lors du processus de confirmation de commande fournisseur. Ces informations ne s'appliquent qu'aux versions de février 2016 &amp; de mai 2016 de Dynamics AX.

Les informations de cette rubrique ne s'appliquent qu'aux versions de février 2016 et de mai 2016 de Dynamics AX. La fonctionnalité de portail fournisseur a été remplacée par la fonctionnalité étendue de collaboration fournisseur dans la version 1611 de Dynamics 365 for Operations. Pour plus d'informations sur la nouvelle fonctionnalité de collaboration fournisseur, voir [Utilisation de la collaboration fournisseur pour utiliser des fournisseurs externes](vendor-collaboration-work-external-vendors.md).  

Le portail Fournisseur est destiné aux fournisseurs qui n'ont pas d'intégration de l'échange de données informatisé (EDI) avec Microsoft Dynamics AX pour échanger des informations de commande fournisseur (CF). Le portail permet aux agents des achats d'envoyer une CF au fournisseur puis de recevoir une réponse Confirmée ou Rejetée directement dans Dynamics AX.  

Le processus peut être configuré de sorte qu'une confirmation du fournisseur confirme automatiquement la commande. Dans ce cas, le suivi n'est nécessaire que de manière occasionnelle, lorsqu'une commande est rejetée ou si la confirmation du fournisseur est enregistrée comme réponse mais que le statut de la CF n'est pas mis à jour comme **Confirmé** en raison d'un problème dans le processus de confirmation.

## <a name="po-confirmation-and-rejection"></a>Confirmation et rejet de CF
Les CF sont préparées dans Dynamics AX. Lorsque vous avez une CF possédant le statut **Approuvé**, vous l'envoyez au fournisseur en générant une demande de confirmation. Si vous souhaitez attirer l'attention du fournisseur sur une nouvelle CF, vous pouvez également utiliser le système de gestion de l'impression pour l'envoyer par courrier électronique. La CF s'affiche dans le portail Fournisseur avec une option pour que le fournisseur puisse la confirmer ou la rejeter. Le fournisseur peut également ajouter des commentaires pour communiquer des informations telles que des modifications à la CF.  

Dans le portail Fournisseur, le fournisseur peut consulter des lignes de commande. Ces lignes incluent des informations telles que le numéro de produit externe, les dimensions, les informations de prix, la quantité, la date de livraison, ainsi que l'adresse de livraison. Le fournisseur peut générer un état affichant les informations de la CF ainsi que le coût total. Les frais pertinents pour le fournisseur sont indiqués si le fournisseur clique sur le bouton **Frais** dans l'en-tête ou les lignes. Les fournisseurs peuvent importer les informations de CF dans leur propre système à l'aide de la fonction **Exporter vers Excel**.  

Le tableau suivant présente l'échange d'informations classique, selon le type de réponse du fournisseur lorsque vous lui envoyez une CF pour confirmation.

| Type de réponse                                                                                                  | Résultat                                                                                                                                                                                                                                                                                          |
|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Le fournisseur confirme la commande. Le système est configuré pour confirmer automatiquement les CF lors de la confirmation du fournisseur.    | Le statut de la commande est mis à jour sur **Confirmé**. Si un événement empêche la commande d'être mise à jour, la réponse du fournisseur est toujours enregistrée comme **Confirmé**, mais le statut de la CF reste dans l'état **En cours de Révision externe**.                                                                       |
| Le fournisseur confirme la commande. Le système n'est pas configuré pour confirmer automatiquement les CF lors de la confirmation du fournisseur. | La réponse du fournisseur est enregistrée comme **Confirmé**, mais le statut de la CF reste dans l'état **En cours de révision externe**.                                                                                                                                                                                      |
| Le fournisseur rejette la commande.                                                                                     | La réponse du fournisseur est enregistrée comme **Rejeté** et le statut de la CF reste dans l'état **En cours de révision externe**. Le rejet est reçu avec le motif et une suggestion relative à une modification, comme une autre date de livraison par exemple. Vous mettez à jour la CF puis vous envoyez une nouvelle version pour confirmation. |

## <a name="changes-to-a-po"></a>Modifications apportées à une CF
Lorsque vous devez modifier une CF déjà confirmée, vous pouvez envoyer une nouvelle CF au fournisseur via le portail Fournisseur. La nouvelle CF aura un suffixe de version pour indiquer qu'il s'agit d'une version modifiée d'une CF qui a été précédemment communiquée. Le portail Fournisseur permet aux fournisseurs de suivre l'historique de chaque commande. La version précédemment confirmée de la CF demeurera dans la liste des CF confirmées jusqu'à ce qu'une nouvelle CF soit confirmée  

Lorsque vous annulez une CF, le statut est modifié pour revenir à **Approuvé**. Vous devez retransmettre la CF au fournisseur via le portail Fournisseur afin qu'il puisse confirmer ou rejeter l'annulation. Une fois l'annulation confirmée, la CF apparaît dans la liste des CF confirmées du fournisseur avec le statut **Annulé**.

## <a name="versions-status-transitions-and-change-management"></a>Versions, transition de statut et gestion des modifications
Lorsqu'une CF est envoyée au fournisseur, elle est enregistrée dans le système comme une version spécifique de la CF et le statut passe de **Approuvé** à **En cours de révision externe**. Si la CF est modifiée ultérieurement, une nouvelle version de la CF est créée, et le statut redevient **Approuvé** (ou **Brouillon**, si la gestion des modifications est activée).  

Le tableau suivant présente un exemple des modifications de statut et de version qui peuvent s'appliquer à une CF.

| Action                                                   | Statut et version                                                                                    |
|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| La première version de la CF est créée dans Dynamics AX. | Le statut est **Approuvé**.                                                                           |
| La CF est envoyée vers le portail Fournisseur.                     | Une version est enregistrée dans le portail Fournisseur et le statut devient **En cours de révision externe**.    |
| Vous apportez certaines modifications qui sont requises par le fournisseur.  | Le statut redevient **Approuvé**.                                                            |
| Vous envoyez la nouvelle version de la CF vers le portail fournisseur. | Une nouvelle version est enregistrée dans le portail Fournisseur et le statut est changé en **En cours de révision externe**. |
| Le fournisseur approuve la nouvelle version de la CF.           | L'état passe à **Confirmé**.                                                                |

Pour afficher les versions de la CF envoyées au fournisseur et les réponses de celui-ci, cliquez sur **Journaux** &gt; **Demandes de confirmation** à partir de la CF.  

Les commandes qui ont été envoyées au fournisseur pour réponse et dont le statut est **En cours de révision externe**, apparaissent soit dans la liste **Commandes fournisseur envoyées au portail fournisseur, en attente de réponse**, soit dans celle des **Commandes fournisseur envoyées au portail fournisseur, réponse en attente d'action**. Lorsque vous modifiez une commande qui a été envoyée au fournisseur, de sorte que son état redevient **Approuvé**, la commande n'apparaît plus dans ces listes. Pour voir s'il existe déjà une réponse du fournisseur concernant une commande, cliquez sur **Journaux** &gt; **Demandes de confirmation**.  

Les fournisseurs ne doivent pas confirmer la CF dans le portail fournisseur. Ils peuvent également envoyer un message électronique ou communiquer leur acceptation d'une CF via autres canaux. Vous pouvez ensuite confirmer la commande manuellement dans Dynamics AX. Dans ce cas, vous recevez un avertissement indiquant que la commande est confirmée même s'il n'y a aucune réponse du fournisseur. La CF apparaît alors dans l'historique de confirmation du portail Fournisseur sous la forme d'une commande confirmée en cours qui n'a pas de réponse. De plus, le fournisseur n'aura plus l'option de confirmer ou de rejeter la CF.  

**Remarque :** La version de CF disponible pour d'autres processus dans Dynamics AX est toujours la version la plus récente, même si cette version n'a pas encore été enregistrée.

### <a name="change-management"></a>Gestion des modifications

Si vous avez activé la gestion des modifications pour une CF, la CF passe par un workflow d'approbation pour atteindre le statut **Approuvé**. Ce processus n'est pas visible au fournisseur.  

Lorsque la gestion des modifications est activée pour une CF, la version est enregistrée lorsque la CF est approuvée et non lorsque la CF est envoyée au fournisseur ou confirmée.  

Le tableau suivant présente un exemple des modifications de statut et de version qui peuvent s'appliquer à une CF lorsque la gestion des modifications est activée.


|                                                    Action                                                     |                                                                                                                                                                                                                      Statut et version                                                                                                                                                                                                                      |
|---------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           La première version de la CF est créée dans Dynamics AX.                            |                                                                                                                                                                                                            Le statut est <strong>Brouillon</strong>.                                                                                                                                                                                                             |
| La CF est soumise au processus d'approbation. (Il s'agit d'un processus interne dans lequel le fournisseur n'est pas impliqué.) |                                                                                                                        Le statut passe de <strong>Brouillon</strong> à <strong>En cours de révision</strong> à <strong>Approuvé</strong> si la CF n'est pas rejetée au cours du processus d'approbation. La CF approuvée est enregistrée comme une version.                                                                                                                        |
|                                      La CF est envoyée sur le portail Fournisseur.                                      |                                                                                                                                                                      La version est enregistrée dans le portail Fournisseur et le statut devient <strong>En cours de révision externe</strong>.                                                                                                                                                                       |
|                            Vous apportez certaines modifications qui sont requises par le fournisseur.                            |                                                                                                                                                                                                    Le statut redevient <strong>Brouillon</strong>.                                                                                                                                                                                                     |
|                              La CF est à nouveau soumise au processus d'approbation.                               | Le statut passe de <strong>Brouillon</strong> à <strong>En cours de révision</strong> à <strong>Approuvé</strong> si la CF n'est pas rejetée au cours du processus d'approbation. Sinon, le système peut être configuré de sorte que des modifications de champ spécifiques ne nécessitent pas de nouvelle approbation. Dans ce cas, le statut est d'abord modifié en <strong>Brouillon</strong> avant d'être automatiquement mis à jour sur <strong>Approuvé</strong>. La CF approuvée est enregistrée comme une nouvelle version. |
|                           Vous envoyez la nouvelle version de la CF vers le portail fournisseur.                            |                                                                                                                                                                    La nouvelle version est enregistrée dans le portail Fournisseur et le statut devient <strong>En cours de révision externe</strong>.                                                                                                                                                                     |
|                                Le fournisseur approuve la nouvelle version de la CF.                                 |                                                                                                                                                     Le statut devient <strong>Confirmé</strong> automatiquement ou lorsque vous recevez la réponse du fournisseur, puis vous confirmez la CF.                                                                                                                                                     |

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Configuration de la sécurité pour les utilisateurs de la collaboration fournisseur](configure-security-vendor-portal-users.md)

[Espace de travail de facturation de collaboration fournisseur](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md)



