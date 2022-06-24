---
title: Traiter les remboursements non liés avec le Connecteur de paiement Dynamics 365 Commerce pour Adyen
description: Cet article décrit le fonctionnement des remboursements non liés lorsque le connecteur de paiement Microsoft Dynamics 365 pour Adyen est utilisé.
author: BrianShook
ms.date: 10/07/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: BrShoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 634b30de7adbfb0c316fe14456581ea8eb89d070
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885195"
---
# <a name="process-unlinked-refunds-with-the-dynamics-365-commerce-payment-connector-for-adyen"></a>Traiter les remboursements non liés avec le Connecteur de paiement Dynamics 365 Commerce pour Adyen

[!include [banner](../includes/banner.md)]

Cet article décrit le fonctionnement des remboursements non liés lorsque le [Connecteur de paiement  Microsoft Dynamics 365 pour Adyen](adyen-connector.md) est utilisé. Il examine également la possibilité de traiter un remboursement par rapport à un nouveau mode de paiement dans un point de vente (PDV) ou un centre d'appels.

Le connecteur de paiement Dynamics 365 pour Adyen prend en charge la possibilité de traiter les remboursements en utilisant un mode de paiement différent de celui utilisé pour la transaction d'origine. Bien que nous vous recommandons d'utiliser les [remboursements liés](linked-refunds.md) pour traiter un remboursement par rapport au mode de paiement d'origine qui a été fourni, des remboursements sur un autre mode sont requis dans certains scénarios. Par exemple, la carte qui a été utilisée pour le paiement d'origine peut maintenant être expirée ou perdue, ou elle peut avoir été annulée par l'utilisateur.

## <a name="prerequisites"></a>Conditions préalables

Les conditions préalables suivantes doivent être remplies avant que le connecteur de paiement Dynamics 365 pour Adyen puisse traiter les remboursements non liés :

- Paramétrer les [modes de paiement](../payment-methods.md).
- Paramétrer les [paiements omnicanaux](../omni-channel-payments.md).

## <a name="additional-configuration"></a>Configuration supplémentaire

Le Connecteur de paiement Dynamics 365 pour Adyen fournit une mise en œuvre prédéfinie pour chaque scénario de remboursement pris en charge qui est décrit dans la section suivante. Les clients qui n'utilisent pas l'implémentation prête à l'emploi du connecteur de paiement Dynamics 365 pour Adyen doivent configurer le connecteur qui prend en charge la tokenisation des cartes de crédit.

## <a name="supported-refund-scenarios"></a>Scénarios de remboursement pris en charge

Dynamics 365 Commerce prend en charge les remboursements liés aux transactions qui étaient précédemment approuvées et confirmées. Les remboursements peuvent consister en un remboursement complet ou en un remboursement partiel de la transaction. Les remboursements ne peuvent pas dépasser le montant total de l'autorisation de paiement d'origine. Les remboursements non liés sont pris en charge uniquement dans les points de vente et les centres d'appels.

## <a name="enable-unlinked-refunds-functionality"></a>Activer la fonctionnalité de remboursements non liés

Pour activer la fonctionnalité de remboursements non liés dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Configuration du Siège \> Paramètres \> Paramètres commerciaux partagés**.
1. Dans l’onglet **Paiements omnicanaux**, définissez l’option **Utiliser les paiements omnicanaux** sur **Oui**.

### <a name="supported-payment-method-variants"></a>Variantes de mode de paiement prises en charge

Les variantes de mode de paiement suivantes prennent en charge les remboursements non liés prêts à l'emploi :

- Cartes
- Portefeuille

Toutes les variantes de modes de paiement ne prennent pas en charge les remboursements non liés. Le tableau suivant fournit une liste des méthodes de paiement courantes et montre la capacité de prise en charge de chaque méthode pour les remboursements liés et non liés.

| Mode de paiement        | Remboursement lié | Remboursement non lié |
|-----------------------|:-------------:|:---------------:|
| amexcommercial        | Oui           | Oui             |
| amexconsumer          | Oui           | Oui             |
| amexcorporate         | Oui           | Oui             |
| amexdebit             | Oui           | Oui             |
| amexprepaid           | Oui           | Oui             |
| amexprepaidreloadable | Oui           | Oui             |
| amexsmallbusiness     | Oui           | Oui             |
| discover              | Oui           | Oui             |
| maestro               | Oui           | Oui             |
| maestrouk             | Oui           | Oui             |
| mc                    | Oui           | Oui             |
| mcalphabankbonus      | Oui           | Oui             |
| mcprepaidanonymous    | Oui           | Oui             |
| visa                  | Oui           | Oui             |
| visaalphabankbonus    | Oui           | Oui             |
| visacheckout          | Oui           | Oui             |
| visadankort           | Oui           | Oui             |
| visahipotecario       | Oui           | Oui             |
| visasaraivacard       | Oui           | Oui             |
| vpay                  | Oui           | Oui             |
| givex                 | **N°**        | Oui             |
| svs                   | **N°**        | Oui             |
| cup                   | Oui           | Oui             |
| diners                | Oui           | Oui             |
| interac               | **N°**        | Oui             |
| jcb                   | Oui           | Oui             |
| jcb_applepay          | Oui           | Oui             |
| unionpay              | Oui           | Oui             |

### <a name="process-an-unlinked-refund-in-pos"></a>Traiter un remboursement non lié dans PDV

Un client renvoie un article à un caissier de point de vente dans le délai imparti pour les retours et dispose d'un reçu valide. Lors du traitement du retour, la boîte de dialogue **Paiement par retour** comprend une option **Choisir un moyen de paiement**. Le caissier peut alors sélectionner un mode de paiement parmi les modes de paiement pris en charge pour les remboursements (cartes et portefeuille).

### <a name="process-an-unlinked-refund-in-call-center"></a>Traiter un remboursement non lié dans un centre d'appels

Lorsqu'un remboursement non lié est traité pour une commande dans un centre d'appels, un employé du centre d'appels sélectionne un mode de paiement différent du mode d'origine. L'employé est alors invité à obtenir un numéro d'identification personnel (NIP) prioritaire pour l'administrateur. Le code PIN est requis avant que le mode de paiement différent puisse être traité pour le remboursement.

#### <a name="set-up-an-administrator-override-pin-for-call-center"></a>Configurer un code PIN de remplacement administrateur pour le centre d'appels

Pour configurer un code PIN de remplacement administrateur pour le centre d'appels de Commerce Headquarters, procédez comme suit.

1. Accédez à **Vente au détail et commerce \> Configuration des canaux \> Configuration du centre d'appels**, ou recherchez "Ignorer les autorisations".
1. Sélectionnez le rôle pour lequel autoriser les autorisations de traitement de remboursement non liées.
1. Dans le raccourci **Retours**, définissez l’option **Autoriser un autre paiement** sur **Oui**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Dynamics 365 Payment Connector pour Adyen](adyen-connector.md)

[Remboursements liés aux transactions précédemment approuvées et confirmées](linked-refunds.md)
