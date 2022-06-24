---
title: Modèles de service
description: Vous pouvez définir un accord de service comme modèle et, ultérieurement, copier les lignes du modèle dans un autre accord de service ou dans une commande de service.
author: sorenva
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7c99e56751230a7b8881dc55c1d460674cc6f0c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850484"
---
# <a name="service-templates"></a>Modèles de service

[!include [banner](../includes/banner.md)]

Vous pouvez définir un accord de service comme modèle et, ultérieurement, copier les lignes du modèle dans un autre accord de service ou dans une commande de service.

## <a name="example"></a>Exemple

Un client pour lequel vous fournissez un service possède des ascenseurs de service identiques en cinq endroits différents.

Vous souhaitez paramétrer cinq accords de service pour le client, un pour chaque site.
Pour un travail répétitif de paramétrage et pour vous assurer que les informations de paramétrage sont identiques dans les accords de services, vous créez un accord de service et le spécifiez comme modèle pour la tâche de service sur les ascenseurs.

À présent, vous pouvez copier les lignes de modèle dans les cinq nouveaux accords de service pour que chacun d’entre eux contienne les lignes du modèle.

## <a name="create-a-template"></a>Créer un modèle

Lorsque vous créez un modèle de service, créez un accord de service, ainsi que les lignes requises dans celui-ci, puis associez l’accord de service à un groupe de modèles de service.

> [!NOTE]
> Un accord de service peut uniquement être défini comme un modèle si aucune commande de service ne lui est associée. De la même manière, aucune commande de service ne peut être générée à partir d’un accord de service qui est défini comme un modèle.

## <a name="copy-template-lines"></a>Copier les lignes de modèle

Vous pouvez copier des lignes d’un modèle de service dans un autre accord de service ou dans une commande de service.

Lorsque vous copiez des lignes de modèle dans vos commandes de service ou accords de service, vos groupes de modèles sont affichés dans une arborescence où chaque groupe peut être développé. Cet affichage vous permet de visualiser chaque modèle et ligne de modèle.

Il est plus facile de déterminer les lignes de modèle de service à copier si vous avez regroupé les modèles sous des noms qui reflètent leur utilisation.

## <a name="related-articles"></a>Articles connexes

[Copie de lignes de modèles de service](copy-service-template-lines.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]