---
title: Surveiller et gérer l’intelligence IoT
description: Cette rubrique explique comment surveiller et gérer l’intelligence IoT.
author: robinarh
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 86e20b9e60e890833c0eb8573e92c0fbb27f8c9a
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908417"
---
# <a name="monitor-and-manage-iot-intelligence"></a>Surveiller et gérer l’intelligence IoT

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment surveiller et gérer l’intelligence IoT.

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a>Surveiller des scénarios dans Microsoft Dynamics 365 Supply Chain Management

Vous pouvez surveiller le traitement de l’intelligence IoT à plusieurs endroits :

+ **Modules \> Contrôle de la production \> Recherches et états \> Intelligence IoT \> Notifications** – Affichez la liste des notifications non résolues.
+ **Modules \> Contrôle de la production \> Recherches et états \> Intelligence IoT \> Notifications clôturées** – Affichez la liste des notifications résolues ou ignorées.
+ **Modules \> Contrôle de la production \> Recherches et états \> Intelligence IoT \> Clés métriques** – Affichez les clés métriques pour les graphiques des séries chronologiques **Statut des ressources**.
+ **Modules \> Contrôle de la production \> Contrôle et suivi de la production \> Statut des ressources** – Suivez des mesures spécifiques en utilisant la boite de dialogue **Configurer**. Si un scénario détecte une exception, une notification en affiche les détails.
+ **Espaces de travail \> Gestion de l’atelier de production \> Notifications** – Affichez la liste des notifications non résolues

## <a name="modify-a-running-iot-intelligence-scenario"></a>Modifier un scénario d’intelligence IoT en cours d’exécution

Lorsqu’un scénario est en cours d’exécution, vous pouvez apporter les modifications suivantes :

+ Ajouter de nouvelles définitions de schéma de capteur.
+ Sélectionner de nouvelles valeurs de données de signal.
+ Annuler la sélection des valeurs de données de signal existantes.
+ Ajouter et mapper de nouvelles valeurs de données de signal.
+ Mettre à jour les valeurs de seuil.

Lorsqu’un scénario est en cours d’exécution, ces modifications sont interdites :

+ Supprimez ou modifiez les définitions de schéma actuellement utilisées par un scénario activé.
+ Modifiez les chemins de schéma sélectionnés du scénario activé.

## <a name="simulation-options"></a>Options de simulation

Vous pouvez simuler des signaux de machine d’usine. Pour plus d’informations, consultez les rubriques suivantes :

+ [Connecter IoT DevKit AZ3166 au hub IoT Azure](/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [Connecter le simulateur Raspberry Pi en ligne au hub IoT Azure (Node.js)](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [Présentation de l’accélérateur de solution de simulation de périphérique](/azure/iot-accelerators/iot-accelerators-device-simulation-overview)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]