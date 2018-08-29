---
title: Incorporer des applications PowerApps
description: "Cette rubrique décrit comment incorporer des PowerApps dans le client Finance and Operations pour augmenter la fonctionnalité du produit."
author: jasongre
manager: AnnBe
ms.date: 06/08/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 3b0bb61a52721f1e2eaf6df53e17b6cc162d8409
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---

# <a name="embed-powerapps-apps"></a>Incorporer des applications PowerApps

[!include [banner](../includes/banner.md)]

Dans Platform update 14, Microsoft Dynamics 365 for Finance and Operations prend en charge l'intégration avec Microsoft PowerApps, un service pour les développeurs et les utilisateurs non techniques pour créer des applications d'entreprise personnalisées pour les appareils mobiles, les tablettes et le Web sans écrire de code. Les PowerApps développées par vous, votre organisation ou l'écosystème élargi peuvent ensuite être incorporées dans le client Finance and Operations pour augmenter la fonctionnalité du produit. Par exemple, vous pouvez créer une PowerApp pour ajouter à Finance and Operations des informations extraites d'un autre système. 

Pour en savoir plus sur l'incorporation de PowerApps, visionnez la courte vidéo [Comment incorporer des PowerApps dans Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-powerapp-to-a-page"></a>Ajout d'une PowerApp incorporée à une page
### <a name="overview"></a>Vue d'ensemble
Avant d'incorporer une PowerApp dans le client Finance and Operations, vous devez d'abord rechercher ou créer une PowerApp avec les éléments visuels et/ou la fonctionnalité souhaités. Nous ne décrirons pas le processus détaillé de création d'une PowerApp ici. La rubrique [Présentation des PowerApps](https://docs.microsoft.com/en-us/powerapps/getting-started) est un bon point de départ si vous ne connaissez pas les PowerApps.

Lorsque vous êtes prêt à incorporer une PowerApp spécifique, vous pouvez choisir entre deux méthodes d'accès à la PowerApp sur une page, selon celle qui convient le mieux à votre scénario. La première méthode consiste à utiliser le bouton PowerApps qui a été ajouté au volet Actions standard. Les PowerApps ajoutées à l'aide de ce mécanisme s'affichent sous forme d'options de menu à l'intérieur du bouton de menu PowerApps. Lorsqu'elle est sélectionnée, chacune de ces options de menu ouvre un volet latéral contenant la PowerApp incorporée. Vous pouvez également choisir d'afficher une PowerApp directement sur une page en tant que nouvel onglet, organisateur, panneau, ou en tant que nouvelle section dans un espace de travail. 

Lorsque vous configurez votre PowerApp incorporée dans Finance and Operations, vous pouvez sélectionner un champ unique à envoyer en tant que entrée vers la PowerApp. Cela permet à la PowerApp d'être réactive en fonction des données actuellement affichées dans Finance and Operations.  

### <a name="details"></a>Détails
Les instructions suivantes indiquent comment incorporer une PowerApp dans le client Web Finance and Operations.  

1. Accédez à la page où vous souhaitez incorporer la PowerApp. Il s'agit de la même page que celle contenant les données à transférer à la PowerApp comme entrée.  
2. Ouvrez le volet **Insérer une PowerApp** :
   - Cliquez sur **Options**, puis sélectionnez **Personnaliser cet écran**. Sous le menu **Insérer**, choisissez **PowerApp**. Enfin, sélectionnez la région où vous souhaitez ajouter la PowerApp. Si vous souhaitez incorporer la PowerApp sous le bouton de menu PowerApps, choisissez le volet Actions. Si vous souhaitez incorporer la PowerApp directement sur la page, choisissez l'onglet, l'organisateur, le panneau ou la section appropriée (si vous êtes dans un espace de travail).   
   - Si la PowerApp est accessible à l'aide du bouton de menu PowerApps, vous pouvez également cliquer sur le bouton de menu **PowerApps** dans le volet Actions standard, puis sélectionner **Insérer une PowerApp**.  
3. Configurez la PowerApp incorporée :
   - Le champ **Nom** indique le texte affiché pour le bouton ou l'onglet contenant la PowerApp incorporée. Il arrive souvent que vous souhaitez répéter le nom de la PowerApp dans ce champ.  
   - **ID d'application** est le GUID de la PowerApp que vous souhaitez incorporer. Pour récupérer cette valeur, recherchez la PowerApp sur [web.powerapps.com](https://web.powerapps.com), puis localisez le champ **ID d'application** sous **Détails**.  
   - Pour **Données d'entrée pour la PowerApp**, vous pouvez également sélectionner le champ contenant les données à transmette à la PowerApp comme entrée. Consultez la section plus loin dans cette rubrique intitulée [Création d'une PowerApp qui utilise les données de Finance and Operations](#building-a-powerapp-that-leverages-data-sent-from-finance-and-operations) pour en savoir plus sur la manière dont la PowerApp peut accéder aux données envoyées depuis Finance and Operations.  
   - Choisissez la **Taille d'application** correspondant au type de PowerApp que vous incorporez. Sélectionnez **Mince** pour les PowerApps créées pour les appareils mobiles, et **Large** pour les PowerApps créées pour les tablettes. Ainsi, une quantité suffisante d'espace est allouée pour la PowerApp incorporée.
   - L'organisateur **Entités juridiques** permet de choisir les entités juridiques pour lesquelles la PowerApp est disponible. La valeur par défaut consiste à afficher la PowerApp dans toutes les entités juridiques.  
4. Après avoir confirmé que la configuration est correcte, cliquez sur **Insérer** pour incorporer la PowerApp sur la page. Vous serez invité à actualiser le navigateur afin d'afficher la PowerApp incorporée. 

## <a name="sharing-an-embedded-powerapp"></a>Partage d'une PowerApp incorporée
Après avoir incorporé une PowerApp sur une page et confirmé qu'elle fonctionne correctement avec n'importe quel contexte de données transmis à partir de la page, vous pouvez partager cette PowerApp incorporée avec d'autres utilisateurs du système. Cette opération peut être effectuée de deux manières à l'aide des fonctions de personnalisation du produit :

- Le scénario recommandé est par le biais de l'administrateur système, qui peut envoyer une personnalisation à tous les utilisateurs ou à un sous-ensemble d'utilisateurs. 

- Vous pouvez également exporter les personnalisations de votre page, les envoyer à un ou plusieurs utilisateurs qui peuvent ensuite importer ces modifications. L'option Gérer dans la barre d'outils de personnalisation vous permet d'exporter et d'importer des personnalisations.

Consultez [Personnaliser l'expérience de l'utilisateur](personalize-user-experience.md) en savoir plus sur les fonctions de personnalisation du produit et leur utilisation.

## <a name="building-a-powerapp-that-leverages-data-sent-from-finance-and-operations"></a>Création d'une PowerApp qui utilise les données envoyées depuis Finance and Operations
Un élément essentiel de la création d'une PowerApp qui sera incorporée dans Finance and Operations est d'utiliser les données d'entrée de Finance and Operations. Dans la PowerApp, ces données d'entrée sont accessibles à l'aide de la variable Param("EntityId").  

Par exemple, dans la fonction OnStart de la PowerApp, vous pouvez définir les données d'entrée de Finance and Operations sur une variable comme suit :

If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, "")); 

## <a name="viewing-an-embedded-powerapp"></a>Affichage d'une PowerApp incorporée
Pour afficher une PowerApp incorporée sur une page dans Finance and Operations, accédez à une page contenant une PowerApp incorporée. N'oubliez pas que les PowerApps sont accessibles via le bouton PowerApps dans le volet Actions standard, ou peuvent s'afficher directement sur la page en tant que nouvel onglet, organisateur, panneau, ou en tant que nouvelle section dans un espace de travail. Lorsqu'un utilisateur tente pour la première fois de charger une PowerApp sur une page, il est invité à se connecter à PowerApps pour s'assurer qu'il dispose des autorisations nécessaires pour utiliser la PowerApp.   

## <a name="editing-an-embedded-powerapp"></a>Modification d'une PowerApp incorporée
Une fois qu'une PowerApp a été incorporée sur une page, vous devez apporter des modifications à la configuration de cette PowerApp. Par exemple, vous souhaitez peut-être modifier le libellé associé à la PowerApp incorporée, ou une nouvelle version d'une PowerApp a été créée et vous devez mettre à jour l'ID d'application pour pointer vers la PowerApp la plus récente. 

Pour modifier la configuration d'une PowerApp incorporée, procédez comme suit :
1. Accédez au volet **Modifier une PowerApp**. 
   - Si la PowerApp incorporée est accessible via le bouton de menu PowerApps, cliquez avec le bouton droit sur le bouton de menu PowerApps et sélectionnez **Personnaliser**. Sélectionnez la PowerApp à configurer dans le menu déroulant **Sélectionner une PowerApp**.  
   - Si la PowerApp incorporée s'affiche directement sur la page, sélectionnez **Options**, puis **Personnaliser cet écran**. À l'aide de l'outil **Sélectionner**, cliquez sur la PowerApp incorporée.  
2. Apportez les modifications nécessaires à la configuration PowerApps, puis cliquez sur **Enregistrer**.  

## <a name="removing-an-embedded-powerapp"></a>Suppression d'une PowerApp incorporée
Une fois qu'une PowerApp a été incorporée sur une page, il existe deux méthodes pour la supprimer si nécessaire : 

- Accédez au volet **Modifier une PowerApp** à l'aide des instructions contenues dans la section [Modification d'une PowerApp incorporée](#editing-an-embedded-powerapp) plus haut dans cette rubrique. Vérifiez que le volet affiche les informations associées à la PowerApp incorporée que vous souhaitez supprimer, puis cliquez sur le bouton **Supprimer**. 

- Une PowerApp incorporée étant enregistrée en tant que données de personnalisation, la suppression de la personnalisation de votre page entraîne également la suppression des PowerApps incorporées sur cette page. Notez que la suppression de la personnalisation de la page est définitive et ne peut pas être annulée. Pour supprimer vos personnalisations sur une page, sélectionnez **Options**, puis cliquez sur **Personnaliser cet écran**. Sous le menu **Gérer**, sélectionnez le bouton **Effacer**. Après avoir actualisé votre navigateur, toutes les personnalisations précédentes pour cette page sont supprimées. Consultez [Personnalisation de l'expérience de l'utilisateur](personalize-user-experience.md) pour plus d'informations sur l'optimisation des pages à l'aide de la personnalisation.  

## <a name="appendix"></a>Annexe 
### <a name="developer-control-over-where-a-powerapp-can-be-embedded"></a>Contrôle du développeur sur l'emplacement d'incorporation d'une PowerApp
Par défaut, les utilisateurs peuvent incorporer les PowerApps sur n'importe quelle page, sous le bouton de menu PowerApps ou directement sur la page en tant qu'onglet, organisateur, panneau, ou en tant que nouvelle section dans un espace de travail. Toutefois, si nécessaire, les développeurs peuvent également configurer cette fonction pour autoriser uniquement l'incorporation des PowerApps sur certaines pages en mettant en œuvre les méthodes suivantes : 

- **isPowerAppPersonalizationEnabled** - Si cette méthode renvoie false pour une page spécifique, le bouton de menu PowerApps ne s'affiche pas, et les utilisateurs ne peuvent pas incorporer des PowerApps n'importe où sur cette page, notamment comme onglet. 

- **isPowerAppTabPersonalizationEnabled** - Si cette méthode renvoie false pour une page spécifique, les utilisateurs ne peuvent pas incorporer des PowerApps directement sur la page en tant qu'onglet, organisateur ou section de panorama. Les utilisateurs peuvent toujours incorporer des PowerApps via le bouton de menu PowerApps si l'incorporation est autorisée sur la page.  

L'exemple suivant présente une nouvelle classe avec les deux méthodes nécessaires pour configurer l'emplacement l'incorporation des PowerApps.  

```
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{

    public static boolean isPowerAppPresonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPresonalizationEnabled(pageName);
        return true;
    }

    public static boolean isPowerAppTabPresonalizationEnabled(str pageName)   
    {
        var result = next isPowerAppTabPresonalizationEnabled(pageName);
        return true;
    }
    ```

}


