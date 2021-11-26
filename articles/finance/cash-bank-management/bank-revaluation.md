---
title: Réévaluation des comptes en devises/bancaires
description: Cette rubrique fournit une vue d’ensemble du processus de réévaluation des comptes en devises bancaires. Elle inclut des informations sur le paramétrage, l’exécution du processus, les calculs pour le processus, et la contrepassation des transactions de réévaluation.
author: roschlom
ms.date: 05/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankCurrencyRevalHistory
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-03-08
ms.dyn365.ops.version: 10
ms.openlocfilehash: 3df6a22e06abbfa75a12ffddac242dd34f5beba5
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/05/2021
ms.locfileid: "7754118"
---
# <a name="bank-foreign-currency-revaluation"></a>Réévaluation des comptes en devises/bancaires

[!include [banner](../includes/banner.md)]


Cette rubrique fournit une vue d’ensemble du processus de réévaluation des comptes en devises bancaires. Elle explique comment paramétrer et exécuter le processus, et fournit des informations sur les calculs pour le processus. Elle décrit également comment contrepasser les transactions de réévaluation, si la contrepassation est requise.

Dans le cadre d’une fin de période, les conventions comptables nécessitent que les soldes de compte bancaire dans des devises étrangères soient réévalués à l’aide des différents types de taux de change (actuel, historique, moyen, et ainsi de suite.). La fonction de réévaluation des comptes en devises bancaires peut être utilisée pour réévaluer un ou plusieurs comptes bancaires. Cette fonction est également une fonction globale. Par conséquent, depuis une seule page, vous pouvez réévaluer les comptes bancaires sur toutes les entités juridiques auxquelles vous avez accès.

> [!NOTE]
> Lorsque vous exécutez le processus de réévaluation, le solde de chaque compte bancaire validé dans une devise étrangère est réévalué. Les transactions de perte ou de profit non réalisé créées lors du processus de réévaluation sont générées par le système. Deux transactions peuvent être créées, l’une pour la devise comptable et l’autre pour la devise de déclaration, si une devise de déclaration existe. Chaque écriture comptable sera validée dans les pertes ou profits non réalisés et dans le compte principal en cours de réévaluation.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>Préparer le traitement de la réévaluation des comptes en devises

Avant d’exécuter le processus de réévaluation, le paramétrage suivant est nécessaire.

- Sur la page **Comptabilité**, spécifiez le type de taux de change. Si un type de taux de change n’est pas défini sur le compte principal, ce type de taux de change est utilisé au cours de la réévaluation des comptes en devises.
- Sur la page **Comptabilité**, précisez les comptes de profit réalisé, de perte réalisée, de profit non réalisé et de perte non réalisée pour la réévaluation en devises. Les comptes de profits et pertes réalisés sont utilisés lors du règlement de transactions de la comptabilité client et de la comptabilité fournisseur. Les comptes des profits et pertes non réalisés sont utilisés pour réévaluer les transactions en cours et la comptabilité des comptes principaux.
- Sur la page **Comptes de réévaluation de la devise**, sélectionnez la réévaluation des différents comptes de réévaluation en devises pour chaque devise et société. Si aucun compte n’est défini, les comptes de la page **Comptabilité** sont utilisés.

## <a name="enable-foreign-currency-revaluation"></a>Activer la réévaluation des comptes en devises

Vous devez activer la fonction de réévaluation des comptes en devises bancaires avant de traiter les réévaluations des comptes en devises.

1. Accédez à **Gestion de la trésorerie et de la banque \> Paramétrage \> Paramètres de gestion de la trésorerie et de la banque**.
2. Dans l’onglet **Général**, sous **Réévaluation des comptes en devises**, définissez l’option **Activer la réévaluation bancaire** sur **Activé** pour activer la fonction pour l’entité juridique actuelle. 
3. Dans l’onglet **Souches de numéros**, ajoutez une souche de numéros pour la réévaluation des comptes en devises.
4. Actualisez le navigateur pour voir **Réévaluation des comptes en devises** dans la section **Tâches périodiques** de la page de zone.

Vous devez activer la fonction pour chaque entité juridique qui utilise la réévaluation des comptes en devises. Si vous le rôle d’Administrateur système ou le rôle de Gestionnaire de fonctionnalités vous est attribué, vous pouvez supprimer cette étape en activant la fonctionnalité nommée **Activer la réévaluation bancaire sans paramètre** dans l’espace de travail **Gestion des fonctionnalités**.

> [!NOTE]
> Si votre entité juridique utilise un code de pays/région russe, polonais ou hongrois, vous pouvez déjà effectuer la réévaluation des comptes en devises bancaires. Vous ne pourrez pas utiliser la réévaluation des comptes en devises utilisées par d’autres pays ou régions.

## <a name="process-foreign-currency-revaluation"></a>Réévaluer des comptes en devises

Une fois le paramétrage terminé, utilisez la page **Réévaluation des comptes en devises** du module Gestion de la trésorerie et de la banque pour réévaluer les soldes d’un ou plusieurs comptes bancaires parmi toutes les entités juridiques. Vous pouvez exécuter le processus en temps réel, ou le replanifier à l’aide d’un traitement par lots.

La page **Réévaluation des comptes en devises** affiche l’historique de chaque processus de réévaluation. Elle montre le moment d’exécution du processus et les critères qui étaient définis, et fournit un lien vers le justificatif qui a été créé pour la réévaluation. Elle affiche également si une réévaluation précédente a été contrepassée. Pour exécuter le processus de réévaluation, sélectionnez **Réévaluation des comptes en devises** dans le volet Actions pour ouvrir la boîte de dialogue **Réévaluation des comptes en devises – Banque**.

Le champ **Date de réévaluation** définit la date limite pour le calcul du solde en devise étrangère qui est réévalué. La somme de toutes les transactions bancaires qui ont eu lieu jusqu’à cette date est réévaluée.

Le champ **Date du taux de change** définit la date du taux de change qui sera utilisée pour réévaluer les soldes en devise. Par exemple, vous pouvez réévaluer les soldes à la date du 31 janvier, mais utiliser le taux de change défini pour le 1er février.

Le processus de réévaluation peut être exécuté pour une ou plusieurs entités juridiques. La recherche affiche uniquement les entités juridiques auxquelles vous avez accès. Sélectionnez les entités juridiques pour lesquelles vous souhaitez sélectionner les comptes bancaires éligibles pour la réévaluation des comptes en devises. Toutes les comptes bancaires de ces entités juridiques sont affichés dans la grille.

Définissez l’option **Aperçu avant validation** sur **Oui** si vous souhaitez consulter les résultats de la réévaluation avant leur validation. La réévaluation des comptes en devises a un aperçu pouvant être validé. Vous n’avez pas à réexécuter le processus de réévaluation. Vous pouvez exporter les résultats de l’aperçu vers Microsoft Excel pour conserver l’historique de la manière dont les montants ont été calculés. Vous ne pouvez pas utiliser le traitement par lots si vous souhaitez afficher l’aperçu des résultats de la réévaluation.

Sélectionnez **OK** pour traiter la réévaluation des comptes en devises. Un enregistrement est créé pour suivre l’historique de chaque exécution. Un enregistrement distinct est créé pour chaque entité juridique et couche de validation.

## <a name="calculate-unrealized-gainloss"></a>Calculer les profits non réalisés/pertes

Dans le module Gestion de la trésorerie et de la banque., la devise bancaire est considérée comme étant la devise de base et n’est pas réévaluée. Le solde du compte bancaire dans la devise comptable est réévalué à l’aide de les taux de change entre la devise bancaire et la devise comptable à la **Date du taux de change**. Le solde du compte bancaire dans la devise de déclaration est également réévalué à l’aide de les taux de change entre la devise bancaire et la devise de déclaration à la **Date du taux de change**.

Une transaction est créée pour la différence entre le solde du compte bancaire et le nouveau solde calculé pour la devise comptable. Une autre transaction est créée pour la différence entre le solde du compte bancaire et le nouveau solde calculé pour la devise de déclaration. Les entrées de ces transactions sont marquées comme rapprochées. 

Aucune entrée n’est effectuée pour la devise comptable si la devise bancaire correspond à la devise comptable. De même, aucune entrée n’est effectuée pour la devise de déclaration si la devise bancaire correspond à la devise de déclaration.

La transaction de réévaluation des comptes en devises est également fractionnée entre les dimensions trouvées dans sur les transactions bancaires. Le fractionnement est basé sur le solde pour chaque dimension. Par exemple, le solde bancaire total est 10 000, mais le solde pour l’unité commerciale 001 est 4 000, alors que le solde pour l’unité commerciale 002 est 6 000. Dans ce cas, 40 % du montant de la réévaluation est imputé sur le compte de réévaluation de l’unité commerciale 001, et 60 % est validé sur le compte de réévaluation de l’unité commerciale 002. Si la structure de compte n’inclut pas d’unité commerciale, le montant total est imputé sur le compte de réévaluation.

## <a name="reverse-foreign-currency-revaluation"></a>Contrepasser la réévaluation des comptes en devises

Si vous devez contrepasser la transaction de réévaluation, sélectionnez le bouton **Transaction de contrepassation** dans le volet Action de la page **Réévaluation des comptes en devises**. Un enregistrement historique de réévaluation des comptes en devises est créé pour tenir à jour le suivi d’audit historique du moment où la réévaluation s’est produite ou a été contrepassée.

Pour contrepasser plusieurs réévaluations, vous devez contrepasser d’abord la réévaluation la plus actuelle. Continuez ensuite à contrepasser les réévaluations précédentes par ordre de date. Vous pouvez ensuite traiter de nouvelles réévaluations pour les périodes que vous avez contrepassées.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
