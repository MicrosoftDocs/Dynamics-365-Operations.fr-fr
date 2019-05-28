---
title: Page de liste des transactions client
description: Cette rubrique fournit des informations sur la page de la liste des transactions client pour Microsoft Dynamics 365 for Finance and Operations.
author: mikefalkner
manager: aolson
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: b9936a66cc8c8abb24601dae91dcfca77e4f58a4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1561081"
---
# <a name="customer-transactions-list-page"></a>Page de liste des transactions client

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Afficher les règlements

Le bouton **Afficher les règlements** dans le volet Actions permet d'accéder rapidement à l'historique des règlements et à des informations détaillées sur la transaction de règlement. Vous pouvez également afficher des transactions supplémentaires associées à la transaction sélectionnée, soit parce qu'elles faisaient partie du même règlement, soit parce qu'il s'agit de paiements créés dans le même journal des paiements.

1. Sélectionnez **Comptabilité client \> Tous les clients**.
2. Sélectionnez un client doté de transactions puis, dans le volet Actions, sous l'onglet **Client**, sélectionnez **Transactions**.
3. Sélectionnez une transaction à rechercher puis, dans le volet Actions, sélectionnez **Afficher les règlements**.

    La boîte de dialogue **Afficher les règlements** s'ouvre et affiche la transaction sélectionnée et tous les documents réglés qui lui sont associés. Cette boîte de dialogue ressemble à la vue de l'historique des règlements, mais elle comprend tous les documents associés.

4. Dans la boîte de dialogue, vous pouvez effectuer plusieurs tâches. Sélectionnez un ou plusieurs N° documents, puis sélectionnez l'un des boutons suivants :

    - **Vue associée** – Permet d'afficher toutes les transactions du journal des paiements et toutes les transactions du grand livre pour le client qui ont été créées dans les journaux dans lesquels les documents affichés dans la liste ont été créés. Par exemple, si un paiement est affiché, tous les paiements du journal des paiements dans lesquels il a été créé, seront affichés. Si une facture ou un paiement est affiché et s'il a été créé dans un grand livre, tous les documents du grand livre dans lequel il a été créé seront affichés. Tous les règlements associés à la liste des documents apparaissent également. Lorsque vous affichez les paiements associés, le libellé de ce bouton est remplacé par **Afficher les règlements**. Sélectionnez **Afficher les règlements** pour afficher uniquement les transactions disponibles lorsque vous avez ouvert pour la première fois la boîte de dialogue **Afficher les règlements**.
    - **Afficher l'historique** – Affiche l'historique des règlements pour les N° documents. Sélectionnez **Fermer** pour fermer la boîte de dialogue.
    - **Afficher la comptabilité** – Affiche tous les N° documents associés aux documents sélectionnés. Sélectionnez **Fermer** pour fermer la boîte de dialogue.
    - **Exporter** – Exportez les N° documents sélectionnés vers Microsoft Excel.
    - **Régler les transactions** – Ce bouton apparaît uniquement si le document initial sélectionné n'était pas totalement réglé. Lorsque vous sélectionnez ce bouton, la boîte de dialogue **Afficher les règlements** s'ouvre pour vous permettre de sélectionner des transactions à régler.
    - **Annuler les règlements** – Ce bouton apparaît uniquement si le document initial sélectionné était totalement réglé. Lorsque vous sélectionnez ce bouton, la boîte de dialogue **Annuler les règlements** s'affiche pour vous permettre d'annuler les règlements effectués pour ce document.

## <a name="global-transactions"></a>Transactions globales

Le bouton **Transactions globales** s'affiche également sur la page de liste **Transactions client**. Ce bouton vous permet d'afficher toutes les transactions d'un client dans toutes les entités juridiques. La page de liste **Transactions client** affiche les transactions uniquement pour les entités juridiques auxquelles l'utilisateur a accès, selon ses paramètres de sécurité.

La page de liste affiche toutes les transactions des clients qui ont le même ID de partie que le client par lequel vous avez commencé. Par exemple, si le client US-001 dans une entité juridique a le même ID de partie que le client DE-001 dans une autre entité juridique, toutes les transactions des deux ID client sont affichées.

Les menus de la page de liste **Transactions client** varient, selon l'entité juridique pour la transaction. Par exemple, si une fonctionnalité n'est disponible que pour les entités juridiques suisses, les options de menu associées à cette fonctionnalité n'apparaissent que lorsqu'une transaction suisse est sélectionnée.

Pour accéder à la fonctionnalité, procédez comme suit.

1. Sélectionnez **Comptabilité client \> Tous les clients**.
2. Sélectionnez un client puis, dans le volet Actions, sous l'onglet **Client**, dans le groupe **Transactions**, sélectionnez **Transactions globales**.

## <a name="more-transaction-filters"></a>Autres filtres de transaction 

Le filtre d'affichage des transactions en cours a été remplacé par un nouveau filtre qui vous permet d'afficher d'autres combinaisons de transactions. Les options suivantes sont disponibles dans le champ **Afficher** :

- **Tous** – Affiche toutes les transactions pour les clients sélectionnés (en cours et clôturées).
- **Clôturé** – Affiche uniquement les transactions qui ont été totalement réglées et clôturées.
- **En cours** – Affiche uniquement les transactions qui n'ont pas été totalement réglées.
- **Transactions en cours et clôturées à la date indiquée ou ultérieurement** – Affiche uniquement les transactions n'ayant pas été complètement réglées ou après une date que vous spécifiez. Lorsque vous sélectionnez cette option, vous pouvez modifier la date affichée en regard du filtre. Les transactions dont la valeur **Dernière date de règlement** est la date ou après la date spécifiée sont répertoriées dans la liste, même si ces transactions sont totalement réglées à la date actuelle. Toutefois, le solde représente les soldes à la date actuelle, et non à la date sélectionnée.

Activez la case à cocher **Masquer les réévaluations de devise** pour masquer les transactions de conversion de devises.

## <a name="modify-due-dates-and-discount-dates"></a>Modifier les dates d'échéance et les dates d'escompte

Vous pouvez mettre à jour les dates d'échéance et les dates d'escompte pour les transactions client en cours. Dans la version 8.1, vous pouvez maintenant ajouter des dates d'échéance à la page de liste **Transactions client**. En cliquant sur la date d'échéance dans la page de liste **Transactions client**, vous pouvez également modifier les dates d'échéance, les dates d'escompte, les conditions de paiement et les conditions d'escompte de règlement dans la boîte de dialogue **Mettre à jour la date d'échéance et les dates d'escompte de règlement**.

### <a name="activate-the-feature"></a>Activer la fonctionnalité

Pour ajouter des dates d'échéance à la page de liste **Transactions client** et modifier les paramètres de paiement pour une transaction à l'aide de la boîte de dialogue **Mettre à jour la date d'échéance et les dates d'escompte de règlement**, procédez comme suit.

1. Sélectionnez **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.
2. Sous l'onglet **Règlements**, définissez l'option **Afficher la date d'échéance et autoriser la modification** sur **Oui**.
3. Pour activer cette fonctionnalité, de nouveaux champs ont été ajoutés aux transactions client. Ces champs seront renseignés lorsqu'une nouvelle transaction sera terminée. Ils seront également renseignés lorsque vous ouvrirez la boîte de dialogue **Mettre à jour la date d'échéance et les dates d'escompte de règlement**. Lorsque vous définissez l'option **Afficher la date d'échéance et autoriser la modification** sur **Oui**, la boîte de dialogue **Mettre à jour les informations de paiement** s'affiche.  Pour mettre à jour les transactions existantes immédiatement, sélectionnez **Mettre à jour toutes les transactions existantes**. Sinon, pour renseigner les champs uniquement pour les nouvelles transactions, sélectionnez **Poursuivre sans la mise à jour**.

La date d'échéance est maintenant ajoutée à la page de liste **Transactions client**, afin que vous puissiez facilement modifier la date d'échéance et les dates d'escompte de règlement pour les transactions.

### <a name="modify-the-payment-settings"></a>Modifier les paramètres de paiement

La page de liste **Transactions client** affiche toutes les transactions d'un client. Lorsque vous sélectionnez la date d'échéance d'une transaction, la boîte de dialogue **Mettre à jour la date d'échéance et les dates d'escompte de règlement** s'affiche. Cette boîte de dialogue affiche la date de référence pour les calculs de la date d'échéance et de l'escompte, la date d'échéance, les conditions de paiement, les conditions d'escompte de règlement et les dates d'escompte de règlement.

Chaque champ a un impact différent sur la transaction lorsque vous le modifiez :

- **Modifier la date de référence** - La date d'échéance et les dates d'escompte sont modifiées comme si la date de référence était la date du document.
- **Modifier la date d'échéance** - Seule la date d'échéance est modifiée.
- **Modifier les dates d'escompte** - Seules les dates d'escompte sont modifiées.
- **Modifier les conditions de paiement** - La date d'échéance est modifiée, selon la date de référence et les conditions de paiement.
- **Modifier les conditions d'escompte de règlement** - Les escomptes de règlement sont modifiés, selon la date de référence et les conditions d'escompte de règlement.

Lorsque vous avez terminé de modifier les paramètres de paiement, cliquez sur **Fermer** pour enregistrer vos modifications.
