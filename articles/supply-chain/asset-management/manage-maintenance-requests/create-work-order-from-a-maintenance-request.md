---
title: Créer des ordres de travail à partir de demandes de maintenance
description: Cet article explique comment créer un ordre de travail à partir d’une demande de maintenance dans Gestion des actifs.
author: johanhoffmann
ms.date: 10/01/2019
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0c73f019951460dc7cb6395d616a0f0a22fd0b91
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909699"
---
# <a name="create-work-orders-from-maintenance-requests"></a>Créer des ordres de travail à partir de demandes de maintenance

[!include [banner](../../includes/banner.md)]

 


Après avoir créé des demandes de maintenance, vous pouvez facilement les convertir en ordres de travail. Cet article décrit le moyen le plus rapide de traiter des demandes de maintenance, de mettre à jour plusieurs demandes de maintenance en même temps, puis de créer un ordre de travail pour plusieurs demandes de maintenance en même temps. Dans la page **Demandes de maintenance actives** ou **Mes demandes de maintenance de poste technique**, vous pouvez également utiliser une demande de maintenance à la fois et convertir une demande de maintenance en ordre de travail.

> [!NOTE]
> Chaque demande de maintenance peut être associée à un seul ordre de travail. Toutefois, plusieurs demandes de maintenance peuvent être incluses dans un même ordre de travail, même si les demandes de maintenance ont des actifs différents.

1. Sélectionnez **Gestion des actifs** \> **Commun** \> **Demandes de maintenance** \> **Toutes les demandes de maintenance**.
2. Avant de pouvoir créer un ordre de travail à partir de demandes de maintenance, vous devez au minimum sélectionner un type de travail de maintenance pour les demandes de maintenance, ainsi qu’une variante et un échange de type de travail de maintenance, si ces informations sont pertinentes. Dans la vue Grille, vous pouvez facilement mettre à jour les informations de mise à jour pour une demande de maintenance.
3. Lorsque vous êtes prêt(e) à créer un ordre de travail, sélectionnez les demandes de maintenance à inclure dans celui-ci.

    - Si vous sélectionnez plusieurs demandes de maintenance à convertir en ordre de travail, le champ **Actif** et le champ **Type de tâche de maintenance** doivent être définis avant de créer les ordres de travail.
    - Si vous sélectionnez une demande de maintenance à convertir en ordre de travail, seul le champ **Actif** doit être défini avant de créer les ordres de travail. Toutefois, lorsque vous créez l’ordre de travail, vous pouvez sélectionner un type de travail de maintenance (et une variante de type de travail de maintenance et un échange associés, si cette information est pertinente) dans la boîte de dialogue **Créer un ordre de travail**.

4. Sélectionnez **Ordre de travail**.
5. Dans la boîte de dialogue **Créer un ordre de travail**, définissez les champs, puis les sélectionnez **OK**.

    Une barre de message peut vous informer qu’un ordre de travail récent a été créé.

    En outre, lorsque vous créez un ordre de travail basé sur une demande de maintenance, si l’actif associé à la demande de maintenance est inclus dans un contrat de garantie, une barre de message vous avertit du contrat de garantie.

6. Sélectionnez **Gestion des actifs** \> **Commun** \> **Ordres de travail** \> **Tous les ordres de travail**, puis ouvrez le nouvel ordre de travail.

    ![Ouvrir le nouvel ordre de travail.](media/05-manage-maintenance-requests.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]