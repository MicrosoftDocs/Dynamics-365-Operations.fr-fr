---
title: Réception de contenant mixte
description: Cet article décrit comment utiliser la réception de contenant mixte pour enregistrer et créer le travail pour plusieurs articles avec un appareil mobile.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76ba316a5ed55902aed35acb4ef21623c7676b38
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907056"
---
# <a name="mixed-license-plate-receiving"></a>Réception de contenant mixte

[!include [banner](../includes/banner.md)]

La réception de contenant mixte vous permet de générer un contenant composé de plusieurs articles avant d’enregistrer et de créer le travail de rangement. 

Un contenant composé de plusieurs articles ne doit pas être réparti au niveau du quai de réception pour que vous puissiez enregistrer chaque article. 

Lorsque vous utilisez un flux relatif aux articles pour identifier les lignes du document source, vous pouvez lire les codes-barres sur le contrôle de l’article. Si le code-barres présente une quantité et une unité de mesure (UOM) configurés dessus, l’article et la quantité seront automatiquement ajoutés au contenant mixte, et vous serez renvoyé à l’écran permettant de lire un autre article. Cela vous permet d’analyser rapidement tous les articles sans devoir apporter une confirmation à chaque étape. 

Dans le flux de la réception du contenant mixte, vous pouvez afficher la liste des articles qui sont déjà lus dans le contenant et de là, vous pourrez modifier ou corriger la quantité d’un article.

## <a name="where-it-applies"></a>Dans ce cas

La réception du contenant mixte correspond à un appareil mobile recevant un flux pour enregistrer et créer du travail pour plusieurs lignes/articles en même temps. Cela est utile si vous recevez des contenants entrants avec plusieurs articles. 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a>Comment configurer une réception de contenant mixte
Une réception de contenant mixte est paramétré en tant qu’option de menu d’appareil mobile.

Vous devez créer une option de menu avec le mode de travail qui n’utilise pas le travail existant, mais l’une des méthodes suivantes :

- Réception de contenant mixte
- Réception et rangement de contenant mixte

Les options permettant d’identifier les lignes du document source sont Article de commande fournisseur, Ligne de commande fournisseur, Ordre de retour, Article d’ordre de transfert et Ligne d’ordre de transfert. Ces options peuvent modifier l’ordre de réception dans un contenant unique. La dernière option concerne le chargement d’articles. Vous pouvez ajouter plusieurs articles à un contenant, mais vous ne pouvez pas basculer entre plusieurs chargements.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]