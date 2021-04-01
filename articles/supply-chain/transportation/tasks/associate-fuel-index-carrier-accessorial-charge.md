---
title: Associer un index de carburant à un transporteur comme frais annexes
description: Ce guide indique comment créer une affectation annexe, des frais annexes transporteur et des données principales annexes pour la surcharge carburant, ainsi que comment associer un index de carburant de transport à un transporteur.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5df75f8dc88124b3e07cc342a3e28c8049068d37
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205176"
---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a>Associer un index de carburant à un transporteur comme frais annexes

[!include [banner](../../includes/banner.md)]

Ce guide indique comment créer une affectation annexe, des frais annexes transporteur et des données principales annexes pour la surcharge carburant, ainsi que comment associer un index de carburant de transport à un transporteur. Vous devez avoir paramétré un index de carburant du transporteur avant d’exécuter ce guide. Pour ce faire, vous pouvez utiliser le guide « Paramétrer un index de carburant du transporteur ». Ces tâches de paramétrage sont généralement effectuées par un responsable logistique. Les données de démonstration utilisées pour créer cette procédure sont USMF.


## <a name="create-an-accessorial-master"></a>Créer des données principales annexes
1. Accédez à Gestion du transport > Configurer > Taux > Données principales de l’élément accessoire.
2. Cliquez sur Nouveau.
3. Dans le champ Données principales annexes, saisissez une valeur.
4. Tapez une valeur dans le champ Nom.
5. Cliquez sur Enregistrer.

## <a name="create-a-carrier-accessorial-charge"></a>Créer des frais annexes de transporteur
1. Accédez à Gestion du transport > Configurer > Classement > Frais annexes du transporteur.
2. Cliquez sur Nouveau.
3. Dans le champ ID annexe du transporteur, saisissez une valeur.
4. Dans le champ Transporteur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Dans cet exemple, choisissez le transporteur par camion.  
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Dans le champ Service de transport, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Dans le champ Données principales annexes, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
10. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Dans cet exemple, sélectionnez l’enregistrement principal annexe nouvellement créé.  
11. Cliquez sur Enregistrer.

## <a name="create-an-accessorial-assignment"></a>Créer une affectation annexe
1. Cliquez sur Affectations annexes.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
4. Activez ou désactivez l’extension de la section Critères.
    * Dans les critères, vous pouvez choisir de toujours appliquer la surcharge carburant ou pour cet exemple, choisir qu’elle s’applique uniquement dans une région en particulier.  
5. Dans le champ Code postal de départ, saisissez une valeur.
6. Dans le champ Code postal d’arrivée, saisissez une valeur.
7. Activez ou désactivez l’extension de la section Calcul.
    * Dans la section de calcul, vous pouvez spécifier le mode de calcul de la surcharge carburant. Ce calcul dépend de l’unité annexe que vous avez sélectionnée comme base pour le calcul.  
8. Dans le champ Type de frais annexes, sélectionnez « supplément carburant ».
9. Dans le champ Unité annexe, sélectionnez « Kilométrage ».
10. Dans le champ Région, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
11. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
12. Cliquez sur Enregistrer.

## <a name="update-the-carrier-rating-profile"></a>Mettre à jour le profil de classement des transporteurs
1. Accédez à Gestion du transport > Paramétrage > Transporteurs > Transporteurs.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
3. Activez ou désactivez l’extension de la section Profils de classement.
4. Cliquez sur Modifier.
5. Dans le champ Index carburant transporteur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]