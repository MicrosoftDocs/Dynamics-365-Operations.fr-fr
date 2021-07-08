---
title: La quantité que vous essayez de mettre à jour dépasse la quantité reçue/livrée.
description: Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui dépasse la quantité de travail qui a été prélevée et réservée pour la commande client.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 66d9cd80cc61e00d1d88ab4f59d03054d746cdd9
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249103"
---
# <a name="quantity-that-youre-trying-to-update-exceeds-the-receiveddelivered-quantity"></a>La quantité que vous essayez de mettre à jour dépasse la quantité reçue/livrée

Code d’erreur : SYS7676

## <a name="symptoms"></a>Symptômes

Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui dépasse la quantité de travail qui a été prélevée et réservée pour la commande client.

Lorsque vous essayez de générer un bon de livraison, le système affiche le message d’erreur suivant :

> La quantité que vous essayez de mettre à jour dépasse la quantité reçue/livrée.

Par conséquent, vous ne pouvez pas générer le bon de livraison pour le chargement.

## <a name="cause"></a>Cause

La quantité retirée ne correspond pas à celle créée sur la ligne de chargement. Par exemple, ce problème peut se produire si la quantité de la ligne de chargement, la quantité créée par le travail ou la quantité prélevée n’est pas précise.

## <a name="resolution"></a>Résolution

Le chargement ou l’expédition est actuellement dans un état où la génération du bon de livraison échoue. Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :

- Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.
- Ajustez la quantité de la ligne de chargement.
- Annulez tous les enregistrements de prélèvement et refaites le prélèvement.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent

Procédez comme suit pour examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Sélectionnez le chargement pour lequel l’expédition ne peut pas être générée.
1. Dans l’organisateur **Lignes de chargement**, sélectionnez la ligne de chargement.
1. Notez la valeur du champ **Quantité créée**.
1. Dans le volet Actions, sous l’onglet **Chargements**, dans le groupe **Informations associées**, cliquez sur **Travail**.
1. Vérifiez que le travail a été terminé à l’emplacement d’expédition finale et que la quantité retirée correspond à celle créée sur la ligne de chargement.
1. Répétez cette procédure pour toutes les lignes de chargement afin de vous assurer que tous les critères sont remplis.

### <a name="adjust-the-load-line-quantity"></a>Ajuster la quantité de la ligne de chargement

Suivez la procédure suivante pour ajuster la quantité de la ligne de chargement.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Sélectionnez le chargement pour lequel le bon de livraison ne peut pas être généré.
1. Dans le volet Actions, dans l’onglet  **Expédier et recevoir**, dans le groupe  **Annuler**, sélectionnez  **Annuler la confirmation de livraison**.
1. Sur l’onglet  **Lignes de chargement**, sélectionnez la ligne de chargement de l’article qui cause le problème.
1. Sélectionnez **Réduire la quantité prélevée** pour ajuster la quantité prélevée.
1. Définissez le champ **Réduire la ligne de chargement** de manière à refléter les ajustements sur la ligne de chargement.

### <a name="reverse-all-pick-registrations-and-redo-picking"></a>Annuler tous les enregistrements de prélèvement et refaire le prélèvement

Si quelqu’un a utilisé l’enregistrement de prélèvement pour fermer une ligne de chargement sans travail, un écart peut se produire entre la quantité de la ligne de chargement et la quantité prélevée. Dans ce cas, l’enregistrement manuel du prélèvement doit être annulé et le prélèvement doit ensuite être effectué à l’aide de l’application mobile Warehouse Management.

Utilisez la procédure suivante pour annuler l’enregistrement du prélèvement.

1. Accédez à **Comptabilité client \> Commandes \> Toutes les commandes**.
1. Sélectionnez la commande client pour laquelle vous ne pouvez pas valider un bon de livraison pour le chargement.
1. Sur l’onglet  **Lignes de commande client**, sélectionnez la ligne de commande client pour laquelle l’enregistrement du prélèvement a été effectué.
1. Sélectionnez **Mettre à jour la ligne \> Prélever** pour annuler le prélèvement des articles.
