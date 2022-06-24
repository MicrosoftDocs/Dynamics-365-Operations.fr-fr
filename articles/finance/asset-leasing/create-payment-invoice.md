---
title: Créer des factures de paiement
description: Cet article explique comment créer des factures de location mensuelles. Vous pouvez créer des factures pour des locations individuelles ou vous pouvez utiliser un processus par lots pour les créer pour plusieurs baux.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePaymentSchedule
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0ac9efaf6d068377053ae36951f4ad808fcb2438
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886404"
---
# <a name="create-payment-invoices"></a>Créer des factures de paiement

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Vous pouvez créer des factures mensuelles pour des locations individuelles ou vous pouvez utiliser un processus par lots pour les créer pour plusieurs baux. La procédure suivante montre comment créer une entrée de paiement de location individuelle lorsque le paramètre **Payer au fournisseur** sur la page **Configuration du registre de location** est activé.

1. Sur la page **Résumé du bail**, sélectionnez un bail, puis sélectionnez **Registres \> Calendrier de paiement**.
2. Sélectionnez le paiement à effectuer, puis sélectionnez **Créer un journal**. Vous recevez un message indiquant qu’un journal a été créé pour le paiement sélectionné.
3. Sélectionnez **Journaux de facturation**, puis sélectionnez la facture à payer.
4. Sur l’onglet **Lignes**, vérifiez l’écriture de journal avant de la valider dans la comptabilité.

    > [!NOTE]
    > Par défaut, les lignes de facture fournisseur qui sont créées utilisent le profil de validation fournisseur de la page **Paramètres de la comptabilité fournisseurs**.

5. Sélectionnez le journal adéquat, puis sélectionnez la facture à payer.

    Pour cet exemple, le paramètre **Payer au fournisseur** du registre de location est activé. Par conséquent, la facture sera dans le journal des factures. La section **Aperçu** présente un résumé de l’entrée de journal et la section **Lignes** montre les détails des lignes de journal réelles.
    
   Le système verrouille l’édition de certains champs financiers pour éviter tout écart entre les transactions et les échéanciers. Les champs verrouillés incluent : **Compte**, **Montants**, **Dimensions financières**, **Devise** et **Type de transaction**. De plus, vous ne pourrez pas ajouter ou supprimer des lignes d’entrée de journal dans les entrées de journal de location d’actifs, car cela pourrait entraîner des écarts entre les échéanciers et les transactions.

    > [!NOTE]
    > Si le paramètre **Payer au fournisseur** est désactivé, les écritures du journal des paiements seront répertoriées sur la page **Location d’actifs** pour le registre de location, et le système créera une entrée de bail d’actif au lieu d’une facture. L’entrée de paiement de location sera enregistrée dans le nom de journal spécifié dans le champ **Journal mensuel des baux**.

6. Une fois la transaction enregistrée, vous pouvez afficher les informations de transaction et la valeur comptable du passif de location en sélectionnant **Transactions de passif** dans le registre de location.

    Dans l’échéancier de paiement, la case **Journal publié** sera cochée et la ligne affichera le numéro du journal de la facture. Après avoir créé un journal des paiements et une écriture pour ce journal, vous devez contrepasser l’écriture avant de pouvoir la recréer.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
