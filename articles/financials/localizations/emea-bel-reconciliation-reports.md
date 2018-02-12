---
title: "États de rapprochement pour la Belgique"
description: "Cette rubrique décrit les états standard que Microsoft Dynamics 365 for Finance and Operations, Enterprise edition fournit pour l'analyse de la déclaration de taxe INTERVAT et de rapprochement."
author: ShylaThompson
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxReportExtraFieldsBE
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 273103
ms.search.region: Belgium
ms.author: shylaw
ms.dyn365.ops.version: AX 7.0.1
ms.search.validFrom: 2016-05-31
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b08befd0a9f77c53e8ef03cc0ef0b5ceafd81e92
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="reconciliation-reports-for-belgium"></a>États de rapprochement pour la Belgique

[!include[banner](../includes/banner.md)]


Cette rubrique décrit les états standard que Microsoft Dynamics 365 for Finance and Operations, Enterprise edition fournit pour l'analyse de la déclaration de taxe INTERVAT et de rapprochement.

Selon les entrées de taxe pour les périodes sélectionnées, la déclaration périodique belge de taxe sur la valeur ajoutée (TVA) combine des montants de taxe dans des zones (codes déclaration de taxe) en triant, en fractionnant et en totalisant les informations de manières spécifiques. Par conséquent, des états de contrôle sont requis, de sorte que les montants de la déclaration de TVA puissent être vérifiés en détail. Le reste de cette rubrique décrit les états qui incluent les détails des données dans la déclaration de TVA.

## <a name="sales-tax-correction"></a>Corrections de taxe
L'état **Correction de taxe** fournit une vue d'ensemble imprimée des corrections de taxe INTERVAT. Le montant de la correction est répertorié pour chaque zone de période de règlement et fiscale. (Les zones de taxe sont des champs spécifiques à la Belgique, utilisés pour regrouper les montants de la TVA dans la déclaration de TVA. Vous paramétrez ces zones dans la table **Codes déclaration de taxe** .) Pour imprimer l'état **Correction de taxe**, cliquez sur **Taxe** &gt; **Déclarations** &gt; **Taxe** &gt; **Zones d'état de taxes supplémentaires**, puis cliquez sur **Corrections de taxe** &gt; **Imprimer**.

## <a name="sales-tax-list---belgium"></a>Liste de taxe - Belgique
Utilisez le rapport **Liste de taxe - Belgique** pour afficher des informations sur la taxe validée. L'état fournit des détails sur le code taxe, le nom, le compte général, le nom du compte, la quantité, le montant (comprenant la taxe, l'origine, et le montant de la taxe). Les paramètres de cet état permettent beaucoup de flexibilité. Vous pouvez consulter un état très détaillé en sélectionnant le document, la date, ou les paramètres de code taxe. Utilisez un filtre pour définir les paramètres de l'état. Pour imprimer le rapport **Liste de taxe - Belgique**, cliquez sur **Taxe** &gt; **Recherches et états** &gt; **Déclarations de taxe** &gt; **Liste de taxe - Belgique**.

## <a name="sales-tax-transactions---details--belgium"></a>Transactions de taxe - Détails - Belgique
Utilisez le rapport **Transactions de taxe - Détails - Belgique** pour afficher et imprimer des informations sur les transactions de taxe validées pour une période donnée et une plage de codes taxe. Les transactions sont répertoriées par code taxe. Pour chaque transaction, vous pouvez voir le client ou le fournisseur, le N° document, le compte dans lequel le montant de base de la taxe est validé, le montant de base de la taxe (d'origine), le montant taxe comprise, le montant de la taxe, les dépenses de taxe et la direction de la taxe. Les montants sont additionnés pour chaque code taxe. Les montants des directions de taxe Taxe déductible et Taxe collectée sont additionnés dans un total général. L'état répertorie également les codes taxe avec d'autres directions de taxe, telles que la Taxe d'utilisation. Pour imprimer le rapport **Transactions de taxe - Détails, Belgique**, cliquez sur **Taxe** &gt; **Recherches et états** &gt; **Déclarations de taxe** &gt; **Transactions de taxe - Détails, Belgique**.

## <a name="sales-tax-transactions-re-sales"></a>Transactions de taxe liées aux ventes
Vous pouvez utiliser l'état **Transactions de taxe liées aux ventes** pour extraire des informations de revente de transaction de taxe spécifiques à la Belgique. Ces informations incluent des détails tels que le journal, le N° document, la date, le compte client, le nom, le montant, et les codes déclaration de taxe. Cet état est généré d'après le numéro identifiant TVA, le numéro d'entreprise, et la période. Les responsables de compte et les comptables génèrent cet état périodiquement ou selon les besoins. **Remarque :** le nombre de zones doit être ajouté de façon dynamique, selon la validation des achats. Pour imprimer le rapport **Transactions de taxe liées aux ventes**, cliquez sur **Taxe** &gt; **Recherches et états** &gt; **Déclarations de taxe** &gt; **Transactions de taxe liées aux ventes**.

## <a name="sales-tax-transactions---belgium"></a>Transactions de taxe - Belgique
L'état **Transactions de taxe - Belgique** affiche les transactions de taxe belges validées. L'état fournit des détails sur la date, le n° document, les codes taxe, le nom, la source, la facture, le montant, la TVA nette dans la devise de la société, le montant TVA net dans la devise du document et la devise du document. Vous pouvez trier l'état par N° document, date, devise de document, code taxe, et source. Les champs **N° document**, **Code taxe** et **Devise du N° document** fournissent l'extraction. Les paramètres de cet état permettent beaucoup de flexibilité. Vous pouvez consulter un état très détaillé en sélectionnant le document, la date, ou les paramètres de code taxe. Utilisez un filtre pour définir les paramètres de l'état. Pour imprimer le rapport **Transactions de taxe - Belgique**, cliquez sur **Taxe** &gt; **Recherches et états** &gt; **Déclarations de taxe** &gt; **Transactions de taxe - Belgique**.

## <a name="sales-tax-by-customer---belgium"></a>Taxe par client - Belgique
Des états de contrôle sont requis, de sorte que les montants de la déclaration de TVA puissent être vérifiés en détail pour un client. Pour chaque compte client et code taxe, les informations suivantes sont imprimées :

-   Numéro de compte client
-   Code taxe
-   Montant taxe comprise
-   Origine
-   Montant de la taxe de vente
-   Total par compte client
-   Total général pour tous les comptes client

Cet état peut être généré comme suit :

-   Pour un compte client pour tous les comptes client
-   Pour un code taxe ou pour tous les codes taxe
-   Pour une date spécifique ou pour une plage de dates

Les paramètres de cet état permettent beaucoup de flexibilité. Vous pouvez consulter un état très détaillé en sélectionnant le compte client, la date, ou les paramètres de code taxe. Utilisez un filtre pour définir les paramètres de l'état plus précisément. Pour imprimer le rapport **Taxe** **par client - Belgique**, cliquez sur **Taxe** &gt; **Recherches et états** &gt; **Déclarations de taxe** &gt; **Taxe** **par client - Belgique**.

## <a name="sales-tax-by-vendor---belgium"></a>Taxe par fournisseur - Belgique
Des états de contrôle sont requis, de sorte que les montants de la déclaration de TVA puissent être vérifiés en détail pour un fournisseur. Pour chaque compte fournisseur et code taxe, les informations suivantes sont imprimées :

-   Numéro de compte fournisseur
-   Code taxe
-   Montant taxe comprise
-   Origine
-   Montant de la taxe de vente
-   Total par compte fournisseur
-   Total général pour tous les comptes fournisseur

Cet état peut être généré comme suit :

-   Pour un compte fournisseur ou pour tous les comptes fournisseurs
-   Pour un code taxe ou pour tous les codes taxe
-   Pour une date spécifique ou pour une plage de dates

Les paramètres de cet état permettent beaucoup de flexibilité. Vous pouvez consulter un état très détaillé en sélectionnant le compte fournisseur, la date, ou les paramètres de code taxe. Utilisez un filtre pour définir les paramètres de l'état plus précisément. Pour imprimer le rapport **Taxe** **par fournisseur - Belgique**, cliquez sur **Taxe** &gt; **Recherches et états** &gt; **Déclarations de taxe** &gt; **Taxe** **par fournisseur - Belgique**.

## <a name="purchase-sales-tax-transactions"></a>Transactions de taxe sur les achats
L'état **Transactions de taxe sur les achats** affiche les transactions comportant des droits de douane sur les achats. Les droits de douane sur les achats sont calculés et validés avec les paiements de taxe. Les droits de douane sur les achats et les taxes sont déclarés pour la période de règlement. La période de règlement varie selon l'administration fiscale définie sur la page **Périodes de règlement de la taxe**. Les informations dans la section d'en-tête de l'état fournissent des détails tels que le numéro identifiant TVA, le numéro d'entreprise, la période. Ces informations de détail incluent le journal, le N° document, la date, le compte fournisseur, le nom, le montant taxte comprise, et les codes déclaration de taxe. Cet état est un rapport externe. Le comptable ou gestionnaire comptable le génère et la soumet périodiquement aux administrations appropriées. Pour imprimer le rapport **Transactions de taxe sur les achats**, cliquez sur **Taxe** &gt; **Recherches et états** &gt; **Déclarations de taxe** &gt; **Transactions de taxe sur les achats**.





