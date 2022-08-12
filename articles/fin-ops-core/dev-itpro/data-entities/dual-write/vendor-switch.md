---
title: Permuter entre les configurations de fournisseur
description: Cet article décrit comment basculer entre l’intégration des données fournisseur entre les applications de finances et d’opérations et Dataverse.
author: RamaKrishnamoorthy
ms.date: 09/20/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 5a1b3a6049e7e31e7e5bdcf690a766ecea8dc4b1
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9112332"
---
# <a name="switch-between-vendor-designs"></a>Permuter entre les configurations de fournisseur

[!include [banner](../../includes/banner.md)]





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

    ![Processus de workflow Créer des fournisseurs dans la table Comptes.](media/create_process.png)

2. Créez un processus de workflow pour la table **Fournisseur** et sélectionnez le modèle de processus de workflow **Mettre à jour les fournisseurs dans la table Comptes**. Puis sélectionnez **OK**. Ce workflow traite le scénario de mise à jour du fournisseur pour la table **Compte**.
3. Créez un processus de workflow pour la table **Compte** et sélectionnez le modèle de processus de workflow **Créer des fournisseurs dans la table Fournisseurs**.
4. Créez un processus de workflow pour la table **Compte** et sélectionnez le modèle de processus de workflow **Mettre à jour les fournisseurs dans la table Fournisseurs**.
5. Vous pouvez configurer les workflows comme workflows en temps réel ou workflows d’arrière plan selon vos besoins. Pour configurer un workflow en tant que workflow d’arrière-plan, sélectionnez **Convertir en workflow d’arrière-plan**.

    ![Bouton Convertir en workflow d’arrière-plan.](media/background_workflow.png)

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
