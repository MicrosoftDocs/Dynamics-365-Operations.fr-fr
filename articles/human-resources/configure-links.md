---
title: Créer des liens depuis Ressources humaines vers un autre environnement
description: Cette rubrique explique comment créer un lien à partir de Microsoft Dynamics 365 Human Resources à un autre environnement Dynamics 365.
author: twheeloc
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-29-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d20eef4b4861d85ead1d47ca493c3a5c2d2d85e8
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712625"
---
# <a name="create-links-from-human-resources-to-another-finance-environment"></a>Créer des liens depuis Ressources humaines vers un autre environnement Finances

Un client peut avoir deux environnements Dynamics 365 dans lesquels il travaille. Par exemple, le client peut avoir un environnement Dynamics 365 Human Resources sur l'infrastructure Finance et devez vous connecter à un autre environnement Dynamics 365 Finance. 

Cette fonctionnalité permettra des liens depuis une page des ressources humaines vers une page spécifique dans un autre environnement financier. Lorsque les liens sont configurés, vous pouvez spécifier où le lien sera disponible dans les ressources humaines, et la page cible qui sera ouverte dans l'autre environnement.

> [!Note] 
> Vous devez activer **Améliorations de l’expérience utilisateur des ressources humaines** dans **Gestion des fonctionnalités** pour obtenir cette fonctionnalité.

## <a name="configure-target-systems"></a>Configurer les systèmes cibles

Dans les ressources humaines, les administrateurs système peuvent définir des liens qui apparaîtront sur les pages **Ressources humaines**. Les parties de la configuration sont les environnements de Finance auxquels vous souhaitez accéder comme cible du lien. 

Pour configurer le système cible :
1. Sur la page **Configurer les liens**, sélectionnez **Configurer le système cible**.  
2. Entrez le nom du système cible et fournissez l'URL de l'environnement Finance. Après avoir configuré vos systèmes cibles, vous pouvez définir vos liens.

## <a name="configure-links"></a>Configurer les liens

Chaque lien créé aura les informations suivantes définies :
 - **Lien** : Nom du lien. Utilisé pour l'identification uniquement.
 - **Activer ce lien** - Définissez sur **Oui** si vous souhaitez afficher le lien pour les utilisateurs de Ressources humaines.
 - **Nom complet** : Entrez le nom qui s'affichera comme lien dans l'environnement secondaire. 
 - **Afficher le lien sur l'écran** - Choisissez la page sur laquelle afficher le lien. Les liens ne peuvent être affichés que sur l'espace de travail **Libre-service pour les employés** et les pages **Emploi**, **Position**, **Ouvrier** et **Collaborateur simplifié**.
 - **Grouper** : Vous pouvez organiser vos liens à l'aide de groupes. Sélectionnez un groupe existant ou créez-en un nouveau à l'aide de la colonne **Grouper**.
 - **Système cible** - Sélectionnez le système cible créé à l'aide de l'option **Configurer le système cible**. Il s'agit de l'environnement secondaire utilisé lors de la navigation avec le lien.
 - **Utiliser la société actuelle de l'utilisateur** - Sélectionnez **Oui** pour utiliser la société actuelle de l'utilisateur en accédant à Finance. Sélectionnez **Non** pour sélectionner la société qui doit être utilisée.
 - Option de menu **cible** - Entrez l'option de menu de l'environnement Finance que le lien doit utiliser lors de la navigation. Des options de menu auxquelles vous pouvez accéder directement sont disponibles. 

   Pour trouver l'élément de menu requis :
   1. Accédez à l'environnement Finance et ouvrez la page cible de la navigation. 
   2. Copiez l'option de menu de l'URL. Par exemple, si vous souhaitez que le lien vous dirige vers la liste des employés dans Finance and Operations, entrez la valeur qui s'affiche après le « &mi » dans l'URL. 
   3. L'option de menu permettant d'accéder à la page de la liste des employés dans cet exemple est : HcmWorkerListPage_Employees.

 - **Lien vers la source de données** - Sélectionnez la source des données à laquelle le lien fait référence. Les sources les plus courantes comme **Collaborateur** et **Poste** sont disponibles.

### <a name="access-to-links"></a>Accès aux liens

Les administrateurs système afficheront les liens nouvellement créés sur les pages définies, même si l'option **Activer ce lien** est définie sur **Non**. Cela peut être utilisé pour tester des liens avant de les afficher pour d'autres employés. Tous les autres rôles n'affichent que les liens configurés une fois l'option **Activer ce lien** définie sur **Oui**. Les employés ayant accès aux pages sur lesquelles les liens sont affichés auront accès aux liens.

Les utilisateurs doivent également disposer de droits de sécurité dans l'environnement secondaire défini pour accéder aux pages de cet environnement. Si ce n'est pas le cas, une boîte de dialogue de sécurité s'affiche lorsque vous utilisez le lien.

