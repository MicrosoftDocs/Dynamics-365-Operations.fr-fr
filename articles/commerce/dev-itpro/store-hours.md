---
title: Créer et mettre à jour les heures d’ouverture du magasin
description: Cette rubrique décrit comment créer et mettre à jour les heures d’ouverture dans Commerce Headquarters.
author: josaw1
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Retail 10.0.1 update
ms.openlocfilehash: 703087f5311205e18b6b8f99b847b539770160b91574b12d505822c8e16ca96c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770092"
---
# <a name="create-and-update-store-hours"></a>Créer et mettre à jour les heures d’ouverture du magasin

[!include [banner](../../includes/banner.md)]

## <a name="overview"></a>Vue d’ensemble

Depuis un emplacement unique, les détaillants peuvent créer, préserver et gérer les heures d’ouverture de magasin pour différents magasins dans diverses régions. Les heures d’ouverture de magasin peuvent être indiquées sur les terminaux de point de vente (PDV). De cette façon, les agents de caisse peuvent partager les heures d’ouverture de magasin avec les clients et mieux aider les clients intéressés par le stock d’autres magasins. Les heures d’ouverture de magasin peuvent être également imprimés sur les reçus, au cas où les clients souhaiteraient revenir ultérieurement au magasin.

Vous pouvez configurer plusieurs heures d’ouverture de magasin dans différents canaux. Ces canaux incluent des magasins physiques, des centres d’appel, des appareils mobiles et des sites de commerce en ligne.

Si un client a un ordre de prélèvement pour un autre magasin, l’agent de caisse peut sélectionner les dates lorsque le prélèvement sera disponible dans ce magasin. La recherche du magasin génère une référence aux dates et heures d’ouverture de magasin. L’agent de caisse peut sélectionner une date et un emplacement, et il peut imprimer un bon de prélèvement incluant les heures d’ouverture de magasin.

Cette fonctionnalité est disponible dans Microsoft Dynamics 365 Retail, versions 8.1.2 et ultérieures.

## <a name="configure-store-hours"></a>Configurer les heures d’ouverture de magasin

Pour configurer les heures d’ouverture de magasin, procédez comme suit :

1. Accédez à **Retail et Commerce** \> **Paramétrage du canal** \> **Heures d’ouverture du magasin**.
2. Sélectionnez **Nouveau** pour créer un modèle d’heures d’ouverture de magasin. Pour utiliser un modèle existant, sélectionnez le modèle dans le volet de gauche.
3. Dans la boîte de dialogue **Ajouter une plage**, définissez la plage de dates, les heures d’ouverture de magasin et les congés requis.

    - Si les heures d’ouverture de magasin ne changent pas, sélectionnez **Ne s’arrête jamais** dans le champ **Date de fin**.
    - Si les heures d’ouverture de magasin sont spécifiques à un mois, une semaine ou une journée, définissez les dates appropriées dans les champs **Date de début** et **Date de fin**.

    > [!NOTE]
    > Vous pouvez créer plusieurs modèles avec des dates de début et de fin se chevauchant. Par conséquent, vous pouvez, par exemple, définir les heures d’ouverture de magasin pour les magasins dans différents fuseaux horaires.

    ![Boîte de dialogue Ajouter une plage.](../dev-itpro/media/Storehours1.png "Boîte de dialogue Ajouter une plage")

4. Associez le modèle des heures d’ouverture de magasin avec les magasins où il est utilisé. Dans la boîte de dialogue **Choisir des nœuds d’organisation**, sélectionnez les magasins, les régions et les organisations auxquels le modèle doit être associé.

    - Seul un modèle d’heures d’ouverture de magasin peut être associé à chaque magasin.
    - Utilisez les boutons de flèche pour sélectionner les magasins, les régions ou les organisations. Le calendrier est disponible pour les magasins ou les groupes de magasins, et il est visible au PDV pour référence.

    ![Boîte de dialogue Choisir des nœuds d’organisation.](../dev-itpro/media/Storehours2.png "Boîte de dialogue Choisir des nœuds d’organisation")

5. Sur la page **Programme de distribution**, exécutez les tâches **1070** et **1090** pour rendre les heures d’ouverture de magasin disponibles au PDV.

## <a name="add-store-hours-to-printed-receipts"></a>Ajouter les heures d’ouverture de magasin aux reçus imprimés

Procédez comme suit pour ajouter des heures d’ouverture de magasin aux reçus du PDV imprimés.

1. Ouvrez le concepteur de reçus.
2. Sélectionnez **Pied de page** dans l’angle inférieur gauche.
3. Faites glisser l’élément **Heures d’ouverture de magasin** du volet gauche vers le pied de page en bas du modèle de ticket de caisse.
4. Vous pouvez modifier l’étiquette par défaut sur l’élément **Heures d’ouverture de magasin**, le cas échéant.
5. Enregistrez le reçu, puis fermez le concepteur de reçus.
6. Sur la page **Programme de distribution**, exécutez les tâches **1070** et **1090**.
7. Connectez-vous au PDV.
8. Validez la vente et sélectionnez pour imprimer un reçu.

Les reçus du PDV incluent désormais les heures d’ouverture de magasin. Si des congés sont inclus dans le modèle, ils figurent sur le ticket de caisse.

![Exemple de ticket de caisse.](../dev-itpro/media/Storehours3.png "Exemple de ticket de caisse")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]