---
title: Codes info et groupes de codes info
description: Cet article fournit une vue d’ensemble à propos des codes d’informations, des groupes de codes d’informations et la manière de les utiliser.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 22761
ms.assetid: 99877dba-a6e3-4d88-ba0a-ee5913aea17e
ms.search.industry: Retail
ms.search.form: RetailInfocodeTable
ms.openlocfilehash: a6fc84db368c602f74778eb0a44ac52798dc5161
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273501"
---
# <a name="info-codes-and-info-code-groups"></a>Codes info et groupes de codes info

[!include [banner](includes/banner.md)]

Cet article fournit une vue d’ensemble à propos des codes d’informations, des groupes de codes d’informations et la manière de les utiliser.

Les codes info fournissent une façon de capturer des données à un registre de point de vente (PDV). Vous pouvez utiliser les codes info pour demander au caissier d’entrer des informations au cours de diverses actions au PDV, tels que les ventes d’article, les retours d’article, ou la sélection des clients. Les caissiers peuvent sélectionner l’entrée dans une liste ou l’entrer sous la forme d’un code, un numéro, une date ou un texte. Des codes info peuvent être affectés à des actions en magasin, des articles vendus au détail, des modes de paiement, des clients ou des activités de point de vente spécifiques prédéfinis. les codes info permettent d’effectuer les opérations suivantes :

- Obtenir un complément d’informations au moment de la transaction, comme le numéro de vol ou le motif du retour.
- Inviter le caissier de la caisse enregistreuse à sélectionner le prix d’un produit spécifique dans une liste.
- Associer un sous-code à un code info pour inviter le caissier à entrer des informations lors de la réalisation d’une activité spécifique. Par exemple, lorsqu’un client retourne un produit, vous pouvez inviter le caissier à demander la raison pour laquelle le produit est retourné. Vous pouvez ensuite utiliser des sous-codes pour afficher la liste des motifs que le caissier peut sélectionner.
- Vendre un produit en tant que vente normale, vente avec escompte ou article gratuit.
- Inviter le caissier à entrer une valeur ou à la sélectionner depuis une liste de sous-codes lorsque le tiroir de la caisse enregistreuse est ouvert sans effectuer d’opération de vente.

## <a name="info-codes-group"></a>Groupe de codes info

Dans Commerce, vous pouvez créer des groupes de codes info. Les groupes de codes info ajoutent une certaine flexibilité en vous permettant de définir moins de codes info et de les utiliser de façon plus polyvalente. Vous pouvez utiliser les groupes de codes info comme suit :

- Définir moins codes info et les réutilisez facilement. Les codes info qui sont inclus dans des groupes de codes info n’ont aucune dépendance prédéfinie à d’autres codes info. Vous pouvez inclure le même code info dans plusieurs groupes de codes info, puis utiliser la définition de priorités pour présenter les mêmes codes info dans la commande qui semble correspondre à n’importe quelle situation particulière.
- Liez les codes info à d’autres codes info ou à des groupes de codes info pour collecter des informations sur un produit ou une transaction sans devoir définir un code info distinct ou un code info lié pour chaque scénario.

## <a name="info-code-examples"></a>Exemples de code info

**Exemple 1 : Réutiliser les codes info**

Vous pouviez les codes info de sorte à ce que lorsqu’un code info se déclenche, un autre code info se déclenche immédiatement après celui-ci. Par exemple, lorsque vous vendez certains produits, vous pouvez inviter le caissier à demander au client s’il souhaite acheter des piles et une garantie de produit. Pour d’autres produits, vous pouvez inviter le caissier à demander au client s’il souhaite acheter des piles et lui demander son code postal. Si vous créez des codes info liés pour ces scénarios, vous devez paramétrer chaque variation de code info afin que le caissier soit invité à demander la bonne information. Si vous utilisez des groupes de codes info, les codes info courants, comme poser la question pour les piles, peuvent être paramétrés une fois, puis réutilisés dans plusieurs groupes de codes info. Vous pouvez également utiliser la définition de priorité dans les groupes de codes info pour identifier l’ordre dans lequel les invites s’affichent.

**Exemple 2 : Lier des codes info à des groupes de codes info**

Lorsque vous vendez certains produits, par exemple des appareils mobiles, vous souhaitez toujours collecter un ensemble d’informations spécifiques, tel que le numéro de téléphone, l’identificateur de l’équipement mobile (MEID), et le numéro de série. Toutefois, vous souhaitez également collecter des informations différentes pour une tablette/un téléphone portable. Vous pouvez paramétrer un groupe de codes info qui inclut des invites pour le numéro de téléphone, le MEID et le numéro de série, puis lier le groupe de codes info à un code info individuel. Lorsque le code info spécifique au produit est déclenché, le groupe de codes info peut être ensuite déclenché pour vous permettre de collecter les données communes sans devoir définir plusieurs ensembles de codes info liés pour chaque périphérique.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
