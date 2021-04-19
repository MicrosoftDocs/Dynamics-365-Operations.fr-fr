---
title: Afficher un aperçu et publier une expérience
description: Cette rubrique décrit comment afficher un aperçu et publier une expérience à partir de Dynamics 365 Commerce.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 52ca23e5aaeb7058853fed2241d5804180fa7f8d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798961"
---
# <a name="preview-and-publish-an-experiment"></a>Afficher un aperçu et publier une expérience

Cette rubrique décrit comment afficher un aperçu et publier votre expérience dans Dynamics 365 Commerce après avoir [connecté votre expérience et modifié vos variantes](experimentation-connect-edit.md). Le diagramme suivant montre toutes les étapes impliquées dans la configuration et l’exécution d’une expérience sur un site web d’e-commerce dans Dynamics 365 Commerce. Les étapes supplémentaires sont traitées dans d’autres rubriques.

[ ![Expérimentation parcours utilisateur - Afficher un aperçu et publier](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)

## <a name="preview-your-experiment-variations"></a>Afficher un aperçu de vos variantes d’expérience
Vous pouvez afficher un aperçu de vos variantes et continuer à les modifier jusqu’à ce qu’elles correspondent à ce que vous souhaitez.

Pour prévisualiser vos variantes d’expérience dans le générateur de site Commerce, procédez comme suit.

1. Dans le menu déroulant des variantes sous la barre de commandes, sélectionnez le contenu dont vous souhaitez afficher un aperçu. 
1. Dans la barre de commande, sélectionnez **Aperçu**. Un aperçu de la forme que prendra le contenu une fois publié s’affiche.
1. Pour afficher un aperçu d’une autre variante, sélectionnez-la dans le menu déroulant des variantes et sélectionnez à nouveau **Afficher un aperçu**.

## <a name="publish-your-experiment"></a>Publier votre expérience
Si vous n’utilisez pas de groupe de publication pour planifier la mise en ligne de votre expérience et que vous souhaitez publier immédiatement, sélectionnez **Publier** dans la barre de commandes. Toutes les variantes appartenant à l’expérience seront publiées.
    
> [!IMPORTANT]
> Si la page a une URL non publiée, vous devez d’abord publier l’URL, sinon les utilisateurs de votre site web ne pourront pas la voir. Pour plus de détails, consultez [Enregistrer, afficher un aperçu et publier une page](save-preview-publish-page.md).
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a>Utiliser des groupes de publication pour planifier la mise en ligne de votre expérience
Les variantes créées dans le générateur de site peuvent être planifiées afin d’être publiées à l’aide d’un groupe de publication. Au sein d’un groupe de publication, vous pouvez connecter une page ou un fragment à votre expérience en sélectionnant **Expériences** dans le volet de navigation de gauche. Vous pouvez également le faire en sélectionnant **Pages** ou **Fragments** et en suivant les instructions [Connecter une expérience et modifier les variantes](experimentation-connect-edit.md). Pour plus d’informations sur les groupes de publication, consultez [Utiliser des groupes de publication](publish-groups.md).

Lorsque vous utilisez des groupes de publication avec des expériences, vous devez prendre en compte certaines considérations importantes.
- Lorsque vous ajoutez à un groupe de publication une page ou un fragment sur lequel une expérience est en cours, l’expérience est supprimée de la page ou du fragment dans le groupe de publication.
- Les expériences connectées aux pages d’un site en ligne ne sont pas disponibles pour les pages des groupes de publication, et inversement. De même, les pages sur lesquelles des expériences sont exécutées dans un site en ligne ne sont pas disponibles pour d’autres expériences dans des groupes de publication, et inversement.
- Lorsque vous publiez ou planifiez un groupe de publication, tout le contenu du groupe de publication est publié, qu’il existe ou non une expérience associée au groupe de publication.
- Étant donné qu’un groupe de publication persiste après sa publication sur un site en ligne, les expériences du groupe de publication persistent également. Par conséquent, vous ne pourrez pas associer d’autres expériences à la même page ou au même fragment. Pour éviter cette limitation, supprimez tous les groupes de publication avec des expériences persistantes. De même, si vous souhaitez supprimer une expérience dans un site en ligne qui existe également dans un groupe de publication, supprimez-la d’abord du groupe de publication.

## <a name="previous-step"></a>Étape précédente
[Connecter et modifier une expérience](experimentation-connect-edit.md)

## <a name="next-step"></a>Étape suivante
[Exécuter et surveiller une expérience](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]