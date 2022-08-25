---
title: Configurer des fournisseurs pour l’état 1099
description: Cet article explique comment configurer les enregistrements de fournisseur afin qu’une zone 1099 soit associée à un compte principal.
author: v-kiarnd
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: v-kiarnd
ms.search.validFrom: 2020-08-03
ms.dyn365.ops.version: 10.0.13
ms.custom: ''
ms.search.industry: public sector
ms.search.form: PSNCanadianHSTTaxFeature
ms.devlang: ''
ms.tgt_pltfrm: ''
ms.openlocfilehash: 5f8b66b14952d27f70aa4a2ca6d38a0db5c2925e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268526"
---
# <a name="set-up-vendors-for-1099-reporting"></a>Configurer des fournisseurs pour l’état 1099

[!include [banner](../includes/banner.md)]

Cet article explique comment configurer les enregistrements de fournisseur afin qu’une zone 1099 soit associée à un compte principal. Il est préférable de terminer ces étapes de configuration avant de valider les transactions du fournisseur. Pour plus d’informations, voir [Génération d’état de fin d’exercice 1099](noam-usa-year-end-1099-reporting.md).

> [!NOTE]
> Il est recommandé d’analyser les modifications apportées à la règle d’administration fiscale pour l’exercice applicable avant de configurer et de traiter les relevés 1099.

Pour configurer des fournisseurs pour les états 1099, suivez ces étapes.

1. Accédez à **Comptabilité fournisseur \> Fournisseurs \> Tous les fournisseurs** ou **Approvisionnements \> Commun \> Fournisseurs \> Tous les fournisseurs**.
2. Sélectionnez un compte fournisseur.
3. Sur le raccourci **Taxe 1099**, sélectionnez l’option **État 1099** pour inclure les informations de transaction et 1099 pour le fournisseur dans l’état 1099. Si cette option n’est pas sélectionnée, les informations sur l’état 1099 pour le fournisseur ne seront pas incluses sur le rapport 1099 et les fichiers électroniques ou magnétiques n’incluront aucun montant pour le fournisseur.
4. Dans le champ **ID de taxe fédérale**, entrez le numéro d’identification du contribuable du fournisseur. Puis, dans le champ **Type d’identification fiscale**, sélectionnez le type de numéro d’identification fiscale que vous venez de saisir.

    > [!NOTE]
    > Le privilège de sécurité **Empêcher les numéros d’enregistrement fiscal en double** détermine si vous pouvez saisir un numéro d’identification de contribuable qui a déjà été utilisé dans un autre enregistrement de fournisseur.

5. Dans le champ **Zone 1099**, entrez la valeur par défaut qui doit apparaître sur chaque ligne de transaction créée pour le fournisseur. Ce paramètre est requis pour inclure des transactions pour le fournisseur sur le rapport 1099 et dans les fichiers électroniques ou magnétiques.
6. Si l’organisation du fournisseur appartient à une entité hors des États-Unis, sélectionnez l’option **Indicateur d’entité étrangère**.
7. Si votre organisation a été avertie deux fois au cours des trois années civiles que le fournisseur a donné un nom incorrect, cochez la case **Deuxième TIN**.
8. Dans le champ **Nom à utiliser sur le 1099**, sélectionnez **Nom du fournisseur**. Si le fournisseur utilise un autre nom, vous pouvez sélectionner **Faisant affaire sous le nom de**. Dans ce cas, entrez l’autre nom dans le champ **DBA**.
9. Dans le champ **Contrôle de nom**, entrez l’ID alphanumérique de contrôle de nom à imprimer sur l’étiquette d’adresse pour l’administration fiscale, pour contrôler le Numéro d’identification d’employeur (EIN) du fournisseur.
10. Activez l'option **CUSIP** pour indiquer que le numéro d’identification du comité sur l’uniformisation des procédures d’identification de sécurité (CUSIP) s’applique à l’instrument de créance.
11. Dans le champ **ID CUSIP**, entrez le numéro CUSIP composé de neuf caractères alphanumériques pour identifier l’instrument de créance.
12. Dans le champ **Détails CUSIP**, entrez l’abréviation de la bourse des valeurs et l’émetteur, le taux de coupon et l’année de l’échéance.

    > [!NOTE]
    > Vous pouvez uniquement entrer les détails CUSIP si la case à cocher **CUSIP** est décochée.

13. Dans le champ **Détails du mandataire**, entrez les noms du mandataire et de l’émetteur.
14. Dans le champ **Type d’investisseur**, sélectionnez le type d’investisseur :

    - **Néant**
    - **Propriétaire** – L’investisseur est le propriétaire du titre de créance.
    - **Mandataire/courtier** – L’investisseur est un courtier qui représente le propriétaire du titre de créance.

15. Dans le volet Action, sous l’onglet **Fournisseur**, dans le groupe **Configuration**, sélectionnez **ID taxe régionale du fournisseur**.
16. Créez un enregistrement pour chaque état où le fournisseur reçoit des paiements de la part de votre organisation. Entrez l’ID taxe régionale. En outre, si des informations d’ID taxe sont disponibles, sélectionnez le type d’ID taxe.
17. Si l’impôt local sur le revenu a été retenu durant l’année, sélectionnez la case à cocher **Impôt local sur le revenu retenu**.
18. Fermez les pages pour enregistrer vos modifications.

## <a name="associate-a-1099-default-value-with-a-main-account"></a>Associer une valeur par défaut de 1099 à un compte principal

Certaines lignes de facture identifiées pour la déclaration de taxe fédérale 1099 peuvent être déclarées pour une zone 1099 différente de la zone par défaut du fournisseur. 

> [!Note]
> Cette fonctionnalité n’est disponible que si vous utilisez le secteur public. 

Étant donné que les fournisseurs peuvent recevoir des paiements qui correspondent à plusieurs zones 1099, il est préférable d’utiliser un compte principal sur une ligne pour une distribution de financement. Cette approche garantit une génération d’état cohérent des paiements à une zone 1099 spécifique. Vous pouvez maintenant recalculer les valeurs de zone 1099 pour les fournisseurs afin de déclarer plus précisément les soldes accumulés à l’IRS.

> [!NOTE]
> La zone 1099 et le montant ne peuvent être renseignés sur la facture que si la case **État 1099** sur le raccourci **Taxe 1099** de la page des détails du fournisseur est sélectionnée.

1. Accédez à **Comptabilité fournisseur \> Tâches périodiques \> Taxe 1099 \> Association de compte principal 1099**.
2. Dans le champ **Numéro de compte principal**, sélectionnez le compte principal à associer à une zone 1099. Vous ne pouvez sélectionner qu’un compte principal du type **Dépense**.
3. Dans le champ **Code zone 1099**, sélectionnez le code de zone sur le formulaire 1099 auquel les montants imputés au compte principal sélectionné doivent être associés.
4. Répétez les étapes précédentes pour ajouter tous les autres comptes principaux requis.

## <a name="update-1099-boxes-and-amounts"></a>Mettre à jour les zones et montants 1099

Vous pouvez mettre à jour les zones et les montants de l’état 1099 pour toutes les factures payées pour une année civile, en fonction de l’affectation actuelle des comptes principaux aux zones 1099.

> [!Note]
> Cette fonctionnalité n’est disponible que si vous utilisez le secteur public. 

1. Accédez à **Comptabilité fournisseur \> Tâches périodiques \> Taxe 1099 \> Mettre à jour les informations par compte principal 1099**.
2. Sélectionnez une plage de dates et un fournisseur, puis sélectionnez **OK**.
3. Sélectionnez **OK** pour mettre à jour les soldes 1099 basés sur le compte principal, qui sont utilisés pour les factures imputées et payées du fournisseur.

Le système évalue tout fournisseur où l’option **État 1099** sélectionnée. Il évalue ensuite toutes les factures du fournisseur. Le montant 1099 est recalculé en fonction des comptes principaux sur chaque ligne, y compris toute ligne qui a des distributions fractionnées. Si le montant entièrement payé de la ligne n’est pas associé à la zone 1099, la ligne n’est pas incluse dans le montant 1099, comme illustré dans les exemples suivants :

- La valeur par défaut du fournisseur pour la zone 1099 diffère de la valeur spécifiée sur la ligne de facture.

    Si une ligne sur une facture fournisseur utilise un compte principal associé à 1099 zone 7 et que la zone par défaut 1099 pour le fournisseur est un numéro différent, l’entrée par défaut pour le fournisseur et le montant à déclarer pour celui-ci, seront recalculés pour 1099 zone 7.

- Toutes les lignes de facture n’ont pas de valeurs de zone 1099.

   Si une ligne sur une facture fournisseur utilise un compte principal associé à 1099 zone 7 et qu’une autre ligne utilise un compte principal qui n’est pas associé à la zone 1099, l’entrée par défaut pour le fournisseur et le montant à déclarer pour celui-ci, seront recalculés pour 1099 zone 7.

- Les lignes de facture ont des valeurs de zone 1099 différentes.

     Si une ligne sur une facture fournisseur utilise un compte principal associé à 1099 zone 7 et qu’une autre ligne utilise un compte principal qui n’est pas associé à 1099 zone 1, le système ignore l’entrée par défaut pour le fournisseur et le montant 1099 sera recalculé pour les comptes principaux associés.

- La facture a des répartitions fractionnées.

    Si une facture fournisseur comprend une ligne comportant des distributions fractionnées, l’entrée par défaut du fournisseur sera recalculée pour la zone 1099 associée au compte principal utilisé dans les distributions.

> [!NOTE]
> Une nouvelle colonne nommée **Créé par le processus de mise à jour 1099** a été ajouté à la page **Transactions taxe 1099**. Les cases à cocher de cette colonne sont sélectionnées pour indiquer que le nouveau processus de mise à jour a mis à jour le solde 1099. Si la case d’une ligne est décochée, la fonctionnalité standard a été utilisée pour créer la transaction. Pour ouvrir la page **Transactions taxe 1099**, accédez à **Comptabilité fournisseur \> Tâches périodiques \> Règlement du fournisseur pour les 1099 \> Transactions 1099 du fournisseur**. Sinon, accédez à **Comptabilité fournisseur \> Fournisseurs \> Tous les fournisseurs**, sélectionnez un fournisseur, puis, dans le volet Action, sur l’onglet **Fournisseur**, dans le groupe **Informations fiscales**, sélectionnez **Règlement du fournisseur pour les 1099 \> transactions 1099 du fournisseur**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
