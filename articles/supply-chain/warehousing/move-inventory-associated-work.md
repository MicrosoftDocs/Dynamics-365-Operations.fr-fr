---
title: Mouvements de stock avec le travail associé dans la gestion d’entrepôt
description: Grâce au mouvement de stock, vous pouvez déterminer quels collaborateurs d’entrepôt sont autorisés à déplacer le stock réservé.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d996886a90037f288e839c54c8c9d932cabb21f19f2aef1552ca82b192c96a51
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736549"
---
# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a>Mouvements de stock avec le travail associé dans la gestion d’entrepôt

[!include [banner](../includes/banner.md)]

Grâce au mouvement de stock, vous pouvez déterminer quels collaborateurs d’entrepôt sont autorisés à déplacer le stock réservé. Ceci permet une grande flexibilité dans les entrepôts définis où vous pouvez choisir de ne pas permettre à un collaborateur de choisir un nouvel emplacement de prélèvement pour le travail de prélèvement qui est déjà créé. Il permet également à un gestionnaire d’entrepôt de contrôler les capacités que certains collaborateurs moins expérimentés doivent posséder.

La flexibilité à gérer les opérations quotidiennes des collaborateurs d’entrepôt peut être utile dans les scénarios suivants :

## <a name="scenario-1"></a>Scénario 1

Une entreprise a une zone de réception relativement petite, et elle est encombrée de palettes et de boîtes qui traînent ça-et-là. Une grande expédition est prévue pour le jour en cours, donc la personne chargée de la réception décide de libérer la zone de réception en déplaçant une partie des palettes dans une zone secondaire.

## <a name="scenario-2"></a>Scénario 2

Un collaborateur expérimenté de l’entrepôt voit une opportunité dans un entrepôt pour regrouper les articles dans un emplacement au lieu de les répartir sur 3 emplacements voisins avec peu de quantité dans chacun. Le collaborateur souhaite consolider la quantité en déplaçant des articles dans chacun de ces emplacements vers le même emplacement et sur le même contenant.

## <a name="scenario-3"></a>Scénario 3

Une palette est en attente d’expédition dans un emplacement intermédiaire, tel que STAGE01, qui est près de BAYDOOR01. Toutefois, en raison d’une modification des plans, le camion est planifié pour arriver à BAYDOOR04. L’employé chargé des expéditions s’en rend compte et doit veiller à ce que le camion n’attende pas d’être chargé à STAGE01. Il décide alors de déplacer les articles de cette expédition de STAGE01 vers STAGE04, qui est plus proche de la nouvelle destination.

### <a name="current-limitations"></a>Restrictions actuelles

Les réservations de travail que vous pouvez déplacer sont limitées à Commande client, Émission d’un ordre de transfert, Réception d’un ordre de transfert, Commande fournisseur et Travail de réapprovisionnement.

Le déplacement des articles est restreint pour empêcher le fractionnement des lignes de travail. Cela signifie que si vous avez une ligne de travail pour 100 PC de l’article A situés sur l’emplacement Loc1, vous ne pourrez déplacer que 30 PC de l’article A à partir de là vers un autre emplacement. Cela mènerait à un fractionnement de la ligne existante de travail à 30 et 70, car les emplacements sont désormais différents.

Pour les scénarios intermédiaires, où le contenant à partir duquel vous déplacez les marchandises ou le contenant vers lequel vous déplacez les marchandises, sont définis en tant que Contenant cible pour un ordre d’exécution, seul le mouvement du contenant entier est autorisé, et ce pour ne pas diviser le contenant cible.

Seul le mouvement ad-hoc est actuellement pris en charge. Cela signifie que vous ne pourrez pas déplacer le stock réservé via le mouvement à l’aide des options de menu de l’appareil mobile.

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a>Paramétrer l’autorisation de déplacer le stock réservé pour différents collaborateurs

Pour le collaborateur qui est autorisé à déplacer le stock réservé, activez la case à cocher **Autoriser le mouvement de stock avec le travail associé** sous **Gestion des entrepôts \> Paramétrage \> Collaborateur**.  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
