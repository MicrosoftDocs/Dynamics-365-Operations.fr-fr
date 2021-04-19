---
title: Conditions de répartition
description: Cette rubrique fournit des informations sur l’utilisation des conditions de répartition sur un compte principal.
author: rachel-profitt
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount, AllocationTerms
audience: Application User
ms.reviewer: roschlom
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-06-15
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5735cbdd4c8b137d01a56be0009b60d32c21e94e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823666"
---
# <a name="allocation-terms"></a>Conditions de répartition

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur l’utilisation des conditions de répartition sur un compte principal. Les conditions de répartition permettent de répartir des montants entre plusieurs combinaisons de comptes généraux. Elles aident à garantir que les dépenses ou les revenus sont imputés à l’objet approprié dans la comptabilité.

Chaque condition de répartition que vous créez sur un compte principal définit le pourcentage d’un N° document à répartir à partir d’un compte principal à source unique et d’une combinaison de dimensions financières. En outre, vous définissez le compte principal de destination et les dimensions financières sur lesquels le montant va être réparti. 

Lorsque vous définissez la dimension financière source pour la répartition, vous pouvez sélectionner si chaque dimension est spécifique ou non. Spécifique indique que la dimension financière de la transaction source doit correspondre à la dimension sélectionnée. Lorsque vous sélectionnez Non spécifique, cela indique que toute valeur de la dimension financière peut contribuer à une correspondance.

Lorsque vous définissez le compte général de destination pour une condition de répartition, vous devez spécifier le compte principal sur lequel vous répartissez le montant. Vous pouvez utiliser le même compte principal que pour la validation de la transaction source, ou un autre compte principal. Si le même compte principal est utilisé, un avertissement s’affiche lors de la sauvegarde de l’enregistrement. En plus de spécifier le compte principal, vous devez également spécifier les dimensions de destination. Pour chaque dimension, vous pouvez spécifier si vous souhaitez conserver la valeur de la dimension financière source ou la modifier. Si vous sélectionnez Non, vous devez sélectionner une nouvelle valeur pour la dimension financière. Si vous sélectionnez Oui, aucune information supplémentaire n’est spécifiée et le système va conserver les dimensions financières d’origine lors de la validation.

Il n’y a pas de limite au nombre de conditions de répartition que vous pouvez ajouter à un compte principal ; cependant, la somme des pourcentages à répartir sur une condition d’allocation ne peut pas dépasser 100. Vous pouvez créer des répartitions pour moins de 100 % si une partie du montant du N° document d’origine doit rester dans les dimensions financières source. Des conditions de répartition peuvent être ajoutées à un compte principal en tant que remplacement d’entité juridique. Si vous utilisez un plan comptable partagé, les conditions de répartition doivent être définies pour chaque entité juridique. Pour accéder au bouton **Conditions de répartition**, vous devez d’abord activer la case à cocher **Répartition** dans la section Remplacement d’entité juridique.

## <a name="allocation-term-example"></a>Exemple de condition de répartition
Vous avez défini un centre de coût pour votre organisation appelé ENTREPRISE qui est numéroté 000. Lorsque des factures sont validées pour les dépenses fonctionnelles, elles sont codées dans ce centre de coût ENTREPRISE. Votre société a défini une règle selon laquelle toutes les dépenses fonctionnelles doivent être réparties selon un pourcentage sur chacun des centres de coût individuels. Les autres dimensions financières du département et de l’unité commerciale restent les mêmes.

Avec cet exemple, une nouvelle condition de répartition est créée pour le compte principal des dépenses fonctionnelles. Une ligne est créée pour chaque centre de coût avec le pourcentage à répartir. Le champ **Critères de sélection** des dimensions financières source pour chaque ligne est **Spécifique** pour le **Centre de coût** et la valeur est définie sur 000 : ENTREPRISE. Pour le département et l’unité commerciale, le champ **Critères de sélection** est **Non spécifique**.

Dans l’organisateur **Compte général de destination**, le compte principal est le même que le compte des dépenses fonctionnelles et l’option **Conserver les dimensions financières source** est définie sur **Oui** pour **Unité commerciale** et **Département**. L’option **Conserver les dimensions financières source** est définie sur **Non** pour **Centre de coût**, et la valeur sélectionnée correspond à chaque centre de coût respectif sur lequel vous répartissez le montant. S’il existe trois centres de coût pour la répartition, trois enregistrements de conditions de répartition sont créés. La seule différence entre chaque condition de répartition est le centre de coût spécifié sur le compte général de destination.

## <a name="create-an-allocation-term-on-a-main-account"></a>Créer une condition de répartition sur un compte principal

1. Dans le **Volet de navigation**, allez dans **Modules > Comptabilité > Plan de comptes > Comptes > Comptes principaux**.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
3. Dans l’organisateur **Remplacements d’entité juridique**, sélectionnez **Ajouter**.
4. Sélectionnez le champ **Société**, puis sélectionnez **Ajouter**.
5. Activez la case à cocher **Répartition**.
6. Sélectionnez **Conditions de répartition**.
7. Sélectionnez **Modifier** pour modifier l’enregistrement par défaut, ou sélectionnez **Nouveau** pour ajouter un enregistrement.
8. Dans le champ **Pourcentage**, entrez le pourcentage de pièces comptables que vous souhaitez répartir.
9. Dans l’organisateur **Dimension financière source**, dans le champ **Critères de sélection** de chaque dimension financière, sélectionnez une option.
    - Si vous sélectionnez **Spécifique**, sélectionnez la valeur de la dimension financière dans la liste déroulante à droite.
    - Si vous sélectionnez **Non spécifique**, aucune information supplémentaire n’est nécessaire pour la dimension financière.
10. Dans l’organisateur **Compte général de destination**, dans le champ **Compte de destination**, sélectionnez le compte principal sur lequel vous souhaitez répartir le pourcentage de la transaction de N° document.
11. Dans le champ **Conserver les dimensions financières source** de chaque dimension financière, sélectionnez une option.
    - Si vous sélectionnez **Non**, sélectionnez dans la liste déroulante à droite la valeur de la dimension financière sur laquelle vous souhaitez répartir la transaction de N° document.
    - Si vous sélectionnez **Oui**, aucune information supplémentaire n’est nécessaire. Le système va converser la valeur du N° document d’origine lors de la validation de la répartition.
12. Répétez les étapes 7 à 11 pour chaque répartition supplémentaire. La somme de toutes les répartitions est indiquée dans le champ **Pourcentage total**. Ce montant ne peut dépasser 100.
13. Fermez toutes les pages.

>[!NOTE] 
> Vous pouvez éventuellement utiliser le bouton **Copier** pour dupliquer la répartition sélectionnée.

Lorsqu’une condition de répartition est créée pour un compte principal, le système va automatiquement valider un nouveau N° document lors de la validation d’un N° document, qui correspond aux dimensions financières source dans les conditions de répartition.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]