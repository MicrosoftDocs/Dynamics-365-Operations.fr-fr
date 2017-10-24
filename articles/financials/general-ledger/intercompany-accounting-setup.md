---
title: "Paramétrage de la comptabilité intersociétés"
description: "Cette rubrique décrit la procédure de paramétrage de la comptabilité intersociétés afin de pouvoir utiliser les journaux intersociétés pour les répartitions comptables et les journaux financiers, tels que les journaux, les journaux de factures fournisseurs, et les journaux des paiements d'opérations diverses."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15761
ms.assetid: 1362297b-7a51-4930-b822-2b204a2e3c37
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9c5e73d97f6f52a417cb71dc5bfb57658765aaa1
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="intercompany-accounting-setup"></a>Paramétrage de la comptabilité intersociétés

[!include[banner](../includes/banner.md)]


Cette rubrique décrit la procédure de paramétrage de la comptabilité intersociétés afin de pouvoir utiliser les journaux intersociétés pour les répartitions comptables et les journaux financiers, tels que les journaux, les journaux de factures fournisseurs, et les journaux des paiements d'opérations diverses.

Les journaux intersociétés peuvent être créés dans divers scénarios, par exemple pour les journaux d'opérations diverses, journaux des factures fournisseur, les répartitions comptables et les paiements centralisés. Pour activer ces scénarios, vous devez paramétrer la comptabilité intersociétés.

## <a name="define-main-accounts"></a>Définir des comptes principaux
Vous devez d'abord créer des comptes principaux intersociétés à utiliser pour les écritures comptables Dû à et À recevoir de. Il est préférable d'utiliser des comptes principaux uniques pour chaque société, pour simplifier le rapprochement et l'élimination des écritures comptables intersociétés. Si vous utilisez une dimension de partenaire commercial ou d'homologues pour identifier le tiers intersociétés, vous pouvez définir la dimension comme fixe dans le compte principal défini dans la comptabilité intersociétés. Lorsque vous paramétrez les comptes principaux, vous devez définir le champ **Type de compte principal** sur **Bilan** sur la page **Comptes principaux**.

## <a name="define-journal-names"></a>Définir des noms de journaux
Ensuite, vous devez définir un nom de journal. Définissez le champ **Type de journal** sur **Quotidien** sur la page **Noms de journal**. Il est préférable d'utiliser un nom de journal spécifique pour la comptabilité intersociétés.

## <a name="define-intercompany-accounting-setup"></a>Définir le paramétrage de la comptabilité intersociétés
La page **Comptabilité intersociétés** est utilisée pour créer des paires d'entités juridiques qui peuvent traiter avec les autres. Le paramétrage de la comptabilité intersociétés est partagé, de sorte que le paramétrage est visible de toutes les entités juridiques. Lors de la création d'une nouvelle paire d'entité juridique, veillez à distinguer l'entité juridique qui est définie comme société d'origine par rapport à la société de destination. Lorsque vous entrez des transactions intersociétés, la transaction détermine l'entité juridique qui initie ou lance la transaction. Par exemple, la comptabilité intersociétés est paramétrée pour USMF (origine) et USSI (destination). Si un utilisateur est actif dans USSI et entre une transaction intersociétés avec USMF, la transaction n'est pas validée car la comptabilité intersociétés n'est définie que pour USMF qui est l'expéditeur. Si l'une des sociétés peut créer une transaction, vous devez créer une deuxième paire d'entité juridique pour le paramétrage réciproque. 

Sélectionnez le **compte de débit (Dû par)** et le **compte de crédit** (Dû à) pour l'entité juridique d'origine et de destination. Indiquez quel **nom de journal** sera utilisé lorsque la transaction est créée dans la société de destination. Le journal de la société d'origine est déjà connu car il est sélectionné par l'utilisateur lors de la création d'une transaction intersociétés. 

Enfin, sélectionnez l'entité juridique qui reçevra la comptabilité pour les montants de prise en charge, tels que l'escompte de règlement ou les profits/pertes réalisés pour les paiements centralisés. 

Une relation réciproque peut être facilement définie sur la page **Comptabilité intersociétés** à l'aide du bouton **Créer une relation réciproque** après la création de la première paire d'entité juridique. Lorsque la paire réciproque est créée, les informations de la société de destination sont copiéees vers la société d'origine et inversement. Le journal défini pour la société de destination est conservé. La plupart des organisations utilisent la même convention d'appellation pour leurs noms de journal, de sorte que le nom du journal soit identique. Si le nom du journal est différent, un avertissement apparaît dans le champ pour vous informer que le journal n'existe pas et qu'un autre journal peut être sélectionné.




