---
title: Regroupements d'ordres de travail
description: Cette rubrique décrit comment utiliser les regroupements d'ordres de travail dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 161244cb4451ddc7b13b579fd02e828a61adeea4
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626360"
---
# <a name="work-order-pools"></a>Regroupements d'ordres de travail

[!include [banner](../../includes/banner.md)]


Vous pouvez utiliser les regroupements d'ordres de travail pour regrouper les ordres de travail qui ont un événement commun. Voici quelques exemples de ce pour quoi vous pouvez créer des regroupements d'ordres de travail :

- Les équipes de travail, par exemple, Équipe de maintenance A ou Équipe de maintenance B  

- Les qualifications professionnelles, par exemple, électriciens ou plombiers  

- Les emplacements physiques  

- Les calendriers, comme les semaines ou autres périodes  

Au besoin, vous pouvez placer un ordre de travail dans plusieurs regroupements d'ordres de travail.


## <a name="create-a-work-order-pool"></a>Créer un regroupement d'ordres de travail

Sur la page de liste **Tous les regroupements d'ordres de travail** ou **Regroupements d'ordres de travail actifs**, vous pouvez obtenir une vue d'ensemble de vos regroupements d'ordres de travail et créer de nouveaux regroupements.

1. Sélectionnez **Gestion des actifs** > **Commun** > **Regroupements d'ordres de travail** > **Tous les regroupements d'ordres de travail** ou **Regroupements d'ordres de travail actifs**.

2. Sélectionnez **Nouveau**.

3. Dans le champ **Regroupement**, entrez un ID pour le regroupements d'ordres de travail.

4. Dans le champ **Nom**, entrez un nom.

5. Définissez l'option **Active** sur **Oui** pour indiquer que le regroupement des ordres de travail est actif.

6. Définissez l'option **Supprimer les relations des ordres de travail** sur **Oui** si vous souhaitez que les ordres de travail soient automatiquement supprimés du regroupement des ordres de travail.

7. Dans le champ **Supprimer l'état du cycle de vie**, sélectionnez l'état du cycle de vie de l'ordre de travail. Par exemple, l'état du cycle de vie de l'ordre de travail pour exécuter un ordre de travail peut être défini pour supprimer automatiquement les relations avec les regroupements d'ordres de travail.

    Vous pouvez commencer à ajouter immédiatement des ordres de travail à votre regroupement d'ordres de travail.

8. Dans l'organisateur **Ordres de travail**, sélectionnez **Ajouter une ligne**.

9. Dans le champ **Ordre de travail**, sélectionnez un ordre de travail. Les champs associés sont alors mis à jour automatiquement.

10. Répétez les étapes 8 à 9 pour ajouter d'autres ordres de travail.

11. Si les ordres de travail que vous avez ajoutés doivent être effectués dans un ordre spécifique, dans le champ **Ordre de tri**, vous pouvez entrer les numéros **1**, **2**, **3**, etc. pour spécifier cet ordre.

12. Pour afficher une liste de tous les ordres de travail inclus dans le regroupement des ordres de travail, dans le volet Actions, sous l'onglet **Regroupement des ordres de travail**, dans le groupe **Afficher le regroupement des ordres de travail associés**, sélectionnez **Ordre de travail** pour ouvrir la page de liste **Tous les ordres de travail**.

13. Pour calculer et afficher la charge maximale du programme de maintenance, les ordres de travail non-programmés, et les ordres de travail prévus, dans le volet Actions, sous l'onglet **Regroupement des ordres de travail**, dans le groupe **Afficher le regroupement des ordres de travail associés**, sélectionnez **Charge maximale** pour ouvrir la boîte de dialogue **Calculer la charge maximale**.

14. Pour calculer et afficher des prévisions d'articles (pièces détachées ou autres articles requis) associées au programme de maintenance, les ordres de travail non-programmés, et les ordres de travail prévus, dans le volet Actions, sous l'onglet **Regroupement des ordres de travail**, dans le groupe **Afficher le regroupement des ordres de travail associés**, sélectionnez **Prévision d'article** pour ouvrir la boîte de dialogue **Calculer la prévision d'article**.

15. Pour afficher une liste des demandes d'achat associées aux ordres de travail du regroupements des ordres de travail, dans le volet Actions, sous l'onglet **Regroupement des ordres de travail**, dans le groupe **Approvisionnement**, sélectionnez **Demande d'achat de l'ordre de travail** pour ouvrir la page de liste **Demande d'achat de l'ordre de travail**.

16. Pour afficher une liste des commandes fournisseur associées aux ordres de travail du regroupements des ordres de travail, dans le volet Actions, sous l'onglet **Regroupement des ordres de travail**, dans le groupe **Approvisionnement**, sélectionnez **Achats de l'ordre de travail** pour ouvrir la page de liste **Achats de l'ordre de travail**.

>[!NOTE]
>Lorsqu'un regroupement d'ordres de travail n'est plus approprié pour la planification de votre travail, définissez l'option **Actif** pour ce regroupement sur **Non** dans la vue de liste de la page **Regroupement des ordres de travail**.

Pour supprimer toutes les lignes d'ordre de travail, définissez l'option **Supprimer les relations des ordres de travail** sur **Oui**. Cette option est utile si, par exemple, pour créer un regroupement vide que vous pouvez utiliser ultérieurement pour d'autres ordres de travail. Si vous êtes prêt à utiliser le regroupement des ordres de travail pour créer ultérieurement des relations de l'ordre de travail, n'oubliez pas de définir l'option **Supprimer les relations des ordres de travail** sur **Non**.

L'illustration suivante présente un exemple de la liste de page **Regroupement des ordres de travail**.

![Figure 1](media/22-work-orders.png)


## <a name="add-a-work-order-to-a-work-order-pool"></a>Ajouter un ordre de travail à un regroupement d'ordres de travail

Comme décrit dans la section précédente, vous pouvez ajouter des ordres de travail à un regroupement d'ordres de travail lorsque vous créez ce regroupement. Vous pouvez également ajouter des ordres de travail à un regroupement des ordres de travail dans la page de liste **Tous les ordres de travail** ou **Ordres de travail actifs**.

1. Sélectionnez l'ordre de travail puis, dans le volet Actions, sous l'onglet **Ordre de travail**, dans le groupe **Tenir à jour**, sélectionnez **Regroupement des ordres de travail**.

2. Sélectionnez l'ordre de travail dans la liste et cliquez sur **Regroupement d'ordres de travail**.

3. Dans la boîte de dialogue **Tenir à jour le regroupement des ordres de travail**, dans le champ **Ajouter/supprimer**, sélectionnez **Ajouter**.

4. Dans le champ **Regroupement**, sélectionnez le regroupement des ordres de travail.

5. Cliquez sur **OK**.

6. Pour mettre l'ordre de travail que vous avez ajouté dans un ordre spécifique dans le regroupement des ordres de travail, dans la page de liste **Tous les regroupements des ordres de travail** ou **Regroupements des ordres de travail actifs**, sélectionnez le regroupement, puis sélectionnez **Modifier**. Puis, dans la page **Regroupement des ordres de travail**, sous l'organisateur **Ordres de travail**, utilisez le champ **Ordre de tri** pour ajuster l'ordre de tri des ordres de travail inclus dans le regroupement.

Pour supprimer un ordre de travail depuis un regroupement d'ordres de travail, répétez ces étapes, mais sélectionnez **Supprimer** à l'étape 3.

