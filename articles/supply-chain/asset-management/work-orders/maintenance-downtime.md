---
title: Temps d'arrêt pour maintenance
description: Cette rubrique décrit le temps d'arrêt pour maintenance dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cc79dc1b5911679586fa560142ada5add1a881d2
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918242"
---
# <a name="maintenance-downtime"></a>Temps d'arrêt pour maintenance


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Vous pouvez créer des enregistrements de temps d'arrêt pour maintenance sur l'actif sélectionné sur un ordre de travail. Cela est utile si vous souhaitez enregistrer le temps d'arrêt pour maintenance sur une ou plusieurs machines dans la zone de production. Premièrement, vous pouvez créer des codes motif de temps d'arrêt pour maintenance que vous souhaitez utiliser, par exemple, la répartition et l'arrêt planifié. Cela est effectué dans **Codes motif de temps d'arrêt pour maintenance**. Ensuite, vous pouvez créer des enregistrements de temps d'arrêt pour maintenance dans **Temps d'arrêt pour maintenance** et ajouter des codes motif appropriés.

## <a name="create-maintenance-downtime-reason-codes"></a>Créer des codes motif de temps d'arrêt pour maintenance

1. Cliquez sur **Gestion des actifs** > **Configuration** > **Ordres de travail** > **Codes motif de temps d'arrêt pour maintenance**.

2. Cliquez sur **Nouveau**.

3. Insérez un ID dans le champ **Code motif de temps d'arrêt pour maintenance**.

4. Insérez un nom pour le code motif dans le champ **Nom**.

5. Sélectionnez la case à cocher **Les indicateurs de performance clés incluent** si le code motif doit être inclus dans les calculs des indicateurs de performance clés des actifs. En général, les arrêts de production planifiés ne doivent pas être inclus dans les calculs des indicateurs de performance clés puisqu'ils n'ont pas d'impact sur les performances prévues.

6. Cliquez sur **Enregistrer**.

![Figure 1](media/15-work-orders.png)


Lorsque vous avez créé les codes motif de temps d'arrêt pour maintenance que vous souhaitez utiliser, vous pouvez créer les enregistrements des temps d'arrêt pour maintenance pour les ordres de travail et les actifs.


## <a name="create-maintenance-downtime-registrations"></a>Créer des enregistrements de temps d'arrêt pour maintenance

1. Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l'ordre de travail et cliquez sur **Temps d'arrêt pour maintenance**.

3. Cliquez sur **Nouveau**.

4. Insérez l'intervalle de date pour l'enregistrement du temps d'arrêt pour maintenance dans les champs **De** et **À**.

5. Lorsque vous quittez le champ **À**, la durée en heures est automatiquement insérée dans le champ **Durée**.

6. Sélectionnez un code motif dans le champ **Code motif de temps d'arrêt pour maintenance**.

7. Répétez les étapes 3-6 si vous souhaitez ajouter plus d'enregistrements.

8. Cliquez sur **Enregistrer**.


![Figure 2](media/16-work-orders.png)


Le calendrier utilisé pour calculer un enregistrement de temps d'arrêt pour maintenance dépend de votre sélection dans la configuration des actifs et des paramètres. Si une ressource est sélectionnée sur un actif dans le champ **Tous les actifs** >  organisateur **Immobilisation** > **Ressource**, la configuration du calendrier pour le groupe de ressources associé est utilisé, comme indiqué sur la figure suivante.

![Figure 3](media/17-work-orders.png)


Si aucune ressource n'est sélectionnée sur l'actif, le calendrier standard sélectionné dans **Paramètres de gestion des actifs** est utilisé, comme indiqué sur la figure suivante.

![Figure 4](media/18-work-orders.png)


Cliquez sur **Gestion des actifs d'entreprise** > **Recherches** > **Temps d'arrêt pour maintenance** pour afficher une vue d'ensemble de tous les enregistrements de temps d'arrêt pour maintenance.

>[!NOTE]
>Tous les calendriers utilisés dans le module **Gestion des actifs** sont configurés dans **Administration d'organisation** > **Configuration** > **Calendriers** > **Calendriers**.

