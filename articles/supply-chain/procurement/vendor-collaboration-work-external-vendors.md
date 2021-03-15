---
title: Collaboration fournisseur avec des fournisseurs externes
description: Cette rubrique explique comment les agents des achats peuvent collaborer avec des fournisseurs externes pour échanger des informations sur les commandes fournisseur et le stock de consignation.
author: RichardLuan
manager: tfehr
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, VendVendorPortalInvoicePart, PurchaseOrderResponseActionRemarks, PurchVendorPortalAllResponse, PurchOrderInExternalReview, PurchVendorPortalPendingResponsesPart, PurchVendorPortalResponses, PurchVendorPortalConfirmedOpenOrdersPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 594a5bc8762d4c3fdc0bfd901ab97262b0f67a53
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016751"
---
# <a name="vendor-collaboration-with-external-vendors"></a>Collaboration fournisseur avec des fournisseurs externes

[!include [banner](../includes/banner.md)]

Le module **Collaboration fournisseur** est destiné aux fournisseurs qui n'ont pas l'intégration d'échange de données informatisé (EDI) avec Microsoft Dynamics 365 Supply Chain Management. Il permet aux fournisseurs d'utiliser les commandes fournisseur, les factures, les informations sur le stock de consignation et les appels d'offre. Il leur permet également d'accéder à des parties de leurs données principales. Cette rubrique explique comment vous pouvez collaborer avec des fournisseurs externes qui utilisent l'interface de collaboration fournisseur pour utiliser les CF, les appels d'offre et le stock de consignation. Elle explique également comment autoriser un fournisseur spécifique à utiliser la collaboration fournisseur, et comment définir les informations visibles par tous les fournisseurs qui répondent à une commande fournisseur.

Pour plus d'informations sur ce que les fournisseurs externes peuvent effectuer dans l'interface de collaboration fournisseur, voir [Collaboration fournisseur avec des clients](vendor-collaboration-work-customers-dynamics-365-operations.md).

> [!NOTE]
> Les informations sur la collaboration fournisseur contenues dans cette rubrique s'appliquent uniquement à la version actuelle de Supply Chain Management. Dans Microsoft Dynamics AX 7.0 (février 2016) et dans la version de l'application 7.0.1 de Microsoft Dynamics AX, vous collaborez avec les fournisseurs à l'aide du module **Portail fournisseur**. Pour plus d'informations sur le module **Portail Fournisseur**, voir [Collaborer avec des fournisseurs à l'aide du portail Fournisseur](collaborate-vendors-vendor-portal.md).

Pour plus d'informations sur la manière dont les fournisseurs peuvent utiliser la collaboration fournisseur dans les processus de facturation, voir [Espace de travail de facturation de collaboration fournisseur](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md). Pour plus d'informations sur la mise en service de nouveaux utilisateurs de la collaboration fournisseur, voir [Gérer les utilisateurs de la fonctionnalité de collaboration du fournisseur](manage-vendor-collaboration-users.md).

## <a name="defining-the-information-that-is-shown-to-vendors-when-they-respond-to-pos"></a>Définition des informations visibles par les fournisseurs lorsqu'ils répondent à des commandes fournisseur

Lorsque les fournisseurs répondent à une commande fournisseur que vous leur envoyez, ils voient une des trois zones de message dans lesquelles ils doivent confirmer s'ils souhaitent accepter la CF, la refuser ou l'accepter avec des modifications. Comme les informations qui doivent être visualisées par le fournisseur à ce stade peuvent être spécifiques à votre entreprise, vous pouvez donc spécifier le texte qui s'affiche dans chaque message de confirmation. Par exemple, le texte peut informer le fournisseur des prochaines étapes du processus, ou des conditions générales.

Pour définir le texte affiché dans la réponse à une CF, procédez comme suit :

1. Sur la page **Informations pour les fournisseurs qui répondent aux CF**, sélectionnez le type de réponse, puis sélectionnez **Modifier**.
2. Dans la zone **Message d'information**, entrez les informations qui doivent être visualisées par les fournisseurs dans la zone de message.

Si vous devez ajouter des messages dans plusieurs langues, créez des messages distincts et spécifiez le code de langue approprié pour chacun d'eux. Le message que verra chaque fournisseur s'affichera dans la langue qu'il utilise.

## <a name="setting-the-vendor-collaboration-options-for-a-specific-vendor"></a>Définition des options de collaboration fournisseur pour un fournisseur spécifique

Un administrateur configure les paramètres généraux de la collaboration fournisseur, comme les rôles de sécurité disponibles pour tous les fournisseurs avec lesquels vous collaborez. Toutefois, il existe aussi des paramètres qui peuvent être différents pour chaque compte fournisseur. Vous devez configurer ces paramètres.

- Activez la collaboration fournisseur.
- Spécifiez si le fournisseur doit voir les informations tarifaires.

### <a name="enabling-vendor-collaboration"></a>Activation de la collaboration fournisseur

Avant que les comptes d'utilisateur puissent être créés pour un fournisseur externe, vous devez configurer le compte fournisseur afin que ce fournisseur puisse utiliser la collaboration fournisseur. Sur la page **Fournisseurs**, sous l'onglet **Général**, définissez le champ **Activation de la collaboration**. Les options suivantes sont disponibles :

- **Actif (la CF est confirmée automatiquement)** – Les CF sont automatiquement confirmées si le fournisseur les accepte sans modifications.
- **Actif (la CF n'est pas confirmée automatiquement)** – Votre organisation doit confirmer manuellement les CF une fois que le fournisseur les a acceptées.

### <a name="specifying-whether-the-vendor-should-see-price-information"></a>Spécifier si le fournisseur doit voir les informations tarifaires

Pour partager les informations tarifaires des CF via l'interface de collaboration fournisseur, vous devez définir l'option **Prix/montant de la commande fournisseur** sous l'onglet **Valeurs par défaut des commandes fournisseur** du compte fournisseur sur **Oui**. Ces informations tarifaires incluent le prix unitaire, les remises et les frais.

## <a name="working-with-pos-when-vendor-collaboration-is-used"></a>Utilisation des CF lors de l'utilisation de la collaboration fournisseur

### <a name="sending-a-po-to-a-vendor"></a>Envoi d'une CF à un fournisseur

Les CF sont préparés dans Supply Chain Management. Lorsqu'une CF a le statut **Approuvé**, vous l'envoyez au fournisseur en sélectionnant **Envoyer pour confirmation** sur la page **Commande fournisseur**. Le statut de la CF passe alors à **En cours de révision externe**. Une fois la CF soumise, le fournisseur peut la voir sur la page **Commandes fournisseur pour examen** dans l'interface de collaboration fournisseur. Le fournisseur peut alors accepter la CF, la refuser ou proposer des modifications. Le fournisseur peut également ajouter des commentaires pour communiquer des informations telles que des modifications à la CF. Si vous souhaitez attirer l'attention du fournisseur sur une nouvelle CF, vous pouvez également utiliser le système de gestion de l'impression pour l'envoyer par courrier électronique.

### <a name="confirmation-and-acceptance-of-a-po-by-a-vendor"></a>Confirmation et acceptation d'une CF par un fournisseur

Une fois qu'un fournisseur accepte une CF, celle-ci peut être confirmée automatiquement, ou elle doit être confirmée manuellement. Le comportement varie selon que le champ **Activation de la collaboration** est défini sur **Actif (la CF est confirmée automatiquement)** ou sur **Actif (la CF n'est pas confirmée automatiquement)** pour le fournisseur.

Le tableau suivant présente l'échange d'informations classique, selon la réponse du fournisseur lorsque vous envoyez une CF pour confirmation.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr>
<th>Réponse du fournisseur</th>
<th>Résultat</th>
</tr>
</thead>
<tbody>
<tr class="even">
<td>Le fournisseur <strong>accepte</strong> la commande, et Supply Chain Management est configuré pour confirmer automatiquement les CF acceptées par le fournisseur.</td>
<td>Le statut de la commande est mis à jour sur <strong>Confirmé</strong>. Si la commande ne peut pas être mise à jour pour une raison quelconque, la réponse du fournisseur est toujours enregistrée comme <strong>Accepté</strong>, mais le statut de la CF reste dans l&#39;état <strong>En cours de révision externe</strong>. 

La CF envoyée au fournisseur avec le statut <strong>En cours de révision externe</strong> est mise à jour avec les dates de livraison confirmées sur les lignes. Cette mise à jour lance une nouvelle version qui est automatiquement définie sur le statut <strong>Confirmé</strong>. Une fois la CF confirmée, elle apparaît dans l'interface de collaboration du fournisseur.</td>
</tr>
<tr class="odd">
<td>Le fournisseur <strong>accepte</strong> la commande, mais Supply Chain Management n&#39;est pas configuré pour confirmer automatiquement les CF acceptées par le fournisseur.</td>
<td>La réponse du fournisseur est enregistrée comme <strong>Accepté</strong>, mais le statut de la CF reste dans l'état <strong>En cours de révision externe</strong>.

La CF envoyée au fournisseur avec le statut <strong>En cours de révision externe</strong> est mise à jour avec les dates de livraison confirmées sur les lignes. Cette mise à jour lance une nouvelle version qui est automatiquement définie sur le statut <strong>En cours de révision externe</strong>. Vous pouvez ensuite confirmer manuellement la CF.</td>
</tr>
<tr class="even">
<td>Le fournisseur <strong>rejette</strong> la commande.</td>
<td>La réponse du fournisseur est enregistrée comme <strong>Rejeté</strong> et le statut de la CF reste dans l'état <strong>En cours de révision externe</strong>. Le rejet est reçu avec la note du fournisseur.</td>
</tr>
<tr class="odd">
<td>Le fournisseur <strong>accepte</strong> la commande avec des <strong>modifications</strong>. Les modifications sont suggérées au niveau de la ligne. Le fournisseur peut accepter ou refuser des lignes individuelles. Voici quelques autres modifications que le fournisseur peut proposer :
<ul>
<li>Modifier les dates ou les quantités.</li>
<li>Fractionnez des lignes pour différentes dates de livraison ou quantités.</li>
<li>Remplacez un article.</li>
</ul>
Le fournisseur ne peut pas modifier les informations sur les prix et les frais. Toutefois, il peut proposer ces modifications à l'aide de notes.</td>
<td>La réponse du fournisseur est enregistrée comme <strong>Accepté avec des modifications</strong>, mais le statut de la CF reste <strong>En cours de révision externe</strong>. Les statuts indiquent les types de modifications suggérées par le fournisseur. Pour plus d'informations sur la consommation automatique des modifications, consultez la section &quot;Mettre à jour la CF lorsqu'un fournisseur propose des modifications&quot; plus loin dans cette rubrique. </td>
</tr>
</tbody>
</table>

Vous pouvez utiliser l'espace de travail **Préparation de la commande fournisseur** pour surveiller les CF auxquelles le fournisseur a répondu. Cet espace de travail contient deux listes contenant les CF dont le statut est **En cours de révision externe** :

- Action requise pour « Fait l'objet d'une révision externe »
- Dans la révision externe en attente de réponse du fournisseur

### <a name="changing-a-po"></a>Modification d'une CF

Pour modifier une CF à laquelle un fournisseur a déjà répondu, vous devez envoyer une nouvelle version de la CF au fournisseur. La nouvelle CF aura un suffixe de version pour indiquer qu'il s'agit d'une version modifiée d'une CF qui a été précédemment envoyée. La page **Historique des confirmations de commandes fournisseur** vous permet, ainsi que vos fournisseurs, de suivre l'historique de chaque commande. La version précédemment confirmée d'une CF demeure dans la liste des CF confirmées jusqu'à ce qu'une nouvelle CF soit confirmée.

### <a name="canceling-a-po"></a>Annulation d'une CF

Lorsque vous annulez une CF, le statut passe à **Approuvé**. Vous devez retransmettre le bon de commande au fournisseur afin qu'il puisse confirmer ou rejeter l'annulation. Une fois l'annulation confirmée, la CF apparaît dans la liste des CF confirmées du fournisseur avec le statut **Annulé**.

### <a name="adding-attachments-to-a-po"></a>Ajouter des pièces jointes à une CF

Vous pouvez ajouter des pièces jointes telles que des fichiers, des images, et des notes à la CF à l'aide du système de gestion des documents. Les pièces jointes du type **Externe** sont visibles par le fournisseur lorsque vous envoyez la CF.

## <a name="updating-a-po-when-a-vendor-suggests-changes"></a>Mise à jour d'une CF lorsqu'un fournisseur propose des modifications

Si un fournisseur a répondu à une CF et proposé des modifications, l'étape suivante consiste à traiter la réponse.

Dans l'espace de travail **Préparation des commandes fournisseur**, dans la liste **Action requise pour « Fait l'objet d'une révision externe »**, vous pouvez identifier les CF qu'un fournisseur a accepté avec des modifications. Dans cette liste, vous pouvez également accéder à la réponse du fournisseur.

Dans une réponse, un fournisseur peut modifier les informations suivantes sur l'en-tête :
 
- Référence du document du fournisseur
- Mode de livraison
- Conditions de livraison
- Date de livraison confirmée

Le fournisseur peut également ajouter une note ou une pièce jointe.

Sur les lignes, le fournisseur peut modifier la quantité et les dates de livraison, ajouter des notes et des pièces jointes, refuser une ligne, remplacer une ligne par un autre produit qui est saisi comme du texte et fractionner une ligne en plusieurs livraisons. Le statut d'une ligne varie, selon les modifications suggérées par le fournisseur :
    
- **Accepter avec les modifications**
- **Rejeté**
- **Remplacé** – Dans ce cas, une ligne supplémentaire est ajoutée avec le statut **Remplacer**.
- **Confirmée**
- **Fractionner en plan de livraison** – Dans ce cas, des lignes supplémentaires sont ajoutées avec le statut **Lignes de plan de livraison**.

Si une ligne n'est pas modifiée, son statut est **Accepté**.

Dans la réponse, les statuts de la ligne indiquent les types de modifications effectuées par le fournisseur. En outre, tous les champs modifiés s'affichent en gras pour vous aider à identifier les modifications.

Vous pouvez mettre à jour une CF en sélectionnant **Traiter la mise à jour de la CF** dans la réponse ou sur une ligne à la fois. Le champ **La mise à jour de la CF a-t-elle été réalisée ?** dans l'en-tête et les lignes indique si le système a traité l'en-tête ou les lignes pour mettre à jour la CF avec les modifications provenant de la réponse. Vous pouvez exécuter l'action **Traiter la mise à jour de la CF** une seule fois par en-tête ou ligne.

Toutes les modifications proposées ne peuvent pas être mises à jour sur une CF. Seules les mises à jour sur l'en-tête et les mises à jour des dates et des quantités sur les lignes peuvent être automatiquement mises à jour sur la CF. Pour les autres modifications, vous devez mettre à jour manuellement la CF. Dans ce cas, la valeur du champ **La mise à jour de la CF a-t-elle été traitée ?** est **Mise à jour manuelle**. Par exemple, si un fournisseur propose de fractionner une ligne en plan de livraison, cette modification doit être effectuée manuellement.

Chaque ligne qui a le statut **Accepté** a une date de livraison confirmée. Lorsque vous exécutez l'action **Mise à jour du processus CF**, cette date est mise à jour sur la CF. Les notes et les pièces jointes ne sont pas automatiquement transférées vers la CF actuelle. En outre, les accords commerciaux ne sont pas réévalués sur les lignes de la CF lorsque vous mettez à jour la CF actuelle via l'action **Traiter la mise à jour de la CF**.

## <a name="po-statuses-and-versions"></a>Statuts et versions de la CF

Cette section décrit les différents statuts d'une CF jusqu'au moment où elle est confirmée. Elle décrit également quand les nouvelles versions d'une CF sont accessibles au fournisseur. Le comportement varie, selon que vous utilisez la gestion des modifications pour les CF. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Versions et statuts si vous n'utilisez pas la gestion des modifications

Le tableau suivant présente un exemple des modifications de statut et de version qui peuvent s'appliquer à une CF.

| Action | Statut et version |
|--------|--------------------|
| La première version de la CF est créée dans Supply Chain Management. | Le statut est **Approuvé**. |
| La CF est envoyée au fournisseur. | Une version est enregistrée dans l'interface de collaboration fournisseur et le statut devient **En cours de révision externe**. |
| Le fournisseur envoie une réponse **Acceptée avec des modifications**. | Le statut est toujours **En cours de révision externe**. |
| Vous apportez certaines modifications demandées par le fournisseur. | Le statut passe à **Approuvée**. |
| Vous envoyez la nouvelle version de la CF au fournisseur. | Une nouvelle version est enregistrée dans l'interface de collaboration fournisseur et le statut devient **En cours de révision externe**. |
| Le fournisseur accepte la nouvelle version de la CF. | Le statut est toujours **En cours de révision externe** à moins que le compte fournisseur soit configuré pour définir automatiquement les CF sur l'état **Confirmé** lorsque le fournisseur les accepte. |

Les fournisseurs ne doivent pas confirmer une CF à l'aide de l'interface de collaboration fournisseur. Ils peuvent également envoyer un message électronique ou communiquer leur acceptation d'une CF via d'autres canaux. Vous pouvez ensuite confirmer manuellement la commande. Dans ce cas, vous recevez un avertissement indiquant que la commande est confirmée même s'il n'y a aucune réponse du fournisseur. La CF apparaît alors dans l'historique de confirmation sous la forme d'une commande confirmée en cours qui n'a pas de réponse. À ce stade, le fournisseur n'a plus l'option de confirmer ou de rejeter la CF.

> [!NOTE]
> La version de CF disponible pour d'autres processus dans Supply Chain Management est toujours la version la plus récente, même si cette version n'a pas encore été enregistrée dans l'interface de collaboration fournisseur.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Versions et statuts si vous utilisez la gestion des modifications

Si la gestion des modifications est activée pour les CF, les CF passent par un workflow d'approbation pour atteindre le statut **Approuvé**. Ce processus n'est pas visible au fournisseur.

Le tableau suivant présente un exemple des modifications de statut et de version qui peuvent s'appliquer à une CF lorsque la gestion des modifications est activée. Une version est enregistrée lorsque la CF est approuvée et non lorsque la CF est envoyée au fournisseur ou confirmée.

| Action | Statut et version |
|--------|--------------------|
| La première version de la CF est créée dans Supply Chain Management. | Le statut est **Brouillon**. |
| La CF est soumise au processus d'approbation. (Il s'agit d'un processus interne dans lequel le fournisseur n'est pas impliqué.) | Le statut passe de **Brouillon** à **En cours de révision** à **Approuvé** si la CF n'est pas rejetée au cours du processus d'approbation. La CF approuvée est enregistrée comme une version. | 
| La CF est envoyée au fournisseur. | La version est enregistrée dans l'interface de collaboration fournisseur et le statut devient **En cours de révision externe**. |
| Vous effectuez les modifications demandées par le fournisseur, manuellement ou à l'aide de l'action **Traiter le mise à jour de la CF** dans la réponse pour mettre à jour la CF. | Le statut redevient **Brouillon**. |
| La CF est à nouveau soumise au processus d'approbation. | Le statut passe de **Brouillon** à **En cours de révision** à **Approuvé** si la CF n'est pas rejetée au cours du processus d'approbation. Sinon, le système peut être configuré de sorte que des modifications de champ spécifiques ne nécessitent pas de nouvelle approbation. Dans ce cas, le statut est d'abord modifié en **Brouillon** avant d'être automatiquement mis à jour sur **Approuvé**. La CF approuvée est enregistrée comme une nouvelle version. |
| Vous envoyez la nouvelle version de la CF au fournisseur. | La nouvelle version est enregistrée dans l'interface de collaboration fournisseur et le statut devient **En cours de révision externe**. |
| Le fournisseur approuve la nouvelle version de la CF. | Le statut devient **Confirmé** automatiquement ou lorsque vous recevez la réponse du fournisseur, puis vous confirmez la CF. |

## <a name="sharing-information-about-consignment-inventory"></a>Partage des informations sur le stock de consignation

Si vous utilisez le stock de consignation, les fournisseurs peuvent utiliser l'interface de collaboration fournisseur pour afficher les informations sur les pages suivantes :

- **Commandes fournisseur consommant le stock de consignation** – Les CF pour le stock de consignation sont générées lorsque la propriété du stock passe du fournisseur à votre société. Un accusé de réception de marchandises est validé en même temps. Ces CF de consignation sont affichées uniquement sur la page **Commandes fournisseur consommant le stock de consignation**. Elles ne sont pas incluses sur la page **Toutes les commandes fournisseur confirmées** du module **Collaboration fournisseur**.
- **Produits reçus du stock de consignation** – Cette page affiche la liste de toutes les transactions dont la propriété des produits a été transférée du fournisseur à votre société. Les fournisseurs peuvent utiliser ces informations pour facturer le client.
- **Stock de consignation disponible** – Cette page affiche le stock de consignation disponible appartenant au fournisseur qui a été reçu dans votre entrepôt.

## <a name="working-with-rfqs-when-you-use-vendor-collaboration"></a>Utilisation des appels d'offre avec la collaboration fournisseur

Cette section décrit les interactions entre les clients et les fournisseurs lors du processus d'appel d'offre. Elle décrit également comment les informations sont communiquées aux fournisseurs. Pour obtenir une vue d'ensemble de la prise en charge du processus d'appel d'offre, voir [Vue d'ensemble des appels d'offre](request-quotations.md).

### <a name="alternates-attachments-amendments-and-returns"></a>Alternatives, pièces jointes, avenants et retours

- **Alternatives** – Dans l'en-tête d'un dossier d'appel d'offre, vous pouvez indiquer que les alternatives sont autorisées pour les lignes d'article hors catalogue. Lorsque les alternatives sont activées, les fournisseurs peuvent ajouter une ligne alternative pour chaque ligne demandée.
- **Pièces jointes** – Des pièces jointes peuvent être ajoutées au niveau de l'en-tête et de la ligne d'un dossier d'appel d'offre. Les pièces jointes peuvent être classifiées comme internes ou externes. Les pièces jointes internes ne peuvent être visualisées que par le client, alors que les fournisseurs peuvent visualiser les pièces jointes externes une fois qu'elles sont envoyées.

    Les fournisseurs peuvent également ajouter des pièces jointes dans leur réponse à une offre. Ces pièces jointes peuvent être visualisées par le client une fois qu'un fournisseur envoie la réponse à une offre. Les pièces jointes ajoutées par les fournisseurs sont toujours classées comme externes. Pour accéder à une pièce jointe soumise par un fournisseur avec une offre, sélectionnez **Pièces jointes à l'offre** ou **Pièces jointes à la ligne d'offre**.
    
    Pour ouvrir les pièces jointes envoyées avec le dossier d'appel d'offre, utilisez le symbole de trombone de gestion des documents dans la réponse.

- **Avenants** – Lorsqu'une modification est finalisée, les réponses existantes à l'offre sont supprimées afin qu'elles puissent être remplacées par les valeurs mises à jour. Les informations telles que le prix et la quantité de ligne dans les réponses précédentes à l'offre peuvent être affichées via les journaux du dossier d'appel d'offre.

    Pour appliquer le processus de modification, dans la page **Paramètres d'approvisionnement**, sous l'organisateur **Appel d'offre**, définissez l'option **Verrouiller les appels d'offre lorsqu'ils sont envoyés** sur **Oui**. (Cette option est définie et requise pour le secteur public.)

- **Retours** – Si un fournisseur a soumis une offre, mais des informations supplémentaires ou modifiées sont requises pour le dossier d'appel d'offre, le client peut retourner l'offre au fournisseur. Les données de l'offre précédemment envoyée sont conservées, et le fournisseur peut apporter les modifications demandées sans avoir à redémarrer le processus d'offre.

## <a name="public-sector-extensions"></a>Extensions du secteur public

Pour le secteur public, la fonctionnalité étendue permet d'envoyer un dossier d'appel d'offre aux fournisseurs et de le publier. Lorsque vous publiez un appel d'offre, toute personne qui demande les informations peut visualiser le travail qui est conforme à la plupart des réglementations du secteur public. Tout le travail disponible est reflété dans la page de liste **Appels d'offre publiés en cours**, et les appels d'offre annulés, en attente ou attribués peuvent être affichés sur la page de liste **Appels d'offre publiés clôturés**. Ces documents peuvent également être visualisés sur un site externe à Supply Chain Management via des intégrations avec les entités de données suivantes :

- Appels d'offre publiés
- Ligne des appels d'offre publiés
- Pièces jointes aux en-têtes des appels d'offre publiés

Ces entités permettent aux personnes qui ne sont pas des utilisateurs mis en service dans Supply Chain Management, mais qui ont un accès anonyme au site externe, d'afficher le travail disponible et clôturé. En outre, la fonctionnalité étendue dans **Envoyer et publier** permet à l'utilisateur qui configure les paramètres du processus d'appel d'offre de définir un modèle d'e-mail. Ensuite, lorsque le professionnel de l'approvisionnement crée le dossier d'appel d'offre, il doit sélectionner le modèle d'e-mail pour envoyer les informations requises aux fournisseurs dans le dossier d'appel d'offre. 

L'utilisateur qui configure les paramètres pour le processus d'appel d'offre peut créer plusieurs modèles d'e-mail. Ces modèles d'e-mail peuvent contenir le texte statique et les jetons de remplacement suivants. Les jetons seront remplacés par des valeurs contextuelles lorsqu'un e-mail est créé.

- %RFQCase%
- %RFQCaseName%
- %bidType%
- %inviteOnly%
- %expiryDateTime%
- %requester%
- %requestingDepartment%
- %accountnum%
- %todaysdate%
- %createddate%

Si une modification est requise et envoyée après l'envoi de l'appel d'offre, l'appel d'offre est renvoyé à tous les fournisseurs invités. Le document publié est également mis à jour sur la page **Appels d'offre publiés en cours**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]