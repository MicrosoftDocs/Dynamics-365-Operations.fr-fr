---
title: Connecter une expérience et modifier les variantes
description: Cet article décrit comment connecter une expérience dans un service tiers à Dynamics 365 Commerce et comment modifier les variantes de l’expérience.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: dcdbd61976402ddd719ece184a86692fbc7c628d
ms.sourcegitcommit: ddcb62bb5fbf26a1178c2bb1aec45a3d2362339e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/07/2022
ms.locfileid: "8942820"
---
# <a name="connect-an-experiment-and-edit-variations"></a>Connecter une expérience et modifier les variantes

Cet article décrit comment connecter votre expérience dans Commerce et apporter des modifications à vos variantes afin qu’elles correspondent à votre hypothèse. 

Le diagramme suivant montre toutes les étapes impliquées dans la configuration et l’exécution d’une expérience sur un site web d’e-commerce dans Dynamics 365 Commerce. Les étapes supplémentaires sont traitées dans d’autres articles.

[ ![Expérimentation parcours utilisateur - Se connecter et modifier.](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)

Après avoir [configuré votre expérience](experimentation-setup.md) dans un service tiers, vous connecterez l’expérience dans Dynamics 365 Commerce et modifierez les variantes de l’expérience.

## <a name="connect-your-experiment"></a>Connecter votre expérience
Pour connecter votre expérience, vous allez lancer l’assistant **Connecter l’expérience**. L’assistant vous fait parcourir les étapes requises pour connecter votre expérience. Lorsque vous avez terminé l’assistant, votre expérience est connectée et les variantes sont créées et prêtes à être modifiées.

Pour démarrer la connexion de votre expérience dans le générateur de site Commerce, procédez comme suit.

1. Pour lancer l’assistant **Connecter l’expérience**, sélectionnez **Expériences** dans le volet de navigation de gauche, puis sélectionnez **Connecter**. Vous pouvez également accéder à l’assistant à partir d’un éditeur de fragment ou de page en le modifiant et en sélectionnant **Connecter l’expérience** sur la barre de commandes.

    > [!NOTE]
    > - Une page peut être connectée à une seule expérience à la fois. Pour connecter une page à une autre expérience, supprimez d’abord l’expérience à laquelle la page est actuellement connectée.
    > - Vous ne pouvez créer une expérience que sur les pages avec une disposition personnalisée. Si votre page a une mise en page prédéfinie, convertissez-la d'abord en une mise en page personnalisée. Vous pouvez le faire en accédant à la page et en sélectionnant **Convertir en mise en page personnalisée** sur la barre de commandes. Pour plus d'informations sur les mises en page, voir [Dispositions prédéfinies et personnalisées](templates-layouts-overview.md#preset-and-custom-layouts). 

1. Si vous vous connectez à une expérience à partir de l'onglet **Expériences** dans le volet de navigation de gauche, sélectionnez le nom de l'expérience dans la liste qui s'affiche.
1. Sélectionnez la page ou le fragment sur lequel vous souhaitez exécuter votre expérience.
1. Dans la dernière étape de l’assistant, sélectionnez **Générer des variantes et quitter l’assistant**. Des variantes sont créées pour l’expérience. 

> [!NOTE]
> Si vous souhaitez planifier la publication de votre expérience sur votre site en ligne, assurez-vous que le contenu que vous souhaitez associer à l’expérience est disponible dans un groupe de publication *avant* de connecter l’expérience. Pour plus d’informations sur les groupes de publication, voir [Utiliser des groupes de publication](publish-groups.md).

## <a name="edit-your-variations"></a>Modifier vos variantes

Lorsque vous quittez l'assistant **Connecter l'expérience**, des variantes sont créées pour vous. Suivez les étapes ci-dessous pour modifier les variantes afin qu’elles reflètent les choix que vous devez vérifier dans l’hypothèse de l’expérience.

1. Dans la vue d’éditeur, utilisez le menu déroulant des variantes sous la barre de commandes pour modifier chaque variante en fonction de votre hypothèse d’origine. Vous pouvez également établir une variante de contrôle ou de base en laissant l’une des variantes inchangée.
1. Sélectionnez le module sur lequel expérimenter, sélectionnez les points de suspension (...), puis sélectionnez **Ajouter à l’expérience**.

> [!NOTE]
> Pensez à établir une variante de contrôle ou de base en laissant l’une des variantes inchangée.

## <a name="previous-step"></a>Étape précédente
[Configurer une expérience](experimentation-setup.md) 


## <a name="next-step"></a>Étape suivante
[Afficher un aperçu et publier une expérience](experimentation-preview-publish.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
