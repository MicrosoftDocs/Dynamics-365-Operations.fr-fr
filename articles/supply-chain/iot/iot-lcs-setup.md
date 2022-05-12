---
title: Installer le complément Intelligence IoT dans LCS
description: Cette rubrique explique comment installer le complément Intelligence IoT dans Microsoft Dynamics Lifecycle Services (LCS).
author: tonyafehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: tfehr
ms.custom: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 89d2f53a761085949885c987d664654c3423524b
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645075"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a>Installer le complément Intelligence IoT dans LCS

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment installer le complément Intelligence IoT dans Microsoft Dynamics Lifecycle Services (LCS). Notez que les compléments ne peuvent pas être installés sur un environnement de démonstration/évaluation. Avant de pouvoir installer le complément, vous devez [créer les ressources Azure](iot-azure-setup.md).

Vous pouvez installer et configurer l’intelligence IoT sans écrire de code. Voici les étapes de base.

1. [Paramétrer les ressources Azure](iot-azure-setup.md) – Créez un hub IoT, un cache Redis et un coffre de clés accessibles depuis Supply Chain Management.
2. [Formats du schéma de message pour hub IoT](iot-schema-format.md) – Configurez vos appareils pour envoyer des messages à IoT Hub et définissez le format de message JavaScript Object Notation (JSON).
3. Dans Gestion des fonctionnalités, activez l’indicateur de la fonctionnalité d’intelligence IoT.
4. Installez le complément d’intelligence IoT dans Microsoft Dynamics Lifecycle Services (LCS) – Installez le complément dans LCS et configurez les secrets Azure (comme décrit dans cette rubrique).
5. [Configurer des mesures](iot-metrics-setup.md) – Configurez des mesures dans Supply Chain Management.
6. [Configuration d’un scénario](iot-scenario-setup.md) – Configurez les scénarios dans Supply Chain Management.

## <a name="set-up-the-lcs-environment"></a>Paramétrage de l’environnement LCS

1. Ouvrez LCS et accédez à votre environnement Microsoft Dynamics 365 Supply Chain Management.
2. Faites défiler jusqu’à la section **Compléments d’environnement**.
3. Sélectionnez **Installer un nouveau complément** pour afficher la liste des compléments qui ont été activés pour l’environnement.
4. Dans la boîte de dialogue **Sélectionner un complément à installer**, sélectionnez **Intelligence IoT**.
5. Dans la boîte de dialogue **Complément d’installation**, fournissez les détails de votre hub IoT et de votre cache Redis. Vous pouvez trouver les valeurs requises dans le coffre de clés que vous avez créé dans [Créer des ressources Azure](iot-azure-setup.md).

    + **ID client** - Dans le portail Azure, accédez au coffre de clés, puis, dans le volet de navigation de gauche, sélectionnez **Vue d’ensemble** et copiez la valeur **ID répertoire**. Collez cette valeur dans la boite de dialogue **Complément d’installation**.
    + **URI du coffre de clés de point d’extrémité compatible avec IoT Event Hub** - Accédez au coffre de clés, puis, dans le volet de navigation de gauche, sélectionnez **Vue d’ensemble** et copiez la valeur du **Nom DNS**. Collez cette valeur dans la boite de dialogue **Complément d’installation**.
    + **Nom secret du point de terminaison compatible avec IoT Event Hub** - Accédez au coffre de clés, puis, dans le volet de navigation de gauche, sélectionnez **Secrets** et copiez le nom du secret dans lequel la chaîne de connexion du concentrateur d’événements du hub IoT est stockée. Collez cette valeur dans la boite de dialogue **Complément d’installation**.
    + **URI du coffre de clés du cache Redis** - Accédez au coffre de clés, puis, dans le volet de navigation de gauche, sélectionnez **Vue d’ensemble** et copiez la valeur du **Nom DNS**. Collez cette valeur dans la boite de dialogue **Complément d’installation**.
    + **Nom secret du point de terminaison du cache Redis** - Accédez au coffre de clés, puis, dans le volet de navigation de gauche, sélectionnez **Secrets** et copiez le nom du secret dans lequel la chaîne de connexion du cache Redis est stockée. Collez cette valeur dans la boite de dialogue **Complément d’installation**.

6. Cochez la case pour accepter les termes et conditions.
7. Sélectionnez **Installer**.
8. Une boîte de message s’affiche et indique : « Le complément a été correctement déclenché pour l’installation . Cliquez sur **OK**.

La configuration LCS est maintenant terminée. La prochaine étape consiste à [mettre en place les scénarios](iot-scenario-setup.md).

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a>Désinstaller le complément

1. Dans Supply Chain Management, [désactivez les scénarios](iot-scenario-setup.md#disable-a-scenario).
2. Dans LCS, accédez aux détails de l’environnement Supply Chain Management.
3. Faites défiler jusqu’à la section **Compléments d’environnement**.
4. Sélectionnez **Désinstaller** pour le complément Intelligence IoT.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]