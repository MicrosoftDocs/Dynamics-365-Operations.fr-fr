---
title: Affecter des rôles utilisateur de bail
description: Cet article décrit les rôles de sécurité utilisés pour les locations d’actifs. Il explique également comment attribuer des utilisateurs à ces rôles.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 38c859d64742d582d0709506d83600ea26a21147
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878129"
---
# <a name="assign-lease-user-roles"></a>Affecter des rôles utilisateur de bail

[!include [banner](../includes/banner.md)]

Cet article décrit les rôles de sécurité utilisés pour les locations d’actifs. Il explique également comment attribuer des utilisateurs à ces rôles.

Trois rôles d’utilisateur différencient l’accès dans la location d’actifs. Un rôle est approprié pour le maintien des baux, un est approprié pour la visualisation des baux et un est approprié pour exécuter les tâches d’un commis aux baux. Chaque rôle dispose d’autorisations spécifiques pour toutes les pages de bail, et chacun permet aux utilisateurs d’afficher, de créer, de modifier ou de supprimer des baux, en fonction de leurs tâches.

| Rôle           | Description |
|----------------|-------------|
| Tenir à jour le bail | Les utilisateurs de ce rôle peuvent ajouter, modifier, supprimer et afficher des baux. Ce rôle est conçu pour les utilisateurs quotidiens dont les tâches incluent la création et la publication d’écritures de journal mensuelles et l’ajout de nouveaux baux. Ce rôle donne accès à toutes les fonctionnalités de location d’actifs. |
| Afficher le bail     | Les utilisateurs de ce rôle peuvent uniquement afficher les enregistrements de bail, les calendriers et exécuter des rapports. Ils ne peuvent pas créer des baux, modifier des baux existants ou créer des écritures de journal par rapport aux baux. Le rôle est conçu pour les utilisateurs qui doivent simplement afficher les baux, les calendriers de location et les transactions qui se produisent avec ces baux. |
| Employé chargé des baux    | Les utilisateurs dans ce rôle peuvent uniquement créer des baux. Ils ne peuvent pas modifier ou supprimer les baux existants, afficher les calendriers de location ou enregistrer les écritures de journal de location. Ce rôle est conçu pour les utilisateurs qui travaillent dans une capacité de saisie de données. |

Suivez ces étapes pour affecter les utilisateurs aux rôles utilisés dans la location d’actifs.

1. Allez dans **Administration du système \> Sécurité \> Affecter des utilisateurs aux rôles**.
2. Sélectionnez le rôle **Maintenir le bail**, **Commis de location**, ou **Voir le bail**, puis sélectionnez **Attribuer/exclure manuellement des utilisateurs**.
3. Sélectionnez l’utilisateur à attribuer au rôle, puis sélectionnez **Attribuer au rôle**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
