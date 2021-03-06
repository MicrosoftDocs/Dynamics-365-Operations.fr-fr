---
title: Gestion des états électroniques pour les exemples de chèques fournisseur
description: Cette rubrique fournit des informations générales sur l’utilisation des exemples de formats de chèque pour la génération d’états électroniques.
author: ShylaThompson
ms.date: 06/14/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a405fee368bb1789addbdf4316a007e85616d98d
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897086"
---
# <a name="electronic-reporting-sample-vendor-checks"></a>Gestion des états électroniques pour les exemples de chèques fournisseur

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser un état électronique (ER) pour mettre en forme les chèques fournisseur. De nombreux formats de chèques spécifiques à la banque sont disponibles sur le marché. Des exemples de formats de chèque ont été inclus dans le modèle de chèque de paiement du référentiel des outils ER. Ces exemples de chèques sont libellés **Chèque au milieu (US)** et **Chèque sur la souche supérieure ci-dessous**.

## <a name="what-check-formats-are-currently-supported"></a>Quels formats de chèques sont actuellement pris en charge ?

Vous devez toujours aller dans la bibliothèque d’actifs partagés de Microsoft Dynamics Lifecycle Services (LCS) et afficher la liste actuelle des fichiers disponibles dont le type d’actif est **Configuration GER**. La section suivante, « Que je dois paramétrer ? », fournit un lien vers une rubrique qui explique comment créer un référentiel LCS pour examiner les configurations disponibles et importer les configurations sélectionnées.

Microsoft Dynamics 365 Finance inclut également un exemple de format dans lequel le chèque est en haut, suivi de deux sections de remise. Il inclut également un exemple de format dans lequel le chèque est au milieu, entre deux sections de remise. Ces exemples de formats correspondent aux formats de chèques professionnels Deluxe.

## <a name="what-do-i-have-to-set-up"></a>Que dois-je paramétrer ?

- Avant d’imprimer des chèques en utilisant un état électronique, au moins une configuration de chèque active doit être importée dans vos configurations ER. Pour plus d’instructions, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
- Lorsque vous configurez les chèques de trésorerie et de gestion bancaire pour le compte bancaire, sélectionnez la case à cocher **Format d’exportation électronique générique**, puis sélectionnez le format de chèque approprié comme configuration de format d’exportation.
- Vous devez également spécifier le nombre de lignes de bordereau à imprimer sur la remise. Veillez à inclure les lignes d’en-tête lorsque vous calculez ce nombre. Pour les deux exemples de formats de chèque, le nombre de lignes recommandées est 17. Toutefois, ce nombre varie, selon votre stock de chèques et les pilotes d’imprimante.
- Il est recommandé d’imprimer un chèque de test pour valider la mise en page des chèques. Pour imprimer un chèque de test, sélectionnez l’option **Test d’impression**. Les exemples de formats de chèque fonctionnent mieux lorsque **Marges** est défini sur **Aucun** dans les propriétés avancées de l’imprimante pour Microsoft Excel. Une fois que le chèque de test est généré, activez la modification de la sortie d’Excel, puis configurez la mise en page des pages afin que toutes les marges soient définies sur **0** (zéro). Comparez la copie de test des chèques avec votre stock de chèques, et ajustez les paramètres jusqu’à ce que vous soyez satisfait de l’alignement.
- Lorsque vous générez des paiements pour le compte bancaire paramétré dans le journal des paiements, les chèques sont imprimés à l’aide du format spécifié.

Pour plus d’informations, voir [Modifier un format de gestion d’états électroniques](../../fin-ops-core/dev-itpro/analytics/modify-electronic-reporting-format-reapply-excel-template.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]