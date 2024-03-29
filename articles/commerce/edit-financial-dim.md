---
title: Modifier les dimensions financières des transactions de vente au détail
description: Cet article décrit la procédure de modification des dimensions financières des transactions de détail dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: b382907cd79a13319601dd694261319875565947
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268392"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a>Modifier les dimensions financières des transactions de vente au détail

[!include [banner](../includes/banner.md)]

Cet article décrit la procédure de modification des dimensions financières des transactions de détail dans Microsoft Dynamics 365 Commerce.

## <a name="edit-financial-dimensions"></a>Modifier les dimensions financières

Pour modifier les dimensions financières des transactions de vente au détail dans Commerce Headquarters, procédez comme suit.

1. Ouvrez la page **Configuration de dimension financière pour les applications d’intégration**.
1. Sélectionnez l’enregistrement **Intégration des dimensions par défaut** actif.
1. Dans le raccourci **Dimensions financières**, assurez-vous que toutes les dimensions que vous souhaitez modifier dans la feuille de calcul Excel sont présentes dans la liste **Sélectionné**. Pour plus d’informations, consultez [Entités de données](../fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration.md#data-entities).
1. Téléchargez et ouvrez le fichier Excel à partir de la page **Relevés**, de la page **Transactions de vente au détail** ou de la vignette **Échecs de validation de transaction** dans l’espace de travail **Finances du magasin**.
1. Pour modifier la dimension financière de la transaction, sélectionnez **Design**, puis sélectionnez le symbole du crayon en regard de la ligne **Transaction (vérifiable)**.
1. Trouvez et sélectionnez le champ **FinancialDimensionDisplayValue**, sélectionnez une cellule dans l’en-tête de la feuille de calcul Excel, puis sélectionnez **Ajouter une étiquette**.
1. Sélectionnez une cellule sous celle que vous avez sélectionnée à l’étape précédente, sélectionnez **Ajouter une valeur**, puis **Rafraîchir**. Les dimensions financières sont ajoutées à la feuille de calcul Excel et peuvent ensuite être modifiées et publiées.
1. Pour modifier les dimensions sur les lignes de transaction, sélectionnez la ligne **Transactions de vente (vérifiables)**, sélectionnez le symbole du crayon, puis répétez les étapes 6 et 7.
1. Pour modifier les dimensions sur les lignes de paiement, sélectionnez la ligne **Transactions de paiement (vérifiables)**, sélectionnez le symbole du crayon, puis répétez les étapes 6 et 7.

## <a name="additional-resources"></a>Ressources supplémentaires

[Modifier et vérifier les transactions de gestion des disponibilités et des paiements au comptant sans livraison](edit-cash-trans.md)

[Modifier et vérifier les commandes en ligne et les transactions de commandes client asynchrones](edit-order-trans.md)

[Créer un classeur Excel pour modifier les transactions de vente au détail](create-excel-edit.md)

[Ajouter des champs à un classeur Excel pour modifier les transactions de vente au détail](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
