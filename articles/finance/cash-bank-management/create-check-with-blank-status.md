---
title: Créer des chèques dont le statut est Vierge
description: Cet article explique comment créer des chèques en blanc pour un compte bancaire.
author: angelad116
ms.date: 10/24/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 86020d9088d8135c83716128a77090608536a78f
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804016"
---
# <a name="create-checks-that-have-blank-status"></a>Créer des chèques dont le statut est Vierge

[!include [banner](../includes/banner.md)]

Cet article explique comment créer des chèques en blanc. Par exemple, vous pouvez créer un chèque en blanc pour enregistrer un chèque qui a été endommagé et ne peut pas être utilisé pour le paiement.

Dans la page **Chèques**, vous effectuez les tâches de maintenance concernant les chèques. Par exemple, vous pouvez créer de nouveaux numéros de chèque et supprimer des chèques. Vous pouvez également créer des chèques ayant le statut **Vierge**. Quand un chèque en blanc a été créé, il est impossible de le supprimer ou de le réutiliser dans le système.

> [!NOTE]
> Cette fonction n’est disponible sur la page **Chèques** que si vous activez la fonctionnalité **Créer des chèques ayant le statut Vierge dans la page Chèques** sur la page **Gestion des fonctionnalités**. Si la fonction n’est pas activée, les chèques ayant le statut **Vierge** ne peuvent être créés qu’à partir de la boîte de dialogue **Paiement par chèque** au moment du processus de génération de paiement dans la Comptabilité fournisseur.

Pour ouvrir la page **Chèques**, accédez à **Gestion de la trésorerie et de la banque \> Comptes bancaires \> Comptes bancaires**, puis, dans le volet Actions, sous l’onglet **Gérer les paiements**, dans le groupe **Informations associées**, sélectionnez **Chèques**. Sinon, accédez à **Gestion de la trésorerie et de la banque \> Recherches et états \> Chèques**.

Ensuite, pour créer des chèques ayant le statut **Vierge**, dans le volet Actions, sélectionnez **Créer des chèques vierges**. Pendant que les chèques en blanc sont créés, le compte bancaire associé est temporairement désactivé. Ce comportement permet de réduire le risque que des paiements soient générés en même temps que des chèques en blanc sont créés. Une fois le processus terminé, le compte bancaire associé est réactivé.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
