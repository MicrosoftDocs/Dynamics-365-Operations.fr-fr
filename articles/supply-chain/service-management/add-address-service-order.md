---
title: Ajout d'une adresse à une commande de service
description: Cette rubrique explique comment ajouter une adresse du client à une commande de service.
author: ShylaThompson
manager: tfehr
ms.date: 05/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5b1c0e300edc45ae3f4be9eae8afa56e06cccd6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203087"
---
# <a name="add-an-address-to-a-service-order"></a>Ajout d'une adresse à une commande de service    

[!include [banner](../includes/banner.md)]


Cette rubrique explique comment ajouter une adresse du client à une commande de service. Lorsque vous créez une commande de service, les informations d'adresse sont transférées à partir du projet auquel la commande de service est associée. Toutefois, vous pouvez sélectionner un autre emplacement à partir des adresses qui sont déjà entrées dans Microsoft Dynamics AX pour des clients, des fournisseurs, des sites, des entrepôts, des commandes de service, et des projets.

Vous pouvez aussi créer une nouvelle adresse. Par défaut, la nouvelle adresse est transférée au projet. Toutefois, vous pouvez spécifier que la nouvelle adresse n'est applicable qu'à cette instance de service. Dans ce cas, la nouvelle adresse n'est pas transférée au projet.

## <a name="create-a-customer-address-for-a-service-order"></a>Créer une adresse de client pour une commande de service

Pour ajouter une adresse à une commande de service, procédez comme suit :

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.

2.  Ouvrez la commande de service pour laquelle vous souhaitez créer une adresse.

3.  Dans le volet **Actions**, cliquez sur **Modifier**, puis sur **Vue de l'en-tête**.

4.  Dans l'organisateur **Adresse**, cliquez sur **Ajouter une adresse**.

5.  Dans l'écran **Nouvelle adresse**, entrez un nom unique pour l'adresse et renseignez les autres champs. 
    

    > [!WARNING]
    > <P>Si vous entrez le même nom comme adresse existante, les informations entrées dans les champs restants remplaceront les informations relatives à l'adresse existante.</P>


6.  Cliquez sur **OK** pour copier la nouvelle adresse sur votre commande de service.

## <a name="specify-an-alternative-address-on-a-service-order"></a>Spécification d'une autre adresse dans une commande de service

Pour ajouter une adresse alternative à une commande de service, procédez comme suit :

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.

2.  Ouvrez la commande de service pour laquelle vous souhaitez entrer une adresse alternative.

3.  Dans le volet **Actions**, cliquez sur **Modifier**, puis sur **Vue de l'en-tête**.

4.  Dans l'organisateur **Adresse**, cliquez sur **Autre adresse**.

5.  Dans l'écran **Sélection d'adresse**, dans le champ **Type d'enregistrement**, sélectionnez **Commandes de service**.

6.  Sélectionnez une adresse, puis cliquez sur **OK** pour la copier sur votre commande de service.


  


