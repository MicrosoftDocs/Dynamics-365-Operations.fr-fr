---
title: Dimensions financières par défaut des journaux financiers
description: Cette rubrique décrit les règles qui définissent la manière dont les valeurs de dimensions financières sont définies sur les transactions entrées à l’aide des journaux financiers. Elle comprend également des détails sur les scénarios dans lesquels des dimensions fixes sont utilisées.
author: kweekley
ms.date: 09/04/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransDaily, LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 327bc27f068e1f9eefacc6b5defa27044cb1a77e
ms.sourcegitcommit: d420b96d37093c26f0e99c548f036eb49a15ec30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2021
ms.locfileid: "7472530"
---
# <a name="default-financial-dimensions-on-financial-journals"></a>Dimensions financières par défaut des journaux financiers

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les règles qui définissent la manière dont les valeurs de dimensions financières sont définies sur les transactions entrées à l’aide des journaux financiers (mais pas des journaux de stock ou des journaux de projets). Elle comprend également des détails sur les scénarios dans lesquels des dimensions fixes sont utilisées.

## <a name="symptom"></a>Problème

Les valeurs de dimensions financières ne sont pas définies comme prévu sur Compte ou Compte de contrepartie dans un journal financier. Voici deux exemples de scénarios :

Un justificatif est entré dans un journal des opérations diverses. Le compte est un compte fournisseur et le compte de contrepartie est un compte bancaire. Les dimensions financières du fournisseur sont entrées par défaut sur le compte, mais les dimensions financières de la banque ne sont pas entrées par défaut sur le compte de contrepartie. Au lieu de cela, les valeurs de dimension du compte sont entrées par défaut sur le compte de contrepartie.

Des valeurs de dimension financière sont affectées au client par défaut, et une valeur de dimension fixe du compte principal de revenus est affectée à la dimension financière du service. Un justificatif est entré dans un journal des opérations diverses.  Le compte est le client et le compte de contrepartie est un compte général, en particulier le compte de revenus avec la valeur de dimension fixe. La dimension fixe n’est pas définie sur le compte de contrepartie pour le compte principal des revenus. Au lieu de cela, il est défini sur la valeur de la dimension du service du compte, qui provient du client.  Après avoir validé le justificatif, la valeur de dimension fixe est utilisée sur l’écriture comptable validée, mais le justificatif affiche toujours la valeur du service du client sur le compte de revenus. 

Quelles règles sont suivies pour les valeurs de dimension financière définies sur les justificatifs dans un journal ?

## <a name="resolution"></a>Résolution

Les règles suivantes permettent d’entrer des valeurs de dimension financière par défaut sur les lignes d’un justificatif dans les journaux financiers, tels que le journal général ou le journal des factures fournisseur. 

1. **En-tête de journal**

   - Les dimensions d’en-tête de journal sont entrées par défaut à partir des dimensions de nom de journal.

2. **Compte de ligne de journal**

   - Les dimensions de compte de ligne de journal sont entrées par défaut à partir des dimensions d’en-tête de journal.
   - Si des dimensions financières sont vides, leurs valeurs sont entrées par défaut à partir des dimensions client, fournisseur, banque, immobilisation, projet ou comptables.

     - Si le type de compte est **Comptabilité**, une dimension fixe sur un compte de la comptabilité est traitée comme une dimension par défaut au moment de l’entrée de la transaction.
     - Si le type de compte est **Client**, **Fournisseur**, **Banque**, **Immobilisations** ou **Projet**, le compte principal ne peut pas encore être déterminé. Par conséquent, une dimension fixe ne sera jamais entrée par défaut pour le compte.

3. **Compte contrepartie de ligne de journal**

 - Pour commencer, les dimensions de compte de contrepartie de ligne de journal proviennent par défaut des dimensions de compte de ligne de journal.

 - Si des dimensions financières sont vides, la prochaine entrée de valeurs par défaut proviendra des dimensions par défaut des client, fournisseur, banque, immobilisation, projet ou comptabilité.
   1. Si le type de compte de contrepartie est **Comptabilité**, une dimension fixe sur un compte général est traitée comme une dimension par défaut au moment de l’entrée de la transaction. Si une valeur de dimension a déjà été entrée par défaut à partir du compte, la valeur de dimension par défaut ou fixe du compte principal ne remplacera pas la valeur existante.
   2. Si le type de compte de contrepartie est **Client**, **Fournisseur**, **Banque**, **Immobilisations** ou **Projet**, le compte principal n’est pas encore connu, par conséquent, une dimension fixe ne sera jamais par défaut définie sur le compte de contrepartie.

4. **Validation**

    1. Pendant la comptabilisation, le compte principal de chaque ligne de l’écriture comptable (à la fois pour le compte et le compte de contrepartie) est évalué pour déterminer s’il existe une valeur de dimension fixe. Si une dimension fixe est définie, toutes les valeurs existantes ou vides sont remplacées par cette valeur de dimension fixe.

        La valeur de dimension fixe **n’est pas** affichée sur les lignes du journal après la comptabilisation. Au lieu de cela, elle est affichée sur l’écriture comptable lorsque vous affichez le justificatif après sa validation.

    2. Aucune autre valeur de dimension n’est entrée par défaut au moment de la validation, y compris les comptes généraux supplémentaires pouvant être ajoutés lors de la validation, tels que les comptes d’arrondi au centime et les comptes intersociétés d’échéance à partir de comptes. Les écritures de dimensions par défaut pour les comptes généraux supplémentaires sont extraites des comptes généraux ou de contrepartie.

Pour entrer des valeurs de dimension par défaut, le processus d’affectation de valeurs par défaut du journal ne peut pas déterminer si une valeur de dimension vide l’est de manière intentionnelle ou si la valeur par défaut n’a pas été entrée. Si une valeur de dimension est intentionnellement laissée vide, une valeur peut toujours être entrée par défaut en utilisant l’ordre de valeur par défaut décrit précédemment. Si vous exigez qu’une dimension ait une valeur vide, vous devrez peut-être créer une dimension avec une valeur de **0** (zéro) ou **Vide**, de sorte qu’elle puisse être utilisée à la place d’une dimension vide.

Consultez les scénarios suivants pour obtenir des exemples de l’ordre de valeur par défaut de la dimension financière.

### <a name="scenario-1"></a>Scénario 1

Accédez à **Comptabilité \> Configuration du journal \> Noms des journaux**, et sélectionnez le nom du journal **GenJrn**. Puis, sur le raccourci **Dimensions financières**, définissez les valeurs suivantes pour les dimensions financières par défaut :

- **BUSINESSUNIT :** 001
- **DEPARTMENT :** 024

[![Page Noms de journal](./media/financial-dimension-defaulting-jrnl-names-01.png)](./media/financial-dimension-defaulting-jrnl-names-01.png)

Accédez à **Comptabilité \> Écritures de journal \> Journal général**, et créer un journal général portant le nom de **GenJrn**. Les dimensions sont entrées par défaut à partir du nom du journal (table LedgerJournalName) vers l’en-tête du journal (table LedgerJournalTable), comme indiqué sur l’onglet **Dimensions financières**.

[![Onglet Dimensions financières sur la page Journaux généraux](./media/financial-dimension-defaulting-genrl-jrnl-02.png)](./media/financial-dimension-defaulting-genrl-jrnl-02.png)

Accédez aux **Lignes**. Dans le champ **Type de compte**, sélectionnez **Comptabilité**, puis, dans le champ **Compte**, entrez **170150**. Appuyez ensuite sur la touche **Tabulation** pour quitter le champ. Les dimensions sont entrées par défaut à partir de l’en-tête du journal. Par conséquent, la valeur **Compte** est affichée au format **170150-001-024**.

[![Lignes de journal pour un journal général sur la page du justificatif du journal](./media/financial-dimension-defaulting-jrnl-vchr-03.png)](./media/financial-dimension-defaulting-jrnl-vchr-03.png)

Remplacez la valeur du **Compte** par **170150-001-023**. Entrez un montant de débit ou un montant de crédit. Dans le champ **Type de compte de contrepartie**, sélectionnez **Comptabilité**, puis, dans le champ **Compte de contrepartie**, entrez **600150**. Les valeurs des dimensions sont entrées par défaut à partir du compte. Par conséquent, la valeur **Compte de contrepartie** est affichée au format **600150-001-023**.

### <a name="scenario-2"></a>Scénario 2

Utilisez les mêmes dimensions financières que vous avez définies pour le nom du journal dans le scénario 1. Ensuite, accédez à **Comptabilité client \> Clients \> Tous les clients**, et définissez les valeurs de dimension financière par défaut pour le client US-001. Sélectionnez le client pour ouvrir les détails du client. Sur l’onglet **Dimensions financières**, conservez la valeur par défaut de la dimension **BUSINESSUNIT** (**001**). Ajoutez la dimension **COSTCENTER** et entrez **007** comme valeur.

Créez un journal général avec portant le nom de **GenJrn**. Sur l’onglet **Dimensions financières**, remplacez la valeur par défaut **001** de **BUSINESSUNIT** par **002**.

Accédez aux **Lignes**. Dans le champ **Type de compte**, sélectionnez **Client**, puis, dans le champ **Compte**, entrez **US-001**. Pour afficher les dimensions financières des types de comptes non généraux, sélectionnez **Dimensions financières \> Compte**. Les écritures par défaut suivantes pour les valeurs de dimension financière sont entrées :

- **BUSINESSUNIT :** 002 – L’entrée par défaut est extraite de l’en-tête du journal. La valeur **001** n’est pas entrée par défaut par le client US-001, car une valeur par défaut a déjà été entrée.
- **COSTCENTER :** 007 – L’entrée par défaut est extraite de la configuration du client US-001.
- **DEPARTMENT :** 024 – L’entrée par défaut est extraite de l’en-tête du journal.

De retour sur la ligne, dans **Type de compte de contrepartie**, sélectionnez **Comptabilité**, puis, dans le champ **Compte de contrepartie**, entrez **600150**. Les valeurs de dimension financière par défaut suivantes sont entrées sur la ligne :

- **BUSINESSUNIT :** 002 – L’entrée par défaut est tirée des dimensions financières du compte. (Elle a été entrée à l’origine par défaut à partir de l’en-tête du journal.)
- **DEPARTMENT :** 024 – L’entrée par défaut est tirée des dimensions financières du compte. (Elle a été entrée à l’origine par défaut à partir de l’en-tête du journal.)
- **COSTCENTER :** 007 – L’entrée par défaut est tirée des dimensions financières du compte. (Elle a été entrée à l’origine par défaut par le client.)

### <a name="scenario-3"></a>Scénario 3

Dans le même journal que celui utilisé pour le scénario 2, ajoutez une nouvelle ligne. Dans le champ **Type de compte**, sélectionnez **Comptabilité**, puis, dans le champ **Compte**, entrez **170150**. Effacez les valeurs de dimension par défaut afin qu’il ne reste que le compte principal 170150. Dans le champ **Type de compte de contrepartie**, sélectionnez **Client**, puis, dans le champ **Compte de contrepartie**, entrez **US-001**. Les écritures par défaut suivantes pour les valeurs de dimension financière sont entrées :

- **BUSINESSUNIT :** 002 – L’entrée par défaut est extraite de l’en-tête du journal, car la valeur de la dimension Compte est vide. La valeur **001** n’est pas entrée par défaut par le client US-001, car une valeur par défaut a déjà été extraite de l’en-tête du journal. Si la valeur **BUSINESSUNIT** a été laissée vide intentionnellement, vous devez également supprimer la dimension financière sur le compte de contrepartie.
- **COSTCENTER :** 007 – L’entrée par défaut provient du client US-001, car la valeur de dimension Compte et la valeur de dimension d’en-tête de journal sont vides. Si la valeur **COSTCENTER** a été laissée vide intentionnellement, vous devez également supprimer la dimension financière sur le compte de contrepartie.
- **DEPARTMENT :** 024 – L’entrée par défaut est extraite de l’en-tête du journal, car la valeur de la dimension Compte est vide. Si la valeur **DEPARTMENT** a été laissée vide intentionnellement, vous devez également supprimer la dimension financière sur le compte de contrepartie.

### <a name="scenario-4"></a>Scénario 4

Utilisez les mêmes valeurs de dimension financière par défaut que celles définies pour le nom du journal et le client dans les scénarios 1 et 2. Ensuite, définissez une valeur de dimension fixe pour la dimension **BUSINESSUNIT** sur le compte principal 170150. Accédez à **Comptabilité \> Plan de comptes \> Comptes \> Comptes principaux**. Dans le champ **Compte principal**, sélectionnez **170150**, puis, sur l’onglet **Remplacements d’entités juridiques**, sélectionnez **Ajouter**. Sélectionnez **USMF** en tant qu’entité juridique, puis sélectionnez **Ajouter**. Sélectionnez cet enregistrement, puis **Dimensions par défaut**. Modifiez la dimension **BUSINESSUNIT** sur **Valeur fixe**, et entrez **003** comme valeur.

Créez un journal général avec portant le nom de **GenJrn**. Sur l’onglet **Dimensions financières**, supprimez toutes les valeurs de dimension par défaut.

Accédez aux **Lignes**. Dans le champ **Type de compte**, sélectionnez **Comptabilité**, puis, dans le champ **Compte**, entrez **170150**. Appuyez ensuite sur la touche **Tabulation** pour quitter le champ. Les valeurs de dimension du compte sont entrées par défaut à partir de la configuration du compte principal pour le compte 170150. Par conséquent, la valeur **Compte** est affichée au format **170150-003-**.

Remplacez la valeur du **Compte** par **170150-004-**. **La fonctionnalité de journal n’empêche pas la modification d’une valeur de dimension fixe.** Entrez un montant de débit ou un montant de crédit. Dans le champ **Type de compte de contrepartie**, sélectionnez **Comptabilité**, puis, dans le champ **Compte de contrepartie**, entrez **170250**. La valeur de la dimension financière de 004 est entrée comme valeur par défaut à partir du Compte. Enregistrez ensuite le document. Dans le journal, sélectionnez **Justificatif**. Notez que la valeur de **BUSINESSUNIT** a été ramenée à la valeur de dimension fixe, **003**, lors de l’enregistrement.

Lorsque vous revenez au justificatif sur le journal, la dimension **BUSINESSUNIT** ne reflète **pas** la valeur de dimension fixe. Elle comporte toujours la valeur affichée à l’écran avant l’enregistrement. Le processus d’enregistrement ne change rien à ce qui est inscrit sur le justificatif. Seule l’écriture comptable est modifiée lors de la validation.

## <a name="developer-notes"></a>Notes du développeur

Si vous êtes développeur et que vous souhaitez examiner le code du processus par défaut, passez en revue les méthodes suivantes :

- **LedgerJournalEngine.accountModified()** – Cette méthode est le point d’entrée principal pour le processus de définition par défaut de la dimension de compte principal standard pour tous les journaux (et remplacé par certains types de journaux).
- **LedgerJournalEngine.offsetAccountModified()** – Cette méthode est le point d’entrée principal pour le processus de définition des valeurs par défaut de la dimension du compte de contrepartie.
