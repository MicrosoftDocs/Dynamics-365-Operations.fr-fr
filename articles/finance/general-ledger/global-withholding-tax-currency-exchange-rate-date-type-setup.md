---
title: Activer la configuration du type de taux de change et du type de date de la devise de retenue à la source globale
description: Cet article explique comment activer la configuration globale du type de taux de change et du type de date de la devise retenue à la source.
author: kailiang
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 9db9cf41381b8b4de7dffe1c755a7df805a003ea
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573222"
---
# <a name="enable-the-global-withholding-tax-currency-exchange-rate-type-and-date-type-setup"></a>Activer la configuration du type de taux de change et du type de date de la devise de retenue à la source globale

[!include[banner](../includes/banner.md)]

Cet article explique comment activer la configuration globale du type de taux de change et du type de date de la devise retenue à la source. Vous pouvez maintenant sélectionner un type de taux de change dédié et un type de date de calcul du taux de change pour la devise de retenue à la source. Ces sélections déterminent le taux de change de la devise étrangère utilisé pour calculer le montant de la retenue à la source, dans la devise de la retenue à la source, dans les opérations de paiement.

Cette fonctionnalité est disponible dans Microsoft Dynamics 365 Finance version 10.0.29 et les versions ultérieures.

1. Accédez à **Taxe** \> **Configuration** \> **Paramètres** \> **Paramètres de comptabilité**.
2. Sur l'onglet **Retenue d’impôt** , définissez l'option **Activer la devise de retenue d’impôt avancée** à **Oui**.
3. Dans le champ **Type de taux de change** , sélectionnez un type de taux de change pour la devise de retenue à la source.
4. Dans le champ **Type de date de calcul** , sélectionnez un type de date de calcul qui détermine le taux de change de la devise de retenue à la source :

    - **Date de paiement** – Déterminer le taux de change en fonction de la date comptable du journal des paiements.
    - **Date de facture** – Déterminer le taux de change en fonction de la date de facture du journal des factures. Si la date de facturation du bon est vide, la date comptable de la facture sera utilisée. 
    - **Date de document**  – Déterminer le taux de change en fonction de la date du document du journal des paiements. Si la date de document du bon est vide, la date de paiement sera utilisée.

5. Cliquez sur **Enregistrer**.

Si la devise de transaction diffère de la devise de retenue à la source définie dans le code de retenue à la source, le montant dans la devise de la retenue à la source sera calculé à partir de la devise de transaction, en fonction des paramètres précédents, et sera enregistré dans les transactions de retenues à la source comptabilisées. .
