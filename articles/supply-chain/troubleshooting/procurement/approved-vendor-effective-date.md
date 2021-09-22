---
title: Impossible de modifier la date d'effet d'un fournisseur approuvé
description: La liste des fournisseurs agréés par entité de produit ne permet pas de modifier la date d’effet
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: cb6dbd134d63daa163261cabdbd7eceb978877ae
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476292"
---
# <a name="cant-change-the-effective-date-for-an-approved-vendor"></a>Impossible de modifier la date d'effet d'un fournisseur approuvé


## <a name="symptoms"></a>Symptômes

Un produit a un fournisseur agréé qui a, par exemple, une date d’effet au 11 janvier 2018 (*11/01/2018*) et une date d’expiration à *Jamais*. Si vous essayez de modifier la date d’effet au 10 janvier 2018 (*10/01/2018*) ou au 12 janvier 2018 (*12/01/2018*), vous recevez l’erreur suivante :

> Impossible de créer un enregistrement dans la liste des fournisseurs agréés (PdsApproveVendorList). La valeur "Expiration" doit être supérieure ou égale à la valeur "Effet".

## <a name="resolution"></a>Résolution

Vous ne pouvez prolonger que la période pour laquelle le fournisseur est agréé. Les règles suivantes s’appliquent :

- Pour modifier la date d’effet afin qu’elle soit antérieure à l’un des enregistrements (périodes) existants pour le fournisseur de l’article, la date d’expiration de la nouvelle période doit être antérieure à toutes les dates d’expiration des enregistrements existants.
- Pour modifier la date d’expiration afin qu’elle soit postérieure à l’une des périodes existantes, la date d’effet doit être postérieure à la dernière date d’expiration de tout enregistrement existant.
- Pour réduire la période globale pour laquelle le fournisseur est agréé, vous devez supprimer ou modifier les enregistrements existants. Vous pouvez également utiliser le commutateur **Tronquer** lors de l’importation. Ce commutateur supprime tous les enregistrements existants dans la table pour les fournisseurs agréés par article.

Pour l’exemple de scénario décrit dans la description du problème, où un enregistrement a une date d’effet au *11/01/2018* et une date d’expiration à *Jamais*, vous pouvez importer un nouvel enregistrement dont la date d’effet est le *10/01/2018* et la date d’expiration *Jamais*. Cependant, vous ne pouvez pas réduire la période pour que la date d’effet soit mise à jour au *12/01/2018* via la gestion des données. Vous devez effectuer cette modification via l’interface utilisateur.
