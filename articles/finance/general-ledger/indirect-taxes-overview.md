---
title: Vue d'ensemble des taxes
description: Cette rubrique offre une vue d'ensemble du système de taxes. Il explique les éléments du paramétrage de la taxe et comment ils fonctionnent ensemble.
author: ShylaThompson
manager: AnnBe
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority, TaxPeriod, TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 13111
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a3dacc755b3d4d3b5c7f51f6bac7c2e9c62773ba
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975025"
---
# <a name="sales-tax-overview"></a>Vue d'ensemble des taxes

[!include [banner](../includes/banner.md)]

Cette rubrique offre une vue d'ensemble du système de taxes. Il explique les éléments du paramétrage de la taxe et comment ils fonctionnent ensemble.

<a name="overview"></a>Vue d'ensemble
--------

L'infrastructure de taxe prend en charge de nombreux types de taxes indirectes, tels que la taxe, la taxe sur la valeur ajoutée (VAT), la Taxe sur les Produits et Services (GST), les frais basés sur l'unité et la retenue à la source. Ces taxes sont calculées et documentées lors des transactions d'achat et de vente. Régulièrement, elles doivent être déclarées et payées à l'administration fiscale. 

Le diagramme suivant indique les entités du paramétrage fiscal et comment elles sont liées.

[![Diagramme présentant la vue d'ensemble des entités du paramétrage fiscal](./media/taxoverview1-300x209.jpg)](./media/taxoverview1.jpg) 

Pour chaque taxe qu'une société doit justifier, un code taxe doit être défini. Un code taxe enregistre les taux et les règles de calcul de la taxe. 

Chaque code taxe doit être lié à une période de règlement de la taxe. Les périodes de règlement de la taxe définissent les intervalles auxquels la taxe doit être déclarée et payée à l'administration fiscale. Chaque période de règlement de la taxe doit être affectée à une administration fiscale. Une administration fiscale représente l'entité à laquelle la taxe est déclarée et payée. Elle définit également la structure de la déclaration de taxe. Les administrations fiscales peuvent être associées à des comptes fournisseur. Pour plus d'informations, voir [Paramétrer des périodes de règlement fiscal](tasks/set-up-sales-tax-settlement-periods.md).

Chaque code taxe doit également être lié à un groupe de validation dans la comptabilité. Un groupe de validation dans la comptabilité spécifie les comptes principaux dans lesquels les montants correspondant aux codes taxe sont validés. 

Vous pouvez également définir des codes déclaration de taxe facultatifs. Ceux-ci peuvent être affectés à des codes taxe pour les divers types de montant calculés pour le code taxe. L'état **Déclaration de taxe par code** indique les totaux par code déclaration de taxe pour une période de règlement de la taxe et un intervalle donnés. 

Chaque transaction pour laquelle une taxe doit être calculée et validée doit être doté d'un groupe de taxe et d'un groupe de taxe d'article. Les groupes de taxe associés à la partie (par exemple, client ou fournisseur) de la transaction, alors que les groupes de taxe d'article sont associés à la ressource (par exemple, article ou catégorie d'approvisionnement) de la transaction. Les groupes de taxe contiennent une liste des codes taxe. Les codes taxe qui figurent à la fois dans le groupe de taxe et le groupe de taxe d'article pour une transaction sont le code taxe qui s'applique à cette transaction. 

Le tableau suivant décrit les entités et la séquence pour le paramétrage fiscal.

| Activité de paramétrage                                                  | Obligatoire/facultatif et description                                                                                                                                                                                                                                                                                         |
|-----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Créer des comptes principaux.                                           | Obligatoire. Avant de pouvoir définir la fonctionnalité de taxe, vous devez créer les comptes principaux que la société utilise pour payer et enregistrer les taxes.                                                                                                                                                                             |
| Paramétrez des groupes de validation dans la comptabilité pour la taxe.                     | Obligatoire. Les groupes de validation dans la comptabilité définissent les comptes principaux pour l'enregistrement et le paiement des taxes.   Pour plus d'informations, voir [Paramétrer des groupes de validation dans la comptabilité de la taxe](tasks/set-up-ledger-posting-groups-sales-tax.md).                                                                                 |
| Paramétrage des administrations fiscales.                                   | Obligatoire. Les autorités fiscales sont les entités auxquelles cette taxe doit être déclarée et payée.    Pour plus d'informations, voir [Paramétrer les administrations fiscales](tasks/set-up-sales-tax-authorities.md).                                                                                                                                          |
| Paramétrage des périodes de règlement de la taxe.                            | Obligatoire. Les périodes de règlement de la taxe contiennent des informations sur la date et la fréquence à laquelle la taxe doit être déclarée et payée. Elles sont associées à une administration fiscale.                                                                                                                                                       |
| Paramétrage des codes déclaration de taxe.                               | Facultatif. Les codes déclaration de taxe peuvent être affectés à des codes taxe afin de déclarer des montants correspondant à plusieurs codes taxe sous un seul code déclaration de taxe. Pour plus d'informations, voir [Paramétrer des codes déclaration de taxe](tasks/set-up-sales-tax-reporting-codes.md).                                         |
| Paramétrage des codes taxe.                                         | Obligatoire. Les codes taxe contiennent les taux et les règles de calcul de chaque taxe. Les codes taxe sont associés à une période de règlement de la taxe, ainsi qu'à un groupe de validations dans la comptabilité. Pour plus d'informations, voir [Paramétrer des codes taxe](tasks/set-up-sales-tax-codes.md).                                |
| Paramétrez les groupes de taxes.                                        | Obligatoire. Les groupes de taxe contiennent une liste des codes de vente applicables pour la partie (client ou fournisseur) d'une transaction. Pour une transaction donnée, l'intersection des codes taxe dans le groupe de taxe et le groupe de taxe d'article détermine les codes taxe qui s'appliquent à cette transaction.                  |
| Paramétrer des groupes de taxes d'article.                                   | Obligatoire. Les groupes de taxe d'article contiennent une liste des codes vente applicables pour la ressource (produit, service, etc.) d'une transaction. Pour une transaction donnée, l'intersection des codes taxe dans le groupe de taxe et le groupe de taxe d'article détermine les codes taxe qui s'appliquent à cette transaction. Pour plus d'informations, voir [Paramétrer des groupes de taxe et groupes de taxe d'article](tasks/set-up-sales-tax-groups-item-sales-tax-groups.md). |
| Définir les paramètres de taxe sur les pages de paramètres d'application. | Obligatoire. Différents domaines, tels que la Comptabilité, la Comptabilité client et la Comptabilité fournisseur, doivent définir les paramètres pour le calcul correct des taxes indirectes. Bien que la plupart de ces paramètres aient des valeurs par défaut, ils doivent être modifiés pour répondre aux exigences de chaque société.                                          |

## <a name="sales-tax-on-transactions"></a>Taxe sur les transactions
Sur chaque transaction (ventes/lignes de document d'achat, journaux, etc.), vous devez entrer un groupe de taxe et un groupe de taxe d'article afin de calculer la taxe. Les groupes par défaut sont spécifiés dans les données principales (par exemple, client, fournisseur, article et catégorie d'approvisionnement), mais vous pouvez modifier manuellement les groupes d'une transaction si nécessaire. Les deux groupes contiennent une liste des codes taxe, et l'intersection des deux listes de codes taxe détermine la liste des codes taxe applicables pour la transaction. 

Sur chaque transaction, vous pouvez rechercher la taxe calculée en ouvrant la page **Transaction de taxe**. Vous pouvez rechercher la taxe pour une ligne de document ou pour l'intégralité du document. Pour certains documents (par exemple, factures fournisseur et journaux des opérations diverses), vous pouvez ajuster la taxe calculée si le document d'origine présente des écarts de montants.

## <a name="sales-tax-settlement-and-reporting"></a>Règlement et déclaration de la taxe
La taxe doit être déclarée et payée à l'administration fiscale à intervalles réglementés (mensuels, trimestriels, etc.). Vous pouvez régler les comptes de taxe pour l'intervalle et de compenser les soldes dans le compte de règlement de la taxe, tel que cela est spécifié dans les groupes de validation dans la comptabilité. Vous pouvez accéder à cette fonctionnalité depuis la page **Régler et valider la taxe**. Vous devez spécifier la période de règlement à laquelle la taxe doit être réglée. 

Une fois la taxe payée, le solde du compte de règlement de la taxe doit être équilibré par rapport au compte bancaire. Si l'administration fiscale spécifiée pour la période de règlement de la taxe est liée à un compte fournisseur, le solde de taxe est validé en tant que facture fournisseur en cours et peut être inclus dans la proposition de paiement régulière.

## <a name="conditional-sales-tax"></a>Taxe sur les encaissements
La taxe sur les encaissements est une taxe qui est proportionnelle au montant réel payé sur une facture. Inversement, la taxe standard est calculée au moment de la facturation. La taxe sur les encaissements doit être payée à l'administration fiscale lors de la validation du paiement, et non de la facture. Lorsque la facture est validée, la transaction doit être déclarée dans l'état du registre des taxes. Toutefois, la transaction doit être exclue de la déclaration de paiement de la taxe. 

Si vous activez la case à cocher Taxe sur les encaissements dans l'écran Comptabilité, aucune taxe ne peut être déduite jusqu'à ce que vous ayez réglé la facture. Il s'agit d'une obligation légale dans certains pays ou régions.

> [!NOTE]
> Si vous sélectionnez la case à cocher Taxe sur les encaissements, vous devez paramétrer les codes taxe et les groupes de taxe, et créer des groupes de validations dans la comptabilité afin de prendre en charge la fonctionnalité. |

###  <a name="example"></a>Exemple

Vous réglez les taxes chaque mois. Le 15 juin, vous créez une facture client de 10 000 EUR plus les taxes.
-   La taxe est de 25 pour cent, soit 25.
-   La facture doit être payée le 30 juillet.

Généralement vous devez payer 2 500 EUR à l'administration fiscale lorsque la facture est validée en juin, même si vous n'avez pas reçu le paiement du client. 

Toutefois, si vous utilisez une taxe sur les encaissements, vous payez l'administration fiscale lorsque vous recevez le paiement du client, le 30 juillet.

### <a name="postdated-check"></a>Chèque postdaté

Si vous utilisez un chèque postdaté comme mode de paiement, lorsque le paiement est créé, le compte bancaire n'est pas effacé. Dans certains pays, la TVA devient un passif « réalisé » lorsque le paiement compense la banque, ce qui signifie que le chèque postdaté est réglé. Vous pouvez l'activer en sélectionnant **Réaliser la taxe conditionnelle lorsque les chèques postdatés sont débités** dans **Gestion de la trésorerie et de la banque > Paramétrage > Paramètres de gestion de la trésorerie et de la banque > Chèques postdatés**.

Pour plus d'informations, voir [Paramétrer la retenue à la source](tasks/set-up-withholding-tax.md).
