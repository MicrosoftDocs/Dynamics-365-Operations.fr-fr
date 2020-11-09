---
title: Permuter entre les configurations de fournisseur
description: Cette rubrique décrit comment basculer l'intégration des données fournisseur entre les applications Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 0ecc401706911f8b92146b95bb6415185df8b451
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997550"
---
# <a name="switch-between-vendor-designs"></a>Permuter entre les configurations de fournisseur

[!include [banner](../../includes/banner.md)]



## <a name="vendor-data-flow"></a>Flux de données fournisseur 

Si vous choisissez d'utiliser l'entité **Compte** pour stocker les fournisseurs du type **Organisation** et l'entité **Contact** pour stocker les fournisseurs de type **Personne** , configurez les workflows suivants. Sinon, cette configuration n'est pas requise.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a>Utiliser la conception de fournisseur étendue pour les fournisseurs du type Organisation

Le pack de solution **Dynamics365FinanceExtended** contient les modèles de processus de workflow suivants. Vous allez créer un workflow pour chaque modèle.

+ Créer des fournisseurs dans l'entité Comptes
+ Créer des fournisseurs dans l'entité Fournisseurs
+ Mettre à jour les fournisseurs dans l'entité Comptes
+ Mettre à jour les fournisseurs dans l'entité Fournisseurs

Pour créer de nouveaux processus de workflow à l'aide des modèles de processus de workflow, procédez comme suit :

1. Créez un nouveau processus de workflow pour l'entité **Fournisseur** et sélectionnez **Créer des fournisseurs dans l'entité Comptes**. Puis sélectionnez **OK**. Ce workflow traite le scénario de création du fournisseur pour l'entité **Compte**.

    ![Processus de workflow Créer des fournisseurs dans l'entité Comptes](media/create_process.png)

2. Créez un nouveau processus de workflow pour l'entité **Fournisseur** et sélectionnez **Mettre à jour les fournisseurs dans l'entité Comptes**. Puis sélectionnez **OK**. Ce workflow traite le scénario de mise à jour du fournisseur pour l'entité **Compte**.
3. Créez un nouveau processus de workflow pour l'entité **Compte** et sélectionnez **Créer des fournisseurs dans l'entité Fournisseurs**.
4. Créez un nouveau processus de workflow pour l'entité **Compte** et sélectionnez **Mettre à jour les fournisseurs dans l'entité Fournisseurs**.
5. Vous pouvez configurer les workflows comme workflows en temps réel ou workflows d'arrière plan selon vos besoins. Pour configurer un workflow en tant que workflow d'arrière-plan, sélectionnez **Convertir en workflow d'arrière-plan**.

    ![Bouton Convertir en workflow d'arrière-plan](media/background_workflow.png)

6. Activez les workflows que vous avez créés sur les entités **Compte** et **Fournisseur** pour commencer à utiliser l'entité **Compte** pour enregistrer les informations fournisseur de type **Organisation**.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a>Utiliser la conception de fournisseur étendue pour les fournisseurs du type Personne

Le pack de solution **Dynamics365FinanceExtended** contient les modèles de processus de workflow suivants. Vous allez créer un workflow pour chaque modèle.

+ Créer des fournisseurs de type Personne dans l'entité Fournisseurs
+ Créer des fournisseurs de type Personne dans l'entité Contacts
+ Mettre à jour les fournisseurs de type Personne dans l'entité Contacts
+ Mettre à jour les fournisseurs de type Personne dans l'entité Fournisseurs

Pour créer de nouveaux processus de workflow à l'aide des modèles de processus de workflow, procédez comme suit :

1. Créez un nouveau processus de workflow pour l'entité **Fournisseur** et sélectionnez **Créer des fournisseurs de type Personne dans l'entité Contacts**. Puis sélectionnez **OK**. Ce workflow traite le scénario de création du fournisseur pour l'entité **Contact**.
2. Créez un nouveau processus de workflow pour l'entité **Fournisseur** et sélectionnez **Mettre à jour les fournisseurs de type Personne dans l'entité Contacts**. Puis sélectionnez **OK**. Ce workflow traite le scénario de mise à jour du fournisseur pour l'entité **Contact**.
3. Créez un nouveau processus de workflow pour l'entité **Contact** et sélectionnez **Créer des fournisseurs de type Personne dans l'entité Fournisseurs**.
4. Créez un nouveau processus de workflow pour l'entité **Contact** et sélectionnez **Mettre à jour les fournisseurs de type Personne dans l'entité Fournisseurs**.
5. Vous pouvez configurer les workflows comme workflows en temps réel ou workflows d'arrière plan selon vos besoins. Pour configurer un workflow en tant que workflow d'arrière-plan, sélectionnez **Convertir en workflow d'arrière-plan**.
6. Activez les workflows que vous avez créés sur les entités **Contact** et **Fournisseur** pour commencer à utiliser l'entité **Contact** pour enregistrer les informations fournisseur de type **Personne**.
