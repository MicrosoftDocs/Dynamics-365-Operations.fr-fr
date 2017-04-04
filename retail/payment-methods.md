---
title: Modes de paiement
description: "Chaque type de paiement qu&quot;un détaillant accepte doit être configuré dans la vente au détail et le commerce dans Microsoft Dynamics 365 pour les opérations moment où le système est paramétré. Cet article décrit les types de paiement que vous pouvez paramétrer, ainsi que leur procédure de paramétrage."
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: MargoC
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b887fc5d03ea8982515e92725ce98cc416e56f9e
ms.openlocfilehash: 011beec07bf1ab858892ab1c374f1acf3839e877
ms.lasthandoff: 03/31/2017


---

# <a name="payment-methods"></a>Modes de paiement

Chaque type de paiement qu'un détaillant accepte doit être configuré dans la vente au détail et le commerce dans Microsoft Dynamics 365 pour les opérations moment où le système est paramétré. Cet article décrit les types de paiement que vous pouvez paramétrer, ainsi que leur procédure de paramétrage.

Les détaillants peuvent accepter différents types de paiement en échange des produits et des services qu'ils vendent. Bien que les espèces soient la forme de paiement la plus courante, les détaillants peuvent également être payés par chèques, cartes, N° document, etc. Chaque type de paiement auquel le détaillant accepte doit être paramétré dans Dynamics 365 pour les opérations - au détail moment où le système est paramétré. La liste ci-dessous décrit chaque type de paiement qui peut être paramétré dans Dynamics 365 pour les opérations - au détail :

-   **Espèces** – Argent sous forme physique de devises, comme des billets de banque et des pièces. Cette devise peut être celle de la société ou la devise locale du magasin.
-   **Chèque** – Effet négociable donnant un ordre de paiement d'un montant spécifique pour une devise particulière, tiré sur une banque spécifiée. Un chèque est généralement valide indéfiniment ou pendant six mois à compter de sa date d'émission, sauf si une autre période de validité est spécifiée. Cette période peut varier en fonction de la banque sur laquelle le chèque est tiré. Il existe différents types de chèques, tels que les chèques à ordre, les chèques-guichets, les chèques au porteur et les chèques à porter en compte. Vous pouvez paramétrer les chèques comme mode de paiement pour chaque magasin. Les chèques sont acceptés dans la devise définie au niveau de la société ou du magasin. Avant d'accepter un paiement par chèque dans un magasin, vous devez paramétrer les chèques comme mode de paiement.
-   **Devise** – Il s'agit du principal moyen de paiement autre que la devise par défaut de la société. Les pièces et les billets sont des formes de devise. Le mode de paiement en devise représente toutes les devises utilisées dans Commerce et vente au détail. Pour utiliser ce mode de paiement, vous devez paramétrer les devises et spécifier les informations de change pour la vente au détail pour les devises.
-   **Carte** : représente tous les types de cartes utilisées dans Commerce et vente au détail, comme les cartes de débit et de crédit. Il est préférable de paramétrer un seul mode de paiement par carte au niveau de l'organisation, pour représenter chaque type de carte. Au niveau du magasin, paramétrez ensuite un mode de paiement par carte ou ensemble de cartes, qui sera traité à l'aide des mêmes paramètres. Avant d'accepter le paiement par cartes dans un magasin, vous devez paramétrer les cartes disponibles sur le marché, à savoir des cartes de débit et de crédit.
-   **Avoir** : représente les avoirs émis ou remboursés au point de vente. L'avoir peut être un avoir ou une note d'intérêt d'avoir émise pour une vente de retour. Si les avoirs ne sont remboursés que partiellement, le programme crée un nouvel avoir pour le nouveau solde. Le nouvel avoir a un nouveau numéro. Un avoir ne peut être utilisé qu'une fois, le système conservant une trace de tous les numéros utilisés. L'enregistrement peut être affiché sur la page **Table des avoirs**. Un client ne peut pas se faire rembourser un montant supérieur à la valeur de l'avoir.
-   **Carte cadeau** – Désigne les cartes cadeaux émises et remboursées au point de vente. Les trop-perçus ne sont pas autorisés pour les cartes cadeaux.
-   **Compte client** – Paiements pouvant être facturés sur le compte d'un client au moment de la vente à partir de la caisse enregistreuse. Vous pouvez également utiliser ce mode de paiement pour collecter des informations de vente ou des remises spécifiques aux clients en cas de paiement par un autre moyen. Dans ce cas, vous devez paramétrer les informations concernant les clients.
-   ** Les points de fidélité ** – Point que les clients s'accumulent dans des programmes de fidélité. Si vous créez des programmes de fidélité, les clients peuvent obtenir les points puis rembourser de différentes manières. Par exemple, dans certains programmes de fidélité, les clients peuvent racheter les points de fidélité sous la forme de remise ou même les utiliser comme moyen de paiement.

Pour paramétrer les modes de paiement dans Commerce et vente au détail, vous devez effectuer les tâches suivantes.

1.  Paramétrez les modes de paiement pour une organisation. Créez les modes de paiement acceptés par toute l'organisation.
2.  Créez les types et numéros de cartes pour l'organisation de carte. Si les cartes de crédit ou de débit sont acceptées, vous devez créer un mode de paiement pour les cartes, puis créer les types et numéros de cartes pour l'organisation de carte.
3.  Mode de paiement du magasin de paramétrage. Associez les modes de paiement à chaque magasin, puis entrez les paramètres spécifiques au magasin pour chaque mode de paiement.
4.  Paramétrage de modes de paiement par carte pour les magasins. Pour tous les modes de paiement par carte que le magasin accepte, complétez Paramétrage de carte.



