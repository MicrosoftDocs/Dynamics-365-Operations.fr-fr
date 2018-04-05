---
title: "N° document"
description: "La fonctionnalité N° document pour les journaux financiers (journal des opérations diverses, journal des immobilisations, journal des paiements fournisseur, etc.) permet d'entrer plusieurs transactions de comptabilité auxiliaire dans le contexte d'un N° document unique."
author: kweekley
manager: AnnBe
ms.date: 03/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 3831a6b5ec458495134b4b490d33a9acd76b6d2e
ms.openlocfilehash: 76ea8470786bd50896400a65564d698d96119d6f
ms.contentlocale: fr-fr
ms.lasthandoff: 03/20/2018

---

# <a name="one-voucher"></a>N° document

[!include[banner](../includes/banner.md)]

> [!NOTE]
>  Cette fonctionnalité sera disponible dans la version 8.0 de Dynamics 365 for Finance and Operations, qui sera disponible dans la version printemps 2018.   

<a name="what-is-one-voucher"></a>Qu'est-ce qu'un « N° document » ?
======================

La fonctionnalité existante pour les journaux financiers (journal des opérations diverses, journal des immobilisations, journal des paiements fournisseur, etc.) permet d'entrer plusieurs transactions de comptabilité auxiliaire dans le contexte d'un N° document unique. Nous appelons cette fonctionnalité « N° document ». Vous pouvez créer un N° document à l'aide de l'une des méthodes suivantes :

-   Paramétrez le nom du journal (**Comptabilité** \> **Paramétrage de journaux** \>**Noms de journal**) afin que le champ **Nouveau N° document** soit défini sur **Un seul N° document**. Chaque ligne que vous ajoutez au journal est désormais incluse sur le même N° document. Comme chaque ligne est ajoutée au même N° document, le N° document peut être entré comme un N° document multiligne, comme un compte/compte de contrepartie sur la même ligne, ou comme une combinaison.

[![Ligne unique](./media/same-line.png)](./media/same-line.png)

-   Entrez un N° document multiligne lorsqu'il n'existe pas de compte de contrepartie.

[![N° document multiligne](./media/Multi-line.png)](./media/Multi-line.png)

-   Entrez un N° document lorsque le compte et le compte de contrepartie contiennent un type de compte auxiliaire, par exemple fournisseur/fournisseur, client/client, fournisseur/client ou banque/banque.

[![N° document du compte général auxiliaire](./media/subledger.png)](./media/subledger.png)

<a name="issues-with-one-voucher"></a>Problèmes liés à la fonctionnalité N° document
=======================

La fonctionnalité N° document génère des problèmes pendant le règlement, le calcul de la taxe, le rapprochement d'un compte auxiliaire dans la comptabilité, la génération d'états financiers, etc. (Par exemple, pour plus d'informations sur les problèmes qui peuvent se produire pendant le règlement, voir [N° de document unique avec plusieurs enregistrements client ou fournisseur](https://docs.microsoft.com/en-us/dynamics365/unified-operations/financials/accounts-payable/single-voucher-multiple-customer-vendor-records)). Pour assurer un bon fonctionnement et générer des états corrects, ces processus et états requièrent les détails de transaction. Bien que certains scénarios puissent continuer à fonctionner correctement, selon le paramétrage de votre organisation, des problèmes se produisent souvent lorsque plusieurs transactions sont entrées dans un N° document.

Par exemple, vous validez le N° document multiligne suivant.

[![Exemple](./media/example.png)](./media/example.png)

Vous générez ensuite l'état **Dépenses par fournisseur** dans l'espace de travail **Financial Insights**. L'état regroupe les soldes des comptes de dépenses sous le groupe de fournisseurs et le fournisseur. Lorsque vous générez l'état, le système ne peut pas déterminer quels groupes de fournisseurs/fournisseurs ont engagé la dépense de 250,00. Comme les détails de la transaction sont manquants, le système suppose que la totalité des 250,00 a été engagée par le premier fournisseur indiqué dans le N° document. Les 250,00 qui sont inclus dans le solde du compte principal 600120, sont affichés sous ce groupe de fournisseurs/fournisseur. Il est très probable que le premier fournisseur indiqué dans le N° document n'était pas le bon fournisseur, l'état est donc incorrect.

[![Dépenses](./media/expenses.png)](./media/expenses.png)

<a name="the-future-of-one-voucher"></a>Avenir de la fonctionnalité N° document
=========================

En raison des problèmes mentionnés précédemment, la fonctionnalité N° document va devenir obsolète. Toutefois, comme il existe des écarts fonctionnels qui dépendent de cette fonctionnalité, la fonctionnalité ne deviendra pas obsolète d'un seul coup. Nous utiliserons le calendrier suivant : 

-   **Version printemps 2018** – La fonctionnalité sera désactivée par défaut via le paramètre Comptabilité. Toutefois, vous pouvez activer la fonctionnalité si votre organisation a un scénario qui s'inscrit dans les écarts de scénario d'entreprise répertoriés plus loin dans cette rubrique.

    -   Si un client a un scénario d'entreprise qui ne nécessite pas la fonctionnalité N° document, n'activez pas la fonctionnalité. Nous ne corrigerons pas les « bogues » dans les zones identifiées plus loin dans cette rubrique si cette fonctionnalité est utilisée même si une autre solution existe.

    -   Arrêtez d'utiliser la fonctionnalité N° document pour les intégrations dans Microsoft Dynamics 365 Finance and Operations, sauf si la fonctionnalité est requise pour l'un des écarts fonctionnels.

-   **Version automne 2018 et versions ultérieures** – Les écarts fonctionnels seront comblés. Une fois les écarts fonctionnels comblés, la fonctionnalité N° document sera définitivement désactivée.

<a name="why-use-one-voucher"></a>Pourquoi utiliser la fonctionnalité N° document ?
====================

À partir des conversations avec les clients, nous avons compilé la liste suivante des scénarios où les clients utilisent la fonctionnalité N° document et les raisons pour lesquelles ils l'utilisent. Certaines de ces exigences métier peuvent être remplies uniquement à l'aide de la fonctionnalité N° document. Toutefois, pour de nombreux scénarios, d'autres solutions permettent de répondre aux mêmes exigences métier.

<a name="scenarios-that-require-one-voucher"></a>Scénarios qui nécessitent la fonctionnalité N° document
----------------------------------

Les scénarios suivants peuvent être réalisés uniquement à l'aide de la fonctionnalité N° document. Ces écarts fonctionnels seront comblés par le biais d'autres fonctionnalités dans la version automne 2018 et les versions ultérieures.

-   **Valider le résumé des paiements fournisseur ou client sur un compte bancaire**

    -   Une organisation communique une liste de fournisseurs et de montants à sa banque, et la banque utilise cette liste pour payer les fournisseurs pour le compte de l'organisation. La banque valide la somme des paiements en tant que prélèvement unique sur le compte bancaire.

>   La synthèse des paiements fournisseur est prise en charge uniquement par la fonctionnalité N°document. Chaque fournisseur est entré comme une ligne distincte pour tenir à jour les détails du compte auxiliaire Comptabilité fournisseur, mais le montant récapitulé de tous les paiements est compensé sur une ligne unique pour le compte bancaire. Par conséquent, le prélèvement s'affiche sous forme de montant récapitulé unique dans le compte auxiliaire.

-   Une organisation dépose des paiements client, ou la banque dépose des paiements client pour le compte de l'organisation, et le dépôt s'affiche sous forme de montant forfaitaire sur le compte bancaire.

>   La synthèse des paiements client est généralement prise en charge par la fonctionnalité de dépôt. Toutefois, si vous utilisez la « transition » pour le mode de paiement, ce scénario est pris en charge uniquement via la fonctionnalité N° document. Les paiements client sont entrés de la même manière que celle décrite pour la synthèse des paiements fournisseur.

-   **Mécanisme pour regrouper les transactions d'un événement commercial**

    -   Une organisation a un événement commercial unique qui déclenche plusieurs transactions. Toutefois, le département Comptabilité souhaite afficher ensemble les écritures comptables pour une meilleure auditabilité.

>   Si une organisation doit afficher ensemble les écritures comptables d'un événement commercial, elle doit utiliser la fonctionnalité N° document. 

-   **Fonctionnalités spécifiques à un pays**

 -   La fonctionnalité Document administratif unique (SAD) pour la Pologne requiert actuellement l'utilisation d'un N° document unique. Tant qu'une option de regroupement n'est pas disponible pour cette fonctionnalité, vous devez continuer à utiliser la fonctionnalité N° document. Des fonctionnalités supplémentaires spécifiques au pays peuvent nécessiter la fonctionnalité N° document.

-   **Journal des paiements client avec acompte contenant des taxes sur plusieurs « lignes »**

 -   Un client effectue un acompte pour une commande, et les lignes de la commande ont plusieurs taxes qui doivent être enregistrées pour l'acompte. Le paiement client avec acompte est une transaction qui simule les lignes de la commande, afin que la taxe appropriée puisse être enregistrée pour le montant sur chaque ligne.

Dans ce scénario, les clients indiqués dans le N° document unique sont les mêmes clients, car la transaction simule les lignes d'une commande client. L'acompte doit être entré dans un N° document unique, car le calcul de la taxe doit être effectué sur les « lignes » du paiement unique effectué par le client.

-   **Maintenance des immobilisations : rattraper l'amortissement, fractionner l'immobilisation, calculer l'amortissement sur la cession**

Les transactions d'immobilisation suivantes créent également plusieurs transactions dans un N° document unique :
-   Une acquisition supplémentaire est effectuée sur une immobilisation et l'amortissement de « rattrapage » est calculé.
-   Une immobilisation est fractionnée.
-   Un paramètre pour calculer l'amortissement sur la cession est activé et l'immobilisation est ensuite cédée.

<a name="scenarios-that-dont-require-one-voucher"></a>Scénarios qui ne nécessitent pas la fonctionnalité N° document
----------------------------------------

Les scénarios suivants peuvent être réalisés par le biais d'autres méthodes et ne doivent pas utiliser la fonctionnalité N° document.

-   **Valider le résumé des paiements client sur le compte bancaire**

Une organisation dépose des paiements client, ou la banque dépose des paiements client pour le compte de l'organisation, et le dépôt s'affiche sous forme de montant forfaitaire sur le compte bancaire.

La synthèse des paiements client est prise en charge par la fonctionnalité de dépôt lorsque la transition n'est pas utilisée pour le mode de paiement.

-   **Compensation**

Lors de la compensation, les soldes d'un fournisseur et client sont compensés les uns en fonction des autres, car le fournisseur et le client sont la même partie. Cette approche réduit l'échange d'argent entre une organisation et la partie client/fournisseur.

La compensation peut être effectuée en saisissant l'augmentation ou la diminution dans des N° documents distincts, et en validant la contrepartie dans un compte général de compensation.

-   **Validation récapitulative dans la comptabilité**

Les organisations souhaitent souvent effectuer une validation récapitulative dans la comptabilité pour réduire la quantité de données. Toutefois, les organisations requièrent toujours que les détails de la transaction soient mis à jour. Lorsque la validation récapitulative est effectuée via un N° document unique, les détails de la transaction ne sont pas connus et ne peuvent pas être mis à jour.

   -   Comme les détails de la transaction ne peuvent pas être actuellement mis à jour, il est recommandé de ne pas utiliser la fonctionnalité N° document pour effectuer une validation récapitulative.
   -   Une fois que la prise en charge de la fonctionnalité N° document est supprimée, nous pouvons implémenter les infrastructures Document source et Comptabilité dans les journaux. Ces infrastructures assurent la mise à jour des détails de la transaction et prennent en charge la synthèse dans la comptabilité.

-   **Régler plusieurs paiements non validés sur la même facture**

Ce scénario est généralement utilisé dans les organisations de vente au détail où les clients peuvent utiliser plusieurs modes de paiement pour les achats. Dans ce scénario, l'organisation doit pouvoir enregistrer plusieurs paiements non validés et les régler pour la facture client.

Une nouvelle fonctionnalité ajoutée dans la version 1611 de Microsoft Dynamics 365 for Operations (novembre 2016) permet de régler plusieurs paiements non validés pour une facture unique. Il n'est plus nécessaire d'entrer plusieurs paiements client dans un N° document unique.

-   **Importer les transactions de relevé bancaire**

Les banques paient et reçoivent souvent des paiements pour le compte d'une organisation, et ces transactions sont enregistrées dans Finance and Operations via un fichier transmis par la banque. Les organisations souhaitent souvent regrouper ces transactions à l'aide du numéro de relevé bancaire dans le fichier. Comme chaque transaction est affichée en détail sur le relevé bancaire, aucune synthèse n'est nécessaire dans le compte auxiliaire.

Les transactions peuvent être regroupées en utilisant d'autres champs du journal, comme le numéro de lot du journal proprement dit ou le numéro de document.

-   **Transférer les soldes**

Une organisation peut être amenée à transférer un solde d'un fournisseur vers un autre fournisseur, en raison d'une erreur ou de la reprise du passif par un autre fournisseur. Les transferts de ce type s'appliquent également aux types de comptes tels que les comptes client ou bancaires.

Les transferts de solde d'un compte (fournisseur, client, compte bancaire, etc.) vers un autre compte peuvent être effectués via des N° documents distincts, et la contrepartie peut être validée dans un compte général de compensation.

-   **Entrer les soldes d'ouverture**

Les organisations entrent souvent les soldes d'ouverture des comptes auxiliaires (fournisseurs, clients, immobilisations, etc.) en tant que transaction de N° document. Les soldes d'ouverture de chaque compte auxiliaire peuvent être entrés en tant que N° documents distincts, et la contrepartie peut être validée dans un compte général de compensation.

-   **Corriger l'écriture comptable d'un document client ou fournisseur validé**

Une organisation peut être amenée à corriger l'écriture comptable d'une facture validée dans le compte général Comptabilité client ou Comptabilité fournisseur, mais cette facture ne peut pas être contrepassée ou corrigée par le biais d'un autre mécanisme.

Si une correction doit être effectuée dans le compte général Comptabilité client ou Comptabilité fournisseur, un ajustement doit être effectué directement dans le compte général. L'ajustement ne peut pas être effectué par validation via le fournisseur ou le client. Cette approche nécessite que l'ajustement ait lieu pendant un « temps d'arrêt » afin que le compte général puisse temporairement autoriser la saisie manuelle.

-   **« Autorisation du système »**

Les organisations utilisent souvent la fonctionnalité N° document simplement parce que le système les y autorise, sans comprendre les implications.

