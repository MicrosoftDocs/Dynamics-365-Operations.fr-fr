---
title: "Création de commandes de service automatiquement"
description: "Vous pouvez créer des commandes de service pour un ou plusieurs accords de service."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c39e5b5eb79859b0a76c357edfee953ca90c0c4a
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="create-service-orders-automatically"></a>Création de commandes de service automatiquement    

[!include [banner](../includes/banner.md)]


Vous pouvez créer des commandes de service pour un ou plusieurs accords de service. Lorsqu'elles sont créées, vous pouvez afficher vos commandes de service dans l'écran **Commandes de service**.

Les commandes de service sont créées uniquement pour la période valide de l'accord de service. Si l'intervalle que vous spécifiez dans l'écran **Créer des commandes de service** se situe avant la date de début ou après la date de fin de l'accord de service, les commandes de service sont créées uniquement pour la partie de l'intervalle s'inscrivant dans les dates de l'accord de service.

Lorsque vous créez des commandes de service manuellement ou automatiquement à partir de la ligne d'accord de service, la commande de service doit avoir lieu dans l'intervalle de temps défini par les dates de début et de fin de la ligne, sauf si vous ne spécifiez pas de date de fin dans la ligne.

## <a name="create-service-orders-automatically-for-a-service-agreement"></a>Création automatique de commandes de service pour un accord de service

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**.

2.  Sélectionnez un accord de service.

3.  Cliquez sur l'onglet **Livrer**, puis sur **Commandes de service prévisionnelles**.

4.  Spécifiez les dates dans les champs **Date de début** et **Date de fin** pour définir la période de service.

5.  Activez la case à cocher **Afficher Infos** pour afficher la liste des commandes de service créées.

6.  Sélectionnez les types de transaction dans le groupe de champs **Inclure les types de transaction**. Les types de transactions représentent les lignes créées dans l'accord de service et chaque type de transaction que vous sélectionnez génère plusieurs commandes de service, en fonction de l'intervalle de service spécifié sur la ligne d'accord de service.

7.  Pour créer des commandes de service manquantes au sein d'une série continue de commandes de service, activez la case à cocher **Continu**.

8.  Cliquez sur **OK**.

## <a name="create-service-orders-automatically-for-several-service-agreements"></a>Création automatique de commandes de service pour plusieurs accords de service

1.  Cliquez sur **Gestion des services** \> **Périodique** \> **Commandes de service** \> **Créer des commandes de service**.

2.  Cliquez sur **Sélectionner** afin d'opérer des sélections pour ajouter ou supprimer des critères à utiliser pour créer des commandes de service.

3.  Cliquez sur **OK**.

## <a name="see-also"></a>Voir également :

[Commandes de service](service-orders.md)

[Création automatique de commandes de service](auto-create-service-orders.md)

  



