---
title: Environnements de service
description: Cet article fournit des informations sur les environnements de service pour la facturation électronique et explique comment les configurer.
author: gionoder
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: ff6f50ff78676f5efed7d905fb622ad662b541d7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291597"
---
# <a name="service-environments"></a>Environnements de service

[!include [banner](../includes/banner.md)]

Les environnements de service sont des partitions logiques créées pour prendre en charge les fonctionnalités de globalisation et les documents correspondants traités dans le service Facturation électronique. Les clés secrètes de sécurité et les certificats numériques, ainsi que la gouvernance (c’est-à-dire les autorisations d’accès), doivent être configurés au niveau de l’environnement de service.

Vous pouvez créer autant d’environnements de service que nécessaire. Tous les environnements de service créés par un client sont indépendants les uns des autres. Comme bonne pratique, nous vous recommandons de créer au moins deux environnements de service :

- Un environnement pour les principaux objectifs de développement et de validation. Cet environnement est généralement un environnement de test d’acceptation utilisateur (UAT).
- Un environnement à des fins de production. Cet environnement est généralement un environnement de production.

Ce type de partitionnement permet de s’assurer que les processus de facturation électronique sont validés et personnalisés dans le bac à sable avant de passer en production.

Les environnements de service doivent être créés et maintenus dans Regulatory Configuration Service (RCS). Puis, lorsqu’ils sont prêts, ils doivent être publiés dans le service de Facturation électronique. Le processus de publication envoie les paramètres de l’environnement de service de l’instance RCS au service de facturation électronique.

Si vous ne terminez pas le processus de publication après avoir créé un nouvel environnement de service ou ajusté un environnement de service existant (par exemple, en ajoutant ou en supprimant des utilisateurs ou des clés secrètes Microsoft Azure Key Vault), les modifications ne seront pas effectives. Seuls les environnements publiés sont accessibles par Dynamics 365 Finance ou Dynamics 365 Supply Chain Management.

## <a name="service-environment-statuses"></a>Statuts de l’environnement de service

Les environnements de service peuvent être gérés via leur statut. Vous pouvez afficher le statut d’un environnement sur la page **Environnements de services**. Les statuts suivants sont disponibles :

- **Non publié** – L’environnement a été créé, mais il n’a pas encore été publié.
- **Publié** - L’environnement a été publié dans le service de facturation électronique.
- **Modifié** – Les attributs d’un environnement publié ont été modifiés, mais les modifications n’ont pas encore été publiées.

## <a name="users"></a>Utilisateurs

Chaque environnement de service doit répertorier les utilisateurs qui peuvent se connecter à la Facturation électronnique partir de Finance et Supply Chain Management.

## <a name="applications"></a>Applications

Dans certains scénarios, des applications autres que Finance ou Supply Chain Management peuvent avoir à se connecter au service de facturation électronique pour soumettre des documents électroniques en vue d’un traitement ultérieur ou pour récupérer des informations telles que le statut de soumission d’un document. Dans ces scénarios, l’application doit être définie dans la liste des applications. De cette façon, il aura accès au service de facturation électronique. L’application doit également être enregistrée en tant qu’application dans Azure Active Directory (Azure AD), et l’ID d’objet doit être utilisé pour l’identifier. 

Étant donné que Microsoft exige un haut niveau de contrôle de sécurité sur les applications qui peuvent se connecter au service de facturation électronique, vous devez contacter Microsoft à l’adresse <DGXRegulatoryservicesengineering@service.microsoft.com> et fournir les détails suivants de votre application :

- ID client Azure AD
- ID d’environnement Microsoft Dynamics Lifecycle Services (LCS)
- ID d’application (ID client)
- ID objet
- Justification et description de haut niveau de l’application

Microsoft évaluera la demande et enregistrera l’application dans le registre de sécurité pour s’assurer qu’elle peut fonctionner avec la facturation électronique.

## <a name="number-sequences"></a>Souches de numéros

Si vos scénarios nécessitent des souches de numéros (par exemple, dans les noms de fichiers), vous pouvez utiliser des souches de numéros qui sont définies pour un environnement spécifique, mais qui peuvent être utilisées dans les fonctionnalités de globalisation ou pour une fonctionnalité de globalisation spécifique. Une fois qu’une souche de numéros est définie, vous pouvez l’utiliser dans des variables et des pipelines de traitement. Pour suivre son utilisation, sur la page **Souches de numéros**, recherchez une valeur pour **Actuel** pour le paramètre **En cours d’utilisation**.

### <a name="working-with-number-sequences"></a>Utiliser les souches de numéros
Sur la page **Souches de numéros** : 

- Sélectionnez **Nouveau** pour créer une souche de numéros. Entrez ensuite un nom et une description. 
- Sélectionnez **Supprimer** pour supprimer une souche de numéros elle n’est plus utilisée.
- Vous n’avez pas à sélectionner **Publier** dans le volet Actions pour publier les modifications apportées à une souche de numéros. La mise à jour se fait automatiquement.

## <a name="create-a-key-vault-reference"></a>Créer une référence Key Vault

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Environnement**, sélectionnez la vignette **Facturation électronique**.
3. Sur la page **Configuration d’environnement**, dans le volet Actions, sélectionnez **Environnements de service**.
4. Sur la page **Environnements de service**, dans le volet Actions, sélectionnez **Paramètres Key Vault**.
5. Sur la page **Paramètres du coffre de clés**, sélectionnez **Nouveau** pour créer une référence Key Vault.
6. Dans le champ **Nom**, entrez le nom de la référence Key Vault.
7. Entrez une description dans le champ **Description**.
8. Dans le champ **URI Key Vault**, collez l’URI Key Vault à partir du coffre de clés (`https://<your key vault>.vault.azure.net/`). Pour plus d’informations, voir [Créer un compte Azure Key Vault dans le portail Azure](e-invoicing-create-azure-key-vault-azure-portal.md).
9. Cliquez sur **Enregistrer**.
    
## <a name="create-a-secret-for-the-storage-account-secret-token"></a>Créer une clé secrète pour le jeton de clé secrète du compte de stockage

1. Sur la page **Paramètres Key Vault**, sélectionnez une référence Key Vault créée à la procédure précédente, puis dans la section **Certificats**, sélectionnez **Ajouter**.
2. Dans le champ **Nom**, entrez le nom du secret du compte de stockage. Ce nom doit correspondre au nom de la clé secrète Key Vault qui contient le jeton de signature d’accès partagé (SAS) de stockage. Pour plus d’informations, voir [Créer un compte de stockage Azure dans le portail Azure](e-invoicing-create-azure-storage-account-azure-portal.md). 
3. Entrez une description dans le champ **Description**.
4. Dans le champ **Type**, sélectionnez **Secret**.
5. Cliquez sur **Enregistrer**.
    
## <a name="create-a-service-environment"></a>Créer un environnement de service

1. Sur la page **Environnements de service**, sélectionnez **Nouveau** pour créer un environnement de service.
2. Dans le champ **Nom**, entrez le nom de l’environnement de facturation électronique.
3. Entrez une description dans le champ **Description**.
4. Dans le champ **Secret de jeton SAS de stockage**, sélectionnez le secret du compte de stockage qui doit être utilisé pour authentifier l’accès au compte de stockage.
5. Dans la section **Utilisateurs**, sélectionnez **Ajouter** pour ajouter un utilisateur autorisé à soumettre des factures électroniques via l’environnement et à se connecter également au compte de stockage.
6. Entrez l’alias de l’utilisateur dans le champ **Identifiant utilisateur**. 
7. Entrez l’adresse e-mail de l’utilisateur dans le champ **E-mail**.
8. Cliquez sur **Enregistrer**.
9. Dans le volet Actions, sélectionnez **Publier** pour publier l’environnement sur le service de facturation électronique. Vérifiez que la valeur du champ **Statut** est remplacée par **Publié**.
