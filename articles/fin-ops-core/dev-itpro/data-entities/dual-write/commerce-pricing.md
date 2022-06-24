---
title: Utilisez le moteur de tarification Dynamics 365 Commerce avec Dynamics 365 Sales
description: Cet article décrit comment utiliser le moteur de tarification dans Microsoft Dynamics 365 Commerce pour créer des devis de vente dans Dynamics 365 Sales.
author: ShalabhjainMSFT
ms.date: 11/19/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: global
ms.author: shajain
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 11a164ec15c8b7a69172a153b961011a8b324712
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881392"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a>Utilisez le moteur de tarification Dynamics 365 Commerce avec Dynamics 365 Sales

[!include [banner](../../includes/banner.md)]

Cet article décrit comment utiliser le moteur de tarification dans Microsoft Dynamics 365 Commerce pour créer des devis de vente dans Dynamics 365 Sales.

Le moteur de tarification Dynamics 365 Commerce prend en charge la plupart des scénarios de tarification d’entreprise à consommateur (B2C), tels que la tarification au niveau du magasin, la tarification basée sur l’affiliation et la fidélité, les remises mix-and-match, les remises sur quantité et les remises sur seuil. Le moteur de tarification utilise des règles complexes pour déterminer le meilleur prix pour une offre ou une commande donnée.

Lorsque vous utilisez la [double écriture](./dual-write-overview.md), vous avez trois options pour vos besoins de tarification. Vous pouvez utiliser la tarification statique issue de la liste de prix dans Dynamics 365 Sales, le moteur de tarification dans Dynamics 365 Supply Chain Management, ou le moteur de tarification dans Dynamics 365 Commerce. Parmi ces options, le moteur de tarification Commerce est le mieux adapté aux scénarios B2C.

## <a name="use-the-commerce-pricing-engine-in-sales"></a>Utiliser le moteur de tarification Commerce dans Sales

> [!NOTE]
> Actuellement, le moteur de tarification Commerce ne peut être utilisé que pour la création de devis dans Sales. L’intégration des commandes client avec le moteur de tarification Commerce n’est pas encore disponible.

Lorsque les utilisateurs lancent un devis dans Sales, la structure à double écriture copie les détails du devis dans Commerce. Toutes les modifications apportées aux lignes de devis existantes ou aux lignes de devis nouvellement ajoutées dans Sales sont copiées dans Commerce. Lorsque les utilisateurs souhaitent utiliser le moteur de tarification Commerce pour fixer le prix du devis, ils peuvent sélectionner **Devis** pour mettre à jour les prix du devis, en fonction du moteur de tarification Commerce. Les prix sont ensuite automatiquement mis à jour dans Sales et Commerce.

## <a name="prerequisites"></a>Conditions préalables

- Avant de pouvoir utiliser le moteur de tarification Commerce dans Sales, vous devez suivre les étapes dans [Prospect en disponibilités en double écriture](./dual-write-prospect-to-cash.md).
- Vous devez désactiver l’évaluation des accords commerciaux pour la saisie manuelle en procédant comme suit :

    1. Dans votre environnement Commerce, accédez à **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.
    1. Sur l’onglet **Prix**, sur le raccourci **Évaluation des accords commerciaux**, décochez la case **Saisie manuelle**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Prospect en disponibilités en double écriture](./dual-write-prospect-to-cash.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]