---
title: Exemple Traiter les lettres de relance
description: Cet article présente un exemple illustrant le processus de création, d’impression et de publication de lettres de relance.
author: JodiChristiansen
ms.date: 02/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 9022051ce1c99da7ff62e30583a20656c77d89f9
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778674"
---
# <a name="process-collection-letters-example"></a>Exemple Traiter les lettres de relance

[!include [banner](../../includes/banner.md)]

Cet article présente un exemple illustrant le processus de création, d’impression et de publication de lettres de relance. L’exemple est basé sur l’option **Ignorer les paiements et les avoirs lors du calcul du code de lettre de relance** dans Crédit et relances. Il utilise les données de la société fictive USMF et d’un nouveau client, US-045.

Pour commencer, accédez à **Comptabilité client \> Clients \> Tous les clients**, sélectionnez **Nouveau**, puis entrez les informations requises pour créer le client US-045.

Lorsque vous avez terminé, vous devez suivre les étapes suivantes.

1. Accédez à **Crédit et relances \> Lettre de relance \> Paramétrer la série de lettres de relance** et paramétrez la série de lettres de relance comme indiqué dans le tableau suivant affecté au profil de validation client.

|   Code lettre de relance      |     Description       |     Devise      |     Compte principal        |     Frais en devise       |   Minimum au-dessus  |   Bloc de jours        |
|-----------------------------  |--------------------   |-----------------  |-----------------------    |--------------------   |-----------------------    |------------------ |
|  Lettre de relance 1          |     Première notification |     EUR          |                   |     0.00              |     0.00                  |     2                 |
|  Lettre de relance 2          |     Deuxième notification avec frais      |     EUR      |     403150         |     20.00         |     10.00     |     3                 |
|  Relance                   |     Dernière notification avec frais       |     USD           |     403150    |     50.00         |     100.00                |     15            |

L’illustration suivante montre les informations contenues dans le tableau telles qu’elles apparaissent sur la page **Lettres de relance**. 

[![Paramétrage d’une série de lettres de relance.](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)

 Vous devez maintenant définir les deux paramètres requis pour cet exemple.

2. Accédez à **Crédit et relances \> Paramétrage \> Paramètres de la comptabilité client** et procédez comme suit :

    1. Dans l’onglet **Relance**, définissez l’option **Ignorer les paiements et les avoirs lors du calcul du code de lettre de relance** dans sur **Oui**.
    2. Assurez-vous que le champ **Créer une lettre de relance par** est défini sur **Client**.

    [![Paramétrage des paramètres de Comptabilité client pour les crédits et relances.](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)

3. Accédez à **Comptabilité client \> Factures \> Toutes factures financières**, sélectionnez **Nouveau**, puis procédez comme suit :

    1. Dans le champ **Compte client**, sélectionnez **US-045**.
    2. Dans le champ **Date de facture**, entrez **15/01/2021**.
    3. Dans le champ **Date d’échéance**, entrez **16/01/2021**.
    4. Sur le raccourci **Lignes de facture**, dans le champ **Compte principal**, entrez **401100**.
    5. Dans le champ **Prix unitaire**, entrez **500.00**.
    6. Sélectionnez **Valider**.

    Vous devez maintenant entrer deux avoirs pour le client.

4. Sélectionnez **Nouveau**, puis procédez comme suit :

    1. Dans le champ **Compte client**, sélectionnez **US-045**.
    2. Dans le champ **Date de facture**, entrez **15/01/2021**.
    3. Dans le champ **Date d’échéance**, entrez **16/01/2021**.
    4. Sur le raccourci **Lignes de facture**, dans le champ **Compte principal**, entrez **401100**.
    5. Dans le champ **Prix unitaire**, entrez **-100,00**.
    6. Sélectionnez **Valider**.

5. Répétez l’étape 4, mais entrez **-200,00** dans le champ **Prix unitaire**.
6. Accédez à **Comptabilité client \> Clients \> Tous les clients** et sélectionnez le client **US-045**. Ensuite, dans le volet Actions, sélectionnez **Transactions \> Transactions** pour vérifier les transactions client que vous avez validées précédemment.

    [![Vérification des transactions client validées.](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)

    Vous devez maintenant créer des lettres de relance pour le client US-045.

7. Accédez à **Crédit et relances \> Lettre de relance \> Créer des lettres de relance** et procédez comme suit :

    1. Définissez les options **Facture** et **Avoir** sur **Oui**.

        Par défaut, le champ **Lettre de relance** doit être défini sur **Lettre de relance par client**.

    2. Dans le champ **Date de la lettre de relance**, entrez **19/01/2021**.
    3. Sur le raccourci **Enregistrements à inclure**, sélectionnez **Filtre**, puis, dans le champ **Compte client**, ajoutez le client **US-045**.
    4. Cliquez sur **OK**.
    5. Sélectionnez **OK** pour créer des lettres de relance.

8. Accédez à **Crédit et relances \> Lettre de relance \> Examiner et traiter les lettres de relance** et procédez comme suit :

    1. Notez que le code de la lettre de relance sur l’en-tête et les lignes de transaction est **Lettre de relance 1**, car cette lettre de relance est la première de la série. (Pour afficher les lignes de transaction, vous devrez peut-être sélectionner le raccourci **Transactions**.)

   [![Vérification que le même code de lettre de relance apparaît sur l’en-tête et les lignes.](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)

    2. Dans le volet Actions, sélectionnez **Valider**.
    3. Dans le champ **Date de validation**, entrez **19/01/2021**.

    Vous devez maintenant créer à nouveau des lettres de relance pour le client US-045.

9. Accédez à **Crédit et relances \> Lettre de relance \> Créer des lettres de relance** et procédez comme suit :

    1. Définissez les options **Facture** et **Avoir** sur **Oui**.

        Par défaut, le champ **Lettre de relance** doit être défini sur **Lettre de relance par client**.

    2. Dans le champ **Date de la lettre de relance**, entrez **23/01/2021**.
    3. Sur le raccourci **Enregistrements à inclure**, sélectionnez **Filtre**, puis, dans le champ **Compte client**, ajoutez le client **US-045**.
    4. Cliquez sur **OK**.
    5. Sélectionnez **OK** pour créer des lettres de relance.

10. Accédez à **Crédit et relances \> Lettre de relance \> Examiner et traiter les lettres de relance** et procédez comme suit :

    1. Notez que le code de lettre de relance sur l’en-tête est **Lettre de relance 1**. Cependant, le code sur les lignes de transaction est **Lettre de relance 2**.

   [![Vérifie que différents codes de lettre de relance apparaissent sur l’en-tête et sur les lignes.](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)

  Les codes sont différents, car l’option **Ignorer les paiements et les avoirs lors du calcul du code de lettre de relance** est définie sur **Oui**.

  2. Ne validez pas cette lettre de relance.

11. Accédez à **Crédit et relances \> Paramétrage \> Paramètres de la comptabilité client**, puis, sur l’onglet **Recouvrement**, définissez l’option **Ignorer les paiements et les avoirs lors du calcul du code de lettre de relance** sur **Non**.

    [![Paramétrage de l’option Ignorer les paiements et les avoirs lors du calcul du code lettre de relance sur Non.](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)

    Vous devez maintenant créer à nouveau des lettres de relance pour le client US-045.

12. Accédez à **Crédit et relances \> Lettre de relance \> Créer des lettres de relance** et procédez comme suit :

    1. Définissez les options **Facture** et **Avoir** sur **Oui**.

        Par défaut, le champ **Lettre de relance** doit être défini sur **Lettre de relance par client**.

    2. Dans le champ **Date de la lettre de relance**, entrez **23/01/2021**.
    3. Sur le raccourci **Enregistrements à inclure**, sélectionnez **Filtre**, puis, dans le champ **Compte client**, ajoutez le client **US-045**.
    4. Cliquez sur **OK**.
    5. Sélectionnez **OK** pour créer des lettres de relance.

13. Accédez à **Crédit et relances \> Lettre de relance \> Examiner et traiter les lettres de relance** et notez que le code de la lettre de relance sur l’en-tête et les lignes de transaction est **Lettre de relance 2**.

    [![Nouvel affichage. Le même code de lettre de relance apparaît sur l’en-tête et les lignes.](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)

    Le même code s’affiche aux deux endroits, car l’option **Ignorer les paiements et les avoirs lors du calcul du code de lettre de relance** est maintenant définie sur **Non**.
