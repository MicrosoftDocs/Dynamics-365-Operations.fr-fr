---
title: Afficher le solde de congés dans l’interface d’exécution de l’atelier de production
description: Cette rubrique fournit un exemple de scénario qui montre comment configurer Microsoft Dynamics 365 Supply Chain Management de sorte qu’il utilise les statistiques de paie pour fournir aux travailleurs un aperçu de leur solde de vacances pour l’année en cours.
author: johanhoffmann
ms.date: 04/22/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-04-22
ms.dyn365.ops.version: 10.0.XX
ms.openlocfilehash: a97858c72b0be50609cee552bd0635e2d68ea478
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645345"
---
# <a name="show-vacation-balances-in-the-production-floor-execution-interface"></a>Afficher le solde de congés dans l’interface d’exécution de l’atelier de production

[!include [banner](../includes/banner.md)]

Cette rubrique fournit un exemple de scénario qui montre comment configurer Microsoft Dynamics 365 Supply Chain Management de sorte qu’il utilise les statistiques de paie pour fournir à chaque travailleur un aperçu de leur solde de vacances pour l’année en cours. Les travailleurs pourront voir leur solde de vacances dans la boîte de dialogue **Ma journée** dans l’interface d’exécution de l’atelier de production.

Ce scénario utilise la loi danoise sur les vacances, où l’année de vacances va du 1er septembre au 31 août. Dans ce scénario, votre entreprise a embauché un nouveau collaborateur et accordera à ce collaborateur un solde de 10 jours de vacances pour le reste de l’année de vacances en cours.

## <a name="turn-on-the-required-features"></a>Activer les fonctionnalités requises

Pour exécuter ce scénario, vous devez activer la fonctionnalité *Vue "Ma journée" pour l’interface d’exécution de l’atelier de production* dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Pour plus d’informations sur l’activation de cette fonctionnalité et d’autres fonctionnalités pour l’interface d’exécution de l’atelier de production, voir [Configurer l’interface d’exécution de l’atelier de production](production-floor-execution-configure.md).

## <a name="make-sample-data-available"></a>Rendre les exemple de données disponibles

Pour utiliser ce scénario à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

## <a name="create-a-new-pay-type"></a>Création d’un type de paie

Commencez par créer un *type de paiement* qui suivra les jours de vacances gagnés par les travailleurs (également appelés leur *solde de vacances*). Généralement, les types de rémunération sont utilisés pour calculer la rémunération des travailleurs. Cependant, le type de paie que vous créez ici sera utilisé pour calculer un solde.

1. Accédez à **Pointage \> Paramétrage \> Paie \> Types de salaire**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Type de paie :** *5151-1*
    - **Description :** *Compteur de jours de vacances des collaborateurs*
    - **Inclure dans l’exportation :** *Non*

## <a name="update-the-pay-agreement"></a>Mettre à jour l’accord salarial

Dans cette section, vous allez modifier un fichier existant *accord salarial* en ajoutant le nouveau type de paie et en définissant les règles qui définissent la manière dont le solde de vacances de chaque collaborateur est ajusté à l’enregistrement des jours de vacances.

1. Accédez à **Pointage \> Paramétrage \> Paie \> Accords salariaux**.
1. Sélectionnez l’accord salarial pour lequel vous souhaitez configurer la politique de congés. (Si vous travaillez avec des exemples de données USMF standard, il n’y a qu’un seul accord salarial, *Man*.)
1. Assurez-vous que l’accord salarial sélectionné est valide pour la date actuelle. Si vous travaillez avec des exemples de données USMF standard, le champ **Date de fin** de l’accord salarial *Man* peut être fixé à une date passée. Modifiez la valeur afin qu’elle soit dans un an ou deux dans le futur, selon les besoins.
1. Dans le volet Actions, cliquez sur **Lignes de l’accord**.
1. Sur la page **Lignes d’accord salarial**, sur le raccourci **Aperçu**, définissez les valeurs suivantes dans la barre d’outils :

    - Dans la première liste déroulante, sélectionnez **Lundi**.
    - Dans la seconde liste déroulante, sélectionnez **Congé**.

1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez le champ **Type de paiement** au type de paie que vous avez créé pour ce scénario (*5151-1*). Laissez tous les autres paramètres définis sur leurs valeurs par défaut.
1. Tandis que la nouvelle ligne est toujours sélectionnée, sur le raccourci **Général**, définissez les valeurs suivantes :

    - **Code d’absence :** *Vacances*
    - **Utiliser une quantité fixe :** *Oui*
    - **Constante :** *-1*

1. Sur le volet Actions, sélectionnez **Copier le jour**.
1. Dans la boîte de dialogue **Copier le jour**, définissez les valeurs suivantes :

    - **Mardi**, **mercredi**, **jeudi** et **vendredi :** *Oui*
    - **Remplacer :** *Oui*
    - **Absence :** *Oui*

1. Cliquez sur **OK**.

## <a name="create-a-payroll-statistic-group"></a>Création d’un groupe de statistiques de paie

*Groupes de statistiques de paie* sont utilisés pour établir des statistiques sur les inscriptions des collaborateurs au cours d’une période. Dans ce scénario, vous utiliserez un groupe de statistiques de paie pour calculer le nombre de jours de vacances que les collaborateurs gagnent pendant une période de vacances. Au Danemark, la période des vacances s’étend du 1er septembre au 31 août.

1. Accédez à **Pointage \> Paramétrage \> Paie \> Groupes de statistiques de paie**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Groupe de statistiques de paie :** *VAC*
    - **Description :** *Solde de vacances*
    - **Transfert :** *Non*

1. Alors que la nouvelle ligne est toujours sélectionnée, sélectionnez **Paramétrage** dans le volet Actions.
1. Dans la page **Paramétrage**, sur le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez le champ **Type de paie** sur *5151-1*.
1. Sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) le champ **Code période**, puis sélectionnez **Afficher les détails**. Vous pouvez maintenant paramétrer le code de période que vous affecterez ultérieurement à ce champ.
1. Sur la page **Types de périodes**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Types de périodes :** *VacYear*
    - **Description :** *Année de vacances*
    - **Fréquence :** *Années*

1. Alors que la nouvelle ligne est toujours sélectionnée, sélectionnez **Générer des périodes** dans le volet Actions.
1. Dans la boîte de dialogue **Générer des périodes**, définissez les valeurs suivantes :

    - **Indiquer la date de début de la période :** *1er septembre 2021*
    - **Longueur de la période :** *5*

1. Cliquez sur **OK**.
1. Fermer la page **Types de période** pour revenir à la page **Groupes de statistiques de paie**.
1. Met le champ **Code période** sur le type de période que vous venez de créer (*VacYear*).

## <a name="create-a-statistical-balance-setup"></a>Créer un paramétrage du solde statistique

Dans cette section, vous allez créer une *configuration de la balance statistique* qui est lié au groupe de statistiques de paie que vous avez créé dans la section précédente. Plus tard, vous lierez ce paramétrage de solde statistique à la vue **Ma journée** dans l’interface d’exécution de l’atelier de production. La vue **Ma journée** pourra alors afficher les soldes de congés pour le type de paie qui est attribué au groupe de statistiques de paie associé.

1. Accédez à **Pointage \> Paramétrage \> Paie \> Configuration du solde statistique**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Groupe de statistiques de paie :** *VAC*
    - **Nom externe :** *Solde de vacances*
    - **Flexible :** *Non*

## <a name="create-a-manual-premium"></a>Créer une prime manuelle

Les *Primes manuelles* sont généralement utilisés pour accorder aux collaborateurs une rémunération supplémentaire pour un travail supplémentaire. Dans ce scénario, vous allez créer une prime manuelle que vous pouvez utiliser pour définir le solde initial des congés pour chaque collaborateur.

1. Accédez à **Pointage \> Paramétrage \> Paie \> Primes manuelles**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un enregistrement.
1. Dans le nouvel enregistrement, définissez les valeurs suivantes :

    - **Primes :** *VAC*
    - **Description :** *Ajustements au solde des congés des collaborateurs*
    - **Type de paie :** *5151-1*

## <a name="set-a-workers-initial-vacation-balance-and-adjust-it-by-one-day"></a>Définissez le solde de vacances initial d’un collaborateur et ajustez-le d’un jour

Les administrateurs de la paie utilisent la page **Approuver** pour examiner et approuver les inscriptions quotidiennes des collaborateurs. Dans ce scénario, vous jouerez le rôle d’un administrateur afin de pouvoir définir le solde initial des vacances d’un collaborateur et enregistrer les jours de vacances pris par le collaborateur.

1. Accédez à **Pointage et présence \> Révision et approbation \> Approbation**.
1. Dans la boîte de dialogue **Approuver**, définissez les champs suivants :

    - **Groupe d’approbation** – Sélectionnez le groupe d’approbation auquel vous appartenez. (Si vous travaillez avec des exemples de données USMF standard, il n’y a qu’un seul groupe d’approbation, *AdmMan*.)
    - **Voir tout le groupe, 1 jour** – Sélectionnez l’option, puis définissez le champ sur la date actuelle.

1. Cliquez sur **OK**.
1. La page **Approuver** affiche une liste d’enregistrements qui correspondent à vos critères. Sélectionnez le collaborateur que vous souhaitez approuver. Si vous travaillez avec des exemples de données USMF standard, sélectionnez le collaborateur *000496* (*Christina Portra*).
1. Accordez au collaborateur sélectionné 10 jours de vacances :

    1. Alors que le collaborateur est toujours sélectionné, sélectionnez **Lignes de primes** dans le volet Actions.
    1. Sur la page **Lignes de primes**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
    1. Sur la nouvelle ligne, définissez les valeurs suivantes :

        - **Primes :** *VAC*
        - **Quantité :** *10*

    1. Fermez la page **Lignes de primes**.

1. Sur la page **Approuver**, enregistrez le fait que le collaborateur a utilisé un de ses jours de vacances à la date du jour :

    1. Tandis que le collaborateur est toujours sélectionné, dans la partie inférieure de la page, sur l’onglet **Vue d’ensemble**, sélectionnez **Nouveau** dans la barre d’outils pour ajouter une ligne à la grille.
    1. Sur la nouvelle ligne, définissez les valeurs suivantes :

        - **Type de journal d’enregistrement :** *Absences*
        - **Référence :** *Vacances*

    1. Dans la partie supérieure de la page, sélectionnez **Transférer** dans la barre d’outils pour appliquer le solde de vacances et calculer la déduction.

## <a name="configure-the-production-floor-execution-interface-so-that-it-includes-the-my-day-dialog-box"></a>Configurez l’interface d’exécution de l’atelier de production afin qu’elle inclue la boîte de dialogue Ma journée

Dans cette section, vous allez ajouter un bouton **Ma journée** vers l’interface d’exécution de l’atelier de production. Les collaborateurs peuvent ensuite utiliser ce bouton pour ouvrir la boite de dialogue **Ma journée**.

1. Accédez à **Contrôle de la production \> Paramétrage \> Contrôle et suivi de la production \> Configurer l’exécution de l’atelier de production**.
1. Sélectionnez une configuration, comme *Par défaut*.
1. Dans le volet Actions, sélectionnez **Onglets Concepteur**.
1. Sur la page **Onglets de conception**, dans le volet de liste, sélectionnez *Tous les postes* pour afficher les paramètres de cet onglet. Le champ **Vue principale** devrait maintenant afficher une valeur de *Tous les postes*.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Sur le raccourci **Barre d’outils secondaire**, dans la colonne **Actions disponibles**, sélectionnez **Ma journée**. Ensuite, sélectionnez le bouton Flèche droite pour la déplacer vers la colonne **Actions sélectionnées**.

## <a name="check-your-balance-in-the-production-floor-execution-interface"></a>Vérifier votre solde dans l’interface d’exécution de l’atelier de production

Dans cette section, vous vous connecterez à l’interface d’exécution de l’atelier de production en tant que collaborateur dont vous avez configuré les vacances plus tôt. Vous ouvrirez alors la boîte de dialogue **Ma journée** pour afficher votre solde de vacances.

1. Accédez à **Contrôle de la production \> Paramétrage \> Exécution de la fabrication \> Exécution de l’atelier de production**.
1. Si vous êtes invité à sélectionner une configuration, sélectionnez la configuration que vous avez configurée précédemment dans ce scénario (*Par défaut*).
1. connectez-vous en tant qu’utilisateur que vous avez configuré précédemment dans ce scénario. Si vous travaillez avec des exemples de données USMF standard, vous devriez pouvoir vous connecter en saisissant *123* dans le champ **ID badge**. L’ID badge correspond à Christina Portra.
1. Sélectionnez **Ma journée** dans la barre d’outils de gauche.
1. Inspectez la section **Soldes** de la boîte de dialogue. Cette section devrait maintenant montrer que vous avez un solde de neuf jours de vacances.
