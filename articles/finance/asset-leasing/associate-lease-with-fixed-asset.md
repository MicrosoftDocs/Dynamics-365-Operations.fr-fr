---
title: Associer des immobilisations à des baux
description: La rubrique explique comment associer une immobilisation existante à un nouveau bail.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 02a17b8c995e8aa97384d8b855afb688324017d6
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881346"
---
# <a name="associate-fixed-assets-with-leases"></a>Associer des immobilisations à des baux

[!include [banner](../includes/banner.md)]

La rubrique explique comment associer une immobilisation existante à un nouveau bail. Lorsque vous associez une immobilisation à un bail, la valeur du droit d’utilisation de l’actif lors de la comptabilisation initiale sera le coût d’acquisition de l’immobilisation.

Avant de pouvoir associer une immobilisation à un bail, vous devez créer un enregistrement pour l’immobilisation dans Immobilisations. Puis, sur la page **Récapitulatif du bail**, vous devez créer un bail et lier l’actif à ce bail.

1. Ajouter un bail en suivant les étapes dans [Ajouter ou copier des baux](add-lease.md). Sur la page **Ajouter un bail**, dans le champ **Numéro d’immobilisation**, sélectionnez l’actif qui n’a pas encore été acquis.
2. Sélectionnez **Registres** et confirmez le programme de paiement.
3. Sélectionnez **Comptabilisation initiale**.
4. Sélectionnez **Journal de location d’actifs**.

    L’entrée de journal de comptabilisation initiale pour le bail débite l’immobilisation pour le montant généralement débité sur le compte de droit d’utilisation de l’actif.

    Vous pouvez maintenant afficher le type de transaction et le registre pour l’immobilisation.

5. Sélectionnez **Détails du journal**.
6. Sélectionnez **Lignes** pour afficher les lignes individuelles de l’entrée de journal.
7. Sélectionnez la ligne de journal qui contient l’actif, puis sélectionnez l’onglet **Immobilisations**.

    L’onglet **Immobilisations** affiche le type de transaction et le registre. Par défaut, le champ **Type de transaction** est défini sur **Acquisition**, et le champ **Registre** est défini sur le registre actuel de l’immobilisation.

Une fois que vous avez validé l’entrée de journal de comptabilisation initiale, la transaction apparaît comme une transaction d’acquisition pour l’immobilisation. Pour afficher la table des transactions, accédez à **Immobilisations \>Immobilisations \> Immobilisations**, sélectionnez l’actif approprié, puis sélectionnez **Évaluations**. Vous devez voir que l’entrée de journal de comptabilisation initiale a créé une transaction d’acquisition pour l’immobilisation spécifiée.

L’immobilisation peut désormais être amortie à l’aide de la fonctionnalité d’amortissement standard dans Immobilisations. Pour plus d’informations sur l’amortissement, voir [Méthodes et conventions d’amortissement](../fixed-assets/depreciation-methods-conventions.md).

> [!NOTE]
> Si vous associez une immobilisation à un bail, les boutons **Amortissement des actifs** et **Dépréciation du bail** sont désactivés dans la location d’actifs. Vous pouvez afficher les transactions d’amortissement des immobilisations et de dépréciation de location à partir des immobilisations. Le bouton **Transactions d’actif**, qui ouvre un formulaire de demande est également désactivé. Vous pouvez également ouvrir le formulaire de demande **Transactions d’actif** dans Immobilisations.  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
