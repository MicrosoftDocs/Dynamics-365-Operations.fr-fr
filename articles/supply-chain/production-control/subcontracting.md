---
title: Sous-traitance
description: Cette rubrique vous aidera à établir une présentation de la sous-traitance en production dans Microsoft Dynamics 365 for Finance and Operations.
author: christophernread
manager: AnnBe
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 55b516f928eadea9b7ddbb1192db79f3ab7fa204
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568386"
---
# <a name="subcontracting"></a>Sous-traitance

[!include [banner](../includes/banner.md)]

Cette rubrique vous aidera à établir une présentation de la sous-traitance en production dans Microsoft Dynamics 365 for Finance and Operations. La première partie de cette rubrique décrit le paramétrage des données. La deuxième partie vous explique les étapes de la procédure.

## <a name="target-audience"></a>Public cible

Dans cette rubrique, vous apprendrez comment paramétrer la sous-traitance de la fabrication. Vous utiliserez les données existantes dans l'entité juridique HQUS pour effectuer le paramétrage de base d'un flux d'activités de sous-traitance. Les données de démonstration de l'entité juridique HQUS comprennent des paramètres de configuration qui ont été prédéfinis pour prendre en charge les étapes de la procédure. Même si la procédure traite des principaux points sensibles et défis pour divers rôles, elle peut être effectuée par l'administrateur du système.

## <a name="demo-scenario"></a>Scénario de démonstration

Dans l'entité juridique HQUS, des haut-parleurs haut de gamme sont fabriqués. Au cours du processus de fabrication, les haut-parleurs passent par les trois opérations suivantes.

- **Préassemblage** – L'enceinte est assemblée. Le matériel pour l'enceinte est prélevé dans l'entrepôt de matières premières avant le démarrage de l'opération.
- **Revêtement** – Une fois que l'enceinte a été assemblée, elle doit être recouverte. Cette opération est effectuée par un fournisseur (sous-traitant). L'enceinte préassemblée est expédiée au sous-traitant en revêtement avec deux matières.
- **Finition** – Une fois que l'enceinte préassemblée a été recouverte par le sous-traitant, elle est renvoyée à l'entité juridique HQUS afin que l'assemblage final du haut-parleur puisse être terminé.

L'illustration suivante présente les trois opérations et les matières utilisées.

![Opérations de préassemblage, de revêtement et de finition et matières utilisées](./media/subcontract01_operations-materials.png)

## <a name="setup"></a>Configuration

Avant de commencer la procédure, vous devez paramétrer les données.

### <a name="set-up-the-finished-product"></a>Paramétrer le produit fini

Cette procédure vous guide dans le paramétrage du produit lancé D8100, « Enceinte avec revêtement ».

1. Sélectionnez **Gestion des informations sur les produits \> Produits \> Produits lancés** pour ouvrir la page **Détails des produits lancés**.
2. Dans le champ de filtre rapide, entrez **D8100** pour rechercher le produit lancé existant.

    ![Filtrage du produit lancé D8100 dans la page Détails des produits lancés](./media/subcontract02_filtering-released-products.png)

3. Dans le volet Actions, sous l'onglet **Ingérieur**, sélectionnez **Gamme** pour ouvrir la page **Gamme**.

    La page **Gamme** affiche les huit versions de gamme pour le produit lancé D8100. Les huit versions de gamme sont réparties sur quatre gammes dans le site 1 et le site 5. La gamme 000400 est utilisée pour l'évaluation des coûts, la gamme 00041 est utilisée lorsque l'opération de revêtement est une opération interne et la gamme 00042 est utilisée lorsque l'opération de revêtement est une opération externe.

    ![Huit versions de gamme dans la page Gamme](./media/subcontract03_route-page.png)

4. Dans le volet supérieur, dans la grille **Versions**, sélectionnez la version de gamme **00042** pour le site **5**.
5. Dans le volet inférieur, sous l'onglet **Vue d'ensemble**, sélectionnez l'opération **20** (**Cbnt CtSc**) dans la grille.

    ![Opération 20 pour la version de gamme 00042 pour le site 5 sélectionné](./media/subcontract04_route-version-operation.png)

6. Sélectionnez l'onglet **Général**.

    Notez que le champ **Type de gamme** est défini sur **Fournisseur**. Cette valeur indique que l'opération 20 (Cbnt CtSc) est une opération sous-traitée.

    ![Champ Type de gamme défini sur Fournisseur dans l'onglet Général](./media/subcontract05_general-tab.png)

7. Sélectionnez l'onglet **Demandes de ressources**.

    Les fonctionnalités seront utilisées pour trouver une ressource applicable lors de la planification de la production. Pour l'opération 20 (Cbnt CtSc), notez qu'une ressource avec deux fonctionnalités, **Revêtement** et **Enceintes avec revêtement**, est requise.

    ![Fonctionnalités Revêtement et Enceintes avec revêtement dans l'onglet Demandes de ressources](./media/subcontract06_resource-requirements-tab.png)

8. Sélectionnez **Ressources applicables** pour ouvrir la boîte de dialogue **Ressources applicables**.

    Trois ressources correspondent aux demandes de ressources pour l'opération. Notez que les ressources 8851 et 8852 sont de type **Fournisseur**.

    ![Trois ressources appropriées dans la boîte de dialogue Ressources applicables](./media/subcontract07_applicable-resources-dialog.png)

9. Cliquez sur **OK** pour fermer la boîte de dialogue **Ressources applicables** et revenir à la page **Gamme**.
10. Fermez la page **Gamme** pour revenir à la page **Détails des produits lancés**.

    ![Page Détails des produits lancés](./media/subcontract08_released-product-details-page.png)

11. Dans le volet Actions, sous l'onglet **Ingérieur**, sélectionnez **Versions de nomenclature** pour ouvrir la page **Versions de nomenclature**.

    La page **Versions de nomenclature** affiche les quatre versions de nomenclature pour le produit lancé D8100. La nomenclature 000040 est utilisée pour l'évaluation des coûts et la planification, la nomenclature 000041 est utilisée si l'opération de revêtement est effectuée en interne et les nomenclatures 000042 et 000043 sont utilisées si l'opération de revêtement est sous-traitée.

    Notez que l'article S8050 est un produit du type d'article **Service**. Cet article représente le travail sous-traité.

    ![Quatre versions de nomenclature dans la page Versions de nomenclature](./media/subcontract09_bom-versions-page.png)

12. Dans l'organisateur **Lignes de nomenclature**, sélectionnez **Modifier** pour ouvrir la boîte de dialogue **Modifier une ligne de nomenclature**.

    Lorsqu'un ordre de fabrication est créé et estimé pour le produit lancé D8100, une commande fournisseur est automatiquement générée pour l'article S8050. Cette commande fournisseur sera associée à l'ordre de fabrication. Pour que les commandes fournisseur soient automatiquement générées, le champ **Type de ligne** doit être défini sur **Fournisseur**, et le compte fournisseur du sous-traitant doit être sélectionné. Dans ce cas, le compte fournisseur est US-801.

    Notez que la ligne de nomenclature est associée à l'opération de revêtement par le biais du numéro d'opération (dans ce cas, 20).

    ![Boîte de dialogue Modifier une ligne de nomenclature](./media/subcontract10_edit-bom-line-dialog.png)

### <a name="create-a-password-for-warehouse-workers"></a>Créer un mot de passe pour les magasiniers

Vous devez définir un mot de passe pour les magasiniers qui utilisent l'appareil portable.

1. Sélectionnez **Gestion des entrepôts \> Paramétrage \> Collaborateur** pour ouvrir la page **Utilisateurs du travail**.
2. Dans l'organisateur **Utilisateurs**, sélectionnez la ligne de l'utilisateur **51**.

    ![Page Utilisateurs du travail](./media/subcontract11_work-users-page.png)

3. Sélectionnez **Réinitialiser le mot de passe**.
4. Dans les champs **Mot de passe** et **Confirmer le mot de passe**, entrez **1**.
5. Sélectionnez **Définir le mot de passe**.

## <a name="step-by-step-walkthrough"></a>Procédure pas-à-pas

**Scénario et arrière-plan**

Un ordre de fabrication de 10 pièces est créé pour le produit D8100, « Enceinte avec revêtement ». Le revêtement des enceintes est une opération sous-traitée qui est réalisée par le fournisseur US-801, Perfect Coating Solutions. L'ordre de fabrication est composée de trois opérations. Dans la première opération, l'enceinte est préassemblée comme une opération interne. Le matériel de préassemblage est lancé pour prélèvement dans l'entrepôt de matières premières. Une fois le préassemblage terminé, l'enceinte préassemblée est envoyée à Perfect Coating Solutions avec deux matières requises pour l'opération de revêtement. Lorsque l'enceinte avec revêtement est renvoyée par le fournisseur, elle passe par une opération d'assemblage interne finale avant d'être déclarée comme terminée.

1. Sélectionnez **Contrôle de la production \> Ordres de fabrication \> Tous les ordres de fabrication** pour ouvrir la page **Tous les ordres de fabrication**.
2. Dans le volet Actions, sélectionnez **Nouvel ordre de fabrication** pour ouvrir la boîte de dialogue **Créer un ordre de fabrication**.

    ![Boîte de dialogue Crée un ordre de fabrication](./media/subcontract12_create-production-order-dialog.png)

3. Dans le champ **Numéro d'article**, sélectionnez **D8100**.
4. Une fois le numéro d'article sélectionné, les champs de la dimension de stock s'affichent. Dans le champ **Couleur**, sélectionnez **Chrome**.

    Une zone de message apparaît pour vous demander si les versions actives de la nomenclature et de la gamme doivent être insérées.

    ![Zone de message](./media/subcontract13_message-box.png)

5. Cliquez sur **Oui**. 

    Dans la boîte de dialogue **Créer un ordre de fabrication**, les versions actives de la nomenclature et de la gamme du produit D8100 sont automatiquement sélectionnées dans les champs **Numéro de nomenclature** et **Numéro de gamme**, respectivement. Dans ce cas, la nomenclature **000040** et la gamme **000040** sont sélectionnées.
    
    > [!NOTE]
    > Pour la nomenclature et la gamme, la version 000040 est utilisée pour l'évaluation des coûts et la planification.

6. Dans le champ **Site**, sélectionnez **5**.
7. Dans le champ **Entrepôt**, sélectionnez **51**.
8. Dans les champs **Numéro de nomenclature** et **Numéro de gamme**, remplacez la valeur qui a été automatiquement sélectionnée par **000042**.

    > [!NOTE]
    > Pour la nomenclature et la gamme, la version 000042 est utilisée pour sous-traiter le revêtement de l'enceinte au fournisseur US-801.

    ![Valeurs définies dans la boîte de dialogue Créer un ordre de fabrication](./media/subcontract14_create-production-order-dialog-set.png)

9. Sélectionnez **Créer** pour créer l'ordre de fabrication et revenir à la page **Tous les ordres de fabrication**.

    ![Nouvel ordre de fabrication dans la page Tous les ordres de fabrication](./media/subcontract15_new-production-order.png)

10. Dans le volet Actions, sous l'onglet **Ordre de fabrication**, sélectionnez **Estimation** pour ouvrir la boîte de dialogue **Estimation**.

    ![Boîte de dialogue Estimation](./media/subcontract16_estimate-dialog.png)

11. Cliquez sur **OK** pour confirmer l'estimation et revenir à la page **Tous les ordres de fabrication**.

    > [!NOTE]
    > Une fois l'ordre de fabrication estimé, la commande fournisseur pour l'article de service S8050 est générée pour le fournisseur US-801.

12. Dans le volet Actions, sous l'onglet **Ordre de fabrication**, sélectionnez **Nomenclature** pour ouvrir la page **Nomenclature**, dans laquelle vous pouvez afficher les lignes de nomenclature pour l'ordre de fabrication.

    Pour l'article de service S8050, notez qu'il existe une référence à la commande fournisseur générée lorsque l'ordre de fabrication a été estimé.

    ![Lignes de nomenclature de l'ordre de fabrication dans la page Nomenclature](./media/subcontract17_production-order-bom-lines.png)

13. Fermez la page **Nomenclature** pour revenir à la page **Tous les ordres de fabrication**.
14. Dans le volet Actions, sous l'onglet **Planification**, sélectionnez **Planifier les tâches** pour ouvrir la boîte de dialogue **Planification de tâche**.
15. Spécifiez les valeurs suivantes :

    - Dans le champ **Direction de la planification**, sélectionnez **En avant à partir d'aujourd'hui**.
    - Définissez l'option **Capacité finie** sur **Oui**.

    ![Boîte de dialogue Planification de tâche](./media/subcontract18_job-scheduling-dialog.png)

16. Cliquez sur **OK** pour fermer la boîte de dialogue **Planification de tâche** et revenir à la page **Tous les ordres de fabrication**.
17. Dans le volet Actions, sous l'onglet **Planification**, sélectionnez **Gantt** pour ouvrir la page **Diagramme de Gantt - Vue Ressource**.

    Le diagramme de Gantt donne une vue d'ensemble visuelle de la manière dont les tâches de production sont planifiées sur les ressources. Notez que l'opération de revêtement externe comporte trois tâches : une tâche de traitement, une tâche de transport et une tâche de temps d'attente.

    ![Page Diagramme de Gantt - Vue Ressource](./media/subcontract19_gantt-chart.png)

18. Fermez la page **Diagramme de Gantt - Vue Ressource** pour revenir à la page **Tous les ordres de fabrication**.
19. Dans le volet Actions, sous l'onglet **Ordre de fabrication**, sélectionnez **Lancement** pour ouvrir la boîte de dialogue **Lancement**.

    ![Boîte de dialogue Lancement](./media/subcontract20_release-dialog.png)

20. Cliquez sur **OK** pour fermer la boîte de dialogue **Lancement**.
21. Sélectionnez **Contrôle de la production \> Tâches périodiques \> Lancer dans l'entrepôt \> Lancement automatique des lignes de nomenclature et de formule** pour ouvrir la boîte de dialogue **Lancement automatique des lignes de nomenclature et de formule**.

    ![Boîte de dialogue Lancement automatique des lignes de nomenclature et de formule](./media/subcontract21_auto-release-bom-formula-lines-dialog.png)

22. Cliquez sur **OK** pour exécuter la tâche Lancement automatique des lignes de nomenclature et de formule.

    Cette tâche lance le travail de prélèvement des matières premières dans l'entrepôt.

23. Sélectionnez **Contrôle de la production \> Ordres de fabrication \> Tous les ordres de fabrication** pour ouvrir la page **Tous les ordres de fabrication**.
24. Utilisez le champ de filtre rapide pour sélectionner l'ordre de fabrication sur lequel vous travaillez.
25. Dans le volet Actions, sous l'onglet **Entrepôt**, sélectionnez **Détails du travail** pour ouvrir la page **Travail**.

    Notez que les page affiche deux ensembles de travail pour le prélèvement des matières premières. Le premier travail s'applique aux matières premières M8100 et M8101. Ces matières sont consommées par l'opération 10. Le deuxième travail s'applique aux matières M8202 et M8250. Ces matières sont consommées par l'opération 20, qui correspond à l'opération sous-traitée.

    ![Deux ensembles de travail pour le prélèvement des matières premières dans la page Travail](./media/subcontract22_work-page.png)

26. Démarrez l'application d'entrepôt pour traiter le travail d'entrepôt pour l'opération 10.

    <!-- TBD – screen shots for processing pick work for the materials. -->

27. Sélectionnez **Contrôle de la production \> Ordres de fabrication \> Tous les ordres de fabrication** pour ouvrir la page **Tous les ordres de fabrication**.
28. Utilisez le champ de filtre rapide pour sélectionner l'ordre de fabrication sur lequel vous travaillez.
29. Dans le volet Actions, sous l'onglet **Ordre de fabrication**, sélectionnez **Démarrer** pour ouvrir la boîte de dialogue **Démarrer**.
30. Sous l'onglet **Général**, spécifiez les valeurs suivantes :

    - Dans le champ **Du n° opér.**, sélectionnez **10**.
    - Dans le champ **Au n° opér.**, sélectionnez **10**.

    ![Valeurs définies dans l'onglet Général](./media/subcontract23_start-dialog.png)

31. Cliquez sur **OK** pour fermer la boîte de dialogue **Démarrer** et revenir à la page **Tous les ordres de fabrication**.

    Notez que l'ordre de fabrication a maintenant le statut **Commencé**. Les matières pour l'opération 10 sont consommées par une validation automatique du journal des prélèvements. La consommation de temps pour l'opération 10 est comptabilisée par une validation automatique du journal des fiches productions.

32. Démarrez l'application d'entrepôt pour traiter le travail d'entrepôt pour l'opération 20.

    <!-- TBD – screen shots for processing pick work for the materials. -->

33. Dans le volet Actions, sous l'onglet **Ordre de fabrication**, sélectionnez **Démarrer** pour ouvrir la boîte de dialogue **Démarrer**.
34. Sous l'onglet **Général**, spécifiez les valeurs suivantes :

    - Dans le champ **Du n° opér.**, sélectionnez **20**.
    - Dans le champ **Au n° opér.**, sélectionnez **20**.
    - Dans le champ **Quantité**, entrez **10**.
    - Définissez l'option **Valider immédiatement les prélèvements** sur **Non**.

    ![Valeurs définies dans l'onglet Général](./media/subcontract24_general-tab.png)

35. Cliquez sur **OK** pour fermer la boîte de dialogue **Démarrer** et revenir à la page **Tous les ordres de fabrication**.

    Des prélèvements sont créés pour les matières utilisées pour l'opération de revêtement, et pour l'article de service. L'article de service représente le coût de l'opération sous-traitée.

36. Dans le volet Actions, sous l'onglet **Afficher**, sélectionnez **Prélèvements** pour ouvrir la page **Prélèvements**.
37. Sélectionnez les prélèvements qui ne sont pas validés, puis sélectionnez le numéro de journal pour afficher les lignes de journal.

    ![Lignes du journal dans la page Prélèvements](./media/subcontract25_picking-list.png)

38. Dans le volet Actions, sélectionnez **Imprimer** \> **État Liste de prélèvement** pour ouvrir la boîte de dialogue **État Liste de prélèvement**.
39. Définissez l'option **Utiliser la mise en page de note de livraison** sur **Oui**.

    ![Boîte de dialogue État Liste de prélèvement](./media/subcontract26_picking-list-report-dialog.png)

40. Cliquez sur **OK** pour générer un état **Liste de prélèvement**.

    Dans ce cas, une note de livraison du fournisseur est imprimée à partir du journal des prélèvements en production. La note de livraison spécifie les matières qui sont expédiées au fournisseur qui effectue l'opération de revêtement.

    ![État sur la liste des prélèvements](./media/subcontract27_picking-list-report.png)

41. Fermez l'état **Liste de prélèvement** pour revenir à la page **Liste de prélèvement**.
42. Dans le volet Actions, sélectionnez **Valider** pour ouvrir la boîte de dialogue **Valider le journal**.

    ![Boîte de dialogue Valider le journal](./media/subcontract28_post-journal-dialog.png)

43. Cliquez sur **OK** pour fermer la boîte de dialogue **Valider le journal**.
44. Ouvrez la commande fournisseur.

    ![Page Commande fournisseur](./media/subcontract29_purchase-order-page.png)

45. Dans le volet Actions, sous l'onglet **Achats**, sélectionnez **Confirmer**.
46. Sélectionnez **Valider** pour ouvrir la boîte de dialogue **Valider le journal**.
47. Cliquez sur **OK** pour fermer la boîte de dialogue **Valider le journal** et revenir à la page **Commande fournisseur**.
48. Modifiez le prix unitaire de **33** en **40**.

    ![Prix unitaire modifié dans la page Commande fournisseur](./media/subcontract30_unit-price.png)

49. Confirmez à nouveau la commande fournisseur.
50. Accusé de réception de produits.

    ![Boîte de dialogue Validation de l'accusé de réception de produits](./media/subcontract31_posting-product-receipt-dialog.png)

51. Facture d'achat.
52. Mettre à jour le statut de rapprochement.

    ![Page Facture fournisseur](./media/subcontract32_vendor-invoice-page.png)

53. Déclaration de fin.

    ![Boîte de dialogue Déclaration de fin](./media/subcontract33_report-as-finished-dialog.png)

54. Terminer.

    ![Boîte de dialogue Terminer](./media/subcontract34_end-dialog.png)

55. Comparaison du coût.

    ![Graphiques de comparaison du coût](./media/subcontract35_cost-comparison-charts.png)

Paramétrage manquant des données.
