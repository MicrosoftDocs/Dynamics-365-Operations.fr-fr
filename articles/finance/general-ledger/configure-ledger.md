---
title: Configurer les registres
description: Cette rubrique fournit des informations sur la configuration des registres pour chaque entité juridique. Elle comprend des informations sur la manière de sélectionner les devises, les calendriers fiscaux, le plan comptable et les structures de compte à utiliser avec chaque entité juridique.
author: kweekley
manager: ''
ms.date: 09/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Ledger
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-09
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 5a7fcda435fd957edbbe09d796685c0c742dc6a8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975814"
---
# <a name="configure-ledgers"></a>Configurer les registres

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur la configuration des registres pour chaque entité juridique. Elle comprend des informations sur la manière de sélectionner les devises, les calendriers fiscaux, le plan comptable et les structures de compte à utiliser avec chaque entité juridique.

## <a name="selecting-the-chart-of-accounts"></a>Sélection du plan de comptes

Pour chaque entité juridique de Microsoft Dynamics 365 Finance, il convient de configurer les détails de la comptabilité. La page **Comptabilité** vous permet de sélectionner le plan comptable et les structures de compte qui seront utilisés pour l’entité juridique sélectionnée. Vous pouvez partager votre plan comptable et les structures de compte en configurant la page **Comptabilité** dans chaque entité juridique pour utiliser les mêmes plan comptable et structures de compte. Vous pouvez également partager une partie de la configuration dans chaque entité juridique et avoir des configurations spécifiques dans chaque entité juridique.

Si vos entités juridiques doivent avoir des plans de comptes différents ou des structures de compte différentes, la fonction de remplacement d’entité juridique peut être utile. En utilisant le même plan comptable et les mêmes structures de compte pour plusieurs entités juridiques, puis en gérant toutes les exceptions via des remplacements d’entités juridiques, vous pouvez simplifier la maintenance au fil du temps.

Pour configurer le plan comptable d’une personne morale, accédez à **Comptabilité \> Configuration de la comptabilité \> Comptabilité**. Sur la page **Comptabilité**, sélectionnez **Plan comptable**, puis, dans la liste, sélectionnez le plan comptable à utiliser. Notez que le plan comptable ne peut pas être modifié une fois que vous avez sélectionné une valeur et enregistré des transactions dans l’entité juridique.

Pour plus d’informations sur la planification et la configuration du plan comptable et des comptes principaux, voir [Planifier le plan comptable](plan-chart-of-accounts.md).

## <a name="selecting-account-structures"></a>Sélection des structures de compte

Chaque entité juridique dans Dynamics 365 Finance peut être configuré pour utiliser une ou plusieurs structures de compte. Chaque structure de compte définit les dimensions financières et les combinaisons de comptes principaux et de dimensions financières qui seront autorisées lors de la validation des transactions. Vous pouvez utiliser les mêmes structures de compte dans plusieurs entités juridiques.

Notez que si vous disposez de plusieurs structures de compte, vous ne pouvez sélectionner que des structures de compte qui ne comportent pas de combinaisons de comptes principaux et de dimensions financières qui se chevauchent. Par exemple, l’une de vos structures de compte est configurée pour ajouter une unité commerciale pour les comptes principaux entre 1 000 et 1 999. Dans une autre structure de compte, vous avez ajouté une dimension financière Département pour les comptes principaux qui commencent par 1. Dans ce cas, une seule des structures de compte peut être ajoutée dans la même entité juridique.

Pour configurer les structures de compte de votre comptabilité, sur la page **Comptabilité**, sur le raccourci **Structures de compte**, sélectionnez **Ajouter**, puis une structure de compte dans la liste, et enfin **Sélectionner**. L’ajout et l’enregistrement des structures de compte peuvent prendre quelques minutes. Notez que les structures de compte que vous sélectionnez doivent être actives. À défaut, les détails des structures de compte ne seront pas effectifs dans les entités juridiques où ils sont liés.

Pour supprimer une structure de compte, sur la page **Comptabilité**, sur le raccourci **Structures de compte**, sélectionnez **Supprimer**. Notez que si vous supprimez une structure de compte de votre comptabilité, vous ne supprimez aucune transaction qui a été validée à l’aide de la configuration de cette structure de compte.

Pour plus d’informations sur la configuration de vos structures de compte, consultez [Configurer les structures de compte](configure-account-structures.md).

## <a name="configuring-calendars-for-the-ledger"></a>Configuration des calendriers pour la comptabilité

Un autre composant de la comptabilité est le calendrier fiscal. Un calendrier fiscal doit être sélectionné pour chaque entité juridique. Vous pouvez utiliser le même calendrier fiscal dans plusieurs entités juridiques. Lorsque vous sélectionnez un calendrier fiscal pour la comptabilité, une copie est effectuée. Cette copie est appelée calendrier comptable. Avec le calendrier comptable, sélectionnez le statut des périodes et des modules dans chaque période.

Pour accéder et mettre à jour le calendrier de l’entité juridique sélectionnée, sur la page **Comptabilité**, dans le volet Actions, sélectionnez **Calendrier comptable**.

Pour sélectionner le calendrier, sélectionnez **Calendriers fiscaux**, puis sélectionnez le calendrier dans la liste. Si vous modifiez le calendrier fiscal après la validation des transactions dans l’entité juridique, vous devez sélectionner **Recalculer les périodes comptables**. Ensuite, dans la boîte de dialogue qui apparaît, vous pouvez mettre à jour les soldes comptables pour les périodes de votre calendrier. Nous vous recommandons d’exécuter le processus **Recalculer les périodes comptables** en mode **Lot** et de l’exécuter lorsque des processus non critiques se produisent dans votre système. En fonction du nombre de transactions et des combinaisons de dimensions financières, ce processus peut prendre un certain temps.

Si aucun calendrier fiscal n’est sélectionné pour une entité juridique, vous recevrez un message d’erreur lorsque vous tenterez de valider une transaction dans cette entité juridique.

Pour plus d’informations, voir [Calendriers fiscaux, exercices, et périodes.](../budgeting/fiscal-calendars-fiscal-years-periods.md).

## <a name="using-a-balancing-financial-dimension"></a>Utilisation d’une dimension financière d’équilibrage

Après avoir sélectionné le plan comptable et ajouté une ou plusieurs structures de compte, vous pouvez éventuellement sélectionner une seule dimension financière à utiliser comme dimension financière d’équilibrage. La dimension que vous sélectionnez doit exister dans toutes les structures de compte. Elle doit être également équilibrée dans toutes les écritures comptables. En d’autres termes, les débits et crédits doivent être égaux pour le compte principal et la dimension financière d’équilibrage. Le système crée automatiquement des transactions pour équilibrer les écritures, en fonction des principaux comptes spécifiés dans les champs **Crédit interunité** et **Débit interunité** sur la page **Comptes pour transaction automatique**.

Pour plus d’informations sur l’équilibrage des entrées, voir [Journaux équilibrés pour la comptabilité interunités](example-balanced-journals-interunit-accounting.md).

## <a name="configuring-currencies-for-the-ledger"></a>Configuration des devises pour la comptabilité

La page **Comptabilité** permet également de contrôler et de définir les devises qui seront utilisées lorsque les transactions sont validées en comptabilité. Vous devez spécifier la devise comptable, qui est la devise utilisée dans la colonne **Devise comptable** dans la comptabilité sur tous les documents. De plus, dans la colonne **Devise de déclaration**, vous pouvez éventuellement sélectionner une deuxième devise. Si vous sélectionnez une devise de déclaration, toutes les transactions seront enregistrées dans cette devise dans la colonne **Devise de déclaration** dans la comptabilité sur tous les documents.

Si les transactions sont enregistrées dans une autre devise, le système convertit automatiquement le montant de la transaction de la devise des transactions dans la devise comptable et la devise de déclaration sur le document. Sur la page **Comptabilité**, dans le champ **Type de taux de change de la devise comptable**, sélectionnez le type de taux de change configuré pour les taux de change à utiliser pour convertir les valeurs de devise de transaction en devise comptable sur un document. Si vous avez sélectionné une devise de déclaration, vous devez également définir le champ **Type de taux de change de la devise comptable** pour indiquer le taux de change à utiliser pour convertir les valeurs de la devise de transaction en devise de déclaration sur un document.

Si vous utilisez la fonctionnalité de budgétisation, vous pouvez également définir le champ **Type de taux de change budgétaire** pour indiquer le taux de change à utiliser pour convertir les transactions budgétaires d’une devise à une autre.

Si vous utilisez deux devises, ou si vous utilisez une seule devise, mais que les transactions sont validées dans une devise différente, vous devez configurer le raccourci **Comptes pour la réévaluation des devises** sur la page **Comptabilité**. Sur ce raccourci, définissez les comptes de pertes et profits réalisés par défaut et non réalisés par défaut à utiliser par défaut lorsque les transactions sont validées, si aucun compte n’est spécifié sur la page **Comptes de réévaluation des devises**. (La page **Comptes de réévaluation des devises** est utilisée pour configurer différents comptes pour les pertes et profits réalisés et non réalisés pour chaque devise.)

Les pertes et profits réalisés correspondent aux pertes et profits obtenus partir des transactions terminées. Ils sont enregistrés dans le compte de résultat. Les pertes et profits non réalisés correspondent aux pertes et profits matérialisés, mais la transaction n’est pas terminée. En d’autres termes, vous avez publié une facture, par exemple, mais la facture n’est pas encore réglée et payée. Les pertes et profits non réalisés sont enregistrés sur le bilan.

Pour plus d’informations sur la manière d’utiliser deux devises, voir [Double devise](dual-currency.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]