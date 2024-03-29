---
title: Configuration des lots plus anciens d’affichage dans l’entrepôt sur un périphérique mobile
description: Cet article décrit la procédure de paramétrage d’un appareil mobile pour afficher une liste des emplacements avec des lots plus anciens que l’emplacement actuel d’une ligne de travail.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5788b42483f2c3046b0d20f45115b98d62cce213
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900533"
---
# <a name="configure-display-older-batches-within-warehouse-on-a-mobile-device"></a>Configuration des lots plus anciens d’affichage dans l’entrepôt sur un périphérique mobile

[!include [banner](../includes/banner.md)]

La configuration **Lots plus anciens d’affichage dans l’entrepôt** permet d’afficher une liste des emplacements avec des lots plus anciens que l’emplacement actuel de la ligne de travail. La liste des emplacements affichés inclut des informations sur les lots plus anciens de l’emplacement avec la date d’expiration et le stock physique de chaque lot. Vous pouvez choisir de collecter à un nouvel emplacement ou de continuer à collecter à l’emplacement actuel. 
- Collecte à un nouvel emplacement : Si vous sélectionnez un nouvel emplacement de collecte, la ligne de travail actuelle est mise à jour pour utiliser le nouvel emplacement et le travail continuera normalement avec le nouvel emplacement. Pour que le nouvel emplacement soit valide, il doit avoir suffisamment de quantité disponible pour la ligne de travail entière. Si la quantité requise n’est pas disponible, la ligne de travail n’est pas mise à jour, et la liste s’affiche. 
- Continuer de collecter à l’emplacement actuel : Si vous ignorez l’emplacement de la ligne de travail actuelle, les quantités de la ligne de travail continuent à être collectées à l’emplacement d’origine.

## <a name="where-it-applies"></a>Dans ce cas
Lots plus anciens d’affichage dans l’entrepôt est configuré sur les options du menu de l’appareil mobile et affecte le prélèvement pour les articles du lot ci-dessous.

## <a name="set-up-display-older-batches-within-warehouse"></a>Paramétrer des lots plus anciens d’affichage dans l’entrepôt
La configuration **Lots plus anciens d’affichage dans l’entrepôt** est disponible dans les options du menu d’appareil mobile lorsque l’option **Prélever le traitement par lots le plus ancien** est définie sur **Avertir**.

- Sous **Gestion des entrepôts** > **Paramétrage** > **Appareil mobile** > **Options de menu d’appareil mobile**, définissez **Utiliser un travail existant** sur **Oui** pour l’option de menu, et sélectionnez **Avertir** dans le champ **Prélever le traitement par lots le plus ancien**. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]