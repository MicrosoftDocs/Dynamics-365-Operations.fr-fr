---
title: Intervalles de services
description: L'intervalle de services indique la fréquence de création des lignes de commande de service pour les lignes d'accord de service lorsque vous créez des commandes de service.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5766d8ce1fa382f3f014e160d311b2dfab2bf774
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216273"
---
# <a name="service-intervals"></a>Intervalles de services

[!include [banner](../includes/banner.md)]

L'intervalle d'accords de service indique la fréquence de création des lignes de commande de service pour les lignes d'accord de service lorsque vous créez automatiquement des commandes de service.

Dans ce dernier cas de figure, les lignes de commande de service sont créées en fonction de l'intervalle spécifié pour la ligne d'accord de service à partir de la date de début de la ligne d'accord.

Si le champ **Intervalle** de la ligne d'accord de service dans la page **Accords de service** est vide, la ligne est un événement unique et ne permet pas de créer des commandes de service de manière répétée.

## <a name="example"></a>Exemple

Cet exemple illustre la manière dont un intervalle de services affecte les lignes d'accord de service et les lignes de commande de service sur une commande de service.

### <a name="create-a-service-agreement"></a>Créer un accord de service

Commencez par créer un accord de service, puis définissez l'option **Combiner les commandes de service** sur **Par accord de service**.

1. Cliquez sur **Accords de service**
2. Dans le **volet Actions**, sous l'onglet **Accord de service**, dans le groupe **Nouveau**, cliquez sur **Accord de service** pour créer un accord de service.
3. Saisissez une description, sélectionnez un projet dans le champ **ID projet**, puis entrez une date dans le champ **Date de début**.
4. Dans le champ **Combiner les commandes de service**, sélectionnez **Par accord de service**.

Vous avez créé l'accord de service suivant :

| Projet      | Date de début                                                                         |
|--------------|------------------------------------------------------------------------------------|
| Votre projet | Date spécifiée pour le projet. Dans cet exemple, la date du jour est utilisée. |

### <a name="create-a-service-agreement-line"></a>Créer une ligne d'accord de service

Créez ensuite une ligne d'accord de service dont le type de transaction est **Heure**.

Pour terminer cette partie de l'exemple, vous devez créer un intervalle de services de 10 jours dans la page **Intervalles de services**. 

1. Sélectionnez l'accord de service que vous venez de créer. 
2. Dans l'organisateur **Lignes**, cliquez sur le bouton **Ajouter** pour créer une ligne dans le volet inférieur de la page **Accords de service**.
3. Dans le champ **Type de transaction**, sélectionnez **Heure**.
4. Dans le champ **Collaborateur**, sélectionnez le collaborateur qui fournira le service.
5. Dans le champ **Intervalle de services**, sélectionnez l'intervalle de 10 jours.

Vous avez créé une ligne d'accord de service avec les informations suivantes :

| Type de transaction | Date de début                               | Intervalle de services |
|------------------|------------------------------------------|------------------|
| Heure             | Date du jour.                        | Tous les 10 jours    |
| Travailleur           | Travailleur qui exécute le service. |                  |

Aucune fenêtre Délai n'est spécifiée pour la ligne. 

### <a name="create-planned-service-orders"></a>Création de commandes de service prévisionnelles

Vous pouvez maintenant créer des commandes de service prévisionnelles et des lignes de commande de service pour le mois prochain.

1. Dans la page **Accords de service**, dans le **volet Actions**, sous l'onglet **Livrer**, cliquez sur **Commandes de service prévisionnelles**.
2. Dans la page **Créer des commandes de service**, entrez la date du jour dans le champ **Date de début** et une date correspondant à un mois à partir de la date du jour dans le champ **Date de fin**.
3. Définissez le curseur **Heure** sur **Oui**. 
4. Cliquez sur **OK**.

Comme il n'existe aucun regroupement sur la commande de service (définie par l'option **Par accord de service** du champ **Combiner les commandes de service**), une seule ligne de commande de service est créée par commande de service.

### <a name="service-orders-created"></a>Commandes de service créées

Trois lignes de commande de service ont été créées dans le délai spécifié dans la boîte de dialogue **Créer des commandes de service**. Vous pouvez afficher les lignes d'accord de service dans la page **Accords de service** (**volet Actions** \> **onglet Livrer** \>**bouton Afficher**).

## <a name="related-topics"></a>Rubriques connexes

[Paramétrage des intervalles de services](set-up-service-intervals.md)  

