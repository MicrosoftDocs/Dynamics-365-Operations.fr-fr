---
title: Configurer les noms des registres des baux
description: Cette rubrique explique comment définir les noms des journaux de location. Les noms des journaux de location spécifient les journaux dans lesquels les entrées provenant de la location d’actifs sont imputées.
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 07b59d56fcb876f73369d0ceaa5ccd8226e58cf9
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725427"
---
# <a name="set-up-lease-journal-names"></a>Configurer les noms des registres des baux

[!include [banner](../includes/banner.md)]


Les noms des journaux de location spécifient les journaux dans lesquels les transactions sont imputées. Seuls les noms de journaux attribués au type de journal **Location d’actifs** apparaît dans les champs **Reconnaissance initiale** et **Nom du journal mensuel** sur la page **Paramètres de location d’actifs**. Seul le type de journal **Enregistrement de la facture fournisseur** peut être affecté au champ **Nom du journal des factures**.

Le système verrouille l’édition de certains champs financiers pour éviter tout écart entre les transactions et les échéanciers. Les champs verrouillés incluent : **Compte**, **Montants**, **Dimensions financières**, **Devise** et **Type de transaction**. De plus, vous ne pourrez pas ajouter ou supprimer des lignes d’entrée de journal dans les entrées de journal de location d’actifs, car cela pourrait entraîner des écarts entre les échéanciers et les transactions.


Pour configurer les noms des journaux de bail, procédez comme suit.

1. Accédez à **Location d’actifs \> Configuration \> Paramètres de location d’actif**.
2. Sur l’onglet **Général**, dans le champ **Nom du journal de reconnaissance initiale** et sélectionnez un journal. Toutes les entrées de journal de reconnaissance initiale seront enregistrées sous ce nom de journal.
3. Dans le champ **Nom du journal des factures**, sélectionnez un journal. Si l’option **Payer au fournisseur** est définie sur **Oui** pour le registre de location, les factures de location et de paiement des dépenses seront imputées à ce nom de journal.
4. Dans le champ **Nom du journal des baux**, sélectionnez un journal. Toutes les écritures d’amortissement, d’intérêts et de reclassement à court terme seront enregistrées sous ce nom de journal. Si l’option **Payer au fournisseur** est définie sur **Non** pour le registre de location, les entrées de paiements de location et de paiement des dépenses seront imputées à ce nom de journal.
5. Dans le champ **Nom du journal de modification des baux**, sélectionnez un journal. Les transactions d’ajustement de bail, de résiliation et de dépréciation seront enregistrées dans ce nom de journal. Le nom du journal que vous sélectionnez ne doit pas avoir de flux de travail ou d’approbation affecté. Si le nom du journal de modification de location n’est pas défini, les transactions d’ajustement de bail, de résiliation et de dépréciation seront enregistrées dans le nom de journal sélectionné dans le champ **Nom du journal des baux**. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
