---
title: Fractionnement client dans les programmes de facturation
description: Cet article décrit comment fractionner un client lorsque la facturation de l’abonnement est utilisée.
author: JodiChristiansen
ms.date: 11/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-11-05
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: cfbe61ca4b7e809a8183f4622bf6db4fc83a4d83
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746313"
---
# <a name="customer-split-on-billing-schedules"></a>Fractionnement client dans les programmes de facturation

Dans un programme de facturation, le *compte de facturation* est le client qui reçoit la facture de commande client afin qu’il puisse payer la facture. Dans certains scénarios, plusieurs clients peuvent payer une facture. La fonctionnalité **Fractionnement client** vous permet d’ajouter d’autres clients qui peuvent être facturés pour le même programme de facturation. Pour activer cette fonctionnalité, accédez à **Facturation de l’abonnement \> Facturation des contrats récurrents \> Configurer \> Paramètres de facturation des contrats récurrents** et définissez l’option **Fractionnement client** sur **Oui**.

## <a name="customer-split-on-the-billing-schedule-header"></a>Fractionnement client dans l’en-tête du programme de facturation

Une fois un programme de facturation créé, des clients supplémentaires peuvent être ajoutés à l’en-tête du programme de facturation.

Pour ajouter un client, procédez comme suit.

1. Dans l’onglet **Programme de facturation**, sélectionnez **Fractionnement client**. Les champs **Compte client** et **Nom du compte client** en haut spécifient le client qui est affecté en tant que **Client du programme de facturation**.

    > [!NOTE]
    > Le compte client que vous ajoutez ne peut pas être le même que le compte de facturation.

2. Dans l’onglet **Lignes de fractionnement client**, sélectionnez **Ajouter une ligne**.
3. Sélectionnez un client, puis saisissez le pourcentage de chaque facture pour ce client.
4. Par défaut, les dates de début et de fin du programme de facturation sont utilisées comme dates de début et de fin. Saisissez des dates de début et de fin différentes si le nouveau client ne paiera le pourcentage spécifié que pour une partie du programme de facturation. Par exemple, si le programme de facturation a une date de début au 1er janvier et une date de fin au 31 décembre et que le nouveau client est facturé à 40 % pour les neuf premiers mois, spécifiez le 1er janvier comme date de début et le 30 septembre comme date de fin et saisissez **40.00** comme pourcentage.

Vous pouvez ajouter plusieurs clients aux lignes de fractionnement client. Dans ce cas, le pourcentage total saisi ne doit pas dépasser 100 %. Saisissez une référence client et une demande d’achat client comme champs d’information qui seront affichés sur la ligne de commande client lors du processus **Générer une facture**.

Les détails de la ligne afficheront les coordonnées, l’adresse de livraison, l’adresse de facturation et les détails de paiement des clients ajoutés. Ces informations seront également indiquées sur la commande client pour les clients.

Lorsque vous ajoutez des informations de fractionnement client à l’en-tête du programme de facturation, s’il existe des lignes de programme de facturation non facturées dans le programme de facturation, vous recevrez le message suivant vous invitant à appliquer les changements : « Souhaitez-vous appliquer le changement effectué dans l’en-tête aux lignes également ? Les modifications ne vont mettre à jour que les lignes d’échéancier de facturation qui ne sont pas facturées. Sélectionnez **Oui** pour mettre à jour les informations de fractionnement client sur la ligne du programme de facturation. Les modifications ne seront pas mises à jour si la ligne du programme de facturation a déjà été facturée.

Si un programme de facturation est créé à l’aide de l’option **Copier le programme**, les informations par défaut seront saisies sur les lignes d’en-tête du fractionnement client. Elles ne peuvent pas être identiques au compte client.

Lorsque le processus **Générer une facture** est terminé, plusieurs commandes client seront créées. (Plusieurs factures client seront également créées si la validation automatique est utilisée.) Ces commandes client et factures client peuvent être consultées dans l’onglet **Facture** du raccourci **Détails de la ligne** sur la page **Afficher les détails de facturation**. L’option **Plusieurs** s’affiche sur la ligne des détails de facturation pour indiquer que plusieurs commandes client et factures client ont été créées.

## <a name="customer-split-on-billing-schedule-lines"></a>Fractionnement client dans les lignes du programme de facturation

Le fractionnement client peut être ajouté à des lignes individuelles du programme de facturation si vous ne souhaitez fractionner que des lignes spécifiques du programme de facturation. Cochez la case **Fractionnement client** sur la ligne, puis sélectionnez **Fractionnement client** dans le menu pour la ligne du programme de facturation à mettre à jour ou saisissez les informations de fractionnement client.

Les informations d’audit sont mises à jour si le programme de facturation a déjà été facturé, mais le pourcentage a ensuite été modifié sur la ligne du programme de facturation. Les lignes facturées après cette modification utiliseront le nouveau pourcentage.

> [!NOTE]
> - L’option de fractionnement client ne peut pas être utilisée avec les produits stockés.
> - Si la case à cocher **Revenus non facturés** est cochée, la case à cocher **Fractionnement client** ne peut pas être sélectionnée.
> - Si vous utilisez l’option **Fractionnement des revenus uniquement**, la ligne parent a l’option **Fractionnement client**, mais pas les éléments de la ligne enfant.
