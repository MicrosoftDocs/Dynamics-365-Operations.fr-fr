---
title: Copier le contenu dans un autre paramètre régional
description: Cet article explique comment copier du contenu existant vers un autre paramètre régional au sein d’un site dans un générateur de sites Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 07/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: bcfa3c7cb2ea8018422803d85df6b6761b8d1145
ms.sourcegitcommit: d719d0a549aecac231fad0abb42250eab9dd0ded
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2022
ms.locfileid: "9126449"
---
# <a name="copy-content-to-another-locale"></a>Copier le contenu dans un autre paramètre régional

[!include[banner](../includes/banner.md)]

Cet article explique comment copier du contenu existant vers un autre paramètre régional au sein d’un site dans un générateur de sites Microsoft Dynamics 365 Commerce.

Lorsque vous créez du contenu dans le générateur de site Commerce, il est toujours associé à un identifiant de paramètres régionaux, tel que « en-us ». Vous pouvez copier des pages et des ressources individuelles dans des paramètres régionaux différents au sein du même site de commerce électronique en changeant de paramètres régionaux lorsque vous modifiez un élément de contenu, puis en créant une nouvelle variante de l’élément. Dans certains cas, comme lorsque vous lancez un paramètre régional entièrement nouveau sur votre vitrine, il est logique de dupliquer tous les éléments de contenu d’un paramètre régional existant vers le nouveau paramètre régional. Si le nouveau paramètre régional a la même langue de base que l’un des paramètres régionaux existants, vous pouvez utiliser le paramètre régional existant comme paramètre régional source pour l’opération de copie de paramètres régionaux. (Par exemple, les paramètres régionaux « en-us » et « en-au » utilisent tous deux la langue anglaise.) De cette manière, vous contribuez à réduire l’effort requis pour localiser le contenu dans le nouveau paramètre régional.

Les procédures suivantes expliquent comment ajouter un nouveau paramètre régional à un canal existant, copier tous les éléments de contenu d’un paramètre régional existant vers un nouveau paramètre régional et surveiller l’état d’une opération de copie de paramètres régionaux.

## <a name="add-a-new-locale"></a>Ajouter un nouveau paramètre régional

Pour ajouter un nouveau paramètre régional dans le générateur de site Commerce, procédez comme suit.

1. Dans le générateur de site Commerce, accédez à votre site.
1. Dans le volet de navigation de gauche, sélectionnez **Paramètres de site**, puis sélectionnez **Canaux**.
1. Sous **Canal**, sélectionnez le canal auquel ajouter les nouveaux paramètres régionaux.
1. Dans la boîte de dialogue du canal qui apparaît à droite, sélectionnez **Ajouter un paramètre régional**.
1. Dans la boîte de dialogue **Ajouter un paramètre régional**, dans le champ **Paramètres régionaux à prendre en charge**, sélectionnez un paramètre régional.
1. Confirmez que la valeur **Domaine** est correcte.
1. Sous **Chemin d’accès**, saisissez un chemin d’accès URL unique (par exemple, **en-us** ou **english-us**).
1. Cliquez sur **OK**.
1. Fermez la boîte de dialogue du canal.
1. Sous **Canal**, confirmez que les nouveaux paramètres régionaux sont répertoriés à côté du canal approprié.
1. Sélectionnez **Enregistrer et publier**.

> [!NOTE]
> Avant que les nouveaux paramètres régionaux puissent être configurés dans le générateur de site, ils doivent être ajoutés au canal de boutique en ligne associé à Commerce headquarters.

## <a name="copy-all-content-items-to-a-new-locale"></a>Copier tous les éléments de contenu dans un nouveau paramètre régional

Pour copier tous les articles de contenu dans un nouveau paramètre régional dans le générateur de site Commerce, procédez comme suit.

1. Dans le générateur de site Commerce, accédez à votre site.
1. Dans le volet de navigation de gauche, sélectionnez **Paramètres de site**, puis sélectionnez **Canaux**.
1. Dans la barre de commandes, sélectionnez **Créer une copie des paramètres régionaux**.
1. Dans la boîte de dialogue **Créer une copie locale** qui apparaît à droite, sous **Site source**, confirmez que le bon site est sélectionné.
1. Dans le champ **Canal source**, sélectionnez le canal source.
1. Dans le champ **Canal de destination**, sélectionnez le même canal source.
1. Dans le champ **Paramètres régionaux source**, sélectionnez les paramètres régionaux source.
1. Dans le champ **Paramètres régionaux de destination**, sélectionnez les nouveaux paramètres régionaux.
1. Sélectionnez **Copier les paramètres régionaux**. Une notification confirme que l’opération de copie des paramètres régionaux a commencé.

> [!NOTE]
> Vous pouvez également copier du contenu entre différents canaux.

## <a name="monitor-the-status-of-the-locale-copy"></a>Surveiller l’état de la copie des paramètres régionaux

Pour surveiller la progression de l’opération de copie des paramètres régionaux, procédez comme suit.

1. Dans le générateur de site Commerce, accédez à votre site.
1. Dans le volet de navigation de gauche, sélectionnez **Paramètres de site**, puis sélectionnez **Tâches**.
1. Sous **Tâches actuelles**, sélectionnez la tâche à surveiller. Les détails de la tâche sont indiqués dans la boîte de dialogue qui s’affiche à droite.
