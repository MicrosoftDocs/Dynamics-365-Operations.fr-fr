---
title: Incorporer des applications canevas à partir de Power Apps
description: Cette rubrique explique comment incorporer des applications canevas de Microsoft Power Apps dans le client pour augmenter la fonctionnalité du produit.
author: jasongre
manager: AnnBe
ms.date: 11/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: ba3b736aeae8540349309ddd82bd431720b9701c
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693481"
---
# <a name="embed-canvas-apps-from-power-apps"></a>Incorporer des applications canevas à partir de Power Apps

[!include [banner](../includes/banner.md)]

Microsoft Power Apps est un service qui permet aux développeurs et aux utilisateurs non techniciens de générer des applications d’entreprise personnalisées pour les appareils mobiles, les tablettes et le web sans écrire de code. Les applications Finance and Operations prennent en charge l’intégration avec Power Apps. Les applications canevas développées par vous, votre organisation ou l’écosystème élargi peuvent être incorporées dans les applications Finance and Operations pour augmenter la fonctionnalité du produit. Par exemple, vous pouvez créer une application canevas de Power Apps en complément d’une application Finance and Operations avec des informations extraites d’un autre système.

Pour en savoir plus sur l’incorporation de Power Apps, visionnez la courte vidéo [Comment incorporer Power Apps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>Ajout d’une application canevas Power Apps incorporée à une page

### <a name="overview"></a>Vue d’ensemble

Avant d’incorporer une application canevas de Power Apps dans le client, vous devez rechercher ou créer une application avec les visuels ou les fonctionnalités souhaités. Cette rubrique ne contient pas de description détaillée du processus de création d’applications. Si vous ne connaissez pas Power Apps, consultez la [documentation de Power Apps](https://docs.microsoft.com/powerapps/).

Il existe deux façons d’accéder à une application canevas spécifique sur une page lorsque vous êtes prêt à incorporer l’application. Vous pouvez choisir l’approche qui convient le mieux à votre scénario. La première approche utilise le bouton **Power Apps** qui a été ajouté au volet Actions standard. Les applications que vous ajoutez à l’aide de cette approche s’affichent sous forme d’éléments sur le bouton de menu **Power Apps**. Lorsque vous sélectionnez l’un de ces éléments, un volet latéral contenant l’application incorporée s’affiche. Vous pouvez également incorporer une application directement sur une page en tant que nouvel onglet, raccourci ou panneau, ou en tant que nouvelle section dans un espace de travail.

Lorsque vous configurez votre application canevas incorporée, vous pouvez sélectionner un champ unique à envoyer comme contexte à l’application. Cette étape permet à l’application d’être réactive en fonction des données actuellement affichées.

> [!NOTE]
> Vous ne pouvez pas utiliser actuellement ce mécanisme pour incorporer des applications modélisées.  

### <a name="details"></a>Détails

La procédure suivante indique comment incorporer une application canevas de Power Apps dans le client web.

1. Accédez à la page où vous souhaitez incorporer l’application canevas. Cette page sera celle contenant les données à transférer à l’application comme entrée.
2. Ouvrez le volet **Ajouter une application depuis Power Apps** :

    - Cliquez sur **Options**, puis sélectionnez **Personnaliser cette page**. Sous le menu **Insérer**, choisissez **Power Apps**. Enfin, sélectionnez la région où vous souhaitez ajouter l’application. Si vous souhaitez incorporer l’application sous le bouton de menu Power Apps, choisissez le volet Actions. Si vous souhaitez incorporer l’application directement sur la page, choisissez l’onglet, le raccourici, le panneau ou la section approprié(e) (si vous êtes dans un espace de travail).
    - Si l’application est ouverte à l’aide du bouton de menu Power Apps, vous pouvez sinon cliquer sur le bouton de menu **Power Apps** dans le volet Actions standard, puis sélectionner **Ajouter une application**.

3. Configurez l’application incorporée :

    - Le champ **Nom** indique le texte affiché pour le bouton ou l’onglet contenant l’application incorporée. Il arrivera souvent que vous souhaitiez répéter le nom de l’application dans ce champ.
    - Le champ **ID d’application** indique l’identificateur global unique (GUID) de l’application canevas que vous souhaitez incorporer. Pour récupérer cette valeur, recherchez l’application sur [make.powerapps.com](https://make.powerapps.com), puis consultez le champ **ID d’application** sous **Détails**.
    - Pour **Contexte d’entrée de l’application**, vous pouvez également sélectionner le champ contenant les données à transmette à l’application comme entrée. Consultez la section plus loin dans cette rubrique intitulée [Création d’une application qui utilise les données envoyées depuis les applications Finance and Operations](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps) pour en savoir plus sur la manière dont l’application peut accéder aux données envoyées depuis les applications Finance and Operations.
    - Choisissez la **Taille d’application** correspondant au type d’application que vous incorporez. Sélectionnez **Mince** pour les applications créées pour les appareils mobiles, et **Large** pour les applications créées pour les tablettes. Ainsi, une quantité suffisante d’espace est allouée pour l’application incorporée.
    - L’organisateur **Entités juridiques** permet de choisir les entités juridiques pour lesquelles l’application est disponible. La valeur par défaut consiste rendre l’application accessible pour toutes les entités juridiques. Cette option n’est disponible que si la fonctionnalité [Vues enregistrées](saved-views.md) est désactivée. 

4. Après avoir confirmé que la configuration est correcte, cliquez sur **Insérer** pour incorporer l’application Power App sur la page. Vous serez invité à actualiser le navigateur afin d’afficher l’application incorporée.

## <a name="sharing-an-embedded-app"></a>Partage d’une application incorporée

Après avoir incorporé une application canevas sur une page et confirmé qu’elle fonctionne correctement avec n’importe quel contexte de données transmis à partir de cette page, vous pouvez partager l’application avec d’autres utilisateurs du système. Pour partager une application canevas intégrée, procédez comme suit.

1. [Partagez l’application canevas](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) avec les utilisateurs appropriés, afin qu’ils puissent accéder à l’application dans Power Apps. 

2. Vérifiez que les utilisateurs ciblés disposent des personnalisations appropriées, afin que l’application incorporée apparaisse lorsque ces utilisateurs affichent la page. Vous pouvez utiliser les approches suivantes :

    - Recommandé : utilisez la fonctionnalité [Vues enregistrées](saved-views.md) pour créer et publier une vue contenant l’application incorporée. Cette approche garantit que tous les utilisateurs disposant des rôles de sécurité ciblés par la vue publiée verront l’application dans les applications Finance and Operations. 
    - Si la fonctionnalité Vues enregistrées n’est pas activée, vous pouvez demander à l’administrateur système d’envoyer une personnalisation incluant l’application incorporée à tous les utilisateurs ou à un sous-ensemble d’utilisateurs. Vous pouvez également exporter les personnalisations de votre page et les envoyer à un ou plusieurs utilisateurs. Chacun de ces utilisateurs peut ensuite importer les personnalisations. La barre d’outils de personnalisation a des actions qui vous permettent d’exporter et d’importer des personnalisations. 
    
> [!NOTE]
> Si l’application canevas a été partagée avec des utilisateurs externes, ces utilisateurs ne peuvent pas utiliser l’application incorporée dans les applications Finance and Operations. Cependant, ils peuvent accéder à l’application directement dans Power Apps. Les utilisateurs externes comprennent les invités et les utilisateurs qui n’appartiennent pas à Microsoft 365 Azure Directory où l’application Finance and Operations est déployée.

Consultez [Personnaliser l’expérience de l’utilisateur](personalize-user-experience.md) en savoir plus sur les fonctions de personnalisation du produit et leur utilisation.

## <a name="building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps"></a>Création d’une application canevas qui utilise les données envoyées depuis les applications Finance and Operations

Lorsque vous créez une application canevas qui sera incorporée dans une application Finance and Operations, une partie importante du processus consiste à utiliser les données d’entrée de cette appplication Finance and Operations. Depuis l’expérience de développement de Power Apps, les données d’entrée transmises à partir d’une application Finance and Operations sont accessibles à l’aide de la variable **Param("EntityId")**.

Par exemple, dans la fonction OnStart de l’application, vous pouvez paramétrer les données d’entrée des applications Finance and Operations sur une variable comme suit :

```powerapps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-a-canvas-app"></a>Affichage d’une application canevas

Pour afficher une application canevas incorporée sur une page dans les applications Finance and Operations, accédez simplement à une page contenant une application incorporée. N’oubliez pas que les applications sont accessibles à l’aide du bouton **Power Apps** sur le volet Actions standard. Elles peuvent également apparaître directement sur la page en tant que nouvel onglet, raccourci ou panneau, ou en tant que nouvelle section dans un espace de travail. Lorsque les utilisateurs essaient pour la première fois de charger une application sur une page, ils sont invités à se connecter. Cette étape garantit que les utilisateurs disposent des autorisations appropriées pour utiliser l’application.

## <a name="editing-an-embedded-app"></a>Modification d’une application incorporée

Une fois qu’une application a été incorporée sur une page, vous devez apporter des modifications à la configuration de cette application. Par exemple, vous souhaitez peut-être modifier l’étiquette associée à l’application incorporée, ou une nouvelle version de l’application a été créée et vous devez mettre à jour l’ID d’application pour pointer vers la plus récente.

Pour modifier la configuration d’une application incorporée, procédez comme suit :

1. Accédez au volet **Modifier l’application**.

    - Si l’application incorporée est ouverte via le bouton de menu Power Apps, cliquez avec le bouton droit sur le bouton de menu Power Apps et sélectionnez **Personnaliser**. Sélectionnez l’application à configurer dans le menu déroulant **Sélectionner une application**.
    - Si l’application incorporée s’affiche directement dans la page, sélectionnez **Options**, puis **Personnaliser cette page**. À l’aide de l’outil **Sélectionner**, cliquez sur l’application incorporée.

2. Apportez les modifications nécessaires à la configuration de l’application, puis cliquez sur **Enregistrer**.

## <a name="removing-an-app"></a>Suppression d’une application

Une fois qu’une application a été incorporée dans une page, il existe deux méthodes pour la supprimer si nécessaire :

- Accédez au volet **Modifier une application** à l’aide des instructions contenues dans la section [Modification d’une application incorporée](#editing-an-embedded-app) plus haut dans cette rubrique. Vérifiez que le volet affiche les informations associées à l’application incorporée que vous souhaitez supprimer, puis cliquez sur le bouton **Supprimer**.
- L’application incorporée étant enregistrée en tant que données de personnalisation, la suppression de la personnalisation de votre page entraîne également la suppression des applications incorporées dans cette page. Notez que la suppression de la personnalisation de la page est définitive et ne peut pas être annulée. Pour supprimer vos personnalisations dans une page, sélectionnez **Options**, puis **Personnaliser cette page**, et enfin le bouton **Effacer**. Après avoir actualisé votre navigateur, toutes les personnalisations précédentes pour cette page sont supprimées. Consultez [Personnaliser l’expérience de l’utilisateur](personalize-user-experience.md) pour plus d’informations sur l’optimisation des pages à l’aide de la personnalisation.

## <a name="appendix"></a>Annexe

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