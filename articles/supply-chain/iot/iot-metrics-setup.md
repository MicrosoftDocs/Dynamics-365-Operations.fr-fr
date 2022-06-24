---
title: Configurer des mesures pour l’intelligence IoT
description: Cet article explique comment configurer des mesures pour l’intelligence IoT.
author: johanhoffmann
ms.date: 04/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 147df50a9d0baf78f2efc3e57b2cda935e38cee3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882690"
---
# <a name="set-up-metrics-for-iot-intelligence"></a>Configurer des mesures pour l’intelligence IoT

[!include [banner](../../includes/banner.md)]

## <a name="configure-metrics"></a>Configurer des mesures

Si vous souhaitez afficher les graphiques de séries chronologiques de vos messages dans Microsoft Dynamics 365 Supply Chain Management, vous devez configurer les mesures en suivant ces étapes.

1. Copier la chaîne de connexion pour le cache Redis :

    1. Dans le portail Azure, accédez au cache Redis.
    2. Accédez à **Paramètres** \> **Paramètres avancés**.
    3. Copiez la valeur dans le champ **Chaîne de connexion principale**.

2. Dans Supply Chain Management, accédez à **Contrôle de la production \> Configuration \> Intelligence IoT \> Paramètres des scénarios**.
3. Sur la page **Paramètres du scénario**, dans l’onglet **Série chronologique**, dans le champ **Chaîne de connexion du magasin de métriques Redis**, collez la chaîne de connexion que vous avez copiée précédemment. Cette étape permet de visualiser les mesures d’Azure IoT Hub dans Supply Chain Management. Lorsque vous collez la valeur dans le champ, elle s’affiche sous la forme **\*\*\*\*\*\***.

    > [!NOTE]
    > Chaque fois que vous mettez à jour la chaîne de connexion du cache Redis, vous devez également mettre à jour ce champ.

4. Accédez à **Contrôle de production \> Recherches et états \> Intelligence IoT \> Clés des mesures**.
5. Sur la page **Clés des mesures**, sélectionnez **Mettre à jour**.
6. Dans la boîte de dialogue **Mettre à jour les clés des mesures**, notez que **Exécuter à l’arrière-plan** est sélectionné dans le champ. Cliquez sur **OK**.

Toutes les clés des mesures du cache Redis sont récupérées et ajoutées à la liste **Clés des mesures**. Les valeurs des mesures n’apparaîtront que lorsque vous [activerez les scénarios](iot-scenario-setup.md).

## <a name="configure-the-resource-status-time-series"></a>Configurer la série chronologique Statut des ressources

Pour configurer la série chronologique **Statut des ressources**, procédez comme suit.

1. Dans Supply Chain Management, accédez à **Contrôle de la production \> Contrôle et suivi de la production \> Statut des ressources**.
2. Sur la page **Statut des ressources**, sélectionnez **Configurer**.
2. Dans la boîte de dialogue **Configurer**, dans la liste **Ressource**, sélectionnez un élément à surveiller.
3. Sélectionnez le bouton **Modifier** pour **Série chronologique 1**.
4. Dans la boîte de dialogue **Sélectionner une série chronologique**, sélectionnez une mesure dans la grille. (Vous pouvez également utiliser le lien **Mettre à jour les clés des mesures** pour mettre à jour les clés des mesures à partir de cette boîte de dialogue.)
5. Sélectionnez **OK** pour revenir à la boîte de dialogue **Configurer**.
6. Entrez un nom d’affichage.
7. Dans le champ **Afficher les données de**, sélectionnez un délai d’exécution.
8. Cliquez sur **OK**.

Le graphique est affiché.

## <a name="delete-a-metric-key"></a>Supprimer une clé de mesure

1. Dans Supply Chain Management, accédez à **Contrôle de production \> Recherches et états \> Intelligence IoT \> Clés des mesures**.
2. Sur la page **Clés des mesures**, sélectionnez la clé de mesure à supprimer.
3. Sélectionnez **Supprimer**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]