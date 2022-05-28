---
title: Enregistrer les baux dans des devises étrangères
description: Cette rubrique explique comment enregistrer les contrats de location dans des devises autres que la devise comptable ou de reporting.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7da4ddb5939d4f950eb7f8c39a9c56edb2ec4db9
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727508"
---
# <a name="record-leases-in-foreign-currencies"></a>Enregistrer les baux dans des devises étrangères

[!include [banner](../includes/banner.md)]

Les comptes de location d’actifs pour les locations dans des devises autres que la devise comptable ou la devise de reporting sont établis sur la page **Configuration de la comptabilité**. Toutes les locations doivent être saisies dans leur devise de transaction. En d’autres termes, elles doivent être saisies dans la devise spécifiée dans le contrat de location. Cette rubrique explique comment enregistrer les contrats de location dans des devises autres que la devise comptable ou de reporting.

Si vous saisissez une location dans une devise étrangère, le droit d’utilisation de l’actif est amorti à la fois dans la devise comptable et dans la devise de reporting. Ces devises sont configurées sur la page **Configuration de la comptabilité**. Ce comportement est également utilisé dans les immobilisations. Lorsque vous créez une location dans une devise étrangère, sélectionnez la devise de transaction dans le champ **Devise**.

Le taux de change de la devise comptable est la valeur par défaut dans le champ **Taux de change de la devise comptable**. Le taux de change de la devise de déclaration est la valeur par défaut dans le champ **Taux de change de la devise de déclaration**. Ces taux de change étaient en vigueur à la date de début du bail. Les champs **Taux de change de la devise comptable** et **Taux de change de la devise de déclaration** sont dans le raccourci **Échange d’informations financières et de reporting**, sur la page **Détails du bail**.

1. Cochez la case **Taux fixe** pour remplacer le taux de change qui a été automatiquement entrés, puis entrez le nouveau taux.
2. Dans les autres champs, entrez les informations requises pour le bail, puis sélectionnez **Créer des échéanciers**.
3. Sur la nouvelle page **Détails du bail**, sélectionnez **Registres**.
4. Sur la page **Registre de location**, sur l’onglet **Échange d’informations financières et de reporting**, vérifiez les valeurs des champ **Droit d’utilisation de l’actif initial en devise comptable** et **Droit d’utilisation de l’actif initial de la devise de déclaration**. Chacun de ces champs affiche le solde du droit d’utilisation de l’actif converti dans la devise correspondante. Ces champs sont mis à jour chaque fois que vous modifiez des informations financières. Sélectionnez **Créer des échéanciers** avant de confirmer l’échéancier de paiement.

    L’entrée de journal de comptabilisation initiale enregistre le droit d’utilisation de l’actif qui utilise les taux de change indiqués sur le contrat de location. L’entrée de journal comprend également les valeurs des champs **Droit d’utilisation de l’actif initial en devise comptable** et **Droit d’utilisation de l’actif initial de la devise de déclaration**.

## <a name="subsequent-measurement-for-foreign-currency-leases"></a>Évaluation ultérieure des locations en devises étrangères

Le plan d’amortissement affiche les montants de la dotation aux amortissements attendus dans la devise de déclaration, la devise comptable et la devise de transaction.

Pour afficher les soldes du droit d’utilisation de l’actif et les montants d’amortissement dans la devise de déclaration ou la devise comptable, ouvrez le **Plan d’amortissement des actifs** et cochez la case **Afficher les montants en devise comptable** ou **Afficher les montants en devise de déclaration**.

Lorsque vous créez les entrées de journal des dotations aux amortissements par rapport à une location libellée dans une devise étrangère, l’écriture utilise les taux de change répertoriés sur la location. Elle utilise également les valeurs des champs **Droit d’utilisation de l’actif initial en devise comptable** et **Droit d’utilisation de l’actif initial de la devise de déclaration**.

Le montant final de la dotation aux amortissements peut être calculé en utilisant un taux de change légèrement différent, de sorte que le droit d’utilisation de l’actif est entièrement amorti à la fois dans la devise comptable et dans la devise de déclaration.

Si le bail a été reclassé en **Loyer différé**, le système efface automatiquement les taux de change des devises de comptabilité et de déclaration, s’ils ont déjà été définis.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
