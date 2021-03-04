---
title: Créer des chèques dont le statut est Nul
description: Cette rubrique explique comment créer des chèques nuls pour un compte bancaire sur la page Chèques.
author: abruer
manager: AnnBe
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: aa1c4c33b977c0173da98aee409389b9242980fb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976448"
---
# <a name="create-checks-that-have-blank-status"></a>Créer des chèques dont le statut est Nul

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment créer des chèques nuls. Par exemple, vous pouvez créer un chèque nul pour enregistrer un chèque qui a été endommagé et ne peut pas être utilisé pour le paiement.

Dans la page **Chèques**, vous effectuez les tâches de maintenance concernant les chèques. Par exemple, vous pouvez créer de nouveaux numéros de chèque et supprimer des chèques. Vous pouvez également créer des chèques ayant le statut **Nul**. Quand un chèque nul a été créé, il est impossible de le supprimer ou de le réutiliser dans le système.

> [!NOTE]
> Cette fonction n’est disponible sur la page **Chèques** que si vous activez la fonctionnalité **Créer des chèques ayant le statut nul dans la page Chèques** sur la page **Gestion des fonctionnalités**. Si la fonction n’est pas activée, les chèques ayant le statut **Nul** ne peuvent être créés qu’à partir de la boîte de dialogue **Paiement par chèque** au moment du processus de génération de paiement dans la Comptabilité fournisseur.

Pour ouvrir la page **Chèques**, accédez à **Gestion de la trésorerie et de la banque \> Comptes bancaires \> Comptes bancaires**, puis, dans le volet Actions, sous l’onglet **Gérer les paiements**, dans le groupe **Informations associées**, sélectionnez **Chèques**. Sinon, accédez à **Gestion de la trésorerie et de la banque \> Recherches et états \> Chèques**.

Ensuite, pour créer des chèques ayant le statut **Nul**, dans le volet Actions, sélectionnez **Créer des chèques nuls**. Pendant que le système crée les chèques nuls, le compte bancaire associé est temporairement désactivé. Ce comportement permet de réduire le risque que des paiements soient générés en même temps que des chèques nuls sont créés. Une fois le processus terminé, le compte bancaire associé est réactivé.
