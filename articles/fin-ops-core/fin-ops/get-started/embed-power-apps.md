---
title: Incorporer des applications canevas à partir de Power Apps
description: Cet article explique comment incorporer des applications canevas de Microsoft Power Apps dans le client pour augmenter la fonctionnalité du produit.
author: jasongre
ms.date: 09/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: fb81aa058e749df346ee87bbe83427b20b234b72
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898396"
---
# <a name="embed-canvas-apps-from-power-apps"></a>Incorporer des applications canevas à partir de Power Apps

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Microsoft Power Apps est un service qui permet aux développeurs et aux utilisateurs non techniciens de générer des applications d’entreprise personnalisées pour les appareils mobiles, les tablettes et le web sans écrire de code. Intégration du support des applications Finances et Opérations avec Power Apps. Les applications canevas développées par vous, votre organisation ou l’écosystème élargi peuvent être incorporées dans les applications Finances et Opérations pour augmenter la fonctionnalité du produit. Par exemple, vous pouvez créer une application canevas de Power Apps en complément d’une application de finances et d’opérations avec des informations extraites d’un autre système.

Pour en savoir plus sur l’incorporation d’applications canevas, visionnez la courte vidéo [Comment incorporer des applications canvas](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>Ajout d’une application canevas Power Apps incorporée à une page

Avant d’incorporer une application canevas de Power Apps dans le client, vous devez rechercher ou créer une application avec les visuels ou les fonctionnalités souhaités. Cet article ne contient pas de description détaillée du processus de création d’applications. Si vous ne connaissez pas Power Apps, consultez la [documentation de Power Apps](/powerapps/).

Il existe trois façons d’intégrer une application canevas dans une application de finances et d’opérations. Vous pouvez utiliser l’approche qui correspond le mieux à votre scénario. 

- Intégrez l’application canevas dans le bouton **Power Apps** sur le volet Actions standard d’une page. Les applications que vous ajoutez de cette manière apparaissent en tant qu’éléments sur le bouton du menu **Power Apps** et les applications s’ouvrent dans les volets latéraux. 
- Incorporez directement l’application canevas ou le site Web sur une page existante en tant que nouvelle page d’onglet (section d’onglet pivotant, de raccourci, de panneau ou d’espace de travail).
- Créez une nouvelle expérience pleine page pour l’application canevas à partir du tableau de bord.

Lorsque vous configurez votre application canevas incorporée, vous pouvez sélectionner un champ unique à envoyer comme contexte à l’application. Cette étape permet à l’application d’être réactive en fonction des données actuellement affichées.

> [!NOTE]
> Vous ne pouvez pas utiliser ce mécanisme pour incorporer des applications pilotées par modèle.

### <a name="embedding-a-canvas-app-on-an-existing-page"></a>Intégrer une application canevas sur une page existante

La procédure suivante indique comment incorporer une application canevas sur une page existante depuis Power Apps.

1. Accédez à la page où vous souhaitez incorporer l’application canevas. Cette page sera celle contenant les données à transférer à l’application comme entrée.
2. Ouvrez le volet **Ajouter une application depuis Power Apps** :

    - Si l’application est intégrée directement sur la page, sélectionnez **Options** \> **Personnaliser cette page** \> **Plus**, puis suivez l’une des étapes suivantes :

        - Si la fonction **Applications pleine page** est activée, sélectionnez **Ajouter une page**, puis sélectionnez la région dans laquelle vous souhaitez ajouter l’application. Pour intégrer l’application dans le bouton de menu **Power Apps**, sélectionnez le volet Actions. Pour incorporer l’application directement sur la page, sélectionnez l’onglet, le raccourci, le panneau ou la section approprié(e) (si vous êtes dans un espace de travail). Ensuite, dans le volet **Ajouter une application**, sélectionnez **Power Apps**.
        - Si la fonction **Applications pleine page** est désactivée, sélectionnez **Ajouter une application depuis Power Apps**, puis sélectionnez la région dans laquelle vous souhaitez ajouter l’application. Pour intégrer l’application dans le bouton de menu **Power Apps**, sélectionnez le volet Actions. Pour incorporer l’application directement sur la page, sélectionnez l’onglet, le raccourci, le panneau ou la section approprié(e) (si vous êtes dans un espace de travail).

    - Si l’application est ouverte à l’aide du bouton de menu **Power Apps**, vous pouvez sélectionner le bouton de menu **Power Apps** dans le volet Actions standard, puis sélectionner **Ajouter une application**.

3. Configurez l’application incorporée. Pour plus d’informations, voir la section [Configuration d’une application canevas](#configuring-a-canvas-app) plus loin dans cet article.
4. Après avoir confirmé que la configuration est correcte, sélectionnez **Insérer**.

    - Si la fonction **Vues enregistrées** est désactivée, vous êtes invité à actualiser le navigateur pour voir l’application intégrée.
    - Si la fonction **Vues enregistrées** est activée, vous devez enregistrer la vue pour que la modification soit conservée.

### <a name="embedding-a-canvas-app-as-a-full-page-experience-from-the-dashboard"></a>Intégrer une application canevas en tant qu’expérience pleine page à partir du tableau de bord

Intégrez une application canevas depuis le tableau de bord si l’application que vous souhaitez intégrer n’est pas liée à une page existante, ou si vous souhaitez simplement faire apparaître l’application comme une expérience pleine page pour l’application dans l’application de finances et d’opérations.

> [!NOTE]
> Pour rendre cette fonctionnalité disponible, vous devez activer la fonction **Applications pleine page** dans la gestion des fonctionnalités. 

1. Ouvrez le tableau de bord.
2. Sélectionnez et maintenez sélectionnée (ou cliquez avec le bouton droit) la page, sélectionnez **Personnaliser**, puis sélectionnez **Ajouter une page**.
3. Dans le volet **Ajouter une page**, sélectionnez **Power Apps**.
4. Configurez l’application incorporée. Pour plus d’informations, voir la section [Configuration d’une application canevas](#configuring-a-canvas-app) plus loin dans cet article.
5. Sélectionnez **Sauvegarder** pour ajouter l’application au tableau de bord en tant que nouvelle mosaïque.
6. Sélectionnez la nouvelle mosaïque sur le tableau de bord et confirmez que l’application canevas apparaît comme prévu.

### <a name="configuring-a-canvas-app"></a>Configuration d’une application canevas

Lorsque vous intégrez une application canevas, vous devez définir les paramètres suivants :

- **Nom** : saisissez le texte à afficher pour le bouton ou l’onglet contenant l’application incorporée. Il arrivera souvent que vous souhaitiez répéter le nom de l’application dans ce champ.
- **ID d’application** : ce champ indique l’identificateur global unique (GUID) de l’application canevas que vous souhaitez incorporer. Pour récupérer cette valeur, recherchez l’application sur [make.powerapps.com](https://make.powerapps.com), puis consultez le champ **ID d’application** sous **Détails**.
- **Contexte d’entrée de l’application** : vous pouvez également sélectionner le champ contenant les données à transmette à l’application comme entrée. Pour en savoir plus sur la manière dont l’application peut accéder aux données envoyées depuis les applications Finances et Opérations, voir [Création d’une application qui exploite les données envoyées depuis les applications Finances et Opérations](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps) ultérieurement dans cet article.

    À partir de la version 10.0.19, l’entité juridique actuelle sera également transmise en tant que contexte à l’application canevas via le paramètre d’URL **cmp**. Ce comportement n’affecte pas l’application canevas cible tant que cette application n’utilise pas ces informations.

- **Taille d’application** : sélectionnez le type d’application que vous incorporez. Sélectionnez **Mince** pour les applications créées pour les appareils mobiles, ou **Large** pour les applications créées pour les tablettes. Ce paramètre garantit que suffisamment d’espace est alloué pour l’application incorporée.
- **Entités juridiques** : vous pouvez sélectionner les entités juridiques pour lesquelles l’application doit être disponible. Par défaut, l’application est disponible pour toutes les personnes juridiques. Cette option n’est disponible que lorsque vous intégrez directement sur une page existante et que la fonction **[Vues enregistrées](saved-views.md)** est désactivée.

## <a name="sharing-an-embedded-app"></a>Partage d’une application incorporée

Après avoir incorporé une application canevas sur une page et confirmé qu’elle fonctionne correctement, vous pouvez partager l’application avec d’autres utilisateurs du système. Pour partager une application canevas intégrée, procédez comme suit.

1. [Partagez l’application canevas dans Power Apps](/powerapps/maker/canvas-apps/share-app) avec les utilisateurs appropriés, afin qu’ils puissent accéder directement à l’application dans Power Apps.
2. Partagez les personnalisations associées à l’application intégrée avec les utilisateurs souhaités. Vous pouvez utiliser les approches suivantes :

    - **Publier la vue (recommandé) :** si la fonction **[Vues enregistrées](saved-views.md)** est activée, l’approche recommandée et préférée consiste à créer une vue qui inclut l’application canevas intégrée, puis à publier cette vue pour les utilisateurs souhaités. Cette approche garantit que tous les utilisateurs disposant des rôles de sécurité ciblés par la vue publiée verront l’application canevas sur la page.

        Vous pouvez également publier une application canevas qui a été incorporée en tant qu’expérience pleine page à partir du tableau de bord. Sur le tableau de bord, sélectionnez et maintenez sélectionnée (ou cliquez avec le bouton droit) la mosaïque associée à l’application, sélectionnez **Personnaliser**, puis sélectionnez **Publier la page**. Une expérience qui ressemble à l’expérience *Publier des vues* est affichée et vous pouvez sélectionner les rôles de sécurité sur lesquels publier. Dans la mise à jour 10.0.21 ou ultérieure, si la fonction **Prise en charge améliorée des entités juridiques pour les vues enregistrées** est activée, vous pouvez également publier l’application sur les entités juridiques souhaitées.

    - Si la fonction **Vues enregistrées** est désactivée, l’administrateur système peut donner une personnalisation qui inclut l’application canevas à l’ensemble d’utilisateurs approprié via la page **Personnalisation**. Vous pouvez également exporter les personnalisations de votre page et les envoyer à un ou plusieurs utilisateurs. Chacun de ces utilisateurs peut ensuite importer la personnalisation. La barre d’outils de personnalisation a des boutons qui vous permettent d’exporter et d’importer des personnalisations.

> [!NOTE]
> Si l’application canevas a été partagée avec des utilisateurs externes, ces utilisateurs ne peuvent pas utiliser l’application incorporée dans les applications Finances et Opérations. Cependant, ils peuvent accéder à l’application directement dans Power Apps. Les utilisateurs externes comprennent les invités et les utilisateurs qui n’appartiennent pas à Microsoft 365 Azure Directeory où l’application de finances et d’opérations est déployée.

Consultez [Personnaliser l’expérience de l’utilisateur](personalize-user-experience.md) en savoir plus sur les fonctions de personnalisation du produit et leur utilisation.

## <a name="building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps"></a>Création d’une application canevas qui utilise les données envoyées depuis les applications Finances et Opérations

Lorsque vous créez une application canevas qui sera incorporée dans une application de finances et d’opérations, une partie importante du processus consiste à utiliser les données d’entrée de cette appplication Finances et Opérations. Depuis l’expérience de développement de Power Apps, les données d’entrée transmises à partir d’une application de finances et d’opérations sont accessibles à l’aide de la variable **Param("EntityId")**. De plus, à partir de la version 10.0.19, l’entité juridique actuelle sera également transmise en tant que contexte à l’application canevas via la variable **Param("cmp")**. 

Par exemple, dans la fonction OnStart de l’application, vous pouvez définir les données d’entrée des applications Finances et Opérations sur une variable comme suit :

``` Power Apps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));

If(!IsBlank(Param("cmp")), Set(FinOpsLegalEntity, Param("cmp")), Set(FinOpsLegalEntity, ""));
```

## <a name="viewing-a-canvas-app"></a>Affichage d’une application canevas

Pour afficher une application canevas incorporée sur une page dans les applications Finances et Opérations, accédez simplement à une page contenant une application incorporée. N’oubliez pas que les applications sont accessibles à l’aide du bouton **Power Apps** sur le volet Actions standard. Elles peuvent également apparaître directement sur la page en tant que nouvel onglet, raccourci ou panneau, ou en tant que nouvelle section dans un espace de travail. Lorsque les utilisateurs essaient pour la première fois de charger une application sur une page, ils sont invités à se connecter. Cette étape garantit que les utilisateurs disposent des autorisations appropriées pour utiliser l’application.

## <a name="editing-an-embedded-app"></a>Modification d’une application incorporée

Une fois qu’une application a été incorporée sur une page, vous devez apporter des modifications à la configuration de cette application. Par exemple, vous souhaitez peut-être modifier l’étiquette associée à l’application incorporée, ou une nouvelle version de l’application a été créée et vous devez mettre à jour l’ID d’application pour pointer vers la plus récente.

Pour modifier la configuration d’une application incorporée, procédez comme suit :

1. Accédez au volet **Modifier l’application**.

    - Si l’application incorporée est ouverte via le bouton de menu Power Apps, sélectionnez et maintenez enfoncé (ou cliquez avec le bouton droit) sur le bouton de menu Power Apps et sélectionnez **Personnaliser**. Sélectionnez l’application à configurer dans le menu déroulant **Sélectionner une application**.
    - Si l’application incorporée s’affiche directement dans la page, sélectionnez **Options**, puis **Personnaliser cette page**. À l’aide de l’outil **Sélectionner**, cliquez sur l’application incorporée.
    - Si l’application intégrée a été ajoutée à partir du tableau de bord, ouvrez le tableau de bord, sélectionnez et maintenez enfoncé (ou cliquez avec le bouton droit) sur la vignette associée à l’application canevas, sélectionnez **Personnaliser**, puis **Modifier la page**.

2. Apportez les modifications nécessaires à la configuration de l’application, puis cliquez sur **Enregistrer**.

## <a name="removing-an-app"></a>Suppression d’une application

Une fois qu’une application a été incorporée dans une page, il existe quelques méthodes pour la supprimer si nécessaire :

- Accédez au volet **Modifier une application** à l’aide des instructions contenues dans la section [Modification d’une application incorporée](#editing-an-embedded-app) plus haut dans cet article. Vérifiez que le volet affiche les informations associées à l’application incorporée que vous souhaitez supprimer, puis cliquez sur le bouton **Supprimer**.
- Si l’application intégrée a été ajoutée à partir du tableau de bord, ouvrez le tableau de bord, sélectionnez et maintenez enfoncé (ou cliquez avec le bouton droit) sur la vignette associée à l’application canevas, sélectionnez **Personnaliser**, puis **Modifier la page**. 
- L’application incorporée étant enregistrée en tant que données de personnalisation, la suppression de la personnalisation de votre page entraîne également la suppression des applications incorporées dans cette page. Notez que la suppression de la personnalisation de la page est définitive et ne peut pas être annulée. Pour supprimer vos personnalisations dans une page, sélectionnez **Options**, puis **Personnaliser cette page**, et enfin le bouton **Effacer**. Après avoir actualisé votre navigateur, toutes les personnalisations précédentes pour cette page sont supprimées. Consultez [Personnaliser l’expérience de l’utilisateur](personalize-user-experience.md) pour plus d’informations sur l’optimisation des pages à l’aide de la personnalisation.

## <a name="appendix"></a>Annexe

### <a name="developer-modeling-a-canvas-app-on-a-form"></a>[Développeur] Modélisation d’une application canvas sur un formulaire

Bien que cet article concerne l’incorporation d’applications canevas via la personnalisation, les développeurs ont également la possibilité d’ajouter une application canevas à un formulaire à l’aide de l’expérience de développement Visual Studio. Pour ce faire, ajoutez simplement un PowerAppsHostControl au formulaire. Les propriétés de métadonnées disponibles pour le contrôle offrent les mêmes fonctionnalités que l’expérience de personnalisation.

### <a name="developer-specifying-where-an-app-can-be-embedded"></a>[Développeur] Spécification de l’emplacement d’incorporation d’une application

Par défaut, les utilisateurs peuvent incorporer les applications sur n’importe quelle page, sous le bouton de menu Power Apps ou directement sur la page en tant qu’onglet, raccourci, panneau, ou nouvelle section dans un espace de travail. Toutefois, si nécessaire, les développeurs peuvent également configurer cette fonctionnalité pour autoriser l’incorporation des applications uniquement sur certaines pages en mettant en œuvre les méthodes suivantes :

- **isPowerAppPersonalizationEnabled** – Si cette méthode renvoie false pour une page spécifique, le bouton de menu Power Apps ne s’affiche pas, et les utilisateurs ne peuvent pas incorporer des applications n’importe où sur cette page, notamment comme onglet.
- **isPowerAppTabPersonalizationEnabled** – Si cette méthode renvoie false pour une page spécifique, les utilisateurs ne peuvent pas incorporer des applications directement dans la page en tant qu’onglet, raccourci ou section de panorama. Les utilisateurs peuvent toujours incorporer des applications via le bouton de menu Power Apps si l’incorporation est autorisée sur la page.

L’exemple suivant présente une nouvelle classe avec les deux méthodes nécessaires pour configurer l’emplacement d’incorporation des applications.

```powerapps
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{
    public static boolean isPowerAppPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPersonalizationEnabled(pageName);
        return result;
    }
    
    public static boolean isPowerAppTabPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppTabPersonalizationEnabled(pageName);
        return result;
    }
}
```

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
