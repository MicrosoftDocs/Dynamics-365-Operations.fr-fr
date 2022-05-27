---
title: Paramétrer des stades de commande de service
description: Paramétrer des stades de commande de service.
author: sorenva
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 557e688ddd1155aa475320365a5b6048759904fd
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8670718"
---
# <a name="set-up-service-order-stages"></a>Paramétrer des stades de commande de service 

[!include [banner](../includes/banner.md)]


1.  Accédez à **Gestion des services** \> **Paramétrage** \> **Commandes de service** \> **Stades du service**.

2.  Sélectionnez **Nouveau** pour créer un enregistrement.

3.  Dans les champs **Stade du service** et **Description**, entrez l’ID et la description du stade de service.

4.  Sélectionnez les paramètres appropriés pour le stade.

5.  Sélectionnez le stade parent du stade actif ou laissez le champ **Parent** vide si le stade actif correspond au stade initial du paramétrage de stade.


> [!NOTE]
> <P>Une fois le stade enregistré, il n’est plus possible de modifier le champ <STRONG>Parent</STRONG>. Vous pouvez supprimer l’enregistrement et le créer à nouveau en sélectionnant un autre élément dans le champ <STRONG>Parent</STRONG>.</P>
> <P>En outre, vous ne pouvez créer qu’un seul stade avec un champ <STRONG>Parent</STRONG> vide. Cela signifie qu’un seul stade initial est autorisé.</P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]