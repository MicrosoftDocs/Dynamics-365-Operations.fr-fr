---
title: Restreindre la modification des répartitions comptables dans les factures
description: Cette rubrique explique comment exiger que les dimensions financières d’une commande fournisseur (CF) correspondent aux dimensions de la facture fournisseur correspondante.
author: v-kiarnd
ms.date: 10/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.search.industry: public sector
ms.author: v-kiarnd
ms.search.validFrom: 2020-10-15
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 3ee157eafbf44fa495e0b8e254aa9c85b2324277
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022647"
---
# <a name="restrict-editing-of-accounting-distributions-on-invoices"></a>Restreindre la modification des répartitions comptables dans les factures

[!include[banner](../includes/banner.md)]

Cette rubrique explique comment exiger que les dimensions financières d’une commande fournisseur (CF) correspondent aux dimensions de la facture fournisseur correspondante. Vous pouvez configurer des dimensions financières spécifiques qui doivent correspondre entre une CF et une facture créée à partir de celui-ci. Par exemple, vous pouvez exiger que toutes les dimensions financières correspondent entre les CF et les factures. Sur les factures associées à une CF, vous ne pouvez pas modifier les comptes généraux sur les lignes de détail de la facture afin qu’ils diffèrent des comptes qui ont été saisis sur les lignes de CF.

## <a name="set-up-locked-financial-dimensions"></a>Paramétrer des dimensions financières verrouillées

Suivez ces étapes pour définir les dimensions financières qui doivent correspondre entre une CF et les factures associées.

1. Allez dans **Comptabilité fournisseur \> Paramètres \> Paramètres de la comptabilité fournisseur**.
2. Sur la page **Activer le contrôle de rapprochement de factures**, sélectionnez **Validation rapprochement de facture/CF**.
3. Cochez la case **Correspondance requise** pour les dimensions qui doivent correspondre. Toutes les dimensions financières mises en place sur la page **Dimensions financières** sont disponibles pour la sélection.
4. Sélectionnez **Fermer**.

## <a name="work-with-locked-financial-dimensions-on-an-invoice"></a>Travailler avec des dimensions financières verrouillées sur une facture

Lorsque vous créez une facture fournisseur à partir d’une CF, vous ne pouvez pas modifier les dimensions financières verrouillées. Si vous essayez de modifier une dimension financière verrouillée, vous recevez un message d’erreur et toute la chaîne de dimension financière revient à la chaîne d’origine.

Vous pouvez afficher des dimensions financières pour la facture.

1. Accédez à **Comptabilité fournisseur \> Commun \> Factures fournisseur \> Factures fournisseur en attente**.
2. Ouvrez la facture.
3. Sur la page **Facture fournisseur**, sur le raccourci **Lignes**, sélectionnez **Finances \> Distribuer le montant**.

> [!NOTE]
> Les dimensions financières ne sont pas verrouillées sur les lignes ajoutées manuellement à une facture et non basées sur la CF. Dans ce cas, vous pouvez modifier les dimensions financières de la facture selon vos besoins, jusqu’à ce que la facture soit validée.
