---
title: Permuter entre les configurations de fournisseur
description: Cette rubrique décrit comment basculer l’intégration des données fournisseur entre les applications Finance and Operations et Dataverse.
author: RamaKrishnamoorthy
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 5a18fed2eac4c120dca20a1d7797d047639275b9
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750592"
---
# <a name="switch-between-vendor-designs"></a>Permuter entre les configurations de fournisseur

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a>Flux de données fournisseur 

Si vous choisissez d’utiliser la table **Compte** pour stocker les fournisseurs de type **Organisation** et la table **Contact** pour stocker les fournisseurs de type **Personne**, configurez les workflows suivants. Sinon, cette configuration n’est pas requise.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a>Utiliser la conception de fournisseur étendue pour les fournisseurs du type Organisation

Le pack de solution **Dynamics365FinanceExtended** contient les modèles de processus de workflow suivants. Vous allez créer un workflow pour chaque modèle.

+ Créer des fournisseurs dans la table Comptes
+ Créer des fournisseurs dans la table Fournisseurs
+ Mettre à jour des fournisseurs dans la table Comptes
+ Mettre à jour des fournisseurs dans la table Fournisseurs

Pour créer de nouveaux processus de workflow à l’aide des modèles de processus de workflow, procédez comme suit :

1. Créez un processus de workflow pour la table **Fournisseur** et sélectionnez le modèle de processus de workflow **Créer des fournisseurs dans la table Comptes**. Puis sélectionnez **OK**. Ce workflow traite le scénario de création du fournisseur pour la table **Compte**.

    ![Processus de workflow Créer des fournisseurs dans la table Comptes](media/create_process.png)

2. Créez un processus de workflow pour la table **Fournisseur** et sélectionnez le modèle de processus de workflow **Mettre à jour les fournisseurs dans la table Comptes**. Puis sélectionnez **OK**. Ce workflow traite le scénario de mise à jour du fournisseur pour la table **Compte**.
3. Créez un processus de workflow pour la table **Compte** et sélectionnez le modèle de processus de workflow **Créer des fournisseurs dans la table Fournisseurs**.
4. Créez un processus de workflow pour la table **Compte** et sélectionnez le modèle de processus de workflow **Mettre à jour les fournisseurs dans la table Fournisseurs**.
5. Vous pouvez configurer les workflows comme workflows en temps réel ou workflows d’arrière plan selon vos besoins. Pour configurer un workflow en tant que workflow d’arrière-plan, sélectionnez **Convertir en workflow d’arrière-plan**.

    ![Bouton Convertir en workflow d’arrière-plan](media/background_workflow.png)

6. Activez les workflows que vous avez créés pour les tables **Compte** et **Fournisseur** pour commencer à utiliser la table **Compte** pour enregistrer les informations fournisseur de type **Organisation**.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a>Utiliser la conception de fournisseur étendue pour les fournisseurs du type Personne

Le pack de solution **Dynamics365FinanceExtended** contient les modèles de processus de workflow suivants. Vous allez créer un workflow pour chaque modèle.

+ Créer des fournisseurs de type Personne dans la table Fournisseurs
+ Créer des fournisseurs de type Personne dans la table Contacts
+ Mettre à jour des fournisseurs de type Personne dans la table Contacts
+ Mettre à jour des fournisseurs de type Personne dans la table Fournisseurs

Pour créer de nouveaux processus de workflow à l’aide des modèles de processus de workflow, procédez comme suit :

1. Créez un processus de workflow pour la table **Fournisseur** et sélectionnez le modèle de processus de workflow **Créer des fournisseurs de type Personne dans la table Contacts**. Puis sélectionnez **OK**. Ce workflow traite le scénario de création du fournisseur pour la table **Contact**.
2. Créez un processus de workflow pour la table **Fournisseur** et sélectionnez le modèle de processus de workflow **Mettre à jour les fournisseurs de type Personne dans la table Contacts**. Puis sélectionnez **OK**. Ce workflow traite le scénario de mise à jour du fournisseur pour la table **Contact**.
3. Créez un processus de workflow pour la table **Contact** et sélectionnez le modèle **Créer des fournisseurs de type Personne dans la table Fournisseurs**.
4. Créez un processus de workflow pour la table **Contact** et sélectionnez le modèle **Mettre à jour les fournisseurs de type Personne dans la table Fournisseurs**.
5. Vous pouvez configurer les workflows comme workflows en temps réel ou workflows d’arrière plan selon vos besoins. Pour configurer un workflow en tant que workflow d’arrière-plan, sélectionnez **Convertir en workflow d’arrière-plan**.
6. Activez les workflows que vous avez créés pour les tables **Contact** et **Fournisseur** pour commencer à utiliser la table **Contact** pour enregistrer les informations fournisseur de type **Personne**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]