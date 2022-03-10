---
title: 'Guide : Créer une prévision de base'
description: Un responsable de production peut créer une prévision de base à l’aide des modèles de prévision de série chronologiques ou en copiant la demande historique.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup, ReqIntercompanyPlanningGroupAllocKeys, ReqDemPlanForecastParameters, ReqDemPlanCreateForecastDialog, SysQueryForm, ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 843e0b3827851e1251a2c77269859bb7903f69ec
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578318"
---
# <a name="guide-create-a-baseline-forecast"></a>Guide : Créer une prévision de base

[!include [banner](../../includes/banner.md)]

Un responsable de production peut créer une prévision de base à l’aide des modèles de prévision de série chronologiques ou en copiant la demande historique. Cette procédure indique comment copier la demande historique pour créer une prévision de base pour tous les produits à l’aide d’une clé de répartition par article.

## <a name="set-up-an-item-allocation-key"></a>Paramétrer une clé de répartition par article

1. Accédez à **Planification > Paramétrage > Groupes de planification intersociétés**.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez sur le champ *Nom* avec une valeur de *10*.
    * Les prévisions de la demande fonctionnent dans les entités juridiques. C’est pourquoi vous devez paramétrer toutes les sociétés pour lesquelles vous souhaitez générer des prévisions à un groupe de planification intersociétés.  
3. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
4. Sélectionnez **Clés de répartition par article**.
    * Sélectionnez toutes les clés de répartition par article pour lesquelles vous souhaitez créer des prévisions.  
5. Dans la liste, marquer la ligne sélectionnée.
    * Sélectionnez la clé de répartition par article D_Aloc.  
6. Sélectionnez **>**.
7. Fermez la page.
8. Fermez la page.

## <a name="set-up-the-demand-forecasting-parameters"></a>Définir des paramètres de prévision de la demande

1. Accédez à **Planification > Paramétrage > Prévision de la demande > Paramètres de prévision de la demande**.
2. Développez la section **Paramètres de l’algorithme de prévision**.
3. Dans le champ **Stratégie de génération de la prévision**, sélectionnez **Copier sur la demande historique**.
4. Sélectionnez **Enregistrer**.

## <a name="create-a-baseline-forecast"></a>Créer une prévision de base

1. Accédez à **Planification > Prévisions > Prévision de la demande > Générer des prévisions de base statistiques**.
2. Entrez une date dans le champ **Date de début**.
    * Si vous avez des commandes client à partir du 1er janvier 2015, entrez cette date. Si ce n’est pas le cas, entrez la date de vos commandes client la plus proche.  
3. Entrez une date dans le champ **Date de fin**.
    * Entrez la dernière date de vos commandes client, par exemple *31-03-2015*.  
4. Entrez une date dans le champ **Date de début**.
    * Entrez *01-04-2015*. Cette date est automatiquement calculée comme date de début pour la prévision suivante.  
5. Développez la section **Enregistrements à inclure**.
6. Sélectionnez **Filtrer**.
7. Dans la liste, marquer la ligne sélectionnée.
    * Marquez la ligne où **Champ** = *Groupe de planification intersociétés*.  
8. Tapez une valeur dans le champ **Critères**.
    * Tapez le groupe de planification intersociétés, (par exemple *10*) que vous avez utilisé dans la première tâche.  
9. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Sélectionnez la ligne où **Champ** = *Clé de répartition par article*.  
10. Tapez une valeur dans le champ **Critères**.
11. Cliquez sur **OK**.
12. Développez la section **Paramètres avancés**.
13. Dans le champ **Intervalle de prévision**, sélectionnez *Mois*.
14. Dans le champ **Horizon de prévision**, sélectionnez *3*.
15. Dans le champ **Limite de période du gel**, entrez *1*.
16. Cliquez sur **OK**.

## <a name="visualize-the-demand-forecast"></a>Visualiser la prévision de la demande

1. Accédez à **Planification > Prévisions > Prévision de la demande > Prévision de la demande ajustée**.
2. Dans la table de vue d’ensemble regroupée, sélectionnez la cellule de la ligne 1, colonne 2. Il s’agit de la cellule pour le deuxième mois pour lequel vous avez créé une prévision.
3. Définissez **QtyCell** sur *400*.
    * Dans la cellule, entrez un nombre différent de celui qui a été planifié, par exemple, 400.  
4. Vous avez effectué un ajustement manuel dans la prévision. Notez l’indication graphique dans l’étape suivante.
5. Sélectionnez **Détails des lignes de prévision**.
    * Dans cette page, vous pouvez voir les valeurs de précision, la demande historique et la prévision. Vous pouvez également apporter des modifications aux prévisions.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]