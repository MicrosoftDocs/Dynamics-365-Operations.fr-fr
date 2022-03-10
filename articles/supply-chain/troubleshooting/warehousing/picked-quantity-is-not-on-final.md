---
title: Vous ne pouvez pas confirmer une expédition car les articles n’ont pas été retirés
description: Vous ne pouvez pas confirmer une expédition car les articles n’ont pas été retirés
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7b57d3151852c9a2880185b7d9414e4246b7efb6429fcfce04c7cdae4ee00e37
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760922"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a>Vous ne pouvez pas confirmer une expédition car les articles n’ont pas été retirés

Code d’erreur : LoadNotPickedAndMovedToFinalShippingLocation

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de confirmer une expédition, le système affiche le message d’erreur suivant :

> Certains des articles nécessaires pour le chargement %1 n’ont pas encore été prélevés et ont été déplacés vers l’emplacement d’expédition final.

Par conséquent, vous ne pouvez pas confirmer l’expédition pour le chargement.

## <a name="cause"></a>Cause

Le chargement ou l’expédition ne peut pas être confirmé dans son état actuel car l’une des conditions suivantes peut exister :

- Le travail associé n’a pas encore été sélectionné et déplacé vers le lieu d’expédition final.
- La quantité retirée ne correspond pas à celle créée sur la ligne de chargement.
- La directive d’emplacement a été configurée avec l’emplacement d’emballage comme emplacement d’expédition final lors de l’utilisation de la conteneurisation du modèle de vague.

## <a name="resolution"></a>Résolution

Le chargement ou l’expédition est actuellement dans un état d’échec. Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :

- Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.
- Annuler les ID de travail qui ont été créés avec l’emplacement d’emballage comme emplacement d’expédition final, reconfigurer la directive d’emplacement et relancer le chargement.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent

Procédez comme suit pour examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Sélectionnez le chargement pour lequel l’expédition ne peut pas être confirmée.
1. Dans l’organisateur **Lignes de chargement**, sélectionnez la ligne de chargement.
1. Notez la valeur du champ **Quantité créée**.
1. Dans le volet Actions, sous l’onglet **Chargements**, dans le groupe **Informations associées**, cliquez sur **Travail**.
1. Vérifiez que le travail a été terminé à l’emplacement d’expédition finale et que la quantité retirée correspond à celle créée sur la ligne de chargement.
1. Répétez cette procédure pour toutes les lignes de chargement afin de vous assurer que tous les critères sont remplis.

### <a name="cancel-the-work-ids-that-have-been-created-with-the-packing-location-as-the-final-shipping-location-reconfigure-the-location-directive-and-rerelease-the-load"></a>Annuler les ID de travail qui ont été créés avec l’emplacement d’emballage comme emplacement d’expédition final, reconfigurer la directive d’emplacement et relancer le chargement

Procédez comme suit pour annuler les ID de travail qui ont l’emplacement d’emballage comme emplacement final de placement avec la conteneurisation automatisée en place.

1. Allez dans **Gestion des entrepôts \> Tâches périodiques \> Nettoyer \> Annuler le travail**.
1. La boîte de dialogue **Annuler le travail** s’ouvre. Dans le champ **ID de travail**, spécifiez l’ID du travail que vous souhaitez annuler. L’ID de travail sélectionné doit avoir une valeur **Statut de travail** *Ouvert*, *En cours*, *Annulé*, *Combiné* ou *Fermé*.
1. Cliquez sur **OK**.
1. Sélectionnez **Oui** pour confirmer que vous souhaitez annuler le travail.
1. Répétez cette procédure pour les autres ID de travail si nécessaire.

Pour en savoir plus, voir [Annuler le travail en entrepôt pour la gestion des exceptions](../../warehousing/cancel-warehouse-work.md).

Utilisez la procédure suivante pour reconfigurer la directive d’emplacement afin qu’elle n’utilise pas l’emplacement d’emballage comme emplacement d’expédition final lorsque la conteneurisation automatisée est configurée pour le modèle de vague.

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Instructions d’emplacements**.
1. Dans le champ **Type d’ordre de travail**, sélectionnez *Commandes client*.
1. Sélectionnez la directive d’emplacement que vous utilisez pour la conteneurisation automatisée.
1. Dans la barre d’outils du raccourci **Actions de directive d’emplacement**, sélectionnez **Modifier la requête**.
1. Dans la boîte de dialogue de l’éditeur de requêtes, sur l’onglet **Plange**, recherchez la ligne où **Champ** est défini sur *Profil d’emplacement*, et vérifiez que le champ **Critères** pour cette ligne n’est pas défini sur un profil d’emplacement qui a un **Type d’emplacement** défini sur *Emballage*. Ajustez le champ **Critères** pour corriger l’emplacement final.

Utilisez la procédure suivante pour libérer le chargement et créer des ID de travail avec l’emplacement d’expédition final correct.

1. Allez dans **Gestion des entrepôts \> Chargements \> Atelier de planification des chargements**.
1. Dans la section **Chargements**, trouvez le chargement qui doit être libéré.
1. Dans la barre d’outils de la section **Chargements**, sélectionnez **Lancer \> Lancement dans l’entrepôt** pour lancer le chargement sélectionné dans l’entrepôt.
1. Répétez cette procédure pour les autres chargements si nécessaire.
