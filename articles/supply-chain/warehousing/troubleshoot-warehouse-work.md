---
title: Résoudre les problèmes de travail d’entrepôt
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de réservations en entrepôts dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 3015ec777953cedb5a5d8eea873ed1043cac04cb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970231"
---
# <a name="troubleshoot-warehouse-work"></a>Résoudre les problèmes de travail d’entrepôt

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de réservations en entrepôts dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a>Je ne peux pas déplacer des contenants comportant des éléments de numéro de série lorsqu'un numéro vierge et un reçu vierge sont autorisés dans le groupe de dimensions de suivi.

### <a name="issue-description"></a>Description du problème

Vous ne pouvez pas déplacer un contenant à l'aide d'un élément de menu **Mouvement** si le numéro de série a des paramètres de *Émission vierge autorisée* et *Reçu vierge autorisé* sur le groupe de dimensions de suivi, et s'il y a plusieurs contenants au même emplacement, dont certaines ont des numéros de série et d'autres ne les ont pas.

### <a name="issue-resolution"></a>Résolution du problème

Ce problème sera résolu par les modifications déployées dans [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687). Ces changements rendront le champ **Numéro de série** facultatif lorsqu'un reçu vierge et une émission vierge sont autorisés.

## <a name="i-receive-the-following-error-message-in-the-warehouse-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a>Je reçois le message d'erreur suivant dans l'application d'entrepôt lorsque je traite des mouvements : "Le propriétaire du stock %1 n'est pas autorisé dans ce processus. »

### <a name="issue-description"></a>Description du problème

La dimension de suivi **Propriétaire** est manquante lorsque l'application d'entrepôt est utilisée pour effectuer des mouvements. Un journal de transfert d'inventaire régulier du client Supply Chain Management semble fonctionner comme prévu et ne peut être enregistré que si la dimension **Propriétaire** est remplie.

### <a name="issue-resolution"></a>Résolution du problème

Microsoft a évalué ce problème et a déterminé qu'il s'agissait d'une limitation de fonctionnalité. Actuellement, les processus de gestion des entrepôts ne prennent en charge que les stocks appartenant à l'entité juridique.
