---
title: Suspendre et reprendre une transaction dans le point de vente (PDV)
description: Cette rubrique explique comment les utilisateurs peuvent suspendre des transactions en cours et les reprendre ultérieurement ou sur une autre caisse à l'aide de Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 11/27/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 823d538bea481aef4f3657fe0ae1ebb3b0cf759c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972528"
---
# <a name="suspend-and-resume-a-transaction-in-the-point-of-sale-pos"></a>Suspendre et reprendre une transaction dans le point de vente (PDV)

[!include [banner](includes/banner.md)]


Les utilisateurs du point de vente (PDV) peuvent suspendre des transactions en cours, puis les reprendre plus tard ou sur une autre caisse. Les transactions sont souvent suspendues pour libérer rapidement une caisse pour une autre tâche sans perdre la progression de la transaction en cours. Par exemple, un employé du magasin commence à traiter la transaction d'un client sur un appareil mobile mais doivent la terminer sur une caisse avec un tiroir-caisse. Dans ce cas, l'employé du magasin peut suspendre la transaction sur l'appareil mobile, puis la rappeler et la reprendre sur une caisse.

## <a name="configure-suspend-and-resume-functionality"></a>Configurer la fonctionnalité Suspendre et reprendre

### <a name="pos-operations"></a>Opérations PDV

Deux [Opérations PDV](pos-operations.md) permettent au PDV la prise en charge des scénarios Suspendre et reprendre. Vous pouvez affecter ces opérations au [groupes de boutons](pos-screen-layouts.md) de la page de transaction ou la page d'accueil.

- 503 : Suspendre une transaction
- 504 : Rappeler une transaction

### <a name="receipt-template"></a>Modèle de ticket de caisse

Le PDV peut être configuré pour générer un bordereau imprimé lorsqu'une transaction est suspendue. Ce bordereau peut être utilisé pour identifier rapidement et rappeler la transaction ultérieurement.

Pour permettre au POS d'imprimer un bordereau, vous devez ajouter le format du ticket de caisse **Transaction suspendue** au profil de ticket de caisse du magasin. Vous pouvez concevoir le format du ticket de caisse afin qu'il inclue ou exclue des détails spécifiques sur la transaction. Par exemple, le format peut inclure un code-barres pour prendre en charge la lecture.

### <a name="receipt-numbering"></a>Numérotation des tickets de caisse

Quant aux autres types de transactions de PDV qui génèrent un ticket de caisse imprimé, vous pouvez définir une souche de numéros pour les transactions suspendues dans la section **Numérotation des tickets de caisse** du profil de fonctionnalité du magasin.

### <a name="void-when-closing-shift"></a>Annuler lors de la clôture de l'équipe

Vous pouvez utiliser l'option **Annuler lors de la clôture de l'équipe** pour obliger les utilisateurs à terminer ou à annuler les transactions suspendues avant de clôturer leur équipe. Lors de l'opération **Clôturer l'équipe**, le PDV invite les utilisateurs à afficher ou annuler les transactions suspendues en attente.

## <a name="suspend-and-resume-a-transaction"></a>Suspendre et reprendre une transaction

### <a name="suspend-a-transaction"></a>Suspendre une transaction

Les utilisateurs disposant des autorisations nécessaires, et dont la mise en page de l'écran comprend l'opération **Suspendre une transaction**, peuvent suspendre une transaction afin qu'elle soit rappelée plus tard ou sur une autre caisse.

Les transactions peuvent être suspendues uniquement si elles ne contiennent **pas** les types de lignes suivants :

- Lignes de paiement actives
- Lignes de carte cadeau (pour émettre une carte cadeau ou ajouter au solde de la carte cadeau)

Une transaction suspendue n'affecte pas les informations de vente ou les informations de disponibilité de stock du magasin.

### <a name="resume-a-suspended-transaction"></a>Reprendre une transaction suspendue

Les transactions suspendues peuvent être rappelées et reprises dans le même magasin par n'importe quel utilisateur disposant d'autorisations nécessaires, et ayant également une mise en page incluant l'opération **Rappeler une transaction**.

Pour rappeler rapidement et facilement une transaction suspendue, lisez le code-barres sur le bordereau imprimé tout en affichant la liste des transactions de l'opération **Rappeler une transaction**.

### <a name="considerations-for-offline-mode"></a>Considérations relatives au mode hors connexion

- Toute transaction suspendue alors que le PDV est en mode en ligne ne peut être reprise en mode hors ligne, car les données ne sont pas synchronisées à la base de données hors ligne.
- Si vous suspendez une transaction alors que le PDV est en mode hors ligne, vous pouvez la rappeler en mode hors ligne, à condition que le PDV n'ait pas été basculé vers le mode en ligne entre-temps depuis que vous avez suspendu la transaction. Lorsque le PDV est basculé vers le mode en ligne, les données sur les transactions suspendues sont déplacées vers la base de données en ligne et supprimées de la base de données hors ligne. Par conséquent, les transactions peuvent être reprises uniquement en mode en ligne. Si vous basculez le PDV vers le mode hors ligne, vous ne pourrez pas reprendre les transaction suspendues, car elles ont déjà été supprimées de la base de données hors ligne.

### <a name="void-a-suspended-transaction"></a>Annuler une transaction suspendue

Vous pouvez annuler des transactions suspendues en rappelant la transaction puis en effectuant l'opération **Annuler la transaction**, ou en sélectionnant la transaction dans la liste **Rappeler la transaction** et en sélectionnant **Annuler** sur la barre d'application. Sinon, le magasin peut être configuré pour inviter les utilisateurs à annuler les transactions suspendues lorsqu'ils clôturent leur équipe.
