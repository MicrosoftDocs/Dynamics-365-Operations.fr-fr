---
title: Configurer les noms des registres des baux
description: Cette rubrique explique comment définir les noms des journaux de location. Les noms des journaux de location spécifient les journaux dans lesquels les entrées provenant de la location d’actifs sont imputées.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: c139df124b249ec9dc5d16096e6f45f22d435456
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880884"
---
# <a name="set-up-lease-journal-names"></a>Configurer les noms des registres des baux

[!include [banner](../includes/banner.md)]

Les noms des journaux de location spécifient les journaux dans lesquels les transactions sont imputées. Seuls les noms de journaux attribués au type de journal **Location d’actifs** apparaît dans les champs **Reconnaissance initiale** et **Nom du journal mensuel** sur la page **Paramètres de location d’actifs**. Seul le type de journal **Enregistrement de la facture fournisseur** peut être affecté au champ **Nom du journal des factures**.

Pour configurer les noms des journaux de bail, procédez comme suit.

1. Accédez à **Location d’actifs \> Configuration \> Paramètres de location d’actif**.
2. Sur l’onglet **Général**, dans le champ **Nom du journal de reconnaissance initiale** et sélectionnez un journal. Toutes les entrées de journal de reconnaissance initiale seront enregistrées sous ce nom de journal.
3. Dans le champ **Nom du journal des factures**, sélectionnez un journal. Si l’option **Payer au fournisseur** est définie sur **Oui** pour le registre de location, les factures de location et de paiement des dépenses seront imputées à ce nom de journal.
4. Dans le champ **Nom du journal des baux**, sélectionnez un journal. Toutes les écritures d’amortissement, d’intérêts et de reclassement à court terme seront enregistrées sous ce nom de journal. Si l’option **Payer au fournisseur** est définie sur **Non** pour le registre de location, les entrées de paiements de location et de paiement des dépenses seront imputées à ce nom de journal.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
