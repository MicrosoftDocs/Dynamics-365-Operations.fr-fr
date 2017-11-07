---
title: "Comptabilité client dans le secteur public"
description: "Cette rubrique décrit la fonctionnalité de Comptabilité client disponible pour le secteur public."
author: rschloma
manager: AnnBe
ms.date: 08/07/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustInvoiceJournal, CustParameters, CustTradingPartnerCode
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 26281
ms.assetid: a411ec87-a209-471c-a141-5f5a92f2e45e
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c207f4982872b7c620ef4fa8abb2dc83d6fc0e56
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="accounts-receivable-in-the-public-sector"></a>Comptabilité client dans le secteur public

[!include[banner](../includes/banner.md)]


Cette rubrique décrit la fonctionnalité de Comptabilité client disponible pour le secteur public.

<a name="how-do-i-set-accounts-receivable-parameters-for-the-public-sector"></a>Comment définir les paramètres de comptabilité client pour le secteur public ?
------------------------------------------------------------------

La plupart des paramètres de comptabilité client sont définis de la même manière si vous êtes dans le secteur public ou le secteur privé. Toutefois, les paramètres requis pour les classifications de facturation et les codes facturation sont utilisés uniquement par le secteur public. Pour plus d'informations, voir [Classifications de facturation et codes facturation dans le secteur public](billing-classifications-billing-codes-public-sector.md).

-   Pour activer l'utilisation des classifications de facturation et des codes facturation, dans la section **Général**, dans l'organisateur **Paramétrage des ventes**, sélectionnez **Utiliser les classifications de facturation**.
-   Pour octroyer la priorité au règlement des factures financières, voir les paramètres requis dans [Priorité de règlement dans le secteur public](settlement-priority-public-sector.md) et [Factures financières dans le secteur public](free-text-invoices-public-sector.md).
-   Pour utiliser les codes facturation avec la comptabilité de projet, sélectionnez l'option permettant d'afficher les champs associés au projet dans les factures financières. Lorsque vous procédez ainsi, deux choses se produisent :
    -   Les champs associés au projet sont affichés à la fois dans les factures financières et les codes facturation.
    -   Le compte général associé au projet est automatiquement utilisé dans la facture financière. Pour autoriser les utilisateurs à modifier le compte général dans la facture financière et dans les répartitions comptables, sélectionnez l'option permettant d'autoriser la modification du numéro du compte général.

## <a name="how-do-i-control-the-settlement-order-for-accounts-receivable-transactions"></a>Comment contrôler l'ordre de règlement pour les transactions de comptabilité client ?
Vous pouvez utiliser les classifications de facturation avec d'autres attributs de facturation pour contrôler l'ordre de règlement de vos transactions de comptabilité client. Pour plus d'informations, voir [Priorité de règlement dans le secteur public](settlement-priority-public-sector.md).

## <a name="is-there-an-easy-way-to-review-reimbursement-transactions"></a>Existe-t-il une manière simple d'examiner les transactions de remboursement ?
Vous pouvez utiliser les classifications de facturation pour créer une transaction de remboursement distincte pour chaque classification de facturation. Lorsque vous procédez ainsi, les transactions de remboursement sont regroupées par l'écriture de type de validation de solde client et la classification de facturation. Pour plus d'informations, voir [Remboursements dans le secteur public](reimbursements-public-sector.md).

## <a name="where-are-the-trading-partner-codes-that-i-need-for-gfrs-and-facts-i-reporting"></a>Où sont les codes partenaire commercial dont j'ai besoin pour la génération d'états GFRS et FACTS I ?
Les codes partenaire commercial, qui sont nécessaires dans le cadre de la génération d'états GFRS et FACTS I, sont établis par le ministère des Finances américain. Toute organisation qui respecte les règles du gouvernement des États-Unis sur la génération d'états pour la comptabilité client doit ajouter des codes de partenaire commercial à ses informations de compte client pour les agences avec lesquelles elle entretient des relations commerciales. Par exemple, si votre agence entretient des relations commerciales avec la Federal Trade Commission, accédez à la page **Codes partenaire commercial** et créez le code partenaire commercial 29. Ensuite, sur la page de détails du client pour la FTC, vous entrez 29 dans le champ **Code partenaire commercial**.

### <a name="i-created-default-financial-dimensions-for-a-customer-group-but-one-customer-in-the-group-needs-a-different-value-for-one-of-the-financial-dimensions-whats-the-easiest-way-to-handle-this"></a>J'ai créé des dimensions financières par défaut pour un groupe de clients, mais un client du groupe a besoin d'une valeur différente pour l'une des dimensions financières. Quelle est la manière la plus simple de procéder ?

Vous pouvez conserver les dimensions financières par défaut pour le groupe de clients. Accédez simplement à l'enregistrement client pour le client qui a besoin d'une valeur différente, puis entrez les dimensions financières par défaut pour le client. Les dimensions financières par défaut du client remplaceront les dimensions financières par défaut qui ont été définies pour le groupe de clients.

## <a name="what-can-i-use-accounts-receivable-posting-definitions-for"></a>À quelles fins puis-je utiliser les définitions de validation de la comptabilité client ?
Vous pouvez utiliser les définitions de validation pour créer des lignes de journal de comptabilité auxiliaire pour les transactions d'origine qui répondent aux critères sélectionnés, par exemple, pour générer plusieurs écritures comptables équilibrées basées sur des attributs tels que des types de transactions et des comptes. Pour plus d'informations sur les définitions de validation, voir [Définitions de validation dans le secteur public](posting-definitions-public-sector.md).

<a name="see-also"></a>Voir également :
--------

[Ventes](..\accounts-receivable\accounts-receivable.md)

[Créer un code facturation](tasks/create-billing-code-public-sector.md)

[Créer une classification de facturation](tasks/create-billing-classification-public-sector.md)

[Créer et affecter un code partenaire commercial](tasks/create-assign-trading-partner-code-public-sector.md)



