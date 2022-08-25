---
title: Module iFrame
description: Cet article couvre le module iframe et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 248da5132d1a2c6dcf8f246628f969c8a200b26c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269893"
---
# <a name="iframe-module"></a>Module iFrame

[!include [banner](includes/banner.md)]

Cet article couvre le module iframe et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Un module iframe fournit un iframe (cadre incorporé) qui héberge du contenu externe sur un site. Par exemple, il peut être utilisé pour héberger une vidéo YouTube ou une visionneuse de fichiers PDF sur une page de site. 

Un module iframe nécessite une URL cible. Il héberge ensuite le contenu de la page cible dans un élément **iframe** HTML. Les URL externes doivent figurer sur la liste d’autorisation conformément aux instructions de la stratégie de sécurité du contenu (CSP) du site. Pour le contenu iframe, les URL doivent être autorisées à l’aide de l’instruction **frame-ancestor**. Pour plus d’informations, voir [Gérer la stratégie de sécurité du contenu (CSP)](manage-csp.md).

> [!NOTE]
> Le module iframe est disponible dans Dynamics 365 Commerce version 10.0.13.

L’image suivante montre des exemples de modules iframe qui présentent des vidéos externes sur des pages de site.

![Exemple de modules iframe qui présentent des vidéos externes.](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a>Propriétés du module iframe

| Nom de la propriété             | Valeur                 | Description |
|---------------------------|-----------------------|-------------|
| Titre | Détails | En-tête du module. |
| URL cible | URL | URL hébergée dans le module. |
| Hauteur | Nombre ou pourcentage | Hauteur du module, en pixels ou en pourcentage. Par exemple, la valeur **100** est traitée comme un nombre de pixels et la valeur **100 %** est traitée comme un pourcentage. |
| Aria-label | Détails | Une étiquette ARIA (Accessible Rich Internet Applications) peut être définie à des fins d’accessibilité. |

## <a name="add-an-iframe-module-to-a-page"></a>Ajouter un module iframe à une page

Pour ajouter un module iframe à une page afin d’afficher une vidéo externe, procédez comme suit.

1. Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle marketing**, puis cliquez sur **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Créer une page**, sous **Nom de la page**, entrez **Page marketing**, puis cliquez sur **Suivant**.
1. Sous **Choisir un modèle**, sélectionnez le **Modèle marketing** que vous avez créé, puis sélectionnez **Suivant**.
1. Sous **Choisir une mise en page**, sélectionnez une mise en page (par exemple, **Disposition flexible**), puis sélectionnez **Suivant**.
1. Sous **Revoir et terminer**, vérifiez la configuration de la page. Si vous devez modifier les informations de la page, sélectionnez **Précédent**. Si les informations de la page sont correctes, sélectionnez **Créer une page**. 
1. Dans l’emplacement **Principal** de la nouvelle page, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**.
1. Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **iframe**, puis cliquez sur **OK**.
1. Dans le volet des propriétés du module, définissez la valeur **URL cible** sur une URL externe pour une vidéo.
1. Définissez d’autres propriétés, telles que **Titre** et **Hauteur**, selon vos besoins.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.
1. Accédez à la page marketing de votre site. Vous devriez voir que la vidéo est affichée dans le module iframe.

> [!NOTE]
> Étant donné que le module iFrame héberge du contenu externe, les auteurs de sites doivent s’assurer que le contenu hébergé dans un module iFrame n’enfreint pas les stratégies de restriction de contenu sur le marché respectif. S’il y a une violation de contenu sur une page qui utilise le module iFrame, l’auteur du site peut supprimer le module iFrame en ouvrant la page dans le constructeur de site, en sélectionnant **Supprimer le module** à l’emplacement du module iFrame, puis enregistrez et republiez la page.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Gérer la stratégie de sécurité de contenu (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
