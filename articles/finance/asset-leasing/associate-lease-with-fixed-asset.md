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
ms.openlocfilehash: bd55d433b0961b8b210b9c28d7340ff880635a85
ms.sourcegitcommit: 3af457fc216bd0020843291ca57fd379acb53c96
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2021
ms.locfileid: "7392472"
---
# <a name="associate-fixed-assets-with-leases"></a>Associer des immobilisations à des baux

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

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

Lorsqu’un contrat de location est associé à une immobilisation, le champ **Durée de vie** sur le livre des immobilisations est mis à jour pour correspondre à la plus petite valeur parmi les critères suivants : 

 - Durée de vie utile de l’actif
 - La durée du bail du registre associé

Si le champ **Transfert de propriété** est défini sur **Oui** pour le registre des baux, la valeur dans le champ **Durée de vie** sera toujours la durée de vie utile de l’actif. 
 
La durée de vie est mise à jour à chaque ajustement du bail afin de s’assurer que le droit d’utilisation de l’actif est amorti sur la durée du bail, comme s’il était amorti en leasing d’actifs.

> [!NOTE]
> Si vous associez une immobilisation à un bail, les boutons **Amortissement des actifs** et **Dépréciation du bail** sont désactivés dans la location d’actifs. Vous pouvez afficher les transactions d’amortissement des immobilisations et de dépréciation de location à partir des immobilisations. Le bouton **Transactions d’actif**, qui ouvre un formulaire de demande est également désactivé. Vous pouvez également ouvrir le formulaire de demande **Transactions d’actif** dans Immobilisations.  

Les pages **Immobilisations** et **Registre des immobilisations** affichent l’ID de bail associé à une immobilisation. Si une immobilisation est associée à un bail, l’ID du bail et la description du bail sont affichés sur le raccourci **Informations du bail** sur la page **Immobilisations**. Pour les registres d’immobilisations associés à des registres des baux, les champs **ID de bail**, **Description du bail** et **Type de registre** affichent des informations pour le registre d’immobilisations sélectionné sur le raccourci **Informations du bail**, pour indiquer qu’il est associé à un registre de baux.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
