---
title: Installer le thème Adventure Works
description: Cet article décrit comment installer le thème Adventure Works dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: f5c195694633c96a473f0f824c1f182903082bff
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274284"
---
# <a name="install-the-adventure-works-theme"></a>Installer le thème Adventure Works

[!include [banner](includes/banner.md)]

Cet article décrit comment installer le thème Adventure Works dans Microsoft Dynamics 365 Commerce. 

> [!IMPORTANT]
> Le thème et les modules Adventure Works sont disponibles à partir de la version 10.0.20 de Dynamics 365 Commerce. Ils sont disponibles à partir de Microsoft AppSource.

## <a name="prerequisites"></a>Conditions préalables

Avant d'installer le thème Adventure Works, vous devez disposer d'un environnement Dynamics 365 Commerce (Commerce version 10.0.20 ou ultérieure) qui inclut Retail Cloud Scale Unit (RCSU), le kit de développement logiciel (SDK) en ligne Commerce et la bibliothèque de modules Commerce. Pour plus d'informations sur l'installation du kit de développement logiciel (SDK) Commerce et de la bibliothèque de modules, consultez [Configurer un environnement de développement](e-commerce-extensibility/setup-dev-environment.md). 

## <a name="installation-steps"></a>Étapes d'installation

### <a name="install-the-adventure-works-theme-in-your-application"></a>Installer le thème Adventure Works dans votre application

Le package du thème Adventure Works est disponible dans le flux **dynamics365-commerce**, sous le nom **@msdyn365-commerce-theme/adventureworks-theme-kit**. Cependant, bien que le package du thème Adventure Works fasse partie de ce flux, il se trouve sous un espace de noms différent. Par conséquent, vous devez suivre ces étapes pour ajouter des entrées de registre pour l'espace de noms.

1. Mettez à jour le fichier **.npmrc** afin qu'il inclue l'entrée de registre suivante (si l'entrée n'est pas déjà incluse) :

    `@msdyn365-commerce-theme:registry=https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/`

1. Mettez à jour le fichier **.yarnrc** afin qu'il inclue l'entrée de registre suivante (si l'entrée n'est pas déjà incluse) :

    `"@msdyn365-commerce-theme:registry" "https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/"`  
    
Pour installer le package dans votre environnement local, exécutez la commande `yarn add THEME_PACKAGE@VERSION` à partir de l'invite de commande, où **THEME_PACKAGE** représente le package du thème (@msdyn365-commerce-theme/adventureworks-theme-kit) et **VERSION** représente le numéro de version de la bibliothèque de modules utilisée. Il est important que les versions du package de thème et de la bibliothèque de modules correspondent. Pour trouver le bon numéro de version de la bibliothèque de modules à utiliser, ouvrez le fichier package.json et localisez la valeur **starter-pack** sous la section **dépendances**. Dans l'exemple suivant, le fichier package.json utilise la version 9.32 de la bibliothèque de modules qui correspond à la version 10.0.22 de Dynamics 365 Commerce.  

```json
"dependencies": {
    "@msdyn365-commerce-modules/starter-pack": "9.32",
}
```

L'exemple suivant montre comment exécuter la commande `yarn add` pour ajouter la version 9.32 du thème Adventure Works. La commande met automatiquement à jour le fichier package.json afin qu'il inclue la dépendance.

`yarn add @msdyn365-commerce-theme/adventureworks-theme-kit@9.32`

Pour plus d'informations sur la mise à jour de la version de la bibliothèque de modules, consultez [Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](e-commerce-extensibility/sdk-updates.md). 

> [!IMPORTANT]
> - La version du thème doit correspondre à la version de la bibliothèque de modules pour garantir que toutes les fonctionnalités fonctionnent comme prévu. 
> - La version minimale de la bibliothèque de modules et du SDK Commerce doit être 10.0.20 (9.31). 

### <a name="add-the-font-files-for-the-adventure-works-theme"></a>Ajouter les fichiers de polices pour le thème Adventure Works

Une fois le thème Adventure Works installé dans votre application, vous devez ajouter les fichiers de police requis pour celui-ci. Pour accomplir cette étape, copiez tous les fichiers de polices depuis **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks\public\webfonts** vers le chemin du répertoire public de l'application partenaire **\public\webfonts**.

### <a name="set-up-the-resources-for-the-adventure-works-theme"></a>Configurer les ressources pour le thème Adventure Works

L'étape suivante consiste à mettre à jour la ressource par défaut requise pour le thème. Pour terminer cette étape, copiez le contenu du fichier global.json sous **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks\r ressources\modules** dans le fichier global.json de l'application partenaire sous **\src\r ressources\modules**. Si le répertoire cible **\src\resources** n'existe pas, il peut être copié dans son intégralité à partir du répertoire source **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks** vers le répertoire cible **\src**.

### <a name="pull-updates-and-validate-the-theme"></a>Extraire les mises à jour et valider le thème

Pour plus d'informations sur la façon d'extraire le dernier SDK, la bibliothèque de modules et d'autres mises à jour de dépendances, consultez la section « Extraire les mises à jour » de la rubrique [Mises à jour du SDK et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md#pull-updates).

Une fois les dernières dépendances extraites, vous pouvez exécuter la commande **yarn start** pour démarrer le serveur Node dans votre environnement de développement et tester le nouveau thème Adventure Works. Parcourez l'application localement à l'aide du paramètre de chaîne de requête `?theme=adventureworks` (par exemple,`https://localhost:4000/?theme=adventureworks`).

## <a name="additional-resources"></a>Ressources supplémentaires

[Thème Adventure Works](adventure-works-theme.md)

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
