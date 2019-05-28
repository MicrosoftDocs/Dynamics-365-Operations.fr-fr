---
title: Expédition partielle d'un chargement de transport
description: Cette rubrique explique comment expédier partiellement un chargement et reporter la planification de la capacité du chargement.
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSTransportLoad
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 8c172f1b66e56f60e89f56ea98910f8d0e4f3e36
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545265"
---
# <a name="partial-shipment-of-a-transport-load"></a>Expédition partielle d'un chargement de transport

[!include[banner](../includes/banner.md)]

En paramétrant l'expédition partielle des chargements, vous pouvez gérer des chargements pour lesquels la capacité ne peut pas être déterminée tant toutes les lignes de vente n'ont pas été ajoutées à un chargement. Ce processus peut ensuite être finalisé lorsque le nombre exact de palettes est connu. Par conséquent, vous ne devez pas décider quelles palettes sont affectées à lesquelles transport jusqu'au moment où un transport est physiquement déchargé du stock intermédiaire.

Cette fonctionnalité offre une alternative à l'application d'une structure plus rigide, dans laquelle vous devez déterminer quelles palettes sont affectées à quel transport avant que le travail de prélèvement ou de chargement puisse être créé. Au lieu de cela, les utilisateurs peuvent configurer des chargements individuels pour une confirmation d'expédition partielle. Le processus de chargement de transport pour ces chargement peut alors avoir lieu. Par conséquent, le service de planification du transport peut planifier des chargements sans avoir à prendre en compte la capacité des transports individuels.

Lors du chargement, les collaborateurs peuvent définir un nouveau chargement de transport dans lequel une palette peut être chargée. Sinon, ils peuvent identifier un chargement de transport existant. Ces données peuvent être enregistrées via un appareil mobile. Par conséquent, plusieurs magasiniers peuvent charger le stock avec les mêmes chargements ou des chargements différents sur le même camion. Les chargements peuvent ensuite être entièrement ou partiellement expédiés.

> [!NOTE] 
> Pour charger le stock d'un chargement vers un chargement de transport spécifique et expédier partiellement le chargement, le travail doit être généré à l'aide d'une classe de chargement dans un modèle de travail. Le travail de prélèvement habituel de type **Prélèvement** ne peut pas être chargé sur un chargement de transport comme un camion.

## <a name="set-up-transport-loads-for-partial-shipment"></a>Paramétrer des chargements de transport pour une expédition partielle

Le paramétrage de l'expédition partielle de chargements inclut les deux procédures suivantes.

### <a name="set-the-loading-strategy"></a>Définir la stratégie de chargement

Vous devez activer le chargement partiel en définissant la stratégie de chargement. Vous pouvez définir la stratégie de chargement après avoir créé un chargement.

1. Sélectionnez **Gestion des entrepôts** \> **Charges** \> **Toutes les charges**.
2. Sélectionnez une charge, puis cliquez sur **En-tête**.
3. Dans le champ **Stratégie de chargement**, sélectionnez **Expédition partielle du chargement autorisée**.

### <a name="create-a-menu-item-for-loading-of-transport-loads"></a>Créez une option de menu pour le chargement des charges de transport

Vous devez créer une option de menu qui active des charges de transport à charger. Un chargement de transport vous permet de regrouper des lignes de travail entre une charge ou plusieurs charges. Tout ce qui est ajouté au chargement de transport peut ensuite être expédié à l'aide d'un scanneur portable.

1. Sélectionnez **Gestion des entrepôts** \> **Configuration** \> **Appareil mobile** \> **Options de menu d'appareil mobile**.
2. Sélectionnez **Nouveau**, puis, dans le champ **Mode**, sélectionnez **Travail**.
3. Définissez l'option **Utiliser un travail existant** sur **Oui**.
4. Sous l'onglet **Général**, dans le champ **Dirigé par**, sélectionnez **Chargement de transport**.
5. Pour activer la confirmation d'expédition sur un scanneur mobile, dans le champ **Type de confirmation d'expédition autorisé**, sélectionnez **Chargement de transport**.

## <a name="confirm-shipment-of-a-transport-load-from-the-client"></a>Confirmer l'expédition d'un chargement de transport depuis le client

Ce paramétrage vous permet de confirmer un chargement de transport qui inclut un chargement complet ou une charge partiellement chargée à expédier.

1. Sélectionnez **Gestion des entrepôts** \> **Charges** \> **Chargements de transport**.
2. Dans le volet Actions, sous l'onglet **Expédier et recevoir**, dans le groupe **Confirmer**, sélectionnez **Transport**.
