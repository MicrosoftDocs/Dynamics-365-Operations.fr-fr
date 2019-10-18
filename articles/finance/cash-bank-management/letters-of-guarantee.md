---
title: Lettres de garantie
description: Cet article fournit des informations sur les lettres de garantie. Dans une lettre de garantie, une banque s'engage à payer une somme d'argent spécifique à une personne si l'un des clients de la banque ne règle pas un paiement ou une obligation au bénéficiaire.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankLGGuarantee
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 18291
ms.assetid: 5c0b5e37-d51d-4a01-bb37-1882173abb9f
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e7ab2e66c378388d002d2f2090f89bf6c96dac2
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177748"
---
# <a name="letters-of-guarantee"></a>Lettres de garantie

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur les lettres de garantie. Dans une lettre de garantie, une banque s'engage à payer une somme d'argent spécifique à une personne si l'un des clients de la banque ne règle pas un paiement ou une obligation au bénéficiaire. 

Une lettre de garantie représente l'accord d'une banque (le garant) de payer une somme d'argent définie à une autre personne (le bénéficiaire) si un client de la banque (le donneur d'ordre) ne règle pas un paiement ou une obligation au bénéficiaire. Les lettres de garantie ne sont pas cessibles. Elles ne s'appliquent qu'au bénéficiaire nommé dans l'accord. Le donneur d'ordre peut demander l'augmentation ou la diminution de la valeur d'une lettre de garantie, sous réserve des conditions stipulées dans l'accord. 

Pour liquider une lettre de garantie, le bénéficiaire doit soumettre la lettre de garantie originale et informer la banque du défaut de paiement de la part du donneur d'ordre avant la date d'expiration. La banque paie ensuite la somme due sur le compte du bénéficiaire, comme convenu dans les conditions de la lettre de garantie. En guise de marge, elle se réserve un pourcentage du paiement. Le pourcentage est déterminé et spécifié dans les termes de l'accord. 

Vous pouvez créer un code pour effectuer le suivi de l'objet d'une lettre de garantie. Vous pouvez également mentionner les motifs qui peuvent être associés à une lettre de garantie lors de l'annulation de cette dernière. Vous pouvez afficher les codes objet et les motifs de banque sur la page **Codes objet de paiement** et **Motifs de banque**. 

Vous pouvez utiliser la page **Lettre de garantie** pour effectuer les tâches suivantes :

-   créer des écritures comptables correctes et éliminer les entrées manuelles ;
-   enregistrer toutes les transactions monétaires et non monétaires et effectuer le suivi des soldes de la lettre de garantie ;
-   enregistrer et effectuer le suivi du statut et de l'expiration des lettres de garantie ;
-   générer un état qui répertorie les banques détentrices de lettres de garantie.

Le tableau suivant décrit les actions que vous pouvez effectuer sur une mettre de garantie.

| Action              | Objectif                                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------|
| Remettre à la banque      | Cette action permet de soumettre la demande de lettre de garantie à la banque.                                                                       |
| Recevoir de la banque   | Dès que la banque a approuvé la demande soumise, cette action permet de récupérer la lettre de garantie auprès de la banque.                            |
| Remettre au bénéficiaire | Après avoir reçu la lettre de garantie de la banque, cette action permet de la remettre au bénéficiaire.              |
| Augmenter la valeur      | Si le bénéficiaire ainsi que le donneur d'ordre approuvent, cette action permet d'augmenter la valeur monétaire.                                                  |
| Diminuer la valeur      | Si le bénéficiaire ainsi que le donneur d'ordre approuvent, cette action permet de diminuer la valeur monétaire.                                                  |
| Étendre              | Après avoir remis la lettre de garantie au bénéficiaire, cette action permet d'étendre la période de validité si nécessaire. |
| Annuler              | Lorsque l'objet pour lequel la lettre de garantie a été demandée ne s'applique plus, cette action permet d'annuler l'accord.                  |
| Liquider           | Lorsque le bénéficiaire présente la lettre de garantie à la banque, cette action permet d'effectuer le décaissement de la lettre.                      |


Pour plus d'informations, voir les rubriques suivantes :

[Transaction de lettre de garantie](tasks/letter-guarantee-transaction.md)

[Paramétrer les établissements bancaires et les profils de validation pour les lettres de garantie](tasks/set-up-bank-facilities-posting-profiles.md)


