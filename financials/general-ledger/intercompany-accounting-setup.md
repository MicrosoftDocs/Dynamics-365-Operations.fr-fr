---
title: "Paramétrage de la comptabilité intersociétés"
description: "Cette rubrique décrit la procédure de paramétrage de la comptabilité intersociétés afin de pouvoir utiliser les journaux intersociétés pour les répartitions comptables et les journaux financiers, tels que les journaux, les journaux de factures fournisseurs, et les journaux des paiements d&quot;opérations diverses."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15761
ms.assetid: 1362297b-7a51-4930-b822-2b204a2e3c37
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 5fd279327013f26230146be38e23e9955c6f12c7
ms.lasthandoff: 03/31/2017


---

# <a name="intercompany-accounting-setup"></a>Paramétrage de la comptabilité intersociétés

Cette rubrique décrit la procédure de paramétrage de la comptabilité intersociétés afin de pouvoir utiliser les journaux intersociétés pour les répartitions comptables et les journaux financiers, tels que les journaux, les journaux de factures fournisseurs, et les journaux des paiements d'opérations diverses.

Les journaux intersociétés peuvent être créés dans des scénarios différents, comme pour les journaux, les journaux des factures fournisseurs, les répartitions comptables, et les paiements centralisés d'opérations diverses. Pour activer ces scénarios, vous devez paramétrer la comptabilité intersociétés.

## <a name="define-main-accounts"></a>Définissez les comptes principaux
Vous devez d'abord créer des comptes principaux intersociétés à utiliser pour les écritures comptables Dû à et À recevoir de. Il est préférable d'utiliser des comptes principaux uniques pour chaque société, pour simplifier le rapprochement et l'élimination des écritures comptables intersociétés. Si vous utilisez une dimension partenaire commercial ou d'équivalents pour identifier la partie intersociétés, vous pouvez définir cette dimension comme fixes dans le compte principal défini dans la comptabilité intersociétés. Lorsque vous paramétrez les comptes principaux, vous devez le bilan définir ** type de compte principal ** champ ** ** sur ** des comptes principaux ** la page.

## <a name="define-journal-names"></a>Définissez les noms de journal
Ensuite, vous devez définir un nom de journal. Le journal définissez ** type de journal ** champ ** ** sur ** des noms de journal ** la page. Il est préférable d'utiliser un nom de journal spécifique pour la comptabilité intersociétés.

## <a name="define-intercompany-accounting-setup"></a>Définissez le paramétrage de la comptabilité intersociétés
** Comptabilité intersociétés ** La page est utilisée pour créer des paires d'entités juridiques qui peuvent traiter avec les autres. Le paramétrage de la comptabilité intersociétés est partagé, de sorte que le paramétrage est visible de toutes les entités juridiques. Lors de la création d'une paire d'entité juridique, assurez-vous que vous rendez compte dont l'entité juridique est définie comme société d'origine et la société de destination. Lorsque vous entrez des transactions intersociétés, la transaction détermine l'entité juridique est initialisante ou lançante la transaction. Par exemple, la comptabilité intersociétés est paramétrée pour USMF (origine) et USSI (destination). Si un utilisateur est active dans USSI et entre une transaction intersociétés avec USMF, la transaction n'est pas validée car Comptabilité intersociétés est définie que pour USMF est l'expéditeur. Si l'une de société peut libérer une transaction, vous devez créer une deuxième paire d'entité juridique pour le paramétrage réciproque. 

Sélectionnez ** compte de débit (directement depuis) ** et ** compte de crédit ({{en:Due_to}} raison {{de:Due_to}}) ** pour le départ et l'entité juridique de destination. Indiquez que ** le nom du journal ** sera utilisé lorsque la transaction est créée dans la société de destination. Le journal pour la société d'origine est déjà connu car il a sélectionné par l'utilisateur lors de la création d'une transaction intersociétés. 

Enfin, sélectionnez l'entité juridique qui reçoit les montants de prise en charge de compte, tels que l'escompte de règlement ou les profits/pertes réalisés pour les paiements centralisés. 

Une relation réciproque peut être facilement définie sous ** comptabilité intersociétés ** la page à l'aide ** créez la relation réciproque ** du bouton après que la première paire de l'entité juridique soit créée. Lorsque la paire réciproque est créée, les informations de la société de destination est copiée dans la société d'origine et inversement. Le journal défini pour la société de destination préalable. La plupart des organisations utilisent la même convention d'appellation pour leurs noms de journal, de sorte que le nom du journal soit identique. Si le nom du journal est différent, un avertissement semblera dans le champ vous informer que le journal n'existe pas et une autre journal peut être sélectionné.


