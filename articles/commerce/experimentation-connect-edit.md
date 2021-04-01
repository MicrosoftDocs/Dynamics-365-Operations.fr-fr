---
title: Connecter une expérience et modifier les variantes
description: Cette rubrique décrit comment connecter une expérience dans un service tiers à Dynamics 365 Commerce et comment modifier les variantes de l'expérience.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: c295f6f8170b6314ddf2d0c3582343b312c815b6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238652"
---
# <a name="connect-an-experiment-and-edit-variations"></a>Connecter une expérience et modifier les variantes

Cette rubrique décrit comment connecter votre expérience dans Commerce et apporter des modifications à vos variantes afin qu'elles correspondent à votre hypothèse. 

Le diagramme suivant montre toutes les étapes impliquées dans la configuration et l'exécution d'une expérience sur un site web d'e-commerce dans Dynamics 365 Commerce. Les étapes supplémentaires sont traitées dans d'autres rubriques.

[ ![Expérimentation parcours utilisateur - Se connecter et modifier](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)

Après avoir [configuré votre expérience](experimentation-setup.md) dans un service tiers, vous connecterez l'expérience dans Dynamics 365 Commerce et modifierez les variantes de l'expérience.

## <a name="planning-considerations"></a>Considérations relatives à la planification

Avant de connecter votre expérience dans Commerce, vous devez prendre des décisions qui ont un impact sur la façon dont Commerce gère votre contenu.

### <a name="determine-the-scope-of-your-experiment"></a>Déterminer la portée de votre expérience
Lorsque vous connectez une expérience, vous êtes invité à définir la portée de l'expérience. La portée des expériences est définie comme **partielle** ou **complète**.
- Choisissez **partielle** si vous souhaitez mener une expérience sur une partie spécifique d'une page. Si vous sélectionnez cette option, vous devez identifier les modules inclus dans l'expérience. Les modifications apportées à des parties de la page ou du fragment par défaut qui ne sont pas liés à l'expérience sont automatiquement synchronisés entre les variantes.
- Choisissez **complète** si vous souhaitez mener une expérience sur une page entière ou sur un fragment entier. Des copies distinctes de la page ou du fragment par défaut sont créées. Vous n'aurez pas à sélectionner les modules inclus dans l'expérience, car l'ensemble de la surface de modification peut être modifiée. Vous pouvez ajouter, supprimer ou réorganiser les modules selon vos besoins. Toutefois, si des modifications sont apportées à la page ou au fragment par défaut auquel l'expérience est associée, ces modifications doivent être synchronisées manuellement sur toutes les variantes.

<!-- not to editors, we're adding an image here to illustrate the difference. it will help.) -->

> [!NOTE]
> Si vous associez votre expérience à une page qui utilise une disposition, vous pouvez uniquement définir l'expérience comme **complète**.

### <a name="decide-if-you-want-to-schedule-when-your-experiment-is-published"></a>Décidez si vous souhaitez planifier la publication de votre expérience
Si vous souhaitez planifier la publication de votre expérience sur votre site en ligne, assurez-vous que le contenu que vous souhaitez associer à l'expérience est disponible dans un groupe de publication *avant* de connecter l'expérience. 

Pour plus d'informations sur les groupes de publication, voir [Utiliser des groupes de publication](publish-groups.md).


## <a name="connect-your-experiment"></a>Connecter votre expérience
Pour connecter votre expérience, vous allez lancer l'assistant **Connecter l'expérience**. L'assistant vous fait parcourir les étapes requises pour connecter votre expérience. Lorsque vous avez terminé l'assistant, votre expérience est connectée et les variantes sont créées et prêtes à être modifiées.

Pour démarrer la connexion de votre expérience dans le générateur de site Commerce, procédez comme suit.

1. Pour lancer l'assistant **Connecter l'expérience**, sélectionnez **Expériences** dans le volet de navigation de gauche, puis sélectionnez **Connecter**. Vous pouvez également accéder à l'assistant à partir d'un éditeur de fragment ou de page en le modifiant et en sélectionnant **Connecter l'expérience** sur la barre de commandes.

    > [!NOTE]
    > Une page peut être connectée à une seule expérience à la fois. Pour connecter une page à une autre expérience, supprimez d'abord l'expérience à laquelle la page est actuellement connectée.

1. Choisissez la page ou le fragment sur lequel vous souhaitez exécuter votre expérience.
1. Définissez la portée de l'expérimentation sur **partielle** ou **complète**, en fonction du choix que vous avez fait dans la section [Déterminer la portée de votre expérience](#determine-the-scope-of-your-experiment) ci-dessus.
    > [!NOTE]
    > L'indicateur de la fonctionnalité **Expérimenter sur des pages ou des fragments** doit être activé si vous souhaitez expérimenter sur une page complète ou sur un fragment complet. Reportez-vous à la rubrique [Expérimentation dans Dynamics 365 Commerce](experimentation-overview.md) pour plus d'informations.
    
1. Dans la dernière étape de l'assistant, sélectionnez **Générer des variantes et quitter l'assistant**. Des variantes sont créées pour l'expérience. 

## <a name="edit-your-variations"></a>Modifier vos variantes
Lorsque vous quittez l'assistant, des variantes sont créées pour vous. 

Vous allez ensuite modifier les variantes afin qu'elles reflètent les choix que vous devez vérifier dans l'hypothèse de l'expérience. Choisissez l'une des procédures suivantes qui correspond à la portée que vous avez choisie pour votre expérience dans la section [Déterminer la portée de votre expérience](#determine-the-scope-of-your-experiment) ci-dessus.

### <a name="edit-variations-for-experiments-with-partial-scope"></a>Modifier les variantes des expériences avec une portée partielle
Suivez ces étapes si vous avez défini la portée de votre expérience comme **partielle** dans l'assistant **Connecter l'expérience**.

1. Dans la vue d'éditeur, utilisez le menu déroulant des variantes sous la barre de commandes pour modifier chaque variante en fonction de votre hypothèse d'origine. Vous pouvez également établir une variante de contrôle ou de base en laissant l'une des variantes inchangée.
1. Sélectionnez le module sur lequel expérimenter, sélectionnez les points de suspension (...), puis sélectionnez **Ajouter à l'expérience**.

### <a name="edit-variations-for-experiments-with-entire-scope"></a>Modifier les variantes des expériences avec une portée complète
Si vous avez défini la portée de votre expérience comme **complète** dans l'assistant **Connecter l'expérience**, utilisez le menu déroulant des variantes sous la barre de commandes dans la vue d'éditeur pour modifier chaque variante en fonction de votre hypothèse d'origine. 

> [!NOTE]
> Dans les deux cas, vous pouvez également établir une variante de contrôle ou de base en laissant l'une des variantes inchangée.

## <a name="previous-step"></a>Étape précédente
[Configurer une expérience](experimentation-setup.md) 


## <a name="next-step"></a>Étape suivante
[Afficher un aperçu et publier une expérience](experimentation-preview-publish.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]