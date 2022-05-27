---
title: Comment configurer les dimensions financières d’équilibrage ?
description: Cette rubrique décrit les options de configuration et d’utilisation de la fonctionnalité Dimension financière d’équilibrage.
author: kweekley
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-08-17
ms.dyn365.ops.version: 10.0.210
ms.openlocfilehash: cb3033a615200a358c1b28b0991bae4b84470ae0
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2022
ms.locfileid: "8720109"
---
# <a name="how-do-i-set-up-balancing-financial-dimensions"></a>Comment configurer les dimensions financières d’équilibrage ?

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les options de configuration et d’utilisation de la fonctionnalité Dimension financière d’équilibrage.

## <a name="symptom"></a>Problème

Il existe deux options pour configurer les dimensions financières d’équilibrage. La première option consiste à utiliser le champ **Dimension financière d’équilibrage** sur la page de configuration **Comptabilité** (**Comptabilité \> Configuration de la comptabilité \> Comptabilité**). La deuxième option consiste à utiliser le champ **Exiger l’équilibrage de la dimension** sur la page **Dimensions financières** (**Comptabilité > Plan comptable \> Dimensions \> Dimensions financières**). Cette rubrique explique la différence entre ces deux options.

## <a name="resolution"></a>Résolution

Les organisations utilisent généralement des dimensions d’équilibrage pour générer un bilan équilibré au niveau de la dimension financière. L’activation de l’une ou l’autre de ces fonctionnalités n’équilibrera pas les dimensions publiées et déséquilibrées. Vous devez d’abord saisir manuellement les écritures de régularisation pour équilibrer le bilan avant d’activer l’une ou l’autre fonctionnalité.

Les deux options sont mutuellement exclusives. L’option utilisée par votre organisation doit être basée sur les besoins de votre entreprise. Nous entendons souvent parler de clients qui définissent la dimension d’équilibrage à la fois dans la configuration de la comptabilité et dans la configuration de la dimension financière, puis effectuent une partie ou la totalité de la configuration supplémentaire requise. Cependant, ils ne peuvent toujours pas valider en raison d’un déséquilibre au niveau de la dimension financière.

Les sections suivantes décrivent les deux options et expliquent comment les configurer.

### <a name="ledger--balancing-financial-dimension"></a>Comptabilité - Dimension financière d’équilibrage

La dimension d’équilibrage sur la page de configuration de la **Comptabilité** sert à activer la comptabilité interunités. Procédez comme suit pour activer la fonctionnalité.

1. Déterminez quelle dimension financière sera la dimension d’équilibrage.

    - Cette fonctionnalité vous permet de sélectionner une seule dimension financière comme dimension d’équilibrage.
    - Ne sélectionnez pas encore la dimension sur la page de configuration de la **Comptabilité**.
    - Assurez-vous que votre bilan est déjà équilibré pour la dimension financière sélectionnée.

2. Mettez à jour la structure de compte pour la dimension financière d’équilibrage.

    - La dimension financière d’équilibrage doit être incluse dans toutes les structures de compte attribuées à la comptabilité.
    - La dimension financière ne doit pas autoriser les blancs dans la structure du compte. Cette restriction garantit que chaque écriture comptable validée en comptabilité contient une valeur de dimension financière. Une dimension vide n’est pas valide lorsque des dimensions d’équilibrage sont utilisées.

3. Sur la page **Comptes pour transactions automatiques** (**Comptabilité \> Paramétrage de la validation \> Comptes pour transactions automatiques**), définissez les comptes principaux de débit et de crédit interunités.
4. Sur la page de configuration de la **Comptabilité** (**Comptabilité \> Paramétrage de la comptabilité \> Comptabilité**), dans le champ **Dimension financière d’équilibrage**, sélectionnez une dimension financière à utiliser pour équilibrage.

Si la dimension financière sélectionnée n’est pas équilibrée lors de la saisie et de la validation des transactions, le système ajoutera automatiquement les écritures de débit ou de crédit nécessaires pour équilibrer l’écriture comptable lors de la validation. Les comptes du grand livre de débit et de crédit pour la transaction inter-unités sont affichés sur la pièce justificative enregistrée en comptabilité. Cependant, ils ne seront pas affichés sur les journaux ou les documents sources pour lesquels les écritures comptables ont été enregistrées.

### <a name="financial-dimensions--require-the-dimension-to-be-balanced"></a>Dimensions financières - Exiger que la dimension soit équilibrée

Bien que la dimension d’équilibrage sur la page **Dimensions financières** soit généralement utilisée par les entreprises du secteur public, la fonctionnalité n’est pas liée à la clé de configuration du secteur public. Parce qu’il n’y a pas de limite dans le système, vous pouvez utiliser cette fonctionnalité même si votre organisation n’est pas une entité du secteur public.

Cette fonctionnalité est généralement utilisée dans la base de clients du secteur public, car elle nécessite que les définitions de validation soient utilisées pour équilibrer automatiquement chaque transaction. Elle n’utilise pas les comptes de débit et de crédit interunités définis sur la page **Comptes pour les transactions automatiques** pour équilibrer automatiquement les écritures comptables. Si une écriture comptable n’est pas équilibrée au niveau de la dimension après l’application des définitions de validation, la transaction ne sera pas validée, même si les comptes de débit et de crédit interunités sont définis.

Nous entendons souvent parler de clients qui définissent la dimension d’équilibrage à la fois dans la configuration de la comptabilité et dans la configuration de la dimension financière. Dans ce cas, le système utilise la fonctionnalité de dimensions financières. Le paramétrage des dimensions d’équilibrage au niveau de la dimension financière est prioritaire lors de la validation. La validation échouera si la définition de validation ne crée pas une entrée comptable équilibrée au niveau de la dimension financière.

Suivez ces étapes pour activer l’utilisation d’une dimension d’équilibrage au niveau de la dimension financière.

1. Déterminez quelles dimensions financières seront les dimensions d’équilibrage.

    - Vous pouvez définir plusieurs dimensions financières comme dimension d’équilibrage.
    - Ne définissez pas encore les dimensions financières qui seront nécessaires pour équilibrer une transaction sur la page **Dimensions financières**.

2. Définissez les définitions de validation pour chaque type de journal ou de document source utilisé par votre organisation. Les définitions de validation utilisent les comptes de comptabilité d’un journal ou d’un document source non validé en tant que « critères de correspondance ». La définition de validation renvoie alors les « écritures générées » qui deviennent l’écriture comptable. Si la définition de validation est correctement configurée, l’écriture générée inclut les comptes de comptabilité des critères de correspondance, ainsi que des comptes supplémentaires pour équilibrer l’écriture comptable au niveau de la dimension. Pour plus d’informations, voir [Définitions de validation](posting-definitions.md). 
   
   Les définitions de validation ne sont pas prises en charge pour tous les types de transaction. Par exemple, les définitions de validation ne peuvent pas être définies pour les transactions saisies via le journal des opérations diverses ou le journal des immobilisations. Si une définition de validation ne peut pas être définie pour un journal ou un document source, la transaction doit être équilibrée manuellement à la valeur de la dimension financière. Par exemple, si une écriture au journal des opérations diverses est effectuée et que la dimension Service est la dimension d’équilibrage, vous devez vous assurer que chaque valeur de service est équilibrée.  Si la dimension n’est pas équilibrée pour chaque valeur de service, le document ne sera pas validé tant que le déséquilibre n’est pas corrigé en ajoutant manuellement un débit ou un crédit interunité au document. 

    > [!IMPORTANT]
    > Si un nombre excessif de transactions doit être soldé manuellement, vous ne devez **pas** utiliser la fonctionnalité de dimension d’équilibrage sur la page **Dimensions financières**. À la place, utilisez la fonctionnalité de dimension d’équilibrage sur la page de configuration de la **Comptabilité**.

3. Une fois les définitions de validation définies, les dimensions financières peuvent être marquées comme requises pour l’équilibrage.

Au fur et à mesure que vous saisissez et validez des transactions, les définitions de validation sont appelées pendant la validation pour déterminer les écritures comptables. Si les dimensions financières sont équilibrées, la validation intervient après la détermination des écritures comptables. Si les dimensions financières ne sont pas équilibrées, la transaction ne sera pas validée et vous recevrez un message indiquant que les débits ne correspondent pas aux crédits pour une dimension spécifique.
