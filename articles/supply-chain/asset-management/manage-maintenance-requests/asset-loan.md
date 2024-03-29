---
title: Financements reposant sur l’actif
description: Cet article décrit comment enregistrer des financements reposant sur l’actif dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectLoanSend, EntAssetObjectLoanListPage, EntAssetObjectLoanReturn, EntAssetObjectLoanInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f70b29ef69b80160f108e6f53edda12b86c2c9db
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015752"
---
# <a name="asset-loans"></a>Financements reposant sur l’actif

[!include [banner](../../includes/banner.md)]

 

Si votre société reçoit des actifs destinés à des travaux de réparation ou de maintenance depuis des sites internes ou des clients, et si vous prêtez temporairement des actifs à ces sites ou à ces clients, le module Gestion des actifs peut suivre les prêts d’actifs.

## <a name="register-asset-loans-on-a-maintenance-request"></a>Enregistrer des financements reposant sur des actifs dans le cadre d’une demande de maintenance

1. Sélectionnez **Gestion des actifs** \> **Demandes de maintenance** \> **Toutes les demandes de maintenance** ou **Demandes de maintenance actives**.
2. Sélectionnez la demande de maintenance pour enregistrer un financement reposant sur l’actif, puis sélectionnez **Modifier**.
3. Dans la page **Demande**, sélectionnez **Envoyer l’actif d’emprunt**.
4. Sélectionnez l’actif, puis entrez la date de retour prévue.
5. Cliquez sur **OK**.

> [!NOTE]
> - Vous pouvez envoyer un actif d’emprunt si un actif du même type d’actif est disponible.
> - L’actif que vous prêtez doit avoir un état de cycle de vie d’actif lui permettant d’être utilisé en tant qu’actif d’emprunt, tel que **InStorage**. Lorsque l’emprunt d’actif est enregistré, l’état de cycle de vie de l’actif est automatiquement mis à jour, par exemple, **OnLoan**.

Pour afficher la liste de tous les actifs que vous avez prêtés à d’autres emplacements ou clients, sélectionnez **Gestion des actifs** \> **Financement reposant sur l’actif** \> **Tous les financements reposant sur l’actif**. Si la case à cocher **Terminé** est activée pour un actif, l’actif a été enregistré comme retourné à votre société.

![Gérer les demandes de maintenance.](media/06-manage-maintenance-requests.png)

Dans la page **Financements actifs reposant sur l’actif**, vous pouvez afficher une liste de toutes les actifs d’emprunt qui n’ont pas encore été retournés à votre société.

## <a name="register-loan-assets-as-returned"></a>Enregistrer l’actif d’emprunt comme retourné

1. Sélectionnez **Gestion des actifs** \> **Emprunt d’actif** \> **Emprunts d’actif actifs**.
2. Sélectionnez le financement reposant sur l’actif à enregistrer comme étant retourné, puis sélectionnez **Retourner un financement reposant sur l’actif**.
3. Dans le champ **Retourné**, entrez de date et l’heure.
4. Cliquez sur **OK**.
5. Actualisez la page de liste **Financements actifs reposant sur l’actif**, et assurez-vous que l’emprunt d’actif n’apparaît plus dans la liste.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]