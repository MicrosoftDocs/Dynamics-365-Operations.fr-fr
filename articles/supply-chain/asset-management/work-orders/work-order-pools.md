---
title: Regroupements d'ordres de travail
description: Cette rubrique décrit comment utiliser les regroupements d'ordres de travail dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 069fa02073808fd7bbaac9bc1603e49ce4d450eb
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875652"
---
# <a name="work-order-pools"></a>Regroupements d'ordres de travail


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Vous pouvez utiliser les regroupements d'ordres de travail pour regrouper les ordres de travail qui ont un événement commun. Par exemple, vous pouvez créer des regroupements d'ordres de travail selon

- les équipes de travail, par exemple, Équipe de maintenance A, Équipe de maintenance B  

- les qualifications professionnelles, par exemple, électriciens ou plombiers  

- les emplacements physiques  

- les calendriers, par exemple, semaines ou autres périodes  


Si nécessaire, un ordre de travail peut être placé dans de nombreux regroupements d'ordres de travail.


## <a name="create-work-order-pool"></a>Créer un regroupement d'ordres de travail

Dans le champ **Tous les regroupements d'ordres de travail** ou **Regroupements d'ordres de travail actifs**, vous pouvez obtenir une vue d'ensemble de vos regroupements d'ordres de travail et créer de nouveaux regroupements.

1. Cliquez sur **Gestion des actifs** > **Commun** > **Regroupements d'ordres de travail** > **Tous les regroupements d'ordres de travail** ou **Regroupements d'ordres de travail actifs**.

2. Cliquez sur **Nouveau**.

3. Insérez un ID de regroupement d'ordres de travail dans le champ **Regroupement**, et un nom de compteur dans le champ **Nom**.

4. Sélectionnez « Oui » sur le bouton à bascule **Actif** pour indiquer que le regroupement des ordres de travail est actif.

5. Sélectionnez « Oui » sur le bouton à bascule **Supprimer les relations des ordres de travail** si vous souhaitez que les ordres de travail soient automatiquement supprimés du regroupement des ordres de travail.

6. Dans le champ **Supprimer l'état du cycle de vie**, sélectionnez l'état du cycle de vie de l'ordre de travail. Par exemple, l'état du cycle de vie de l'ordre de travail pour exécuter un ordre de travail peut être défini pour supprimer automatiquement les relations avec les regroupements d'ordres de travail.

7. Vous pouvez commencer à ajouter immédiatement des ordres de travail à votre regroupement d'ordres de travail. Dans l'organisateur **Ordres de travail**, cliquez sur **Ajouter une ligne**.

8. Sélectionnez un ordre de travail dans le champ **Ordre de travail**. Les champs associés sont alors mis à jour automatiquement.

9. Répétez les étapes 7-8 si vous souhaitez ajouter plus d'ordres de travail.

10. Dans le champ **Ordre de tri**, vous pouvez indiquer si les ordres de travail doivent être effectués dans un certain ordre. Insérez des chiffres 1, 2, 3, etc. pour indiquer un ordre spécifique pour les ordres de travail sélectionnés.

11. Cliquez sur le bouton **Ordres de travail** pour voir une liste de tous les ordres de travail inclus dans le regroupement d'ordres de travail.

12. Cliquez sur le bouton **Capacité maximale** pour ouvrir **Capacité maximale** afin de calculer et d'afficher la capacité maximale pour le programme de maintenance, les ordres de travail non planifiés et les ordres de travail planifiés.

13. Cliquez sur le bouton **Prévision d'article** pour ouvrir **Prévision d'article** afin de calculer et d'afficher les prévisions pour les articles (pièces détachées et autres articles requis) associées au programme de maintenance, aux ordres de travail non planifiés et aux ordres de travail planifiés.

14. Cliquez sur le bouton **Demande d'achat de l'ordre de travail** pour ouvrir la liste **Demande d'achat de l'ordre de travail** et voir une liste des demandes d'achat en lien avec les ordres de travail dans le regroupement d'ordres de travail.

15. Cliquez sur le bouton **Achat de l'ordre de travail** pour ouvrir la liste **Achat de l'ordre de travail** et voir une liste des commandes fournisseur en lien avec les ordres de travail dans le regroupement d'ordres de travail.

>[!NOTE]
>Lorsqu'un regroupement d'ordres de travail n'est plus approprié pour la planification de votre travail, définissez la case **Actif** pour ce regroupement sur « Non » dans la vue de liste **Regroupement des ordres de travail**.

Cochez la case **Supprimer les relations de l'ordre de travail** si vous souhaitez supprimer toutes les lignes de l'ordre de travail, par exemple pour créer un regroupement vide que vous pouvez ensuite utiliser pour d'autres ordres de travail. Pensez à activer la case à cocher **Supprimer les relations de l'ordre de travail** si vous souhaitez utiliser le regroupement des ordres de travail pour créer ultérieurement des relations de l'ordre de travail.


![Figure 1](media/22-work-orders.png)


## <a name="add-work-order-to-a-work-order-pool"></a>Ajouter un ordre de travail à un regroupement d'ordres de travail

Comme décrit dans la section ci-dessus, vous pouvez ajouter des ordres de travail à un regroupement d'ordres de travail lorsque vous créez le regroupement. Vous pouvez également ajouter un ordre de travail à un regroupement d'ordres de travail depuis une liste **Tous les ordres de travail**.

1. Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l'ordre de travail dans la liste et cliquez sur **Regroupement d'ordres de travail**.

3. Sélectionnez « Ajouter » dans le champ **Ajouter/supprimer**.

4. Sélectionnez le regroupement d'ordres de travail dans le champ **Regroupement**.

5. Cliquez sur **OK**.

6. Après avoir ajouté un ordre de travail à un regroupement d'ordres de travail, si vous souhaitez placer l'ordre de travail dans un ordre spécifique dans le regroupement : ouvrez une des pages de liste de regroupement des ordres de travail, sélectionnez le regroupement et cliquez sur **Modifier**, et ajuster l'ordre de tri des ordres de travail inclus dans le regroupement sur l'écran **Regroupement des ordres de travail** > organisateur **Ordre de travail** > champ **Ordre de tri**.

Si vous souhaitez supprimer l'ordre de travail sélectionné depuis un regroupement d'ordres de travail, sélectionnez « Supprimer » à l'étape 3.

