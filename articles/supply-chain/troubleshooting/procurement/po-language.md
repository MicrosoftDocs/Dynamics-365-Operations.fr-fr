---
title: Les commandes fournisseur ne reflètent pas les paramètres linguistiques de l’entité juridique
description: Le nom du produit sur une commande fournisseur est affiché dans la langue du système au lieu de la langue définie pour l’entité juridique dans laquelle la commande fournisseur a été créée
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
ms.openlocfilehash: 4deec493b5480dc570ac82876243bc31a2ae87aa
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476325"
---
# <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a>Les commandes fournisseur ne reflètent pas les paramètres linguistiques de l’entité juridique


## <a name="symptoms"></a>Symptômes

Le nom du produit sur une commande fournisseur est affiché dans la langue du système au lieu de la langue définie pour l’entité juridique dans laquelle la commande fournisseur a été créée.

## <a name="reproduce-the-issue"></a>Reproduire le problème

La procédure suivante montre comment reproduire le problème.

1. Définissez la langue du système sur *EN-US* (Anglais américain).
1. Assurez-vous qu’il y a un produit où les langues *EN-US* et *DE* (Allemand) sont tenues à jour pour les traductions du nom du produit.
1. Changez la langue d’une entité juridique en *DE*.
1. Dans l’entité juridique où *DE* est défini comme langue, créez une commande fournisseur qui inclut le produit.
1. Notez que le nom du produit est toujours affiché en anglais américain (la langue du système).

## <a name="resolution"></a>Résolution

Ce comportement est fait exprès. Sur les commandes fournisseur, le produit est toujours affiché dans la langue du système. La langue de la commande fournisseur est utilisée lors de la création d’un journal de confirmation.
