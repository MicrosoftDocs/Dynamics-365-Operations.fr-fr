---
title: Ajout d’une adresse à une commande de service
description: Cet article explique comment ajouter une adresse du client à une commande de service.
author: sorenva
ms.date: 06/15/2020
ms.topic: article
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c485c50bab7c2e945aa0f0fc0601008dcebd3328
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015723"
---
# <a name="add-an-address-to-a-service-order"></a>Ajout d’une adresse à une commande de service

[!include [banner](../includes/banner.md)]

Cet article explique comment ajouter une adresse du client à une commande de service. Lorsque vous créez une commande de service, les informations d’adresse sont transférées à partir du projet auquel la commande de service est associée. Toutefois, vous pouvez sélectionner un autre emplacement à partir des adresses qui sont déjà entrées dans Microsoft Dynamics AX pour des clients, des fournisseurs, des sites, des entrepôts, des commandes de service, et des projets.

Vous pouvez aussi créer une nouvelle adresse. Par défaut, la nouvelle adresse est transférée au projet. Toutefois, vous pouvez spécifier que la nouvelle adresse n’est applicable qu’à cette instance de service. Dans ce cas, la nouvelle adresse n’est pas transférée au projet.

## <a name="create-a-customer-address-for-a-service-order"></a>Créer une adresse de client pour une commande de service

Pour ajouter une adresse à une commande de service, procédez comme suit :

1. Accédez à **Gestion des services** \> **Commandes de service**\> **Commandes de service**.

1. Ouvrez la commande de service pour laquelle vous souhaitez créer une adresse.

1. Ouvrez l’onglet **En-tête**.

1. Développez le raccourci **Adresse**, puis sélectionnez **Ajouter l’adresse** dans la barre d’outils Raccourcis.

1. Dans la boîte de dialogue **Nouvelle adresse**, entrez un nom unique pour l’adresse et renseignez les autres champs. 

    > [!WARNING]
    > Si vous entrez le même nom comme adresse existante, les informations entrées dans les champs restants remplaceront les informations relatives à l’adresse existante.

1. Sélectionnez **OK** pour copier la nouvelle adresse sur votre commande de service.

## <a name="specify-an-alternative-address-on-a-service-order"></a>Spécification d’une autre adresse dans une commande de service

Pour ajouter une adresse alternative à une commande de service, procédez comme suit :

1. Accédez à **Gestion des services** \> **Commandes de service**\> **Commandes de service**.

1. Ouvrez la commande de service pour laquelle vous souhaitez entrer une adresse alternative.

1. Ouvrez l’onglet **En-tête**.

1. Développez le raccourci **Adresse**, puis sélectionnez **Autre adresse** dans la barre d’outils Raccourcis.

1. Dans la boîte de dialogue **Sélection d’adresse**, sélectionnez **Commandes de services** dans la liste déroulante au-dessus de la grille.

1. Sélectionnez une adresse, puis sélectionnez **OK** pour la copier sur votre commande de service.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]