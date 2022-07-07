---
title: Temps d’arrêt pour maintenance pour des ordres de travail
description: Cet article décrit comment créer des enregistrements de temps d’arrêt pour maintenance sur l’actif sélectionné sur un ordre de travail.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4a310152685f733093cc7e50404c23b6f24c40cc
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016650"
---
# <a name="maintenance-downtime-for-work-orders"></a>Temps d’arrêt pour maintenance pour des ordres de travail

[!include [banner](../../includes/banner.md)]


Vous pouvez créer des enregistrements de temps d’arrêt pour maintenance sur l’actif sélectionné sur un ordre de travail. Cette capacité est utile si vous souhaitez enregistrer le temps d’arrêt pour maintenance sur une ou plusieurs machines dans la zone de production. Premièrement, vous pouvez créer des codes motif de temps d’arrêt pour maintenance que vous souhaitez utiliser, par exemple, la **répartition** et **l’arrêt planifié**. Cette étape s’effectue sur la page **Codes motif de temps d’arrêt pour maintenance**. Vous pouvez ensuite créer des enregistrements de temps d’arrêt pour maintenance sur la page **Temps d’arrêt pour maintenance** et ajouter des codes motif de temps d’arrêt pour maintenance appropriés.

## <a name="create-maintenance-downtime-reason-codes"></a>Créer des codes motif de temps d’arrêt pour maintenance

1. Sélectionnez **Gestion des actifs** > **Configuration** > **Ordres de travail** > **Codes motif de temps d’arrêt pour maintenance**.

2. Sélectionnez **Nouveau**.

3. Dans le champ **Code motif de temps d’arrêt pour maintenance**, entrez un ID de code motif de temps d’arrêt pour maintenance.

4. Dans le champ **Nom**, entrez un nom.

5. Activez la case à cocher **Les indicateurs de performance clés incluent** si le code motif doit être inclus dans les calculs des indicateurs de performance clés pour l’actif. En général, les arrêts de production planifiés ne doivent pas être inclus dans les calculs des indicateurs de performance clés, car ils n’affectent pas les performances prévues.

6. Sélectionnez **Enregistrer**.

L’illustration ci-dessous présente un exemple de la page **Codes motif des temps d’arrêt pour maintenance**.

![Figure 1.](media/15-work-orders.png)

Après avoir créé les codes motif de temps d’arrêt pour maintenance que vous souhaitez utiliser, vous pouvez créer les enregistrements des temps d’arrêt pour maintenance pour les ordres de travail et les actifs.


## <a name="create-maintenance-downtime-registrations"></a>Créer des enregistrements de temps d’arrêt pour maintenance

1. Cliquez sur **Gestion des actifs** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l’ordre de travail puis, sous l’onglet **Ordre de travail**, dans le groupe **Actif**, sélectionnez **Temps d’arrêt pour maintenance**.

3. Sélectionnez **Nouveau**.

4. Dans les champs **De** et **À**, définissez l’intervalle de date et d’heure pour l’enregistrement du temps d’arrêt pour maintenance.

>[!NOTE]
>Lorsque vous quittez le champ **À**, la durée en heures est automatiquement insérée dans le champ **Durée**.

5. Dans le champ **Code motif de temps d’arrêt pour maintenance**, sélectionnez un code motif.

6. Répétez les étapes 3 à 5 pour ajouter d’autres inscriptions.

7. Sélectionnez **Enregistrer**.

L’illustration ci-dessous présente un exemple d’inscription de temps d’arrêt pour maintenance.

![Figure 2.](media/16-work-orders.png)

Le calendrier qui est utilisé pour calculer un enregistrement de temps d’arrêt pour maintenance dépend de votre sélection dans la configuration des actifs et des paramètres. Si une ressource est sélectionnée sur un actif dans le champ **Ressource** de l’organisateur **Immobilisation** de la page **Tous les actifs**, la configuration du calendrier pour le groupe de ressources associé est utilisé, comme indiqué sur l’illustration suivante.

![Figure 3.](media/17-work-orders.png)

Si aucune ressource n’est sélectionnée sur l’actif, le calendrier standard sélectionné sur la page **Paramètres de gestion des actifs** est utilisé, comme indiqué sur l’illustration suivante.

![Figure 4.](media/18-work-orders.png)

Pour afficher une vue d’ensemble de tous les enregistrements de temps d’arrêt pour maintenance, cliquez sur **Gestion des actifs** > **Recherches** > **Temps d’arrêt pour maintenance**.

>[!NOTE]
>Tous les calendriers qui sont utilisés dans le module **Gestion des actifs** sont configurés dans **Administration d’organisation** > **Configuration** > **Calendriers** > **Calendriers**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]