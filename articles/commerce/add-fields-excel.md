---
title: Ajouter des champs à un classeur Excel pour modifier les transactions de vente au détail
description: Cet article décrit comment ajouter des champs à un classeur Microsoft Excel afin que vous puissiez modifier les transactions de vente au détail dans Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.industry: Retail
ms.openlocfilehash: a5cf726e25364b883cfd644f064a9ed4fb6f509d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270397"
---
# <a name="add-fields-to-an-excel-workbook-to-edit-retail-transactions"></a>Ajouter des champs à un classeur Excel pour modifier les transactions de vente au détail

[!include [banner](../includes/banner.md)]

Cet article décrit comment ajouter des champs à un classeur Microsoft Excel afin que vous puissiez modifier les transactions de vente au détail dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Lorsque vous générez un fichier Excel afin de pouvoir modifier les transactions de vente au détail, le fichier est rempli avec certains champs par défaut. Si un champ qui doit être mis à jour n’est pas visible par défaut dans le fichier Excel généré, vous pouvez l’ajouter.

## <a name="add-fields-to-a-worksheet-in-an-excel-workbook"></a>Ajouter des champs à une feuille de calcul dans un classeur Excel

Pour ajouter des champs à un classeur Excel afin de pouvoir modifier les transactions de vente au détail, procédez comme suit.

1. Téléchargez et ouvrez le fichier Excel à partir de la page **Relevés**, de la page **Transactions de vente au détail** ou de la vignette **Échecs de validation de transaction** dans l’espace de travail **Finances du magasin**.
1. Sélectionnez **Design**.
1. Sélectionnez le symbole du crayon pour la table souhaitée, puis, dans la liste des champs disponibles, recherchez et sélectionnez le champ que vous souhaitez ajouter.
1. Sélectionnez **Ajouter**, puis sélectionnez **Mettre à jour**. Vous pouvez réorganiser les champs.
1. Une fois la mise à jour terminée, sélectionnez **Rafraîchir** pour récupérer les données de la nouvelle colonne.

Le nouveau champ et les données doivent maintenant être disponibles afin d’être modifiées dans Excel.

## <a name="additional-resources"></a>Ressources supplémentaires

[Modifier et vérifier les transactions de gestion des disponibilités et des paiements au comptant sans livraison](edit-cash-trans.md)

[Modifier et vérifier les commandes en ligne et les transactions de commandes client asynchrones](edit-order-trans.md)

[Modifier les dimensions financières des transactions de vente au détail](edit-financial-dim.md)

[Créer un classeur Excel pour modifier les transactions de vente au détail](create-excel-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
