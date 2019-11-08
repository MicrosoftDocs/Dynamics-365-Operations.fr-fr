---
title: Spécification de taxe par écriture comptable
description: Cette rubrique explique comment utiliser la spécification de taxe par écriture comptable afin d'afficher et d'imprimer des informations sur les écritures comptables pour laquelle la taxe est calculée.
author: ericwang
manager: Ann Beebe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 1c36d9f8fb81a0a7e7a6de3db48cebdcf9d13b2d
ms.sourcegitcommit: bdbca89bd9b328c282ebfb681f75b8f1ed96e7a8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/14/2019
ms.locfileid: "2591192"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a>Spécification de taxe par écriture comptable
[!include [banner](../includes/banner.md)]

Cette rubrique explique comment utiliser la **spécification de taxe par écriture comptable** afin d'afficher et d'imprimer des informations sur les écritures comptables pour laquelle la taxe est calculée.

## <a name="tax-accounts-vs-non-tax-accounts"></a>Comptes avec taxe vs Comptes hors taxe

L'état **Spécification de taxe par écriture comptable** indique les transactions de taxe pour les comptes avec taxe et les comptes hors taxe. Ces comptes sont classés de la façon suivante :

- **Compte avec taxe** : un compte est considéré comme tel lorsqu'une transaction de taxe est validée, et que le compte principal sur la ligne du journal **Taxe** est un compte de taxe, comme un compte de comptabilité client ou un compte de comptabilité fournisseur.
- **Compte hors taxe** : un compte est considéré comme tel lorsqu'une transaction de taxe est validée, et que le compte principal sur la transaction d'origine est un compte hors taxe, comme un compte de recettes ou un compte de dépenses.

Pour les comptes avec taxe, les colonnes **Origine**, **Taxe déductible** et **Taxe collectée** sur l'état indiquent **0** (zéro). Pour les comptes hors taxe, ces colonnes indiquent des montants.

## <a name="filtering-the-data-on-the-report"></a>Filtrage des données sur l'état

Lorsque vous générez l'état, les champs par défaut suivants sont disponibles. Ces champs permettent de filtrer les données qui apparaissent sur l'état.

| Champ                      | Description |
|----------------------------|-------------|
| Date                       | Utilisez les champs dans les sections **De** et **À** pour définir une plage de dates pour les transactions de taxe. |
| Compte principal               | Utilisez les champs dans les sections **De** et **À** pour définir une plage de dates des comptes principaux. |
| Code taxe             | Utilisez les champs dans les sections **De** et **À** pour définir une plage de dates des codes de taxe. |
| Regroupement                   | Indiquez si l'état doit être regroupé par compte général ou par code de taxe. |
| Sous-total par code taxe | Définissez cette option sur **Oui** pour afficher les sous-totaux par code de taxe. |
| Totaux uniquement                | Définissez cette option sur **Oui** pour n'afficher que les totaux. |
| Comptes principaux uniquement         | Définissez cette option sur **Oui** pour n'inclure que les comptes principaux sur l'état. |

## <a name="showing-only-non-tax-accounts-on-the-report"></a>Afficher uniquement les comptes hors taxe sur l'état

Pour afficher uniquement les comptes hors taxe sur l'état, paramétrez une condition de filtre, comme un astérisque (\*), comme le montre l'illustration suivante.

![État affichant des comptes hors taxe](media/taxspecperledgertrans.png)