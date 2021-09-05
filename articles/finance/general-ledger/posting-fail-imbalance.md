---
title: Échec de validation du journal en raison de déséquilibres
description: Cette rubrique explique pourquoi les débits et les crédits peuvent ne pas être équilibrés dans les pièces comptables, de sorte que les transactions ne peuvent pas être validées. La rubrique comprend également des étapes pour résoudre le problème.
author: kweekley
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-8-03
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a59724ff698b6ad0e84b0642240da5f8953ab3d1
ms.sourcegitcommit: 9642494da87c0d237f9fcbe15df14315d9e88fa2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/15/2021
ms.locfileid: "7385721"
---
# <a name="journal-posting-failure-because-of-imbalance"></a>Échec de validation du journal en raison de déséquilibres

[!include [banner](../includes/banner.md)]

Cette rubrique explique pourquoi les débits et les crédits peuvent ne pas être équilibrés dans les pièces comptables, de sorte que les transactions ne peuvent pas être validées. La rubrique comprend également des étapes pour résoudre le problème.

## <a name="symptom"></a>Problème

Dans certains cas, un journal ne peut pas être validé et le message suivant s'affiche : "Les transactions sur un document spécifique ne sont pas équilibrées à une certaine date (devise comptable : 0,01 - devise de déclaration : 0,06)." Pourquoi le journal ne peut-il pas être validé ?

## <a name="resolution"></a>Résolution

Lors de la validation dans la comptabilité, chaque document doit être équilibré dans la devise de transaction, la devise comptable et la devise de déclaration, si ces devises sont définies sur la page **Configuration de la comptabilité**. (Les justificatifs sont équilibrés lorsque le total des débits est égal au total des crédits.)

Au bas de la page des lignes de journal, les totaux sont affichés dans la devise comptable et la devise de déclaration. Ils ne sont **pas** affichés dans la devise de transaction pour les transactions en devises étrangères. De plus, le message d'erreur que les utilisateurs reçoivent lors de la simulation ou de la validation indique les différences uniquement dans la devise comptable et la devise de déclaration. Il ne les affiche pas dans la devise de la transaction, car un même document peut avoir plusieurs devises de transaction et le journal peut inclure des documents dans différentes devises de transaction. Par conséquent, il est important de vérifier pour chaque document que les montants dans la devise de transaction sont équilibrés.

### <a name="transaction-currency"></a>Devise de la transaction

Lors de la simulation et de la validation, le système vérifie que chaque document est équilibré dans la devise de transaction. Pour chaque document saisi, il peut y avoir une ou plusieurs devises pour la devise de transaction. Par exemple, une pièce justificative saisie dans le journal des opérations diverses peut avoir deux devises de transaction lorsque des espèces sont transférées d'un compte bancaire utilisant des euros (EUR) vers un compte bancaire utilisant des dollars canadiens (CAD).

Si un document n'a qu'une seule devise de transaction, le total des débits doit être égal au total des crédits pour ce document. Les clients ont rencontré les scénarios suivants où la validation a logiquement échoué car les montants en devise de transaction n'étaient pas équilibrés :

- Le total des débits et le total des crédits n'étaient **pas** équilibrés dans la devise de transaction, mais ils étaient équilibrés pour la devise comptable et la devise de déclaration. Un client a supposé que le document serait quand même validé. Cependant, cette supposition était incorrecte. **Les montants en devise de transaction sur un document doivent toujours être équilibrés lorsque toutes les lignes du document ont la même devise.**
- Le document a été importé via Microsoft Excel, et l'utilisateur pensait que les montants en devise de transaction étaient équilibrés. Dans le classeur Excel, les montants importés étaient définis comme valeurs **Numériques** et non comme valeurs **Monétaires**. Dans ce scénario, les montants numériques du classeur comportaient plus de deux décimales et plus de deux décimales étaient incluses lors de l'importation des montants. Par conséquent, les débits n'étaient pas égaux aux crédits, car ils étaient décalés d'une fraction de centime. Le journal ne reflétait pas cette différence sur les lignes du document, car les montants qui sont affichés n'ont que deux décimales.
- Le document a été importé via Excel, et l'utilisateur pensait que les montants en devise de transaction étaient équilibrés. Bien que le document ait été équilibré, certaines lignes du document avaient des dates de transaction différentes. Si vous ajoutiez le total des débits et le total des crédits par document et date de transaction, ils n'étaient pas équilibrés. Le système empêche maintenant ce scénario. Un document ne peut avoir qu'une seule date de transaction. Cette exigence est appliquée lorsque vous saisissez un document via le journal des opérations diverses dans le système. Cependant, il n'était pas appliqué à l'origine lorsqu'un document était importé via Excel.

Dans un scénario pris en charge, un document peut avoir plusieurs devises de transaction. Dans ce cas, le système ne vérifie **pas** que les débits sont égaux aux crédits dans la devise de transaction, car les devises ne correspondent pas. Au lieu de cela, le système vérifie que les montants en devise comptable sont équilibrés.

### <a name="accounting-currency"></a>Devise comptable

Si toutes les lignes d'un document ont la même devise de transaction et si les montants en devise de transaction sont équilibrés, le système vérifie que les montants en devise comptable sont équilibrés. Si le document est saisi dans une devise étrangère, le taux de change sur les lignes du document est utilisé pour convertir les montants en devise de transaction dans la devise comptable. Tout d'abord, chaque ligne du document est convertie. Ensuite, les lignes sont additionnées pour déterminer le total des débits et le total des crédits. Étant donné que chaque ligne est convertie, le total des débits et le total des crédits peuvent ne pas être équilibrés. Néanmoins, si la différence entre dans la valeur **Différence minime maximale** définie sur la page **Paramètres de Comptabilité**, le document sera validé et la différence sera automatiquement enregistrée sur le compte pour la différence minime.

Si le document comporte plusieurs devises de transaction, chaque ligne du document est convertie dans la devise comptable, puis les lignes sont additionnées pour déterminer le total des débits et des crédits. Pour être considérés comme équilibrés, les débits et les crédits doivent être équilibrés et il ne doit pas y avoir de différence d'arrondi minime.

### <a name="reporting-currency"></a>Devise de déclaration

Si toutes les lignes d'un document ont la même devise de transaction et si les montants en devise de transaction sont équilibrés, le système vérifie que les montants en devise de déclaration sont équilibrés. Si le document est saisi dans une devise étrangère, le taux de change sur les lignes du document est utilisé pour convertir les montants en devise de transaction dans la devise de déclaration. Tout d'abord, chaque ligne du document est convertie. Ensuite, les lignes sont additionnées pour déterminer le total des débits et le total des crédits. Étant donné que chaque ligne est convertie, le total des débits et le total des crédits peuvent ne pas être équilibrés. Néanmoins, si la différence entre dans la valeur **Arrondi maximal dans la devise de déclaration** définie sur la page **Paramètres de Comptabilité**, le document sera validé et la différence sera automatiquement enregistrée sur le compte pour la différence minime.

Si le document comporte plusieurs devises de transaction, chaque ligne du document est convertie dans la devise de déclaration, puis les lignes sont additionnées pour déterminer le total des débits et des crédits. Pour être considérés comme équilibrés, les débits et les crédits doivent être équilibrés et il ne doit pas y avoir de différence d'arrondi minime.
