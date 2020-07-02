---
title: Modes de paiement
description: Chaque type de paiement accepté par un détaillant doit être configurée lors du paramétrage du système. Cet article décrit les types de paiement que vous pouvez paramétrer, ainsi que leur procédure de paramétrage.
author: sericks007
manager: AnnBe
ms.date: 06/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 710c2f3bbe5b76af6d0bc0bf9a469e52c98c18d2
ms.sourcegitcommit: 550006e6376815237c21b5b30e928353f62fd97c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "3463158"
---
# <a name="payment-methods"></a>Modes de paiement

[!include [banner](includes/banner.md)]

Chaque type de paiement accepté par un détaillant doit être configurée lors du paramétrage du système. Cet article décrit les types de paiement que vous pouvez paramétrer, ainsi que leur procédure de paramétrage.

Les détaillants peuvent accepter différents types de paiement en échange des produits et des services qu'ils vendent. Bien que les espèces soient la forme de paiement la plus courante, les détaillants peuvent également être payés par chèques, cartes, N° document, etc. Chaque type de paiement accepté par le détaillant doit être configurée dans Dynamics 365 Commerce lors du paramétrage du système. La liste suivante décrit chaque type de paiement pouvant être paramétré :

- **Espèces** – Argent sous forme physique de devises, comme des billets de banque et des pièces. Cette devise peut être celle de la société ou la devise locale du magasin.
- **Chèque** – Effet négociable donnant un ordre de paiement d'un montant spécifique pour une devise particulière, tiré sur une banque spécifiée. Un chèque est généralement valide indéfiniment ou pendant six mois à compter de sa date d'émission, sauf si une autre période de validité est spécifiée. Cette période peut varier en fonction de la banque sur laquelle le chèque est tiré. Il existe différents types de chèques, tels que les chèques à ordre, les chèques-guichets, les chèques au porteur et les chèques à porter en compte. Vous pouvez paramétrer les chèques comme mode de paiement pour chaque magasin. Les chèques sont acceptés dans la devise définie au niveau de la société ou du magasin. Avant d'accepter un paiement par chèque dans un magasin, vous devez paramétrer les chèques comme mode de paiement.
- **Devise** – Il s'agit du principal moyen de paiement autre que la devise par défaut de la société. Les pièces et les billets sont des formes de devise. Le mode de paiement en devise représente toutes les devises utilisées. Pour utiliser ce mode de paiement, vous devez paramétrer les devises et spécifier les informations de change pour les devises.
- **Carte** – Tous les types de cartes utilisées dans , telles que les cartes de débit et de crédit. Il est préférable de paramétrer un seul mode de paiement par carte au niveau de l'organisation, pour représenter chaque type de carte. Au niveau du magasin, paramétrez ensuite un mode de paiement par carte ou ensemble de cartes, qui sera traité à l'aide des mêmes paramètres. Avant d'accepter le paiement par cartes dans un magasin, vous devez paramétrer les cartes disponibles sur le marché, à savoir des cartes de débit et de crédit.
- **Avoir** : représente les avoirs émis ou remboursés au point de vente. L'avoir peut être un avoir ou une note d'intérêt d'avoir émise pour une vente de retour. Si les avoirs ne sont remboursés que partiellement, le programme crée un nouvel avoir pour le nouveau solde. Le nouvel avoir a un nouveau numéro. Un avoir ne peut être utilisé qu'une fois, le système conservant une trace de tous les numéros utilisés. L'enregistrement peut être affiché sur la page **Table des avoirs**. Un client ne peut pas se faire rembourser un montant supérieur à la valeur de l'avoir.
- **Carte cadeau** – Désigne les cartes cadeaux émises et remboursées au point de vente. Les trop-perçus ne sont pas autorisés pour les cartes cadeaux. Toutes les cartes-cadeaux doivent avoir des mappages de numéros de carte. 
- **Compte client** – Paiements pouvant être facturés sur le compte d'un client au moment de la vente à partir de la caisse enregistreuse. Vous pouvez également utiliser ce mode de paiement pour collecter des informations de vente ou des remises spécifiques aux clients en cas de paiement par un autre moyen. Dans ce cas, vous devez paramétrer les informations concernant les clients.
- **Points de fidélité** : représente les points que les clients accumulent via les programmes de fidélité. Si vous créez ce type de programmes, les clients peuvent obtenir des points, puis les racheter de différentes manières. Par exemple, dans certains programmes de fidélité, les clients peuvent racheter les points de fidélité sous la forme de remise ou même les utiliser comme moyen de paiement.

Pour paramétrer les modes de paiement dans , vous devez effectuer les tâches suivantes.

1. Paramétrez les modes de paiement pour une organisation. Créez les modes de paiement acceptés par toute l'organisation.
2. Création de types et de numéros de cartes pour l'organisation. Si les cartes de crédit ou de débit sont acceptées, vous devez créer un mode de paiement par carte, puis créer les types et numéros de cartes pour toute l'organisation.
3. Paramétrer le mode de paiement du magasin. Associez les modes de paiement à chaque magasin, puis entrez les paramètres propres au magasin pour chaque mode de paiement de ce dernier.
4. Paramétrer les modes de paiement par carte pour les magasins. Vous devez paramétrer la carte pour tous les modes de paiement par carte acceptés par le magasin.
