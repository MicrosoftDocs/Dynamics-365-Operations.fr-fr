---
title: Permuter entre les configurations de fournisseur
description: Cette rubrique décrit comment basculer l’intégration des données fournisseur entre les applications Finance and Operations et Dataverse.
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
ms.openlocfilehash: 731efd3ae841960f3a2c0b9be210c5c68ac835f5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685507"
---
# <a name="switch-between-vendor-designs"></a>Permuter entre les configurations de fournisseur

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a>Flux de données fournisseur 

Si vous choisissez d’utiliser l’entité **Compte** pour stocker les fournisseurs du type **Organisation** et l’entité **Contact** pour stocker les fournisseurs de type **Personne**, configurez les workflows suivants. Sinon, cette configuration n’est pas requise.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a>Utiliser la conception de fournisseur étendue pour les fournisseurs du type Organisation

Le pack de solution **Dynamics365FinanceExtended** contient les modèles de processus de workflow suivants. Vous allez créer un workflow pour chaque modèle.

+ Créer des fournisseurs dans la table Comptes
+ Créer des fournisseurs dans la table Fournisseurs
+ Mettre à jour des fournisseurs dans la table Comptes
+ Mettre à jour des fournisseurs dans la table Fournisseurs

Pour créer de nouveaux processus de workflow à l’aide des modèles de processus de workflow, procédez comme suit :

1. Créez un processus de workflow pour l’entité **Fournisseur** et sélectionnez **Créer des fournisseurs dans la table Comptes**. Puis sélectionnez **OK**. Ce workflow traite le scénario de création du fournisseur pour l’entité **Compte**.

    ![Processus de workflow Créer des fournisseurs dans la table Comptes](media/create_process.png)

2. Créez un processus de workflow pour l’entité **Fournisseur** et sélectionnez **Mettre à jour des fournisseurs dans la table Comptes**. Puis sélectionnez **OK**. Ce workflow traite le scénario de mise à jour du fournisseur pour l’entité **Compte**.
3. Créez un processus de workflow pour l’entité **Compte** et sélectionnez **Créer des fournisseurs dans la table Fournisseurs**.
4. Créez un processus de workflow pour l’entité **Compte** et sélectionnez **Mettre à jour des fournisseurs dans la table Fournisseurs**.
5. Vous pouvez configurer les workflows comme workflows en temps réel ou workflows d’arrière plan selon vos besoins. Pour configurer un workflow en tant que workflow d’arrière-plan, sélectionnez **Convertir en workflow d’arrière-plan**.

    ![Bouton Convertir en workflow d’arrière-plan](media/background_workflow.png)

6. Activez les workflows que vous avez créés sur les tables **Compte** et **Fournisseur** pour commencer à utiliser l’entité **Compte** pour enregistrer les informations fournisseur de type **Organisation**.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a>Utiliser la conception de fournisseur étendue pour les fournisseurs du type Personne

Le pack de solution **Dynamics365FinanceExtended** contient les modèles de processus de workflow suivants. Vous allez créer un workflow pour chaque modèle.

+ Créer des fournisseurs de type Personne dans la table Fournisseurs
+ Créer des fournisseurs de type Personne dans la table Contacts
+ Mettre à jour des fournisseurs de type Personne dans la table Contacts
+ Mettre à jour des fournisseurs de type Personne dans la table Fournisseurs

Pour créer de nouveaux processus de workflow à l’aide des modèles de processus de workflow, procédez comme suit :

1. Créez un processus de workflow pour l’entité **Fournisseur** et sélectionnez **Créer des fournisseurs de type Personne dans la table Contacts**. Puis sélectionnez **OK**. Ce workflow traite le scénario de création du fournisseur pour l’entité **Contact**.
2. Créez un processus de workflow pour l’entité **Fournisseur** et sélectionnez **Mettre à jour des fournisseurs de type Personne dans la table Contacts**. Puis sélectionnez **OK**. Ce workflow traite le scénario de mise à jour du fournisseur pour l’entité **Contact**.
3. Créez un processus de workflow pour l’entité **Contact** et sélectionnez **Créer des fournisseurs de type Personne dans la table Fournisseurs**.
4. Créez un processus de workflow pour l’entité **Contact** et sélectionnez **Mettre à jour des fournisseurs de type Personne dans la table Fournisseurs**.
5. Vous pouvez configurer les workflows comme workflows en temps réel ou workflows d’arrière plan selon vos besoins. Pour configurer un workflow en tant que workflow d’arrière-plan, sélectionnez **Convertir en workflow d’arrière-plan**.
6. Activez les workflows que vous avez créés sur les tables **Contact** et **Fournisseur** pour commencer à utiliser l’entité **Contact** pour enregistrer les informations fournisseur de type **Personne**.
