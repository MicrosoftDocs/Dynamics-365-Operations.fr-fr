---
title: Ajout d’informations sur la gestion du crédit pour des clients
description: Cette rubrique explique comment ajouter des informations de gestion de crédit pour un client.
author: JodiChristiansen
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3c8584c33b4f77b6d1f5a4dc0d62208b76b3ffa3
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/05/2021
ms.locfileid: "7753968"
---
# <a name="add-credit-management-information-for-customers"></a>Ajout d’informations sur la gestion du crédit pour des clients

[!include [banner](../includes/banner.md)]

Après avoir configuré les paramètres qui contrôlent la gestion des crédits, vous pouvez ajouter plus de détails pour chaque client. Ces détails contrôlent les processus de gestion du crédit et fournissent également des informations supplémentaires qui aident les membres de l’équipe de recouvrement à gérer les clients.

## <a name="customer-information"></a>Informations client

Vous povuez ajouter les détails du client dans le raccourci **Crédit et relances** de la page **Tous les clients** (**Comptabilité fournisseur \> Clients \> Tous les clients**).

1. Paramétrez l’option **Limite de crédit illimitée** sur **Oui** si le client ne doit pas être limité par des tests de limite de crédit.
2. Paramétrez l’option **Exclure de la gestion du crédit** sur **Oui** pour exclure le client de toutes les actions qui se produisent généralement au cours des processus de gestion de crédit.
3. Sélectionnez le groupe de gestion des crédits pour le client.
4. Pour calculer la limite de crédit dans la devise du client, dans le champ **Limite de crédit dans la devise du client**, entrez la limite de crédit du client. La limite de crédit dans la devise de l’entreprise sera convertie en utilisant les taux de change définis par le type de taux de change de limite de crédit sélectionné dans les paramètres de gestion de crédit.
5. Dans le champ **Date du dernier examen**, entrez la date à laquelle la limite de crédit du client a été révisée pour la dernière fois par un gestionnaire de crédit.
6. Dans le champ **Prochaine date d’examen prévue**, entrez la date à laquelle le client doit effectuer une révision et une mise à jour du crédit.
7. Dans le champ **Limite de crédit éligible**, entrez la limite de crédit la plus élevée qui peut être attribuée au client, en fonction de votre examen de l’historique de crédit de ce client. La limite de crédit éligible peut différer de la limite de crédit indiquée sur le raccourci **Crédit et recouvrements**.
8. Dans le champ **Devise de limite de crédit éligible**, entrez la devise de la limite de crédit éligible.
9. Dans le champ **Date de limite de crédit éligible**, entrez la date de créartion de la limite de crédit éligible.
10. Dans le champ **Statut du compte de crédit**, entrez le statut du compte de crédit du client.
11. Dans le champ **Motif du statut**, entrez le motif associé au statut du compte.
12. Paramétrez l’option **Avec agence** sur **Oui** pour indiquer que le client est actuellement affecté à une agence de crédit. Cette valeur est fournie uniquement à titre indicatif. Il n’est utilisé dans aucun processus de gestion de crédit.
13. Paramétrez l’option **Titre détenu** sur **Oui** pour indiquer qu’un titre est détenu pour l’entreprise. Cette valeur est fournie uniquement à titre indicatif. Il n’est utilisé dans aucun processus de gestion de crédit.
14. Dans le champ **Date de création de l’entreprise**, entrez la date de début d’activité du client. Ces informations sont utilisées lors de la création des scores de risque.
15. Dans le champ **Client depuis**, entrez la date à laquelle les premières transactions ont été traitées pour le client. Ces informations sont utilisées lors de la création des scores de risque.
16. Entrez des notes que l’équipe de crédit peut utiliser pour évaluer davantage la solvabilité du client.

Notez que certaines des informations affichées dans la page **Client** sont créées par un autre processus :

- Le champ **Date d’expiration de limite de crédit** indique date d’expiration de la limite de crédit. Si vous ne définissez pas ce champ, la limite de crédit du client n’expirera pas.
- Le champ **Date de limite de crédit** indique date de création de la limite de crédit. Ce champ est mis à jour chaque fois que la limite de crédit est ajustée.
- Les limites de crédit temporaires remplacent la limite de crédit d’un client pour une période. Elles sont utilisées à la place de la limite de crédit pour calculer la limite de crédit totale. Ces informations ne s’affichent que s’il existe une limite de crédit active. Vous pouvez ajouter des limites de crédit temporaires via des ajustements de limite de crédit.
- Le champ **Assurances et garanties** affiche la valeur totale de l’assurance et des garanties qui peuvent augmenter la limite de crédit pour le client.
- Le champ **Limite de crédit totale** indique la limite de crédit finale pour le client. La limite de crédit totale comprend les assurances et les garanties, ainsi que les limites de crédit temporaires.

## <a name="temporary-credit-limits"></a>Limites de crédit temporaires

Les limites de crédit temporaires remplacent les limites de crédit d’un client pour une période définie. Vous pouvez ajouter des limites de crédit temporaires en utilisant des ajustements de limite de crédit. Les ajustements de limite de crédit permettent aux gestionnaires de crédit de mettre à jour les limites de crédit et les dates d’expiration d’un seul client, d’un groupe de clients ou de tous les clients via un processus de validation.

Vous pouvez créer des entrées d’ajustement de limite de crédit à la page **Ajustements de limite de crédit** (**Gestion de crédit \> Ajustements de limite de crédit \> Ajustements de limite de crédit**).

## <a name="create-insurance-policies-and-guarantees"></a>Créer des polices d’assurance et des garanties

Vous pouvez créer une ou plusieurs polices d’assurance et garanties pour chaque client. Vous pouvez ensuite les utiliser pour calculer l’exposition de votre entreprise lorsqu’elle offre du crédit à un client. Les polices d’assurance et les garanties peuvent également être incluses dans la limite de crédit pour un client.

Vous pouvez créer des polices d’assurance et des garanties sur la page **Tous les clients** (**Comptabilité client \> Clients \> Tous les clients**). Sélectionnez un client, puis, dans le volet Actions, sous l’onglet **Gestion de crédit**, sélectionnez **Assurances et garanties**.

> [!NOTE]
> Dans la procédure suivante, vous sélectionnez un assureur ou un garant dans le carnet d’adresses global. Par conséquent, avant de commencer cette procédure, vous devez vous assurer que les assureurs et garants ont été ajoutés au carnet d’adresses global.

1. Dans le champ **Identificateur**, entrez **Garantie** ou **Assurance**.
2. Dans le champ **Type de garantie/assurance**, sélectionnez l’un des types de garantie ou d’assurance que vous avez précédemment paramétrés.
3. Dans le champ **Assureur/Garant**, sélectionnez l’assureur ou le garant dans le carnet d’adresses global. 
4. Si vous avez sélectionné **Assurance** dans le champ **Identificateur**, dans le champ **Type de couverture de police**, sélectionnez l’un des types de couverture que vous avez précédemment paramétrés. Vous ne pouvez pas sélectionner un type de couverture de police pour une garantie.
5. Dans le champ **Identification**, entrez l’ID de la police. Cet ID est généralement un numéro de police.
6. Dans le champ **Date d’effet**, entrez la date de début de la police d’assurance ou de la garantie.
7. Dans le champ **Expiration**, entrez la date d’expiration de la police d’assurance ou de la garantie .
8. Dans le champ **Valeur**, entrez la valeur de la police d’assurance ou de la garantie. Cette valeur est la valeur totale de la police.
9. Sélectionnez la devise pour la valeur de police dans le champ **Devise**. 
10. Dans le champ **Mettre à jour la limite de crédit**, spécifiez un pourcentage entre **0** et **100**. Ce pourcentage sera appliqué à la valeur de la police et le montant résultant sera utilisé pour augmenter la limite de crédit utilisée dans les calculs de limite de crédit. La valeur calculée est indiquée sous **Limite de crédit totale, assurance et garanties** sur le raccourci **Crédit et recouvrements** de la page **Clients**.

    Voici un exemple :

    - La limite de crédit (A) est de 100 000.
    - La valeur de police (B) est de 50 000.
    - Le pourcentage **Mettre à jour la limite de crédit** (C) est de 50,00.
    
    Dans ce cas, la limite de crédit effective est de 125 000 (= A + \[B × C\]).

11. Cochez la case **Inclus dans l’exposition** pour réduire la limite de crédit utilisée dans les calculs de limite de crédit de la valeur totale de la police. Si cette case est cochée, la valeur qui est calculée lorsque le pourcentage **Mettre à jour la limite de crédit** est spécifié ne sera pas utilisé dans les calculs de limite de crédit.

    Voici un exemple :

    - La limite de crédit (A) est de 100 000.
    - La valeur de police (B) est de 50 000.
    - Le pourcentage **Mettre à jour la limite de crédit** (C) est de 50,00.

    Dans ce cas, la limite de crédit effective est de 125 000 (= A + \[B × C\]).
    
    Cependant, si vous cochez la case **Inclus dans l’exposition**, la valeur **Mettre à jour la limite de crédit** de 50 000 (= 50,00 % de 100 000) est supprimée et la valeur d’exposition est de 75 000 (= A + \[B × C\] - B).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
