---
title: Installer le complément Intelligence IoT dans LCS
description: Cette rubrique explique comment installer le complément Intelligence IoT dans Microsoft Dynamics Lifecycle Services (LCS).
author: robinarh
ms.date: 07/07/2020
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
ms.openlocfilehash: 2d1cc9a7535be05a3e466c27e53047d694cf0160
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826441"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a>Installer le complément Intelligence IoT dans LCS

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment installer le complément Intelligence IoT dans Microsoft Dynamics Lifecycle Services (LCS). Notez que les compléments ne peuvent pas être installés sur un environnement de démonstration/évaluation. Avant de pouvoir installer le complément, vous devez [créer les ressources Azure](iot-azure-setup.md).

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