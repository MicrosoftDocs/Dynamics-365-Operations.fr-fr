---
title: Collaboration fournisseur avec des clients
description: Cette rubrique décrit comment utiliser la collaboration fournisseur pour utiliser des CF et surveiller le stock de consignation.
author: TaylorVH
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart, VendVendorProfileCard, PurchVendorPortalAllResponse, PurchVendorPortalPendingResponsesPart, PurchVendorPortalResponses, PurchVendorPortalConfirmedOpenOrdersPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: v-savanh
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 9ad7f116f979d571a5e34eee67beb7218a271522
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2021
ms.locfileid: "7777592"
---
# <a name="vendor-collaboration-with-customers"></a>Collaboration fournisseur avec des clients

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment utiliser la collaboration fournisseur avec les clients dans Microsoft Dynamics 365 Supply Chain Management. Les fournisseurs peuvent effectuer une série de processus d’entreprise dans les espaces de travail suivants :

- **Confirmation de la commande fournisseur** – Permet de surveiller les commandes fournisseur et d’y répondre.
- **Offre du fournisseur** – Permet d’afficher les appels d’offre et d’y répondre en saisissant des offres.
- **Informations fournisseur** – Permet d’afficher et de mettre à jour les données principales du fournisseur.
- **Facturation** – Permet d’utiliser les factures. Cette rubrique ne couvre pas l’espace de travail **Facturation**. Pour plus d’informations sur cet espace de travail, voir [Espace de travail de facturation de collaboration fournisseur](../../finance/accounts-payable/vendor-portal-invoicing-workspace.md).

Les fournisseurs peuvent également surveiller les informations sur le stock de consignation.

## <a name="working-with-pos-in-the-purchase-order-confirmation-workspace"></a>Utilisation des CF dans l’espace de travail Confirmation de la commande fournisseur

L’espace de travail **Confirmation de la commande fournisseur** vous permet de répondre aux commandes fournisseur (CF) qui vous ont été envoyées pour révision. Il permet également d’afficher des informations sur les CF en attente d’une action du client et les CF qui ont été confirmées, mais qui sont toujours en cours.

Il existe trois listes dans l’espace de travail **Confirmation de commande fournisseur** :

- **Commandes fournisseur pour examen** – Cette liste affiche les CF qui vous ont été soumises et qui sont en attente d’une réponse de votre part. Lorsque vous répondez, la CF disparaît de la liste. Si le client vous envoie une nouvelle version de la CF avant que vous ayez répondu à la précédente version, seule la dernière version s’affiche.
- **En attente d’une action du client** - Cette liste affiche toutes les CF auxquelles vous avez répondu, mais qui n’ont pas encore été confirmées par le client. Si vous acceptez une CF, vous pouvez la surveiller dans cette liste jusqu’à ce que son statut passe à **Confirmé**. Si vous refusez une CF ou que vous l’acceptez avec des modifications, vous pouvez la surveiller ici jusqu’à ce que le client envoie une nouvelle version.
- **Commandes fournisseur confirmées en cours** – Cette liste affiche toutes les CF de votre compte ayant le statut **Confirmé**. Lorsque des produits ou services sont entièrement reçus par rapport à la CF, la CF disparaît de la liste.

Les pages suivantes permettent d’utiliser les CF :

- **Commandes fournisseur pour examen** – Cette page contient les mêmes informations que la liste **Commandes fournisseur pour examen** dans l’espace de travail. Consultez la description plus haut dans cette rubrique.
- **Historique des confirmations de commandes fournisseur** – Cette page contient toutes les CF et toutes les versions de CF qui ont été envoyées au fournisseur. Elle contient également les réponses qui ont été retournées par le fournisseur.
- **Commandes fournisseur confirmées en cours** – Cette page contient les mêmes informations que la liste **Commandes fournisseur confirmées en cours** dans l’espace de travail. Consultez la description plus haut dans cette rubrique.
- **Toutes les commandes fournisseur confirmées** – Cette page contient toutes les CF qui ont été confirmées. Les CF affichés sur cette page comprennent les CF où les produits ou services ont été reçus. Vous pouvez utiliser cette liste pour surveiller les CF pour lesquelles vous pouvez envoyer des factures.

### <a name="responding-to-pos"></a>Réponse aux CF

Les CF que le client vous envoie pour examen s’affichent dans l’espace de travail **Confirmation de la commande fournisseur** et dans la page **Commandes fournisseur pour examen**. Après avoir ouvert une CF, vous pouvez l’accepter, la rejeter ou l’accepter avec des modifications. Des documents peuvent être joints dans l’en-tête de la CF ou sur des lignes individuelles. En outre, vous pouvez associer des informations à votre réponse sur l’en-tête de la CF ou des lignes individuelles. Par exemple, vous pouvez proposer un article de remplacement pour l’une des lignes.

Vous pouvez prévisualiser et imprimer la CF comme fichier PDF à l’aide de l’option **Aperçu/Imprimer**. Vous pouvez également utiliser l’action **Afficher les dimensions** pour masquer ou afficher les colonnes de dimension suivantes : **Site**, **Entrepôt**, **Couleur**, **Taille**, **Style** et **Configuration**. 

Si vous utilisez l’option **Accepter avec des modifications**, vous pouvez accepter ou rejeter des lignes séparément. Vous pouvez également apporter les modifications suivantes aux lignes :

- Modifiez les dates ou les quantités. Pour mettre à jour la date de livraison confirmée sur toutes les lignes, utilisez l’option **Mettre à jour la date de livraison** sur l’en-tête de la CF.
- Fractionnez des lignes pour différentes dates de livraison ou quantités.
- Remplacez un article. Dans la section **Détails de ligne**, entrez une description d’article et le numéro d’article dans le champ **Externe**.

Vous ne pouvez pas modifier les informations tarifaires ou les frais, mais vous pouvez utiliser des notes pour faire des suggestions pour ces modifications.

Si le client vous envoie une nouvelle version d’une CF, celle-ci a un suffixe de version pour indiquer qu’il s’agit d’une version modifiée d’une CF qui a été précédemment envoyée. La page **Historique des confirmations de commandes fournisseur** vous permet de suivre l’historique de chaque commande.

## <a name="monitoring-consignment-inventory"></a>Surveillance du stock de consignation

Si vous utilisez le stock de consignation, vous pouvez utiliser l’interface de collaboration fournisseur pour afficher les informations sur les pages suivantes :

- **Commandes fournisseur consommant le stock de consignation** - Les CF pour le stock de consignation sont générées lorsqu’un client prend la propriété du stock. Ces CF de consignation ne sont affichées que sur cette page. Elles ne sont pas incluses sur la page **Toutes les commandes fournisseur confirmées**.
- **Produits reçus du stock de consignation** – Cette page affiche la liste de toutes les transactions dont la propriété des produits a été transférée à la société qui consomme le stock. Ces informations vous permettent de facturer le client.
- **Stock de consignation disponible** – Cette page affiche le stock de consignation disponible appartenant à votre société, mais qui est disponible dans l’entrepôt du client.

## <a name="working-with-rfqs-in-the-vendor-bidding-workspace"></a>Utilisation des appels d’offre dans l’espace de travail Offre du fournisseur

L’espace de travail **Offre du fournisseur** permet d’afficher les appels d’offre auxquels votre société a été invitée à répondre. Vous pouvez également répondre aux appels d’offre. 

L’espace de travail affiche également tous les appels d’offre que vous avez perdus ou gagnés. En outre, si le système est configuré pour le secteur public, l’espace de travail affiche les appels d’offre qui sont accessibles au public.

### <a name="viewing-rfqs"></a>Affichage des appels d’offre

Ouvrez l’espace de travail **Offre du fournisseur** pour accéder aux informations suivantes :

- Sélectionnez **Nouvelles invitations à une offre** pour afficher les appels d’offre auxquels votre société a été invitée à répondre. Vous pouvez alors afficher un appel d’offre et démarrer le processus d’offre. Vous pouvez également voir les appels d’offre modifiés pour lesquels un nouvelle offre doit être soumise.
- Sélectionnez **Offres renvoyées** pour afficher les appels d’offre que le client vous a renvoyés afin que vous puissiez fournir d’autres informations ou mettre à jour l’offre.
- Sélectionnez **Offres en cours** pour afficher les appels d’offre sur lesquels vous ou un représentant de votre société travaillez, mais qui n’ont pas encore été envoyés.
- Sélectionnez **Offres attribuées** pour voir quand le client a attribué au moins une ligne de votre offre.
- Sélectionnez **Offres perdues** pour afficher les offres où toutes les lignes ont été rejetées.
- Sélectionnez le lien **Appels d’offre** pour afficher la liste de toutes les invitations à un appel d’offre du fournisseur ainsi que les offres qui ont été soumises. La page **Appels d’offre** répertorie tous les appels d’offre auxquels un fournisseur a participé. Vous pouvez effectuer une recherche par statut.
- Sélectionnez le lien **Offres refusées** pour afficher la liste de tous les appels d’offre où la personne à contacter chez le fournisseur a refusé de faire une offre.

### <a name="working-with-rfqs-that-are-publicly-available"></a>Utilisation des appels d’offre accessibles au public

Les personnes qui travaillent dans le secteur public peuvent afficher les appels d’offre en cours et arrivés à expiration qui sont accessibles au public.

- Sélectionnez le lien **Appels d’offre publiés en cours** pour afficher la liste des appels d’offre en cours qui sont accessibles au public. Un appel d’offre en cours est un appel d’offre qui n’a pas encore expiré. Vous pouvez rechercher la date et l’heure d’expiration sur l’en-tête de l’appel d’offre.

    Si vous avez été invité pour faire une offre, vous pouvez rechercher le même appel d’offre sur la page **Nouvelles invitations à une offre**. Vous souhaitez parfois faire une offre pour un appel d’offre en cours, mais vous n’y avez pas été invité. Dans ce cas, vous pouvez vous inviter vous-même, à condition que le client ait activé l’auto-invitation pour le dossier d’appel d’offre.

    Améliorer l’accessibilité du lien **Ouvrir les appels d’offre publiés** en activant la fonctionnalité **Afficher le lien "Ouvrir les appels d’offre publiés" sous forme de vignette**. Cette fonctionnalité convertit le lien en vignette et le déplace vers un emplacement bien en vue, afin qu’il soit facile à trouver. (Depuis la version 10.0.21 de Supply Chain Management, cette fonctionnalité est activée par défaut.)

- Sélectionnez le lien **Appels d’offre publiés clôturés** pour afficher la liste des appels d’offre clôturés qui sont accessibles au public. Un appel d’offre clôturé est un appel d’offre qui a expiré. Vous pouvez rechercher la date et l’heure d’expiration sur l’en-tête de l’appel d’offre.

    Un appel d’offre clôturé affiche toutes les offres du fournisseur jusqu’au niveau de la ligne. Comme les offres sont attribuées ou refusées, ces informations apparaissent dans l’appel d’offre clôturé. Les pièces jointes incluses dans l’offre sont également disponibles.

> [!NOTE]
> Cette fonctionnalité n’est disponible que si la configuration du secteur public est activée.

### <a name="bidding"></a>Offre

- Cliquez sur **Offre** pour faire une offre pour un appels d’offre.

    Lorsque la modification est activée pour les champs d’offre sur les en-têtes et les lignes d’un appel d’offre, vous pouvez entrer votre offre directement dans la grille de ligne. Vous devez également tenir compte des informations supplémentaires sur l’offre qui doivent être ajoutées dans les détails de la ligne.

    Lorsque vous commencez à travailler sur une offre, celle-ci s’affiche dans la section **Offres en cours**.

    À tout moment avant la date d’expiration, vous pouvez enregistrer une offre. Vous pouvez ensuite revenir ultérieurement pour finaliser et soumettre l’offre. Après avoir soumis une offre, vous pouvez la rappeler et la mettre à jour jusqu’à la date d’expiration.

- Sélectionnez **Réinitialiser à partir de l’appel d’offre** pour réinitialiser les données saisies pour une offre et rétablir l’appel d’offre d’origine. Vous pouvez réinitialiser l’en-tête ou la ligne.
- Sélectionnez **Ajouter une alternative** ou **Supprimer l’alternative** dans la grille de ligne pour utiliser les alternatives.

    Certains appels d’offre autorisent les offres alternatives. Vous pouvez spécifier des offres alternatives uniquement pour les lignes de type **Catégorie**, car des articles spécifiques ne peuvent pas être ajoutés en tant qu’alternatives. 

- Sélectionnez **Pièce jointe à un appel d’offre** ou **Pièce jointe à des lignes d’appel d’offre** pour ouvrir une pièce jointe que le client a ajoutée à un appel d’offre. Sélectionnez **Pièces jointes à l’offre** ou **Pièces jointes à la ligne d’offre** pour télécharger les pièces jointes à l’offre.

    Vous devrez peut-être répondre à des questionnaires avant d’être autorisé à soumettre une offre.

- Sélectionnez **Refuser** si vous ne souhaitez pas faire une offre. Après avoir sélectionné **Refuser**, vous ne pouvez pas rappeler l’action et saisir une offre.

Si un appel d’offre est modifié, vous devez saisir une nouvelle offre. Vous trouverez des informations sur l’avenant dans l’onglet **Avenants** de la page d’appel d’offre. Les appels d’offre modifiés s’affichent sur la page **Nouvelles invitations à un appel d’offre**.

## <a name="accessing-vendor-master-data-in-the-vendor-information-workspace"></a>Accès aux données principales du fournisseur dans l’espace de travail Informations fournisseur

En tant que fournisseur, vous pouvez accéder à une partie des informations gérées par le client dans l’enregistrement des données principales du fournisseur. Par conséquent, vous pouvez tenir à jour les informations. Pour mettre à jour les informations, vous devez disposer d’un rôle administrateur fournisseur (externe).

Les informations accessibles sont le nom du fournisseur, les adresses, les informations de contact, les personnes à contacter et leurs informations de contact, les numéros d’identification, les numéros d’identification fiscale, les catégories d’approvisionnement dans lesquelles le fournisseur est agréé pour vendre au client et les informations sur les certifications.

## <a name="additional-resources"></a>Ressources supplémentaires

[Gérer les utilisateurs de la fonctionnalité de collaboration fournisseur](manage-vendor-collaboration-users.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]