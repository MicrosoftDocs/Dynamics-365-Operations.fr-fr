---
title: Codes info
description: "Cet article fournit une vue d&quot;ensemble à propos des codes d&quot;informations, des groupes de codes d&quot;informations et la manière de les utiliser."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 22761
ms.assetid: 99877dba-a6e3-4d88-ba0a-ee5913aea17e
ms.search.region: global
ms.search.industry: Retail
ms.author: sijoshi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d463d4ac9b4258c2282dc70547145ce38e4e8e98
ms.lasthandoff: 03/31/2017


---

# <a name="info-codes"></a>Codes info

Cet article fournit une vue d'ensemble à propos des codes d'informations, des groupes de codes d'informations et la manière de les utiliser.

Les codes info fournissent une façon de capturer des données à un registre de point de vente (PDV). Vous pouvez utiliser les codes info pour demander au caissier d'entrer des informations au cours de diverses actions au PDV, tels que les ventes d'article, les retours d'article, ou la sélection des clients. Les caissiers peuvent sélectionner l'entrée dans une liste ou l'entrer sous la forme d'un code, un numéro, une date ou un texte. Des codes info peuvent être affectés à des actions en magasin, des articles vendus au détail, des modes de paiement, des clients ou des activités de point de vente spécifiques prédéfinis. les codes info permettent d'effectuer les opérations suivantes :
-   Obtenir un complément d'informations au moment de la transaction, comme le numéro de vol ou le motif du retour.
-   Inviter le caissier de la caisse enregistreuse à sélectionner le prix d'un produit spécifique dans une liste.
-   Associer un sous-code à un code info pour inviter le caissier à entrer des informations lors de la réalisation d'une activité spécifique. Par exemple, lorsqu'un client retourne un produit, vous pouvez inviter le caissier à demander la raison pour laquelle le produit est retourné. Vous pouvez ensuite utiliser des sous-codes pour afficher la liste des motifs que le caissier peut sélectionner.
-   Vendre un produit en tant que vente normale, vente avec escompte ou article gratuit.
-   Inviter le caissier à entrer une valeur ou à la sélectionner depuis une liste de sous-codes lorsque le tiroir de la caisse enregistreuse est ouvert sans effectuer d'opération de vente.

## <a name="info-codes-group-in-retail-and-commerce"></a>Groupe de codes info dans le module Commerce et vente au détail
Dans Dynamics 365 pour les opérations - au détail, vous pouvez créer des groupes de codes info. Les groupes de codes info ajoutent une certaine flexibilité en vous permettant de définir moins de codes info et de les utiliser de façon plus polyvalente. Vous pouvez utiliser les groupes de codes info comme suit :
-   Définir moins codes info et les réutilisez facilement. Les codes info qui sont inclus dans des groupes de codes info n'ont aucune dépendance prédéfinie à d'autres codes info. Vous pouvez inclure le même code info dans plusieurs groupes de codes info, puis utiliser la définition de priorités pour présenter les mêmes codes info dans la commande qui semble correspondre à n'importe quelle situation particulière.
-   Liez les codes info à d'autres codes info ou à des groupes de codes info pour collecter des informations sur un produit ou une transaction sans devoir définir un code info distinct ou un code info lié pour chaque scénario.

## <a name="info-code-examples"></a>Exemples de code info
**Exemple 1 : réutilisation des codes info** Vous pouvez lier les codes info de manière à ce que lorsqu'un code info se déclenche, un autre code info se déclenche immédiatement après celui-ci. Par exemple, lorsque vous vendez certains produits, vous pouvez inviter le caissier à demander au client s'il souhaite acheter des piles et une garantie de produit. Pour d'autres produits, vous pouvez inviter le caissier à demander au client s'il souhaite acheter des piles et lui demander son code postal. Si vous créez des codes info liés pour ces scénarios, vous devez paramétrer chaque variation de code info afin que le caissier soit invité à demander la bonne information. Si vous utilisez des groupes de codes info, les codes info courants, comme poser la question pour les piles, peuvent être paramétrés une fois, puis réutilisés dans plusieurs groupes de codes info. Vous pouvez également utiliser la définition de priorité dans les groupes de codes info pour identifier l'ordre dans lequel les invites s'affichent. **Exemple 2 : lier des codes info à des groupes de codes info** Lorsque vous vendez certains produits, par exemple des appareils mobiles, vous souhaitez toujours collecter un ensemble spécifique d'informations tel que le numéro de téléphone, l'identificateur de l'équipement mobile (MEID) et le numéro de série. Toutefois, vous souhaitez également collecter des informations différentes pour une tablette/un téléphone portable. Vous pouvez paramétrer un groupe de codes info qui inclut des invites pour le numéro de téléphone, le MEID et le numéro de série, puis lier le groupe de codes info à un code info individuel. Lorsque le code info spécifique au produit est déclenché, le groupe de codes info peut être ensuite déclenché pour vous permettre de collecter les données communes sans devoir définir plusieurs ensembles de codes info liés pour chaque périphérique.

 
-




