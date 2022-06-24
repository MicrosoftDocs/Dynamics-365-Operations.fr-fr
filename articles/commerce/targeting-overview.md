---
title: Ciblage par appareil, marché et géolocalisation
description: Cet article explique comment créer, modifier et gérer des audiences et des cibles dans le générateur de site Microsoft Dynamics 365 Commerce à l’aide d’informations d’appareil, de marché et de géolocalisation.
author: sushma-rao
ms.date: 02/03/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2021-07-31
ms.dyn365.ops.version: AX 10.0.21
ms.openlocfilehash: 90772fd942db30bbf4f65a87b1dca4b2aaacee1e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881655"
---
# <a name="device-market-and-geolocation-targeting"></a>Ciblage par appareil, marché et géolocalisation

[!include [banner](includes/banner.md)]

Cet article explique comment créer, modifier et gérer des audiences et des cibles dans le générateur de site Microsoft Dynamics 365 Commerce à l’aide d’informations d’appareil, de marché et de géolocalisation.

Dynamics 365 Commerce vous permet de personnaliser des variantes du contenu de votre page (appelées *cibles*) pour des groupes spécifiques de clients (appelés *audiences*) pour augmenter l’engagement et la satisfaction utilisateur. Vous pouvez d’abord créer une audience ou une cible. Cependant, une expérience de ciblage réussie nécessite ces deux composants.

Vous créez et gérez des audiences dans le générateur de site Commerce en fonction de données client telles que l’emplacement, les informations d’appareil, le statut de connexion et d’autres informations extraites dynamiquement des requêtes web client. Vous créez et gérez également des cibles sur des modules et fragments d’e-commerce dans le générateur de site Commerce.

**Exclusion de responsabilité :** vous êtes responsable de l’utilisation de cette fonctionnalité conformément à toutes les lois et réglementations en vigueur, y compris celles relatives au ciblage et au profilage. 

## <a name="audiences"></a>Audiences

Une audience est un groupe d’utilisateurs et l’appartenance au groupe est déterminée par un ensemble de règles dynamiques. Ces règles sont de simples tests logiques exécutés sur des informations disponibles dans des requêtes client ou d’autres segments disponibles. Vous pouvez combiner plusieurs règles à l’aide d’opérateurs AND/OR.

Commerce prend en charge de manière native des segments de base tels que les informations d’appareil, le statut de connexion, le référent et les paramètres de chaîne de requête. Il prend également en charge des segments extensibles au moyen de connexions à des fournisseurs tiers.

### <a name="basic-segments"></a>Segments de base

Par défaut, les segments suivants sont disponibles et peuvent être intégrés aux définitions d’audience :

- **Statut de connexion** : testez si un utilisateur est authentifié.
- **Plateforme d’appareils** : testez les types d’appareils suivants :

    - Téléphone portable
    - Bureau
    - Tablette
    - Autres

- **Système d’exploitation d’appareil** : testez les systèmes d’exploitation suivants :

    - Windows
    - Linux
    - iOS
    - Android, Autres

- **Paramètres de chaîne de requête** : testez l’existence d’une paire clé-valeur dans un paramètre de chaîne de requête d’une URL de requête. Par exemple, pour l’URL `www.fabrikam.com/en-us/request?promo=true`, une règle peut être écrite pour vérifier que le paramètre **promo** a la valeur **true**.
- **Cookie** : testez une valeur de cookie définie pour le domaine dans l’URL de requête. Par exemple, une requête Fabrikam.com peut comprendre un cookie nommé **CustomLayout** dont la valeur est **1**. Le test de cookie vérifie l’existence d’un cookie mais n’en crée pas explicitement. Dans l’exemple précédent, JavaScript doit avoir préalablement défini le cookie **CustomLayout** à partir d’un autre module ou d’un autre processus métier.

    > [!NOTE]
    > Assurez-vous que votre utilisation des cookies est conforme aux lois en vigueur.

- **Référent** : si un utilisateur suit un lien pour demander la page, le référent est l’URL de la page ayant hébergé le lien.

### <a name="extensible-segments"></a>Segments extensibles

Commerce vous permet d’étendre la liste des segments disponibles en vous connectant à des fournisseurs de segmentation tiers. Un fournisseur de segmentation décrit les types de segments disponibles. Pour en savoir plus sur la connexion à un fournisseur de géolocalisation ou de segmentation, consultez [Configurer et activer des connecteurs](e-commerce-extensibility/connectors.md).

> [!NOTE]
> - Si un fournisseur externe est activé, il peut se connecter à un service dont les performances sont imprévisibles. Pour garantir une meilleure expérience utilisateur, si un utilisateur demande une page comprenant le ciblage et que cette page référence une audience vérifiant un fournisseur de segment tiers, la version par défaut de la page s’affiche.
> - L’utilisateur doit consentir à autoriser les cookies. Le navigateur de l’utilisateur demande ensuite tous les segments aux fournisseurs concernés, et les résultats sont placés dans un cookie renvoyé à l’utilisateur. Les requêtes ultérieures sur la page utilisent ces informations pour présenter un contenu ciblé à l’utilisateur. Pour en savoir plus sur la conformité des cookies, consultez [Conformité des cookies](cookie-compliance.md).

**Exclusion de responsabilité :** si vous activez cette fonctionnalité, vos données sont communiquées aux systèmes tiers que vous sélectionnez. Le cas échéant, vous contrôlez les données que vous fournissez au tiers. Vous comprenez que les normes de traitement des données et de conformité du tiers peuvent différer des normes de Microsoft Dynamics 365 Commerce. La protection de vos données personnelles est importante pour Microsoft. Pour en savoir plus, lisez notre [Déclaration de confidentialité et relative aux cookies](https://privacy.microsoft.com/privacystatement).

### <a name="create-an-audience-in-site-builder"></a>Créer une audience dans le générateur de site

Pour créer une audience dans le générateur de site Commerce, procédez comme suit :

1. Dans le volet de navigation à gauche, sélectionnez **Audiences**.
1. Cliquez sur **Nouveau**.
1. Saisissez un nom pour l’audience. Vous pouvez également ajouter des balises et une description.
1. Cliquez sur **Créer**, puis sur **Ajouter un nouveau bloc de règles**. Un bloc de règles est un ensemble de règles jointes par des conditions AND. Vous pouvez également créer plusieurs blocs de règles ayant des conditions OR entre eux.
1. Sélectionnez une source de données pour vos segments, puis indiquez le nom du segment, l’opérateur et les valeurs. Vous pouvez créer et supprimer soit d’autres règles dans un bloc de règles, soit des blocs de règles entiers. Vous pouvez également déplacer des blocs de règles vers le haut ou vers le bas, le cas échéant.

    > [!NOTE]
    > Vous pouvez avoir jusqu’à 100 valeurs dans une liste, et chaque élément de liste peut contenir jusqu’à 50 caractères.

1. Lorsque vous êtes satisfait de la configuration de l’audience, cliquez sur **Terminer l’édition**. Vous pouvez ensuite cliquer sur **Publier** pour rendre l’audience utilisable dans une cible active. Vous pouvez également publier l’audience conjointement avec la cible. 

Pour modifier une audience, cliquez sur le lien hypertexte correspondant dans l’onglet **Audiences**, puis sur **Modifier** dans l’éditeur d’audience qui s’affiche. Pour afficher la liste des cibles et pages référençant une audience, sélectionnez l’audience dans la vue de liste d’audiences, puis cliquez sur **Afficher les affectations**. Pour supprimer une audience dans la vue de liste d’audiences ou dans l’éditeur d’audience, annulez sa publication si elle a déjà été publiée, puis cliquez sur **Supprimer** dans la barre de commandes.

> [!NOTE]
> Les audiences sont un concept au niveau du site dans le générateur de site Commerce. Vous pouvez partager la même audience sur plusieurs cibles.

### <a name="rename-an-audience-in-site-builder"></a>Renommer une audience dans le générateur de site

Pour renommer une audience existante dans le générateur de site Commerce, procédez comme suit :

1. Dans le volet de navigation à gauche, sélectionnez **Audiences**.
1. Sélectionnez le nom du segment de l’audience que vous souhaitez renommer.
1. Sélectionnez **Modifier** pour commencer à modifier l’audience.
1. Dans le volet des propriétés de l’audience, sélectionnez le symbole du stylo à côté du nom de l’audience.
1. Modifiez le nom de l’audience, le cas échéant.
1. Sélectionnez la coche pour confirmer le changement de nom.
1. Sélectionnez **Terminer la modification**.

## <a name="targets"></a>Cibles

Une cible est l’expérience utilisateur présentée aux membres d’une ou plusieurs audiences sélectionnées. Elle peut comprendre des variantes d’un ou plusieurs modules sur une page ou dans un fragment. 

Vous pouvez définir un calendrier pour vos cibles afin d’indiquer la durée pendant laquelle elles doivent rester actives. Notez que cette action est distincte de l’action de planification d’un groupe de publication déterminant le moment de la publication d’une collection de contenus. Vous pouvez également prévisualiser vos cibles pour voir à quoi elles ressembleront pour les membres des audiences sélectionnées. De plus, vous pouvez hiérarchiser vos cibles pour indiquer la cible à afficher en cas de conflit.

### <a name="create-a-target"></a>Créer une cible

Pour créer un shell cible pour des modules de page dans le générateur de site Commerce, procédez comme suit :

1. Dans le volet de navigation à gauche, sélectionnez **Pages**. Cliquez ensuite sur le lien hypertexte de la page contenant les modules que vous souhaitez cibler.
1. Cliquez sur **Modifier** pour consulter la page à des fins d’édition.
1. Dans le menu **Cible**, cliquez sur **Nouvelle cible** pour créer un shell cible. Vous pouvez créer plusieurs cibles sur une page, le cas échéant.
1. Saisissez un nom et une description pour votre cible, puis cliquez sur **Suivant**.
1. Cliquez sur **Ajouter** pour inclure les audiences qui verront le contenu ciblé ou pour exclure des audiences. Cliquez ensuite sur **Suivant**.

    > [!NOTE]
    > L’affectation d’audience est une étape facultative lors de la création de la cible. Cependant, avant de publier la cible, vous devez inclure au moins une audience pour vous assurer que les groupes d’utilisateurs visés verront le contenu ciblé.

1. Définissez la période d’affichage de votre cible en sélectionnant le fuseau horaire et les dates et heures de début et de fin. Vous pouvez définir la cible afin qu’elle s’affiche à tout moment sur la période ou sélectionner des jours et heures spécifiques. Ensuite, cliquez sur **Suivant**.

    > [!NOTE]
    > Les heures et le fuseau horaire que vous spécifiez sont globaux. Si vous souhaitez cibler différents emplacements à différentes heures ou dans différents fuseaux horaires, vous devez créer différentes cibles et définir le calendrier souhaité pour chaque emplacement.

1. Vérifiez les détails et lorsque tout semble correct, cliquez sur **Créer une expérience cible**, puis sur **Accéder à la cible**. Le shell cible est alors créé. Vous pouvez maintenant y ajouter des modules.
1. Sélectionnez le module à cibler, cliquez sur les points de suspension (**…**), puis sélectionnez **Ajouter à la cible actuelle**. Lorsque vous ciblez un module parent, tous ses enfants font partie de cette cible. Les modules ciblés sont surlignés en vert.
1. Apportez les mises à jour de contenu nécessaires au module ciblé, puis ajoutez d’autres modules à la cible, le cas échéant. Cliquez ensuite sur **Enregistrer** pour enregistrer toutes vos modifications.
1. Avant de publier votre cible, veillez à cliquer sur **Aperçu** dans la barre de commandes pour la consulter. Vous pouvez ensuite sélectionner l’une des options suivantes :

    - **Aperçu de base** : sélectionnez cette option pour prévisualiser uniquement la variante sélectionnée (page ou cible par défaut), sans aucune audience associée.
    - **Aperçu avancé** : sélectionnez cette option si vous avez plusieurs cibles sur une page et que vous souhaitez les prévisualiser en tant qu’utilisateur faisant partie d’un ensemble sélectionné d’audiences, ou à une date/heure spécifique. Cliquez sur **Suivant** pour faire votre choix parmi une liste d’audiences pertinentes. Vous pouvez également supprimer le filtre pour faire votre choix parmi toutes les audiences.

1. Lorsque vous êtes satisfait de la configuration cible, vous devez publier la page afin que la cible soit mise en service. Cliquez sur **Publier** afin que la cible soit mise en service immédiatement. Vous pouvez également utiliser un groupe de publication pour planifier la mise en service de la page. Pour en savoir plus sur les groupes de publication, consultez [Utiliser des groupes de publication](publish-groups.md).

Vous pouvez également cibler des fragments. La procédure est similaire. Cependant, à l’étape 1, vous sélectionnez **Fragment** au lieu de **Pages** dans le volet de navigation à gauche.

> [!NOTE]
> Pour éviter tout impact négatif sur vos indicateurs, vous pouvez avoir une expérience ou des cibles sur une page ou dans un fragment. Vous ne pouvez pas avoir à la fois une expérience et des cibles.

### <a name="manage-targets"></a>Gérer les cibles

Pour modifier, dupliquer ou supprimer des cibles, accédez à la page ou au fragment par défaut, puis procédez comme suit :

1. Dans le menu déroulant, sélectionnez **Cible**, puis cliquez sur **Gérer les cibles**.
1. Sélectionnez une cible à modifier, dupliquer ou supprimer.
1. Si vous avez plusieurs cibles dans le même module ou si plusieurs cibles ont des calendriers conflictuels, cliquez sur **Hiérarchiser les cibles** pour indiquer l’ordre dans lequel elles doivent s’afficher. Si vous ajoutez plusieurs cibles sur une page ou dans un fragment, le bouton **Hiérarchiser les cibles** s’affiche également dans la barre de notification pour vous rappeler de hiérarchiser les cibles. Si aucune priorité n’est spécifiée, la cible la plus récente est sélectionnée par défaut.

### <a name="localize-targets"></a>Localiser les cibles

Les cibles sur les pages et dans les fragments sont automatiquement incluses lorsque les fichiers XLIFF sont exportés et importés à des fins de localisation. Cependant, si des paramètres régionaux ne sont pas requis, vous pouvez supprimer leurs cibles après l’importation des fichiers XLIFF localisés.

> [!NOTE]
> Les cibles sont gérées par canal et par paramètre régional. Les modifications que vous apportez aux cibles d’un canal ou d’un paramètre régional ne sont pas automatiquement reportées sur d’autres canaux ou paramètres régionaux.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
