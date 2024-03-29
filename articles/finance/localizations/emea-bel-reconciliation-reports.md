---
title: États de rapprochement pour la Belgique
description: Cet article décrit les états standard que Microsoft Dynamics 365 Finance fournit pour l’analyse de la déclaration de taxe INTERVAT et de rapprochement.
author: AdamTrukawka
ms.date: 06/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Belgium
ms.author: atrukawk
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 273103
ms.search.form: TaxReportExtraFieldsBE
ms.openlocfilehash: edc45c235a8c226fbe2bfc5621b1ba7d9412239c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292309"
---
# <a name="reconciliation-reports-for-belgium"></a>États de rapprochement pour la Belgique

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Cette fonctionnalité a été remplacée par la fonctionnalité de déclaration de TVA. Pour plus d’informations, voir [Déclaration de TVA (Belgique)](emea-bel-vat-declaration-belgium.md).

Dynamics 365 Finance a évolué en applications spécialement conçues pour vous aider à gérer des fonctions commerciales spécifiques. Pour plus d’informations sur ces modifications, voir [Guide de gestion des licences Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Cet article décrit les états standard fournis pour l’analyse de la déclaration de taxe INTERVAT et de rapprochement.

Selon les entrées de taxe pour les périodes sélectionnées, la déclaration périodique belge de taxe sur la valeur ajoutée (TVA) combine des montants de taxe dans des zones (codes déclaration de taxe) en triant, en fractionnant et en totalisant les informations de manières spécifiques. Par conséquent, des états de contrôle sont requis, de sorte que les montants de la déclaration de TVA puissent être vérifiés en détail. Le reste de cet article décrit les états qui incluent les détails des données dans la déclaration de TVA.

Les captures d’écran présentées dans cet article montrent des données basées sur des transactions provenant d’un exemple de l’article, [Déclaration de taxe INTERVAT](emea-bel-intervat-tax-declaration.md).


## <a name="sales-tax-correction"></a>Corrections de taxe
L’état **Correction de taxe** fournit une vue d’ensemble imprimée des corrections de taxe INTERVAT. Le montant de la correction est répertorié pour chaque zone de période de règlement et fiscale. (Les zones de taxe sont des champs spécifiques à la Belgique, utilisés pour regrouper les montants de la TVA dans la déclaration de TVA. Vous paramétrez ces zones dans la table **Codes déclaration de taxe**.)

Pour imprimer l’état **Correction de taxe**, allez dans **Taxe** \> **Déclarations** \> **Taxe de vente** \> **Zones de déclaration de taxe supplémentaires**, puis cliquez sur **Corrections de taxe** \> **Imprimer**.

![État généré des corrections de taxe.](media/1_Sales_tax_corrections.png)

## <a name="sales-tax-list---belgium"></a>Liste de taxe - Belgique
Utilisez le rapport **Liste de taxe – Belgique** pour afficher des informations sur la taxe validée. L’état fournit des détails sur le code taxe, le nom, le compte général, le nom du compte, la quantité, le montant (comprenant la taxe, l’origine, et le montant de la taxe). Les paramètres de cet état permettent beaucoup de flexibilité. Vous pouvez consulter un état très détaillé en sélectionnant le document, la date, ou les paramètres de code taxe. Utilisez un filtre pour définir les paramètres de l’état.

Pour imprimer l’état **Liste de taxe – Belgique**, allez dans **Taxe** \> **Recherches et états** \> **Déclarations de taxe** \> **Liste de taxe – Belgique**.

![État généré de la liste de taxe.](media/2_Sales_tax_list.png)

## <a name="sales-tax-transactions---details--belgium"></a>Transactions de taxe – Détails – Belgique
Utilisez le rapport **Transactions de taxe – Détails – Belgique** pour afficher et imprimer des informations sur les transactions de taxe validées pour une période donnée et une plage de codes taxe. Les transactions sont répertoriées par code taxe. Pour chaque transaction, vous pouvez voir le client ou le fournisseur, le justificatif, le compte dans lequel le montant de base de la taxe est validé, le montant de base de la taxe (d’origine), le montant taxe comprise, le montant de la taxe, les dépenses de taxe et la direction de la taxe. Les montants sont additionnés pour chaque code taxe. Les montants des directions de taxe Taxe déductible et Taxe collectée sont additionnés dans un total général. L’état répertorie également les codes taxe avec d’autres directions de taxe, telles que la Taxe d’utilisation.

Pour imprimer l’état **Transactions de taxe – Détails, Belgique**, allez dans **Taxe** \> **Recherches et états** \> **Déclarations de taxe** \> **Transactions de taxe – Détails, Belgique**.

![État généré des détails des transactions de taxe pour la Belgique.](media/3_Sales_tax_transactions_details.png)

## <a name="sales-tax-transactions-re-sales"></a>Transactions de taxe liées aux ventes
Vous pouvez utiliser l’état **Transactions de taxe liées aux ventes** pour extraire des informations de revente de transaction de taxe spécifiques à la Belgique. Ces informations incluent des détails tels que le journal, le N° document, la date, le compte client, le nom, le montant, et les codes déclaration de taxe. Cet état est généré d’après le numéro identifiant TVA, le numéro d’entreprise, et la période. Les responsables de compte et les comptables génèrent cet état périodiquement ou selon les besoins.

> [!NOTE]
> Le nombre de zones doit être ajouté de façon dynamique, selon la validation des achats.

Pour imprimer l’état **Transactions de taxe liées aux ventes**, allez dans **Taxe** \> **Recherches et états** \> **Déclarations de taxe** \> **Transactions de taxe liées aux ventes**.

![État généré des transactions de taxe liées aux ventes.](media/4_Sales_tax_transactions_re_sales.png)


## <a name="sales-tax-transactions---belgium"></a>Transactions de taxe - Belgique

L’état **Transactions de taxe – Belgique** affiche les transactions de taxe belges validées. L’état fournit des détails sur la date, le n° document, les codes taxe, le nom, la source, la facture, le montant, la TVA nette dans la devise de la société, le montant TVA net dans la devise du justificatif et la devise du justificatif.

Vous pouvez trier l’état par N° document, date, devise de document, code taxe, et source. Les champs **N° document**, **Code taxe** et **Devise du justificatif** fournissent l’extraction. Les paramètres de cet état permettent beaucoup de flexibilité. Vous pouvez consulter un état très détaillé en sélectionnant le document, la date, ou les paramètres de code taxe. Utilisez un filtre pour définir les paramètres de l’état.

Pour imprimer l’état **Transactions de taxe – Belgique**, allez dans **Taxe** \> **Recherches et états** \> **Déclarations de taxe** \> **Transactions de taxe – Belgique**.

![État généré des transactions de taxe.](media/5_Sales_tax_transactions.png)

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

Les paramètres de cet état permettent beaucoup de flexibilité. Vous pouvez consulter un état très détaillé en sélectionnant le compte client, la date, ou les paramètres de code taxe. Utilisez un filtre pour définir les paramètres de l’état plus précisément.  Pour imprimer le rapport **Taxe** **par client – Belgique**, cliquez sur **Taxe** &gt; **Recherches et états** &gt; **Déclarations de taxe** &gt; **Taxe** **par client – Belgique**.

![État généré de la taxe belge par client.](media/6_Sales_tax_by_customer.png)

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

Les paramètres de cet état permettent beaucoup de flexibilité. Vous pouvez consulter un état très détaillé en sélectionnant le compte fournisseur, la date, ou les paramètres de code taxe. Utilisez un filtre pour définir les paramètres de l’état plus précisément. Pour imprimer le rapport **Taxe** **par fournisseur – Belgique**, cliquez sur **Taxe** &gt; **Recherches et états** &gt; **Déclarations de taxe** &gt; **Taxe** **par fournisseur – Belgique**.

![État généré de la taxe belge par fournisseur.](media/7_Sales_tax_by_vendor.png)

## <a name="purchase-sales-tax-transactions"></a>Transactions de taxe sur les achats
L’état **Transactions de taxe sur les achats** affiche les transactions comportant des droits de douane sur les achats. Les droits de douane sur les achats sont calculés et validés avec les paiements de taxe. Les droits de douane sur les achats et les taxes sont déclarés pour la période de règlement. La période de règlement varie selon l’administration fiscale définie sur la page **Périodes de règlement de la taxe**. Les informations dans la section d’en-tête de l’état fournissent des détails tels que le numéro identifiant TVA, le numéro d’entreprise, la période. Ces informations de détail incluent le journal, le N° document, la date, le compte fournisseur, le nom, le montant taxte comprise, et les codes déclaration de taxe. Cet état est un rapport externe. Le comptable ou gestionnaire comptable le génère et la soumet périodiquement aux administrations appropriées. Pour imprimer l’état **Transactions de taxe sur les achats**, cliquez sur **Taxe** &gt; **Recherches et états** &gt; **Déclarations de taxe** &gt; **Transactions de taxe sur les achats**.

![État généré des transactions de taxe sur les achats.](media/8_Purchase_sales_tax_transactions.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
