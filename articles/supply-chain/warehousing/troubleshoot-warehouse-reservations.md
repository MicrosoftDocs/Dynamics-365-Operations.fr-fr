---
title: Résoudre des problèmes de réservations dans la gestion des entrepôts
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de réservations en entrepôts dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: d0d73396772ed9e8397797d6685fb550d911303b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828104"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a>Résoudre des problèmes de réservations dans la gestion des entrepôts

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de réservations en entrepôts dans Microsoft Dynamics 365 Supply Chain Management.

Pour les rubriques liées aux enregistrements de lots et de numéros de série, voir [Résoudre les problèmes liés aux hiérarchies de réservation de lots et de série en entrepôt](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a>Je reçois le message d’erreur suivant : "Impossible de supprimer les réservations, car un travail qui a été créé repose sur ces réservations."

### <a name="issue-description"></a>Description du problème

Vous ne pouvez pas annuler la réservation d’un stock sur une ligne de vente, car il y a un travail en cours sur la ligne.

### <a name="issue-resolution"></a>Résolution du problème

Vérifiez s’il existe un travail de groupe d’emballage ouvert pour amener l’article d’une station d’emballage à un autre emplacement (tel que *Baydoor*). Passez en revue les enregistrements sur les pages **Journal de l’historique de création de travail** et **Détails du travail** pour déterminer ce qui réserve physiquement le stock, puis terminer ou supprimer le travail pour libérer la réservation.

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a>Je reçois le message d’erreur suivant : "Quantité de stock -%1 n’a pas pu être mis à jour en raison de transactions de stock insuffisantes pour l’article %2..."

### <a name="issue-description"></a>Description du problème

Ce problème peut se produire si le système ne peut pas mettre à jour une quantité de stock car il n’y a pas suffisamment de transactions de stock qui ont les dimensions spécifiées. Voici l’intégralité du message d’erreur :

> Quantité de stock -%1 n’a pas pu être mis à jour en raison de transactions de stock insuffisantes pour l’article %2 avec dimensions Taille=%3, Couleur=%4, Ajouts=%5, Site=%6, Entrepôt=%7, Emplacement=%8, Statut du stock=Disponible, Contenant=%9, Numéro de lot=%10 pour l’ID de référence %11 sur l’ID de lot %12.

### <a name="issue-resolution"></a>Résolution du problème

Assurez-vous qu’aucune transaction de stock ne réserve physiquement la quantité. Par exemple, ces transactions peuvent ouvrir des commandes de qualité, des enregistrements de blocage des stocks ou des commandes de sortie.

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a>Je reçois le message d’erreur suivant : "Physique disponible... ne peut pas être réservé car seuls 0,00 sont disponibles dans le stock. »

### <a name="issue-description"></a>Description du problème

Ce problème peut se produire si le système ne peut pas mettre à jour une quantité de stock car il n’y a pas suffisamment de transactions de stock qui ont les dimensions spécifiées. Voici l’intégralité du message d’erreur :

> Site physique disponible=%1, Entrepôt=%2, Statut du stock=Disponible, Numéro de lot=%3, Propriétaire=%4 :%5 ne peut pas être réservé car seuls 0,00 sont disponibles dans le stock.

### <a name="issue-resolution"></a>Résolution du problème

Ce problème est probablement dû à un travail ouvert. Soit terminer le travail, soit recevez sans création de travail. Assurez-vous qu’aucune transaction de stock ne réserve physiquement la quantité. Par exemple, ces transactions peuvent être des commandes de qualité ouvertes, des enregistrements de blocage des stocks ou des commandes de sortie.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
