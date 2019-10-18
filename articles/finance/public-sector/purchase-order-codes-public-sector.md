---
title: Codes de commande fournisseur dans le secteur public
description: Cet article fournit des informations sur les codes et les messages spéciaux pouvant être utilisés lors de la confirmation des commandes fournisseur. Une commande fournisseur de confirmation contourne le processus d'achat habituel.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConfirmingPOCodes, PurchTableListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 27291
ms.assetid: 65032886-4dc6-4411-98c8-8969287fd7df
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1da7937219c3ba8bfa8c94ca0cfcdb3790cc386b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183637"
---
# <a name="purchase-order-codes-in-the-public-sector"></a>Codes de commande fournisseur dans le secteur public

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur les codes et les messages spéciaux pouvant être utilisés lors de la confirmation des commandes fournisseur. Une commande fournisseur de confirmation contourne le processus d'achat habituel.

Cet article décrit la fonctionnalité de codes de commande fournisseur disponible pour le secteur public. Vous devez commencer par déterminer vos codes et messages. La page **Codes commande fournisseur de confirmation** permet de créer des codes et les messages spéciaux que vous pouvez utiliser avec les commandes fournisseur de confirmation. Une commande fournisseur de confirmation contourne le processus d'achat habituel. Par exemple, vous devez autoriser une commande non planifiée par l'intermédiaire d'un numéro de commande fournisseur au moment d'un achat, plutôt que via un document qui est fourni avant que l'article soit requis. 

Après avoir paramétré les codes, vous pouvez les affecter aux commandes fournisseur sur la page **Toutes les commandes fournisseur**. 

Si vous affectez un code commande fournisseur de confirmation à une commande fournisseur dans l'organisateur **Achats non planifiés** (par exemple, lorsque vous créez une commande fournisseur), le message associé à ce code est imprimé dans la partie supérieure de la commande fournisseur.

## <a name="tips"></a>Conseils
-   Si vous modifiez un code commande fournisseur de confirmation déjà affecté à une commande fournisseur, le nouveau code remplace l'ancien. Cette modification affecte à la fois les nouvelles commandes fournisseur et les commandes fournisseur qui ont été validées. Par exemple, une commande fournisseur avait un code de confirmation de commande fournisseur **Confirmation** lorsqu'elle a été validée, mais ce code a été modifié ultérieurement pour devenir **Urgence**. Dans ce cas, chaque commande fournisseur dotée du code **Confirmation**sera désormais dotée du code **Urgence**.
-   Vous pouvez créer des messages dans différentes langues. Cette fonctionnalité s'avère utile lorsque vous effectuez des achats auprès de fournisseurs implantés dans d'autres pays ou régions. Par exemple, votre organisation est implantée dans un pays ou une région anglophone et vous souhaitez créer un message en espagnol pour les commandes fournisseur de confirmation ayant **Confirmation** pour code de commande fournisseur de confirmation.





