---
title: Paramétrage des transporteurs
description: Cette procédure décrit comment paramétrer un transporteur et définir des détails tels que le service, le mode d'expédition, l'offre de transport, les contraintes de transport, et les frais de livraison.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c5ac13d17c97f20ee79e7faf57c570f02158424
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569100"
---
# <a name="set-up-shipping-carriers"></a>Paramétrage des transporteurs

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment paramétrer un transporteur et définir des détails tels que le service, le mode d'expédition, l'offre de transport, les contraintes de transport, et les frais de livraison. Un coordinateur de transport pourra ensuite affecter un transporteur à une charge entrante ou sortante.


## <a name="create-a-new-shipping-carrier"></a>Créer un transporteur
1. Accédez à Gestion du transport > Paramétrage > Transporteurs > Transporteurs.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Transporteur.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Mode, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>Renseigner les informations générales du transporteur
1. Activez ou désactivez l'extension de la section Vue d'ensemble.
2. Activez ou désactivez la case à cocher Activation du transporteur.
3. Dans le champ Fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Sélectionnez le compte fournisseur à affecter au transporteur.  
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Sélectionnez une option dans le champ Type d'offre de transport.
    * Sélectionnez Manuel pour utiliser la page Offre de transport ou sélectionnez EDI pour mettre à jour l'offre à l'aide de l'échange de données informatisé (EDI).  
7. Activez ou désactivez la case à cocher Activer le classement du transporteur.

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>Créer les services nécessaires pour le transporteur
1. Activez ou désactivez l'extension de la section Services.
2. Cliquez sur Nouveau.
3. Dans la liste, marquez la ligne sélectionnée.
4. Tapez une valeur dans le champ Service de transporteur.
5. Tapez une valeur dans le champ Nom.
6. Dans le champ Mode de transport, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

## <a name="set-up-the-address-for-the-carrier-optional"></a>Paramétrer l'adresse du transporteur (facultatif)
1. Activez ou désactivez l'extension de la section Adresses.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom ou description.
4. Dans le champ Pays/Région, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Dans le champ Code postal, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Tapez une valeur dans le champ Rue.
10. Cliquez sur OK.

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>Paramétrer le profil de classement du transporteur
1. Activez ou désactivez l'extension de la section Profils de classement.
2. Cliquez sur Nouveau.
3. Dans la liste, marquer la ligne sélectionnée.
4. Tapez une valeur dans le champ Profil de classement.
5. Tapez une valeur dans le champ Nom.
6. Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
10. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
11. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
12. Dans le champ Moteur de taux, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Sélectionnez le moteur de frais correspondant au contrat que vous avez avec le transporteur.  
13. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
14. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
15. Dans le champ Données principales du taux, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
16. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
17. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
18. Dans le champ Moteur de temps de transit, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
19. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
20. Cliquez sur Enregistrer.

