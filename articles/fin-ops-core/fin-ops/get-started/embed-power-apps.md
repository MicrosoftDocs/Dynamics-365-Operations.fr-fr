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
ms.openlocfilehash: 8b5e64cb9ba916f9cbd628703394318b4044867b
ms.sourcegitcommit: dc953c316c396c45ddd596e25c2b358e39a95d84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/02/2019
ms.locfileid: "2870239"
---
# <a name="embed-microsoft-power-apps"></a>Intégrer Microsoft Power Apps

[!include [banner](../includes/banner.md)]

Platform update 14 prend en charge l'intégration avec Microsoft Power Apps, un service pour les développeurs et les utilisateurs non techniques pour créer des applications d'entreprise personnalisées pour les appareils mobiles, les tablettes et le Web sans écrire de code. Power Apps développées par vous, votre organisation ou l'écosystème élargi peuvent ensuite être incorporées dans les applications Finance and Operations pour augmenter la fonctionnalité du produit. Par exemple, vous pouvez créer une application Power App pour ajouter aux applications Finance and Operations des informations extraites d'un autre système.

Pour en savoir plus sur l'incorporation de Power Apps, visionnez la courte vidéo [Comment incorporer Power Apps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-power-app-to-a-page"></a>Ajout d'une application Power App incorporée à une page

### <a name="overview"></a>Présentation

Avant d'incorporer une application PowerApp dans le client, vous devez d'abord rechercher ou créer une application PowerApp avec les éléments visuels et/ou la fonctionnalité souhaités. Nous ne décrirons pas le processus détaillé de création d'une application Power App ici. La rubrique [Présentation des Power Apps](https://docs.microsoft.com/powerapps/getting-started) est un bon point de départ si vous ne connaissez pas les Power Apps.

Lorsque vous êtes prêt à incorporer une application Power App spécifique, vous pouvez choisir entre deux méthodes d'accès à l'application Power App sur une page, selon celle qui convient le mieux à votre scénario. La première méthode consiste à utiliser le bouton Power Apps qui a été ajouté au volet Actions standard. Les Power Apps ajoutées à l'aide de ce mécanisme s'affichent sous forme d'options de menu à l'intérieur du bouton de menu Power Apps. Lorsqu'elle est sélectionnée, chacune de ces options de menu ouvre un volet latéral contenant l'application Power App incorporée. Vous pouvez également choisir d'afficher une application Power App directement sur une page en tant que nouvel onglet, organisateur, panneau, ou en tant que nouvelle section dans un espace de travail.

Lorsque vous configurez votre application Power App incorporée, vous pouvez sélectionner un champ unique à envoyer en tant que entrée vers l'application Power App. Cela permet à l'application Power App d'être réactive en fonction des données actuellement affichées.

### <a name="details"></a>Détails

Les instructions suivantes indiquent comment incorporer une application Power App dans le client Web.

1. Accédez à la page où vous souhaitez incorporer l'application Power App. Il s'agit de la même page que celle contenant les données à transférer à l'application Power App comme entrée.
2. Ouvrez le volet **Insérer une application Power App** :

    - Cliquez sur **Options**, puis sélectionnez **Personnaliser cet écran**. Sous le menu **Insérer**, choisissez **Power App**. Enfin, sélectionnez la région où vous souhaitez ajouter l'application Power App. Si vous souhaitez incorporer l'application Power App sous le bouton de menu Power Apps, choisissez le volet Actions. Si vous souhaitez incorporer l'application Power App directement sur la page, choisissez l'onglet, l'organisateur, le panneau ou la section appropriée (si vous êtes dans un espace de travail).
    - Si l'application Power App est accessible à l'aide du bouton de menu Power Apps, vous pouvez également cliquer sur le bouton de menu **Power Apps** dans le volet Actions standard, puis sélectionner **Insérer une application Power App**.

3. Configurez l'application Power App incorporée :

    - Le champ **Nom** indique le texte affiché pour le bouton ou l'onglet contenant l'application Power App incorporée. Il arrive souvent que vous souhaitez répéter le nom de l'application Power App dans ce champ.
    - **ID d'application** est le GUID de l'application Power App que vous souhaitez incorporer. Pour récupérer cette valeur, recherchez l'application Power App sur [web.powerapps.com](https://web.powerapps.com), puis localisez le champ **ID d'application** sous **Détails**.
    - Pour **Données d'entrée pour l'application Power App**, vous pouvez également sélectionner le champ contenant les données à transmette à l'application Power App comme entrée. Consultez la section plus loin dans cette rubrique intitulée [Création d'une application Power App qui utilise les données de Finance and Operations](#building-a-power-app-that-leverages-data-sent-from-finance-and-operations-apps) pour en savoir plus sur la manière dont l'application Power App peut accéder aux données envoyées depuis les applications Finance and Operations.
    - Choisissez la **Taille d'application** correspondant au type de Power App que vous incorporez. Sélectionnez **Mince** pour les Power Apps créées pour les appareils mobiles, et **Large** pour les Power Apps créées pour les tablettes. Ainsi, une quantité suffisante d'espace est allouée pour l'application Power App incorporée.
    - L'organisateur **Entités juridiques** permet de choisir les entités juridiques pour lesquelles l'application Power App est disponible. La valeur par défaut consiste à afficher l'application Power App dans toutes les entités juridiques.

4. Après avoir confirmé que la configuration est correcte, cliquez sur **Insérer** pour incorporer l'application Power App sur la page. Vous serez invité à actualiser le navigateur afin d'afficher l'application Power App incorporée.

## <a name="sharing-an-embedded-power-app"></a>Partage d'une application Power App incorporée

Après avoir incorporé une application Power App sur une page et confirmé qu'elle fonctionne correctement avec n'importe quel contexte de données transmis à partir de la page, vous pouvez partager cette application Power App incorporée avec d'autres utilisateurs du système. Cette opération peut être effectuée de deux manières à l'aide des fonctions de personnalisation du produit :

- Le scénario recommandé est par le biais de l'administrateur système, qui peut envoyer une personnalisation à tous les utilisateurs ou à un sous-ensemble d'utilisateurs.
- Vous pouvez également exporter les personnalisations de votre page, les envoyer à un ou plusieurs utilisateurs qui peuvent ensuite importer ces modifications. L'option Gérer dans la barre d'outils de personnalisation vous permet d'exporter et d'importer des personnalisations.

Consultez [Personnaliser l'expérience de l'utilisateur](personalize-user-experience.md) en savoir plus sur les fonctions de personnalisation du produit et leur utilisation.

## <a name="building-a-power-app-that-leverages-data-sent-from-finance-and-operations-apps"></a>Création d'une application Power App qui utilise les données envoyées depuis les applications Finance and Operations

Un élément essentiel de la création d'une application Power App qui sera incorporée dans les applications Finance and Operations est d'utiliser les données d'entrée des applications Finance and Operations. Dans l'application Power App, ces données d'entrée sont accessibles à l'aide de la variable Param("EntityId").

Par exemple, dans la fonction OnStart de l'application Power App, vous pouvez définir les données d'entrée des applications Finance and Operations sur une variable comme suit :

```
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-embedded-power-app"></a>Affichage d'une application Power App incorporée

Pour afficher une application Power App incorporée sur une page dans les applications Finance and Operations, accédez à une page contenant une application Power App incorporée. N'oubliez pas que les Power Apps sont accessibles via le bouton Power Apps dans le volet Actions standard, ou peuvent s'afficher directement sur la page en tant que nouvel onglet, organisateur, panneau, ou en tant que nouvelle section dans un espace de travail. Lorsqu'un utilisateur tente pour la première fois de charger une application Power App sur une page, il est invité à se connecter à Power Apps pour s'assurer qu'il dispose des autorisations nécessaires pour utiliser l' application Power App.

## <a name="editing-an-embedded-power-app"></a>Modification d'une application Power App incorporée

Une fois qu'une application Power App a été incorporée sur une page, vous devez apporter des modifications à la configuration de cette application Power App. Par exemple, vous souhaitez peut-être modifier le libellé associé à l'application Power App incorporée, ou une nouvelle version d'une application Power App a été créée et vous devez mettre à jour l'ID d'application pour pointer vers l'application Power App la plus récente.

Pour modifier la configuration d'une application Power App incorporée, procédez comme suit :

1. Accédez au volet **Modifier une application Power App**.

    - Si l'application Power App incorporée est accessible via le bouton de menu Power Apps, cliquez avec le bouton droit sur le bouton de menu Power Apps et sélectionnez **Personnaliser**. Sélectionnez l'application Power App à configurer dans le menu déroulant **Sélectionner une application Power App**.
    - Si l'application Power App incorporée s'affiche directement sur la page, sélectionnez **Options**, puis **Personnaliser cet écran**. À l'aide de l'outil **Sélectionner**, cliquez sur l'application Power App incorporée.

2. Apportez les modifications nécessaires à la configuration Power Apps, puis cliquez sur **Enregistrer**.

## <a name="removing-an-embedded-power-app"></a>Suppression d'une application Power App incorporée

Une fois qu'une application Power App a été incorporée sur une page, il existe deux méthodes pour la supprimer si nécessaire :

- Accédez au volet **Modifier une application Power App** à l'aide des instructions contenues dans la section [Modification d'une application Power App incorporée](#editing-an-embedded-power-app) plus haut dans cette rubrique. Vérifiez que le volet affiche les informations associées à l'application Power App incorporée que vous souhaitez supprimer, puis cliquez sur le bouton **Supprimer**.
- Une application Power App incorporée étant enregistrée en tant que données de personnalisation, la suppression de la personnalisation de votre page entraîne également la suppression des Power Apps incorporées sur cette page. Notez que la suppression de la personnalisation de la page est définitive et ne peut pas être annulée. Pour supprimer vos personnalisations sur une page, sélectionnez **Options**, puis cliquez sur **Personnaliser cet écran**. Sous le menu **Gérer**, sélectionnez le bouton **Effacer**. Après avoir actualisé votre navigateur, toutes les personnalisations précédentes pour cette page sont supprimées. Consultez [Personnaliser l'expérience de l'utilisateur](personalize-user-experience.md) pour plus d'informations sur l'optimisation des pages à l'aide de la personnalisation.

## <a name="appendix"></a>Annexe

### <a name="developer-control-over-where-a-power-app-can-be-embedded"></a>Contrôle du développeur sur l'emplacement d'incorporation d'une application Power App

Par défaut, les utilisateurs peuvent incorporer les Power Apps sur n'importe quelle page, sous le bouton de menu Power Apps ou directement sur la page en tant qu'onglet, organisateur, panneau, ou en tant que nouvelle section dans un espace de travail. Toutefois, si nécessaire, les développeurs peuvent également configurer cette fonction pour autoriser uniquement l'incorporation des Power Apps sur certaines pages en mettant en œuvre les méthodes suivantes :

- **isPowerAppPersonalizationEnabled** – Si cette méthode renvoie false pour une page spécifique, le bouton de menu Power Apps ne s'affiche pas, et les utilisateurs ne peuvent pas incorporer des Power Apps n'importe où sur cette page, notamment comme onglet.
- **isPowerAppTabPersonalizationEnabled** – Si cette méthode renvoie false pour une page spécifique, les utilisateurs ne peuvent pas incorporer des Power Apps directement sur la page en tant qu'onglet, organisateur ou section de panorama. Les utilisateurs peuvent toujours incorporer des Power Apps via le bouton de menu Power Apps si l'incorporation est autorisée sur la page.

L'exemple suivant présente une nouvelle classe avec les deux méthodes nécessaires pour configurer l'emplacement l'incorporation des Power Apps.

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
