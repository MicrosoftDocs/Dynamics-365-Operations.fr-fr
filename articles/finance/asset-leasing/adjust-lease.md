---
title: Ajuster les baux
description: La rubrique explique comment ajuster un bail. Un ajustement peut être nécessaire si les conditions du bail sont modifiées, si le bail est prolongé ou si d’autres circonstances changent.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9d1c6e20e72fb2816c32e71e8921a94724ae5656
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4443384"
---
# <a name="adjust-leases"></a>Ajuster les baux

[!include [banner](../includes/banner.md)]

La rubrique explique comment ajuster un bail. Un ajustement peut être nécessaire si les conditions du bail sont modifiées, si le bail est prolongé ou si d’autres circonstances changent. La location d’actifs est conforme aux directives fournies par l’article 842 sur la codification des normes comptables (ASC 842) et la norme internationale en matière de génération des états financiers 16 (IFRS 16) concernant les modifications des baux. ASC 842-20-15-1 définit une modification de bail comme toute modification des termes et conditions d’un contrat qui entraîne une modification de la portée ou de la prise en compte d’un bail. Le paragraphe 39 d’IFRS 16 indique qu’un locataire doit réévaluer le passif locatif afin qu’il reflète les modifications des paiements de location.

Pour les organisations qui respectent l’ASC 842 ou l’IFRS 16, un bail est réévalué pour refléter une modification de la valeur actuelle des paiements minimaux de location minimums à venir (PVFMLP). Si la PVFMLP augmente, l’écriture de journal créée est un débit au droit d’utilisation de l’actif et un crédit au passif locatif pour la différence entre la nouvelle PVFMLP et la précédente PVFMLP. Si la PVFMLP diminue, l’écriture de journal est un débit au passif locatif et un crédit au droit d’utilisation de l’actif pour la différence.

Si l’ajustement diminue le droit d’utilisation de l’actif au-delà de 0 (zéro), le reste est crédité au gain sur le compte de validation des modifications du bail spécifié sur la page **Comptes de validation de bail**. Le système comptabilise ces transactions et d’autres écritures d’ajustement, telles que les changements de classification, les coûts directs initiaux, les incitations à la location, les acomptes et les coûts de démantèlement qui résultent des modifications de location.

Pour obtenir des indications spécifiques sur les transactions d’ajustement de bail, nous vous recommandons de consulter IFRS 16 et ASC 842.

Pour ajuster un bail, procédez comme suit. Les données modifiées mettent à jour les échéanciers de bail après l’exécution de création d’un échéancier.

1. Accédez à **Location d’actifs \> Baux \> Récapitulatif du bail**.
2. Sur la page **Récapitulatif du bail**, sélectionnez le bail à ajuster, puis sélectionnez **Ajuster le bail**.
3. Sur la page **Ajuster le bail**, entrez les nouvelles informations pour le bail ajusté.

    Notez que la page **Ajuster le bail** ressemble à la page **Ajouter un bail**. De plus, tout comme la date de début que vous spécifiez lorsque vous ajoutez un bail détermine le moment où le nouveau bail commence, le champ **Date de modification** sur la page **Ajuster le bail** détermine le début du bail modifié. Cette date ne peut pas être postérieure à la date de début des échéances de paiement.

    > [!NOTE]
    > Les champs **Considérations du droit d’utilisation** s’appliquent à l’ajustement du bail. Si aucun coût direct initial, aucune incitation à la location, aucun paiement anticipé ou aucun coût de démantèlement n’est associé au bail modifié, vous devez laisser ces champs vides. Les montants d’origine ne s’appliqueront pas au bail mis à jour. Tous les frais supplémentaires encourus lors de la modification du bail doivent être inscrits sur la page **Ajuster le bail**.
    > 
    > Par exemple, un bailleur offre une incitation de 1 000 $ pour accepter une prolongation du bail. Dans ce cas, lorsque vous ajustez le bail pour tenir compte de l’extension, vous entrez **1 000** dans le champ **Incitations à la location**. Si aucune incitation n’est associée à l’ajustement du bail, vous devez effacer toute valeur précédemment saisie dans ce champ. La même logique est appliquée à d’autres considérations du droit d’utilisation.

    Les échéanciers de paiement du bail ajusté doivent être créés sur une base prospective. Les échéanciers de paiement créés sur une base prospective ne peuvent pas démarrer avant que les modifications du bail entrent en vigueur.

    Les étapes suivantes sont presque identiques aux étapes de comptabilisation initiale d’un bail.

4. Sélectionnez **Créer des échéanciers** pour générer l’échéancier de paiement ajusté. Vous recevez un message indiquant que l’échéancier de paiement a été créé pour le bail.

    > [!IMPORTANT]
    > Avant de sélectionner **Créer des échéanciers**, veillez à ce que la date de modification et les échéanciers de paiement soient exacts. Veillez également à ce que tous les coûts directs initiaux, les incitations à la location, les paiements anticipés ou les coûts de démantèlement correspondent uniquement aux coûts résultant de l’ajustement.

5. Pour afficher l’échéancier de paiement récemment créé, sélectionnez **Registres**, et ouvrez la page **Échéancier de paiement**.
6. Sur la page **Échéancier de paiement**, vous pouvez modifier les montants de paiement ajustés avant de confirmer l’échéancier de paiement. Pour confirmer l’échéancier, sélectionnez **Confirmer l’échéancier**.

    Lorsque l’échéancier de paiement est confirmé, le nouvel amortissement des immobilisations et les nouveaux échéanciers de passif locatif sont créés.

7. Pour afficher le nouvel échéancier d’amortissement du passif locatif généré à partir des nouvelles entrées, fermez la page **Échéancier de paiement** et ouvrez la page **Programme d’amortissement du passif**.
8. Pour afficher le nouvel échéancier d’amortissement des actifs, ouvrez la page **Programmes d’amortissement des actifs** de la page **Détails des registres**.
9. Pour générer l’entrée de journal d’ajustement, sélectionnez **Fonction \> Ajustement de bail**. Vous recevez un message indiquant que l’entrée de journal d’ajustement a été créée. 
10. Pour afficher l’entrée de journal, sélectionnez **Journaux \> Journal de location d’actifs**.
11. Pour valider l’écriture de journal, sélectionnez la ligne, puis sélectionnez **Valider**.

## <a name="view-lease-versions"></a>Voir les versions de bail

Si un bail a été modifié, vous pouvez en afficher les différentes versions. Vous pouvez également voir les échéanciers historiques et les détails des baux passés.

1. Sur la page **Récapitulatif du bail**, sélectionnez le bail à copier, puis, dans le volet Actions, sélectionnez **Historique de version des baux**.

    Si le bail sélectionné a été ajusté, la page **Historique de version des baux** montre les différentes versions de celui-ci. Le bail d’origine est étiqueté **1** et les versions ultérieures ont un ordre numérique croissant.

    Pour une version de location sélectionnée, vous pouvez afficher les dimensions financières, les détails du contrat, l’emplacement et les échéances de paiement.

2. Pour afficher les horaires historiques, ouvrez le bail modifié à partir de la page **Récapitulatif du bail**, sélectionnez le livre souhaité, puis, dans le volet Actions, sélectionnez **Historique de version des baux**.
3. Sur la page **Version des registres**, sélectionnez la version souhaitée et l’échéance souhaitée à afficher.
