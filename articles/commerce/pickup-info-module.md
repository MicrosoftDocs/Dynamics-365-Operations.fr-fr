---
title: Module d’information sur le retrait
description: Cet article couvre le module d’informations de retrait et décrit comment l’ajouter aux pages de paiement dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-09021
ms.dyn365.ops.version: Release 10.0.15
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 57633b7a23e581278ec0bc09ea146f5453570c4e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288404"
---
# <a name="pickup-information-module"></a>Module d’information sur le retrait

[!include [banner](includes/banner.md)]

Cet article couvre le module d’informations de retrait et décrit comment l’ajouter aux pages de paiement dans Microsoft Dynamics 365 Commerce.

Le module d’informations de retrait peut être utilisé dans un module de paiement pour afficher les informations de retrait de commande. Les clients peuvent consulter les dates et les plages horaires de retrait disponibles, puis sélectionner une heure appropriée pour récupérer leur commande. Par exemple, un client peut choisir de récupérer une commande à 15 h le 21 mars dans le magasin de San Francisco.

Les plages horaires de retrait pour les magasins appropriés doivent être configurées au siège social Commerce. Pour plus d’informations, consultez [Créer et mettre à jour des plages horaires pour le retrait client](dev-itpro/pickup-timeslots.md).

Si un module d’informations de retrait est créé sur une page de paiement, mais qu’aucune plage horaire n’est définie pour le magasin sélectionné pour la collecte, le module affichera des informations, mais l’utilisateur ne pourra sélectionner aucune plage horaire. Les plages horaires sont facultatives et ne sont pas nécessaires pour passer une commande.

Si plusieurs articles sont sélectionnés pour le retrait dans plusieurs magasins, le module d’information de retrait permettra à l’utilisateur de sélectionner un créneau horaire pour chaque magasin, à condition que des créneaux horaires soient disponibles pour celui-ci.

> [!NOTE]
> La prise en charge des créneaux horaires et du module d’informations de retrait à la caisse est disponible dans Dynamics 365 Commerce version 10.0.15 et ultérieure.

L’illustration suivante montre un exemple de sélection de créneau horaire via le module d’informations de retrait sur une page de paiement.

![Exemple de module d’informations de retrait sur une page de paiement.](./dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="module-properties"></a>Propriétés du module

- **En-tête** – Entrez un titre pour le module.

## <a name="show-time-slot-information-after-an-order-is-placed"></a>Afficher les informations sur les plages horaires après qu’une commande est passée

Une fois la commande passée, les informations sur la plage horaire sélectionnée peuvent être consultées dans le [module de confirmation de commande](order-confirmation-module.md) et le [module de détails de la commande](account-management.md#order-details-page). Ces deux modules ont une propriété **Afficher les informations sur les plages horaires**. Avant de pouvoir afficher la plage horaire sélectionnée pendant le processus de commande, cette propriété doit être définie sur **Vrai**.

## <a name="add-a-checkout-pickup-information-module-to-a-page"></a>Ajouter un module d’informations de retrait de paiement sur une page

Pour obtenir des instructions sur la façon d’ajouter un module d’informations sur le retrait à une page de paiement et de définir les propriétés requises, voir [Module de paiement](add-checkout-module.md).

L’illustration suivante montre un exemple de page de paiement pour l’e-commerce qui comprend des plages horaires pour les éléments de campagne de retrait.

![Exemple de page de paiement pour l’e-commerce qui comprend des plages horaires pour les articles de lignes de retrait.](./dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="additional-resources"></a>Ressources supplémentaires

[Créer et mettre à jour des créneaux horaires pour le prélèvement client](dev-itpro/pickup-timeslots.md)

[Module Validation](add-checkout-module.md)

[Module de confirmation de commande](order-confirmation-module.md)

[Module Détails de la commande](account-management.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
