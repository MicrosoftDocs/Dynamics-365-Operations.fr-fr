---
title: Création de modèles de prévision pour les budgets de projet
description: Cette rubrique décrit comment créer un modèle de prévision pour les budgets restants.
author: RadhikaRS
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 07e540f23a668b40a54906a67d87552fe991825a
ms.sourcegitcommit: 5de75c61c33e57c813944f1ab6100aceb020d432
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/29/2020
ms.locfileid: "3321777"
---
# <a name="create-forecast-models-for-project-budgets"></a>Création de modèles de prévision pour les budgets de projet 

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment créer un modèle de prévision pour les budgets restants. Un projet soumis au contrôle budgétaire fait appel à deux types de budgets : le budget d'origine et le budget restant. Lorsque vous créez un budget de projet, vous devez spécifier les modèles de prévision du budget d'origine et du budget restant créés dans la page **Modèles de prévision**. Les budgets de projet basés sur les modèles spécifiés sont créés lorsque vous approuvez le budget de projet.

> [!NOTE]
> Un modèle de prévision utilisé pour le contrôle budgétaire ne peut pas disposer d'un sous-modèle et ne peut pas être utilisé en tant que sous-modèle.

1. Sélectionnez **Gestion de projet et comptabilité** > **Configuration** > **Prévisions**  > **Modèles de prévision**.
2. Sélectionnez **Nouveau** pour créer un modèle de prévision, puis entrez un ID modèle, ainsi qu'un nom pour le nouveau modèle. 
3. Définissez l'option **Arrêté** sur **Oui** pour empêcher toute modification des lignes de prévision du modèle de prévision. 
4. Si les lignes de prévision auxquelles le modèle est associé doivent générer des prévisions de flux de trésorerie dans la comptabilité, définissez **Inclure les budgets dans les prévisions de flux de trésorerie** sur **Oui**. 
5. Pour utiliser la date du projet comme date de facture, définissez **Date prévisionnelle de facturation** sur **Oui**. 
6. Dans le champ **Type de budget**, sélectionnez l'un des types de modèles suivants :

   - **Budget d'origine** : Utilisez ce type de modèle pour les montants de budget d'origine engagés lors de la création et de l'approbation du budget initial.
   - **Budget restant** : Utilisez ce type de modèle pour les montants de budget restant au cours du cycle de vie du projet. Les soldes de ce modèle de prévision sont réduits par les transactions réelles et augmentés ou diminués par les révisions de budget.
   - **Report de budget** : Utilisez ce type de modèle pour les montants de report de budget pour le projet. Le report est un processus facultatif qui peut être exécuté pour transférer les montants de budget inutilisés d'un exercice à un autre.

7. Définissez les options suivantes selon vos besoins :

   - Activez **Date prévisionnelle de facturation** pour utiliser la date du projet comme date de facture.
   - Activez **Prévision avec WIP** pour effectuer des prévisions en fonction des travaux en cours (WIP), puis sélectionnez le type de WIP. 
   - Vous pouvez conserver la valeur par défaut **Type de budget** sur la valeur **Aucun**, ou entrez un nouveau type. Le type de budget ne peut pas être modifié après avoir modifié un enregistrement.     
    > [!NOTE]
    > Si vous modifiez le type de budget par défaut, toutes les autres options ne seront plus disponibles pour les mises à jour et vous ne pourrez pas réutiliser ce modèle de prévision. 
   


 

