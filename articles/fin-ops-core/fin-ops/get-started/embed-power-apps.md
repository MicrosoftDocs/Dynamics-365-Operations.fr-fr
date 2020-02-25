---
title: Intégrer Power Apps
description: Cette rubrique décrit comment incorporer des Power Apps dans le client pour augmenter la fonctionnalité du produit.
author: jasongre
manager: AnnBe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: 9585d5a399ebf45b0ad7640f3c4e48d8afc46cd8
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3017726"
---
# <a name="embed-microsoft-power-apps"></a>Intégrer Microsoft Power Apps

[!include [banner](../includes/banner.md)]

Finance and Operations prend en charge l'intégration avec Microsoft Power Apps, un service pour les développeurs et les utilisateurs non techniques pour créer des applis métier personnalisées pour les appareils mobiles, les tablettes et le web sans écrire de code. Les Power Apps développées par vous, votre organisation ou l'écosystème élargi peuvent ensuite être incorporées dans les applications Finance and Operations pour augmenter la fonctionnalité du produit. Par exemple, vous pouvez créer une application depuis Power Apps en complément d'une application Finance and Operations avec des informations extraites d'un autre système.

Pour en savoir plus sur l'incorporation de Power Apps, visionnez la courte vidéo [Comment incorporer Power Apps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-app-from-power-apps-to-a-page"></a>Ajout d'une application Power Apps incorporée à une page

### <a name="overview"></a>Vue d'ensemble

Avant d'incorporer une application de Power Apps dans le client, vous devez d'abord rechercher ou créer une application avec les éléments visuels et/ou la fonctionnalité souhaités. Nous ne décrirons pas le processus détaillé de création d'applications ici. La rubrique [Présentation des Power Apps](https://docs.microsoft.com/powerapps/getting-started) est un bon point de départ si vous ne connaissez pas les Power Apps.

Lorsque vous êtes prêt à incorporer une application spécifique, vous pouvez choisir entre deux méthodes d'accès à l'application sur une page, selon celle qui convient le mieux à votre scénario. La première méthode consiste à utiliser le bouton Power Apps qui a été ajouté au volet Actions standard. Les applications ajoutées à l'aide de ce mécanisme s'affichent sous forme d'options de menu à l'intérieur du bouton de menu Power Apps. Lorsqu'elle est sélectionnée, chacune de ces options de menu ouvre un volet latéral contenant l'application incorporée. Vous pouvez également choisir d'intégrer une application directement sur une page en tant qu'onglet, raccourci ou panneau nouveau, ou en tant que nouvelle section dans un espace de travail.

Lorsque vous configurez votre application incorporée, vous pouvez sélectionner un champ unique à envoyer en tant que contexte à l'application. Cela permet à l'application d'être réactive en fonction des données actuellement affichées.

### <a name="details"></a>Détails

Les instructions suivantes indiquent comment incorporer une application depuis Power Apps dans le client web.

1. Accédez à la page où vous souhaitez incorporer l'application. Il s'agit de la même page que celle contenant les données à transférer à l'application comme entrée.
2. Ouvrez le volet **Ajouter une application depuis Power Apps** :

    - Cliquez sur **Options**, puis sélectionnez **Personnaliser cette page**. Sous le menu **Insérer**, choisissez **Power Apps**. Enfin, sélectionnez la région où vous souhaitez ajouter l'application. Si vous souhaitez incorporer l'application sous le bouton de menu Power Apps, choisissez le volet Actions. Si vous souhaitez incorporer l'application directement sur la page, choisissez l'onglet, le raccourici, le panneau ou la section approprié(e) (si vous êtes dans un espace de travail).
    - Si l'application est ouverte à l'aide du bouton de menu Power Apps, vous pouvez sinon cliquer sur le bouton de menu **Power Apps** dans le volet Actions standard, puis sélectionner **Ajouter une application**.

3. Configurez l'application incorporée :

    - Le champ **Nom** indique le texte affiché pour le bouton ou l'onglet contenant l'application incorporée. Il arrivera souvent que vous souhaitiez répéter le nom de l'application dans ce champ.
    - **ID d'application** est le GUID de l'application que vous souhaitez incorporer. Pour récupérer cette valeur, recherchez l'application sur [web.powerapps.com](https://web.powerapps.com), puis localisez le champ **ID d'application** sous **Détails**.
    - Pour **Contexte d'entrée de l'application**, vous pouvez également sélectionner le champ contenant les données à transmette à l'application comme entrée. Consultez la section plus loin dans cette rubrique intitulée [Création d'applications qui utilisent les données d'applications Finance and Operations](#building-a-power-app-that-leverages-data-sent-from-finance-and-operations-apps) pour en savoir plus sur la manière dont l'application peut accéder aux données envoyées depuis les applications Finance and Operations.
    - Choisissez la **Taille d'application** correspondant au type d'application que vous incorporez. Sélectionnez **Mince** pour les applications créées pour les appareils mobiles, et **Large** pour les applications créées pour les tablettes. Ainsi, une quantité suffisante d'espace est allouée pour l'application incorporée.
    - L'organisateur **Entités juridiques** permet de choisir les entités juridiques pour lesquelles l'application est disponible. La valeur par défaut consiste rendre l'application accessible pour toutes les entités juridiques. Cette option n'est disponible que si la fonctionnalité [Vues enregistrées](saved-views.md) est désactivée. 

4. Après avoir confirmé que la configuration est correcte, cliquez sur **Insérer** pour incorporer l'application Power App sur la page. Vous serez invité à actualiser le navigateur afin d'afficher l'application incorporée.

## <a name="sharing-an-embedded-app"></a>Partage d'une application incorporée

Après avoir incorporé une application une page et confirmé qu'elle fonctionne correctement avec n'importe quel contexte de données transmis à partir de la page, vous pouvez la partager avec d'autres utilisateurs du système. Cette opération peut être effectuée de deux manières à l'aide des fonctions de personnalisation du produit :

- Le scénario recommandé est par le biais de l'administrateur système, qui peut envoyer une personnalisation à tous les utilisateurs ou à un sous-ensemble d'utilisateurs.
- Vous pouvez également exporter les personnalisations de votre page, les envoyer à un ou plusieurs utilisateurs qui peuvent ensuite importer ces modifications. La barre d'outils de personnalisation a des actions qui vous permettent d'exporter et d'importer des personnalisations.

Consultez [Personnaliser l'expérience de l'utilisateur](personalize-user-experience.md) en savoir plus sur les fonctions de personnalisation du produit et leur utilisation.

## <a name="building-an-app-that-leverages-data-sent-from-finance-and-operations-apps"></a>Création d'une application qui exploite les données envoyées depuis des applications Finance and Operations

Une partie importante de la création d'une application à partir de Power Apps qui sera intégré dans une application Finance and Operations utilise les données d'entrée de cette application. Depuis l'expérience de développement de Power Apps, les données d'entrée transmises à partir d'une application Finance and Operations sont accessibles à l'aide de la variable Param("EntityId").

Par exemple, dans la fonction OnStart de l'application, vous pouvez paramétrer les données d'entrée des applications Finance and Operations sur une variable comme suit :

```
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-app"></a>Affichage d'une application

Pour afficher une application incorporée sur une page dans les applications Finance and Operations, accédez simplement à une page contenant une application incorporée. N'oubliez pas que les applications sont accessibles via le bouton Power Apps dans le volet Actions standard, ou peuvent s'afficher directement sur la page en tant que nouvel onglet, organisateur, panneau, ou en tant que nouvelle section dans un espace de travail. Lorsqu'un utilisateur tente pour la première fois de charger une application sur une page, il est invité à se connecter pour s'assurer qu'il dispose des autorisations nécessaires pour utiliser l' application.

## <a name="editing-an-embedded-app"></a>Modification d'une application incorporée

Une fois qu'une application a été incorporée sur une page, vous devez apporter des modifications à la configuration de cette application. Par exemple, vous souhaitez peut-être modifier l'étiquette associée à l'application incorporée, ou une nouvelle version de l'application a été créée et vous devez mettre à jour l'ID d'application pour pointer vers la plus récente.

Pour modifier la configuration d'une application incorporée, procédez comme suit :

1. Accédez au volet **Modifier l'application**.

    - Si l'application incorporée est ouverte via le bouton de menu Power Apps, cliquez avec le bouton droit sur le bouton de menu Power Apps et sélectionnez **Personnaliser**. Sélectionnez l'application à configurer dans le menu déroulant **Sélectionner une application**.
    - Si l'application incorporée s'affiche directement dans la page, sélectionnez **Options**, puis **Personnaliser cette page**. À l'aide de l'outil **Sélectionner**, cliquez sur l'application incorporée.

2. Apportez les modifications nécessaires à la configuration de l'application, puis cliquez sur **Enregistrer**.

## <a name="removing-an-app"></a>Suppression d'une application

Une fois qu'une application a été incorporée dans une page, il existe deux méthodes pour la supprimer si nécessaire :

- Accédez au volet **Modifier une application** à l'aide des instructions contenues dans la section [Modification d'une application incorporée](#editing-an-embedded-power-app) plus haut dans cette rubrique. Vérifiez que le volet affiche les informations associées à l'application incorporée que vous souhaitez supprimer, puis cliquez sur le bouton **Supprimer**.
- L'application incorporée étant enregistrée en tant que données de personnalisation, la suppression de la personnalisation de votre page entraîne également la suppression des applications incorporées dans cette page. Notez que la suppression de la personnalisation de la page est définitive et ne peut pas être annulée. Pour supprimer vos personnalisations dans une page, sélectionnez **Options**, puis **Personnaliser cette page**, et enfin le bouton **Effacer**. Après avoir actualisé votre navigateur, toutes les personnalisations précédentes pour cette page sont supprimées. Consultez [Personnaliser l'expérience de l'utilisateur](personalize-user-experience.md) pour plus d'informations sur l'optimisation des pages à l'aide de la personnalisation.

## <a name="appendix"></a>Annexe

### <a name="developer-control-over-where-an-app-can-be-embedded"></a>Contrôle du développeur sur l'emplacement d'incorporation d'une application

Par défaut, les utilisateurs peuvent incorporer les applications sur n'importe quelle page, sous le bouton de menu Power Apps ou directement sur la page en tant qu'onglet, raccourci, panneau, ou nouvelle section dans un espace de travail. Toutefois, si nécessaire, les développeurs peuvent également configurer cette fonctionnalité pour autoriser l'incorporation des applications uniquement sur certaines pages en mettant en œuvre les méthodes suivantes :

- **isPowerAppPersonalizationEnabled** – Si cette méthode renvoie false pour une page spécifique, le bouton de menu Power Apps ne s'affiche pas, et les utilisateurs ne peuvent pas incorporer des applications n'importe où sur cette page, notamment comme onglet.
- **isPowerAppTabPersonalizationEnabled** – Si cette méthode renvoie false pour une page spécifique, les utilisateurs ne peuvent pas incorporer des applications directement dans la page en tant qu'onglet, raccourci ou section de panorama. Les utilisateurs peuvent toujours incorporer des applications via le bouton de menu Power Apps si l'incorporation est autorisée sur la page.

L'exemple suivant présente une nouvelle classe avec les deux méthodes nécessaires pour configurer l'emplacement d'incorporation des applications.

```
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
