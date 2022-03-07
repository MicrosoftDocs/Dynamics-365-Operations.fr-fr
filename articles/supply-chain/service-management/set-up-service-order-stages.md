---
title: Paramétrer des stades de commande de service
description: Paramétrer des stades de commande de service.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9774d5f4e97d3f768366ba552e5928929bacf508
ms.sourcegitcommit: 34b8f6f5c6134b7b97a9fb41d0b2e63215c67062
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470927"
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