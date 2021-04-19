---
title: N° document
description: La fonctionnalité N° document pour les journaux financiers (journal des opérations diverses, journal des immobilisations, journal des paiements fournisseur, etc.) permet d’entrer plusieurs transactions de comptabilité auxiliaire dans le contexte d’un justificatif unique.
author: kweekley
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerParameters, AssetProposalDepreciation
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 8.0.2
ms.openlocfilehash: e98f1803e43df0fbd5ab700b959faaeee017b7a9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834498"
---
# <a name="one-voucher"></a>N° document

[!include [banner](../includes/banner.md)]


## <a name="what-is-one-voucher"></a>Qu’est-ce qu’un N° document ?

La fonctionnalité existante pour les journaux financiers (le journal des opérations diverses, le journal des immobilisations, le journal des paiements fournisseur, etc.) permet d’entrer plusieurs transactions de comptabilité auxiliaire (client, fournisseur, immobilisations, projet et banque) dans le contexte d’un N° document unique. Microsoft fait référence à cette fonctionnalité comme *N° document*. Vous pouvez créer un N° document unique à l’aide de l’une des méthodes suivantes :

- Paramétrez le nom du journal (**Comptabilité** \> **Paramétrage de journaux** \> **Noms de journal**) afin que le champ **Nouveau N° document** soit défini sur **Un seul N° document**. Chaque ligne que vous ajoutez au journal est désormais incluse sur le même N° document. Par conséquent, le N° document peut être entré comme un N° document multiligne, comme un compte/compte de contrepartie sur la même ligne, ou comme une combinaison.

    [![Ligne unique](./media/same-line.png)](./media/same-line.png)

    > [!IMPORTANT]
    > La définition de N° document n’inclut **pas** les cas où les noms de journaux paramétrés comme **Un N° document uniquement**, mais que l’utilisateur entre ensuite un N° document qui inclut uniquement des types de comptes généraux. Dans cette rubrique, un N° document signifie un justificatif unique contenant plusieurs fournisseurs, clients, banques, immobilisations, ou projets.

- Entrez un N° document multiligne lorsqu’il n’existe pas de compte de contrepartie.

    [![N° document multiligne](./media/Multi-line.png)](./media/Multi-line.png)

- Entrez un N° document lorsque le compte et le compte de contrepartie contiennent un type de compte auxiliaire, par exemple **fournisseur**/**fournisseur**, **client**/**client**, **fournisseur**/**client** ou **banque**/**banque**.

    [![N° document du compte général auxiliaire](./media/subledger.png)](./media/subledger.png)

## <a name="issues-with-one-voucher"></a>Problèmes liés à la fonctionnalité N° document

La fonctionnalité N° document génère des problèmes pendant le règlement, le calcul de la taxe, la contrepassation d’une transaction, le rapprochement d’un compte auxiliaire dans la comptabilité, la génération d’états financiers, etc. (Pour plus d’informations sur les problèmes qui peuvent se produire pendant le règlement, par exemple, voir [N° de document unique avec plusieurs enregistrements client ou fournisseur](https://docs.microsoft.com/dynamics365/finance/accounts-payable/single-voucher-multiple-customer-vendor-records).) Pour assurer un bon fonctionnement et générer des états corrects, ces processus et états requièrent les détails de transaction. Bien que certains scénarios puissent continuer à fonctionner correctement, en fonction du paramétrage de votre organisation, des problèmes se produisent souvent lorsque plusieurs transactions sont entrées dans un justificatif.

Par exemple, vous validez le justificatif multiligne suivant.

[![Exemple de justificatif multiligne](./media/example.png)](./media/example.png)

Vous générez ensuite l’état **Dépenses par fournisseur** dans l’espace de travail **Financial Insights**. Sur cet état, les soldes des comptes de dépenses sont regroupés par groupe de fournisseurs et fournisseur. Lorsque l’état est généré, le système ne peut pas déterminer quels groupes de fournisseurs/fournisseurs ont engagé la dépense de 250,00. Comme les détails de la transaction sont manquants, le système suppose que la totalité de la dépense de 250,00 a été engagée par le premier fournisseur indiqué dans le N° document. Par conséquent, la dépense de 250,00 qui sont inclus dans le solde du compte principal 600120, sont affichés sous ce groupe de fournisseurs/fournisseur. Toutefois, il est très probable que le premier fournisseur indiqué dans le justificatif ne soit pas le bon fournisseur. Par conséquent, l’état est probablement incorrect.

[![Dépenses par état fournisseur](./media/expenses.png)](./media/expenses.png)

## <a name="the-future-of-one-voucher"></a>Avenir de la fonctionnalité N° document

En raison des problèmes qui peuvent survenir lorsque la fonctionnalité N° document est utilisée, cette fonctionnalité sera au final obsolète. Toutefois, comme il existe des écarts fonctionnels qui dépendent de cette fonctionnalité, elle ne deviendra pas obsolète d’un seul coup. Au lieu de cela, le calendrier suivant sera utilisé :

- **Version du printemps 2018** – Cette fonctionnalité a été désactivée par défaut via le paramètre **Autoriser plusieurs transactions dans un justificatif** sous l’onglet **Général** de la page **Paramètres de comptabilité**. Toutefois, vous pouvez réactiver la fonctionnalité si votre organisation a un scénario qui s’inscrit dans l’un des écarts de scénario fonctionnels répertoriés plus loin dans cette rubrique.

    - Si votre scénario commercial ne nécessite pas N° document, nous vous recommandons de laisser la fonctionnalité désactivée. Si vous utilisez cette fonctionnalité même si une autre solution existe, Microsoft ne corrigera pas les « bogues » dans les zones identifiées plus loin dans cette rubrique.
    - Nous vous recommandons d’arrêter d’utiliser la fonctionnalité N° document pour les intégrations dans , sauf si elle est requise pour l’un des écarts fonctionnels.

- **Versions ultérieures** – Certaines de ces exigences métier peuvent être remplies uniquement à l’aide de la fonctionnalité N° document. Microsoft doit s’assurer que toutes les exigences métier identifiées peuvent toujours être satisfaites dans le système une fois la fonctionnalité obsolète. Par conséquent, de nouvelles fonctionnalités devront probablement être ajoutées pour combler les lacunes fonctionnelles. Microsoft ne peut pas fournir de solution spécifique, car chaque lacune de fonctionnalités est différente et doit être évaluée en fonction des exigences de l’entreprise. Certaines lacunes fonctionnelles seront probablement remplacées par des fonctionnalités qui permettent de répondre à des exigences métier spécifiques. Cependant, d’autres lacunes peuvent être comblées en continuant à autoriser la saisie dans un journal, comme lorsque la fonctionnalité N° document est utilisée, mais en améliorant le système pour suivre plus de détails si nécessaire.

Une fois que toutes les lacunes fonctionnelles sont comblées, Microsoft indiquera que la fonctionnalité est obsolète. Cependant, la suppression ne sera effective qu’au bout d’au moins un an après ce message. Bien que Microsoft ne puisse pas fournir une estimation du moment où la fonctionnalité N° document sera obsolète, il faudra probablement au moins deux ans avant que cela ne se produise. La politique de Microsoft est de laisser au moins 12 mois entre l’annonce de l’obsolescence de la fonctionnalité et la dépréciation réelle, afin que les clients et les éditeurs de logiciels indépendants (ISV) aient le temps de réagir au changement. Par exemple, une organisation peut devoir mettre ses processus d’entreprise, entités, et intégrations à jour.

La dépréciation de la fonctionnalité N° document est un changement important qui sera largement diffusé. Dans le cadre de cette communication, Microsoft mettra à jour cette rubrique, publiera un billet de blog sur le site Microsoft Dynamics 365 Finance, mettra à jour la rubrique « Fonctionnalités supprimées ou obsolètes », indiquera la modification lors des conférences Microsoft appropriées, etc.

## <a name="why-use-one-voucher"></a>Pourquoi utiliser la fonctionnalité N° document ?

À partir des conversations avec les clients, Microsoft a compilé la liste suivante des scénarios où les clients utilisent la fonctionnalité N° document et les raisons pour lesquelles ils l’utilisent. Certaines de ces exigences métier peuvent être remplies uniquement à l’aide de la fonctionnalité N° document. Toutefois, pour de nombreux scénarios, d’autres solutions permettent de répondre aux mêmes exigences métier.

### <a name="scenarios-that-require-one-voucher"></a>Scénarios qui nécessitent la fonctionnalité N° document

Les scénarios suivants peuvent être réalisés uniquement à l’aide de la fonctionnalité N° document. Si votre organisation a l’un de ces scénarios, vous devez activer plusieurs transactions à entrer dans un justificatif en modifiant la définition du paramètre **Autoriser plusieurs transactions dans un justificatif** sur la page **Paramètres de comptabilité**. Ces écarts fonctionnels seront comblés par le biais d’autres fonctionnalités dans les versions ultérieures.

> [!Note]
> [Pour chacun des scénarios suivants, le champ **Autoriser plusieurs transactions dans un justificatif** doit être défini sur Oui dans l’organisateur **Général** sur la page **Paramètres de comptabilité**.]

### <a name="post-vendor-or-customer-payments-in-summary-form-to-a-bank-account"></a>Valider le résumé des paiements fournisseur ou client sur un compte bancaire

**Scénario** Une organisation communique une liste de fournisseurs et de montants à sa banque, et la banque utilise cette liste pour payer les fournisseurs pour le compte de l’organisation. La banque valide la somme des paiements en tant que prélèvement unique sur le compte bancaire.

La synthèse des paiements fournisseur est prise en charge uniquement par la fonctionnalité N° document. Chaque fournisseur est entré comme une ligne distincte pour tenir à jour les détails dans le sous-compte Comptabilité fournisseur. Toutefois, le montant récapitulé de tous les paiements est contrepassé sur une ligne unique pour le compte bancaire. Par conséquent, le prélèvement s’affiche sous forme de montant récapitulé unique dans le compte auxiliaire.

**Scénario** Une organisation dépose des paiements client, ou la banque dépose des paiements client pour le compte de l’organisation, et le dépôt s’affiche sous forme de montant forfaitaire sur le compte bancaire.

La synthèse des paiements client est généralement prise en charge par la fonctionnalité de dépôt. Toutefois, si vous utilisez la « transition » pour le mode de paiement, ce scénario est pris en charge uniquement via la fonctionnalité N° document. Les paiements client sont entrés de la même manière que celle décrite pour la synthèse des paiements fournisseur.

### <a name="mechanism-to-group-transactions-from-a-business-event"></a>Mécanisme pour regrouper les transactions d’un événement commercial

**Scénario** Une organisation a un événement commercial unique qui déclenche plusieurs transactions. Toutefois, le département Comptabilité souhaite afficher ensemble les écritures comptables pour une meilleure auditabilité.

Si une organisation doit afficher ensemble les écritures comptables d’un événement commercial, elle doit utiliser la fonctionnalité N° document. 

### <a name="country-specific-features"></a>Fonctionnalités spécifiques à un pays

**Scénario** La fonctionnalité Document administratif unique (SAD) pour la Pologne requiert actuellement l’utilisation d’un N° document unique. Tant qu’une option de regroupement n’est pas disponible pour cette fonctionnalité, vous devez continuer à utiliser la fonctionnalité N° document. Des fonctionnalités supplémentaires spécifiques au pays peuvent nécessiter la fonctionnalité N° document.

### <a name="customer-prepayment-payment-journal-that-has-taxes-on-multiple-lines"></a>Journal des paiements client avec acompte contenant des taxes sur plusieurs « lignes »

Dans ce scénario, les clients indiqués dans le N° document unique sont les mêmes clients, car la transaction simule les lignes d’une commande client. L’acompte doit être entré dans un justificatif unique, car le calcul de la taxe doit être effectué sur les « lignes » du paiement unique effectué par le client.

### <a name="customer-reimbursement"></a>Remboursement client

**Scénario** Un client effectue un acompte pour une commande, et les lignes de la commande ont plusieurs taxes qui doivent être enregistrées pour l’acompte. Le paiement client avec acompte est une transaction qui simule les lignes de la commande, afin que la taxe appropriée puisse être enregistrée pour le montant sur chaque ligne.

Si la tâche périodique Remboursement est exécutée dans le module Comptabilité client, elle crée une transaction pour déplacer le solde d’un client à un fournisseur. Pour ce scénario, N° document doit être utilisé pour rembourser le client.

### <a name="fixed-asset-maintenance-catch-up-depreciation-split-asset-calculate-depreciation-on-disposal"></a>Maintenance des immobilisations : rattraper l’amortissement, fractionner l’immobilisation, calculer l’amortissement sur la cession
Les transactions d’immobilisation suivantes créent également plusieurs transactions dans un justificatif unique :

- Une acquisition supplémentaire est effectuée sur une immobilisation et l’amortissement de « rattrapage » est calculé.
- Une immobilisation est fractionnée.
- Un paramètre pour calculer l’amortissement sur la cession est activé et l’immobilisation est ensuite cédée.
- Une date de mise en service d’immobilisation est antérieure à la date d’acquisition. Par conséquent, un ajustement d’amortissement est validé.

> [!Note]
> Lorsque vous entrez des transactions, assurez-vous que toutes les transactions s’appliquent à la même immobilisation. Le justificatif n’est pas validé s’il contient plus d’une immobilisation, même si le champ **Nouveau justificatif** est défini sur Un seul N° document sur la page **Noms de journal** dans la comptabilité. Si vous incluez plusieurs immobilisations dans le justificatif, le message **Il ne peut y avoir qu’une transaction d’immobilisation par justificatif** s’affiche et vous ne pouvez pas publier le justificatif.  

### <a name="bills-of-exchange-and-promissory-notes"></a>Lettres de change et billets à ordre
Les lettres de change et les billets à ordre nécessitent qu’un N° document soit utilisé, car les transactions déplacent le solde client ou fournisseur d’un compte général Comptabilité client/Comptabilité fournisseur à un autre, selon l’état du paiement.

## <a name="scenarios-that-dont-require-one-voucher"></a>Scénarios qui ne nécessitent pas la fonctionnalité N° document

Les scénarios suivants peuvent être réalisés par le biais d’autres méthodes et ne doivent pas utiliser la fonctionnalité N° document.

### <a name="post-customer-payments-in-summary-form-to-the-bank-account"></a>Valider le résumé des paiements client sur le compte bancaire

Une organisation dépose des paiements client, ou la banque dépose des paiements client pour le compte de l’organisation, et le dépôt s’affiche sous forme de montant forfaitaire sur le compte bancaire.

La synthèse des paiements client est prise en charge par la fonctionnalité de dépôt lorsque la transition n’est pas utilisée pour le mode de paiement.

### <a name="netting"></a>Compensation

Lors de la compensation, les soldes d’un fournisseur et client sont compensés les uns en fonction des autres, car le fournisseur et le client sont la même partie. Cette approche réduit l’échange d’argent entre une organisation et la partie client/fournisseur.

La compensation peut être effectuée en saisissant l’augmentation ou la diminution dans des justificatifs distincts, puis en validant la contrepartie dans un compte général de compensation.

### <a name="post-in-summary-to-the-general-ledger"></a>Validation récapitulative dans la comptabilité

Les organisations souhaitent souvent effectuer une validation récapitulative dans la comptabilité pour réduire la quantité de données. Toutefois, ces organisations requièrent toujours que les détails de la transaction soient mis à jour. Lorsque la validation récapitulative est effectuée via un justificatif unique, les détails de la transaction ne sont pas connus et ne peuvent pas être mis à jour.

- Comme les détails de la transaction ne peuvent pas être actuellement mis à jour, il est recommandé de ne **pas** utiliser la fonctionnalité N° document pour effectuer une validation récapitulative.
- Une fois que la prise en charge de la fonctionnalité N° document est supprimée, les infrastructures Document source et Comptabilité peuvent être implémentées dans les journaux. Ces infrastructures assurent la mise à jour des détails de la transaction et prennent en charge la synthèse dans la comptabilité.


### <a name="settle-multiple-unposted-payments-to-the-same-invoice"></a>Régler plusieurs paiements non validés sur la même facture

Ce scénario est généralement utilisé dans les organisations où les clients peuvent utiliser plusieurs modes de paiement pour les achats. Dans ce scénario, l’organisation doit pouvoir enregistrer plusieurs paiements non validés et les régler pour la facture client.

Une nouvelle fonctionnalité ajoutée dans la version 1611 de Microsoft Dynamics 365 for Operations (novembre 2016) permet de régler plusieurs paiements non validés pour une facture unique. Il n’est plus nécessaire d’entrer plusieurs paiements client dans un justificatif unique.

### <a name="import-bank-statement-transactions"></a>Importer les transactions de relevé bancaire

Les banques paient et reçoivent souvent des paiements pour le compte d’une organisation, et ces transactions sont enregistrées via un fichier transmis par la banque. Les organisations souhaitent souvent regrouper ces transactions à l’aide du numéro de relevé bancaire dans le fichier. Comme chaque transaction est affichée en détail sur le relevé bancaire, aucune synthèse n’est nécessaire dans le compte auxiliaire.

Les transactions peuvent être regroupées en utilisant d’autres champs du journal, comme le numéro de lot du journal proprement dit ou le numéro de document.


### <a name="transfer-balances"></a>Transférer les soldes

Une organisation peut être amenée à transférer un solde d’un fournisseur vers un autre fournisseur, en raison d’une erreur ou de la reprise du passif par un autre fournisseur. Les transferts de ce type s’appliquent également aux types de comptes tels que les **Client** ou **Banque**.

Les transferts de solde d’un compte (fournisseur, client, banque, etc.) vers un autre compte peuvent être effectués via des justificatifs distincts, et la contrepartie peut être validée dans un compte général de compensation.

### <a name="enter-beginning-balances"></a>Entrer les soldes d’ouverture

Les organisations entrent souvent les soldes d’ouverture des comptes auxiliaires (fournisseurs, clients, immobilisations, etc.) en tant que transaction de justificatif. Les soldes d’ouverture de chaque compte auxiliaire peuvent être entrés en tant que justificatifs distincts, et la contrepartie peut être validée dans un compte général de compensation.

### <a name="correct-the-accounting-entry-of-a-posted-customer-or-vendor-document"></a>Corriger l’écriture comptable d’un document client ou fournisseur validé

Une organisation peut être amenée à corriger l’écriture comptable d’une facture validée dans le compte général Comptabilité client ou Comptabilité fournisseur, mais cette facture ne peut pas être contrepassée ou corrigée par le biais d’un autre mécanisme.

Si une correction doit être effectuée dans le compte général Comptabilité client ou Comptabilité fournisseur, un ajustement doit être effectué directement dans le compte général. L’ajustement ne peut pas être effectué par validation via le fournisseur ou le client. Cette approche nécessite que l’ajustement ait lieu pendant un « temps d’arrêt » afin que le compte général puisse temporairement autoriser la saisie manuelle.

### <a name="the-system-allows-it"></a>« Autorisation du système »

Les organisations utilisent souvent la fonctionnalité N° document simplement parce que le système les y autorise, sans comprendre les implications.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]