---
title: Paramétrer et générer des informations sur la plage âgée de la comptabilité client
description: Ce guide vous aidera à paramétrer une définition de plage âgée, des soldes client échus et à afficher des soldes dans la liste Solde échu et sur la page Recouvrement.
author: mikefalkner
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 77b5dd5feb16cc3bd6d64b6520cc47087c5b5224
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188646"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a>Paramétrer et générer des informations sur la plage âgée de la comptabilité client

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide vous aidera à paramétrer une définition de plage âgée, des soldes client échus et à afficher des soldes dans la liste Solde échu et sur la page Recouvrement. La société fictive USMF sert d'exemple dans cet enregistrement.


## <a name="create-an-aging-period-definition"></a>Créer une définition de plage âgée
1. Accédez à **Volet de navigation > Modules > Crédit et recouvrements > Paramétrage > Définitions des plages âgées**.
2. Cliquez sur **Nouveau**.
3. Entrez une valeur dans le champ **Définition de la plage âgée**.
4. Tapez une valeur dans le champ **Description**.
5. Cliquez sur **Ajouter au-dessous** pour insérer une nouvelle plage âgée.
6. Dans le champ **Période**, entrez la description à indiquer sur les balances âgées.
7. Entrez un numéro dans le champ **Unité**.
8. Sélectionnez une option dans le champ **Intervalle**. La période comptable correspond à la période de votre calendrier comptable. Le jour, la semaine, le mois, le trimestre et les années définissent l'étendue de l'intervalle par type de date. L'option Illimité permet de sélectionner l'ensemble des transactions avant ou après la période précédente, selon qu'il s'agisse de la première ou la dernière période.  
9. Sélectionnez une option dans le champ **Indicateur âgé**.
10. Sélectionnez la période en haut de la grille. Mettez la description à jour pour décrire la période la plus ancienne dans la définition de plage âgée.
11. Entrez la nouvelle description de la plage âgée dans le champ **Période**.
12. Fermez la page.

## <a name="age-the-balances"></a>Définir l'âge des soldes
1. Accédez à **Crédit et relances > Tâches périodiques > Soldes client échus**.
2. Dans le champ **Définition de la plage âgée**, sélectionnez la définition de plage âgée que vous avez créée.
    + Vous pouvez avoir un instantané actif pour chaque définition de plage âgée.  
    + Tous les clients sont traités par défaut. Vous pouvez utiliser cette sélection pour calculer un seul regroupement de recouvrements de clients.  
    + Sélectionnez la date de la transaction que vous utiliserez pour la balance âgée.  
    + Sélectionnez une date « en date du » pour la balance âgée. La valeur par défaut est la date du jour, mais si vous remplacez ce champ par Date sélectionnée, vous pourrez choisir la date que vous souhaitez. Utilisez la date du jour pour le traitement par lots.  
3. Développez la plage **Société**. Vous pouvez sélectionner les sociétés qui seront incluses dans l'instantané. La société actuelle est sélectionnée par défaut.
4. Cliquez sur **OK** pour traiter l'instantané. Cela prendra un certain du temps, vous devez donc attendre que le curseur disparaisse et consulter les messages du centre de message.

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a>Afficher les soldes dans la liste Soldes chronologiques et dans la page Collection
1. Accédez à **Crédit et relances > Collections > Soldes chronologiques**. La page de liste affiche les soldes du client. L'icône de balance âgée indique la plage âgée de la transaction la plus ancienne.  
2. Sélectionnez un client avec un solde.
3. Développez la zone de récapitulatif **Âgé** pour afficher les balances âgées. La définition de plage âgée pour le récapitulatif provient de celle par défaut spécifiée dans les paramètres. Vous pouvez la modifier à l'aide du menu Collecter.  
