---
title: Configurer des comptes de validation de baux
description: Cette rubrique répertorie les comptes de validation requis pour les transactions de location d’actifs et explique comment définir des comptes de validation sur la page Paramètres de validation de location.
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
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 183560dca385d618eb11d1580b0f82dcaa50474e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249603"
---
# <a name="set-up-lease-posting-accounts"></a>Configurer des comptes de validation de baux

[!include [banner](../includes/banner.md)]

Cette rubrique répertorie les comptes de validation requis pour les transactions de location d’actifs et explique comment définir des comptes de validation sur la page **Paramètres de validation de location**.

Pour vous conformer à l’article 842 sur la codification des normes comptables (ASC 842) et la norme internationale en matière de génération des états financiers 16 (IFRS 16), vous devrez peut-être créer des comptes dans votre plan comptable. Cependant, tous les comptes que vous créez pour vous conformer aux normes ASC et IFRS ne sont pas des comptes d’immobilisations. En vertu de l’ASC 842, un droit d’utilisation de l’actif est comptabilisé à la fois pour les contrats de location-financement et de location simple. Ces contrats de location sont séparés des immobilisations. (Vous pouvez toujours gérer un droit d’utilisation de l’actif en utilisant des immobilisations.)

Pour plus d’informations sur la création de vos structures de compte, consultez [Créer les structures de compte](../general-ledger/tasks/create-account-structures.md). Pour plus d’informations sur la création d’un compte principal, consultez [Créer un compte principal](../general-ledger/tasks/create-main-account.md).

Le tableau suivant présente des exemples de comptes que vous devez créer pour les transactions d’actif loué, s’ils n’ont pas déjà été créés. Selon IFRS 16, les contrats de location simple sont toujours utilisés pour les contrats de location de faible valeur et à court terme.

| Numéro de compte général | Type de compte  | Intitulé du compte                                          |
|-----------------------|---------------|-------------------------------------------------------|
| 180150                | Actif         | Droit d’utilisation de l’actif du véhicule                                     |
| 180160                | Actif         | Droit d’utilisation de l’actif Bâtiment                                    |
| 180250                | Actif         | Dépense d’amortissement – véhicules                   |
| 180260                | Actif         | Dépense d’amortissement – Bâtiments                  |
| 222300                | Passif     | Obligation à court terme – contrats de location-financement                |
| 222310                | Bilan | Obligation à court terme – locations simples              |
| 250200                | Passif     | Effets à payer                                         |
| 250601                | Bilan | Obligation à long terme – contrats de location-financement                 |
| 250602                | Bilan | Obligation à long terme – locations simples               |
| 250606                | Bilan | Loyer reporté                                         |
| 300160                | Bilan | Bénéfices non répartis                                     |
| 604500                | Dépense       | Dépense de bail                                         |
| 604501                | Dépense       | Frais de location simple de véhicule – augmentation des intérêts  |
| 604502                | Dépense       | Frais de location simple de véhicule – amortissement        |
| 605200                | Dépense       | Frais de location simple de bâtiment – augmentation des intérêts |
| 605201                | Dépense       | Frais de location simple de bâtiment – amortissement       |
| 607101                | Dépense       | Frais d’amortissement de location de véhicule                    |
| 607102                | Dépense       | Frais d’amortissement de location de bâtiment                   |
| 607103                | Dépense       | Charges de dépréciation – contrats de location-financement                   |
| 607104                | Dépense       | Charges de dépréciation – locations simples                 |
| 618910                | Dépense       | Charges de location – contrats de location-financement                        |
| 618920                | Dépense       | Paiements variables – contrats de location-financement                    |
| 618930                | Dépense       | Paiements variables – contrats de location simple                  |
| 800600                | Dépense       | Charges d’intérêts de location de véhicule                        |
| 800601                | Dépense       | Charges d’intérêts de location de bâtiment                       |
| 801201                | Bilan | Profit/perte suite – modification du bail                      |

## <a name="configure-posting-accounts"></a>Configurer des comptes de validation

Pour affecter des comptes aux registres et groupes de location qui ont été créés, vous devez configurer des paramètres pour la location d’actifs.

1. Accédez à **Location d’actifs \> Configuration \> Paramètres de validations de baux**.
2. Sur l’onglet **Comptes**, ouvrez le raccourci **Comptes de location**. Déterminer les comptes principaux des contrats de location-financement et d’exploitation aux **Type de publication** correspondant. Le tableau précédent présente les comptes relatifs aux contrats de location simple et de location-financement.

    > [!NOTE]
    > Cette étape nécessite que vous configuriez des comptes séparés pour les contrats de location simple et de location-financement pour chaque type d’écriture, sauf **Compensation des frais de location** et **Augmentation/diminution du bail**. Les entreprises qui adhèrent au cadre comptable IFRS 16 doivent ajouter un compte principal pour la location simple. Mais le système n’utilisera pas ce compte même s’il s’agit d’un champ obligatoire, car tous les contrats de location selon l’IFRS 16 sont classés comme contrats de location-financement.
    >[!NOTE]
    > **Augmentation/diminution du bail** sera utilisé comme type de validation pour des considérations relatives aux actifs supplémentaires, notamment **Coût direct initial, primes de location, paiements anticipés de location et coûts de démantèlement**, mais publiez sur le compte principal du droit d’utilisation de l’actif qui est par défaut **Actif de location**.        
    
3. Pour sélectionner un groupe de location spécifique correspondant au compte principal, dans le champ **Code de compte**, sélectionnez **Groupe**. Puis, dans le champ **Numéro de compte/groupe**, sélectionnez le groupe de baux à affecter au compte principal.
4. Pour affecter des codes compte aux coûts administratifs qui ont été configurés dans le système, sur le raccourci **Frais accessoires**, dans le champ **Type de dépense**, sélectionnez une dépense. Attribuez ensuite les comptes financiers et d’exploitation à utiliser pour chaque registre.

    > [!NOTE]
    > Le compte financier ou opérationnel sélectionné sera débité lors de la validation de la facture des dépenses prévues.
    > **Compensation des frais de location** sera utilisé comme type de comptabilisation pour les transactions de frais accessoires mais validé sur le **Compte de compensation** défini dans les **Lignes de échéancier de paiement des coûts exécutoires** dans les détails du bail ou le formulaire de registre de location.   


[!INCLUDE[footer-include](../../includes/footer-banner.md)]