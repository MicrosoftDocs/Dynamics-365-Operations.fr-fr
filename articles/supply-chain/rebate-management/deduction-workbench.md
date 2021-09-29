---
title: Gérer les déductions à l’aide du workbench de déduction
description: Cette rubrique décrit comment utiliser le workbench de déduction afin de traiter les paiements client qui incluent des déductions.
author: sherry-zheng
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: bf98529176fbed368708ea925f542a70f2936037
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500400"
---
# <a name="manage-deductions-using-the-deduction-workbench"></a>Gérer les déductions à l’aide du workbench de déduction

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment utiliser le workbench de déduction afin de traiter les paiements client qui incluent des déductions.

Un client qui possède une remise peut choisir de ne pas attendre un paiement de remise. Au lieu de cela, il peut envoyer un paiement incluant une déduction du montant de la remise. Pour traiter ce type de transaction, vous pouvez utiliser le workbench de déduction pour faire correspondre les déductions aux transactions de crédit en cours, déductions fractionnées, déductions refusées, et déductions annulées.

> [!NOTE]
> Le workbench de déduction fait partie des fonctionnalités de vente et de marketing de Microsoft Dynamics 365 Supply Chain Management depuis longtemps. Cependant, il a maintenant été amélioré de sorte qu’il fonctionne également avec le nouveau module **Gestion des remises**. Cette rubrique explique comment utiliser à la fois les anciennes fonctionnalités et les fonctionnalités de gestion des remises du workbench de déduction. Cependant, si vous n’avez pas [activé le module **Gestion des remises** pour votre système](rebate-management-enable.md), certaines des fonctionnalités décrites ici ne seront pas disponibles.

## <a name="prerequisites"></a>Conditions préalables

### <a name="set-up-the-old-deduction-management-system"></a>Configurer l’ancien système de gestion des déductions

Vous pouvez utiliser le workbench de déduction avec les anciennes fonctionnalités de gestion des déductions de Supply Chain Management, même si vous n’utilisez pas le **Gestion des remises**. Cependant, vous devez d’abord préparer votre système comme décrit dans cette section.

Avant d’utiliser le workbench de déductions, vous devez effectuer les tâches de paramétrage décrites dans [Paramétrer la gestion des déductions](/dynamicsax-2012/appuser-itpro/set-up-deduction-management). Vous devez également disposer d’un certain type d’accord de remise paramétré pour le client : soit une remise client, telle que décrite dans [Paramétrage et mise à jour des remises client](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-customer-rebates), ou une remise de reprise.

Si vous appliquez une déduction à une remise client, vous devez effectuer les tâches suivantes :

- [Configurez vos remises clients](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-customer-rebates).
- Approuver et traiter la remise, afin que vous puissiez utiliser le workbench des déductions.

Si vous appliquez une déduction à une remise de reprise, vous devez effectuer les tâches suivantes :

- Paramétrer des remises par facture rétroactive.
- Application des remises par facture rétroactive.

### <a name="configure-accounts-receivable-and-deductions"></a><a name="accounts-receivable-deductions"></a>Configuration des modules Comptabilité client et déductions

Le système enregistre tous les événements de déduction dans un journal des réclamations. Par conséquent, votre système doit inclure un journal qui peut être utilisé à cette fin. Si vous n’avez pas encore de journal des réclamations, configurez-le maintenant. Ce journal est nécessaire pour créer des retenues directement sur le workbench des retenues, le décompte client ou la page client.

Pour paramétrer un nouveau journal des réclamations, procédez comme suit.

1. Accédez à **Comptabilité \> Paramétrage du journal \> Noms des journaux**.
1. Sélectionner **Nouveau**, et définissez les champs suivants pour le nouveau nom de journal :

    - **Nom** – Permet d’entrer un nom unique pour le journal des réclamations.
    - **Description** – Permet d’entrer une brève description du nouveau journal.
    - **Type de journal** – Sélectionnez *Quotidien*.
    - **Souche de N° documents** – Attribuez une séquence de numéros existante. Vous pouvez également créer une séquence de numéros qui a une portée de société et l’affecter au nouveau nom de journal.

1. Accédez à **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.
1. Sur l’onglet **Déductions**, sur le raccourci **Général**, définissez le champ **Nom du journal des réclamations** sur le nom du journal que vous venez de créer.
1. Sur le raccourci **Ordre de retour**, définissez les champs suivants :

    - **Créer un ordre de retour** – Définissez cette option pour spécifier ce que le système doit faire lorsqu’une réclamation basée sur la quantité est approuvée :

        - *Oui* – Créez un ordre de retour.
        - *Non* – Créez une commande client négative.

    - **Création sans facture jointe** – Sélectionnez une valeur pour spécifier ce que le système doit faire lorsqu’une réclamation basée sur la quantité est approuvée mais qu’aucune facture n’est jointe :

        - *Accepter* – Créer un ordre de ordre de retour.
        - *Avertissement* – Créez un ordre de retour, mais affichez le message d’avertissement suivant : « La réclamation n’est pas jointe à une facture ».
        - *Erreur* – Ne créez pas d’ordre de retour, et affichez le message d’erreur suivant : « La réclamation n’est pas jointe à une facture. La mise à jour a été annulée."

    - **Créer un ordre de retour avant l’approbation de la déduction** – Réglez cette option sur *Oui* si des ordres de retour peuvent être créés avant que la réclamation ne soit approuvée. Ce paramètre s’applique uniquement aux réclamations basées sur la quantité pour lesquelles l’option **Créer un ordre de retour** est définie sur *Oui*.

### <a name="configure-general-ledger-parameters"></a>Configuration des paramètres de comptabilité

Lorsque le système crée un journal des réclamations pour une nouvelle déduction, il crée également deux nouvelles transactions client : une pour compenser le montant de la réclamation par rapport à la facture d’origine et une pour enregistrer la dette d’un client au montant de la réclamation (car la réclamation n’a pas été pas encore été approuvée). Par conséquent, vous devez configurer votre système de manière à ce qu’un seul justificatif puisse avoir plusieurs lignes client.

Pour permettre à un même justificatif d’avoir plusieurs lignes client, procédez comme suit.

1. Accédez à **Comptabilité \> Paramétrage de la comptabilité \> Paramètres de comptabilité**.
1. Sur l’onglet **Comptabilité**, sur le raccourci **Général**, définissez l’option **Autoriser plusieurs transactions au sein d’un même justificatif** sur *Oui*.
1. Si vous recevez un message d’avertissement, sélectionnez **Fermer** pour accepter le changement.

### <a name="create-deduction-reasons"></a><a name="deduction-reasons"></a>Créer des motifs de déduction

Le système exige que les utilisateurs spécifient un motif pour chaque déduction qu’ils saisissent directement sur le workbench des déductions, le décompte client ou la page client. La raison détermine comment la déduction est gérée lorsqu’elle est approuvée.

1. Aller à **Ventes et marketing \> Reprises \> Déductions \> Motifs de déduction**.
1. Sélectionnez **Nouveau** pour ajouter une ligne à la grille, puis définissez les champs suivants pour elle :

    - **Nom de la réclamation** – Permet d’entrer un nom unique pour la raison.
    - **Description** – entrez une description de la raison pour fournir plus d’informations sur la façon dont il doit être utilisé.
    - **Base de réclamation** – Sélectionnez une base de réclamation pour le motif de réclamation :

        - *Basé sur le prix* – Créer un avoir financier après approbation.
        - *Basé sur la quantité* – Créez une commande client négative ou un ordre de retour après approbation.

    - **Code de motif de retour** – Sélectionnez un code de motif de retour à appliquer comme valeur de **Code de motif de retour** pour l’ordre de retour.
    - **Type** – Permet de sélectionner un type de déduction. La valeur **Déduction compensée** du type sélectionné sera utilisée pour définir le champ **Déduction compensée** lorsqu’une déduction ou une réclamation est créée. Les types de déduction sont définis sur la page **Types de déduction** (**Ventes et marketing \> Reprises \> Déductions \> Types de déduction**).
    - **Réclamer le compte de validation** – Ce champ est disponible uniquement lorsque le champ **Base de réclamation** est défini sur *Basé sur le prix*. Lorsqu’une réclamation basée sur le prix est approuvée, le système affecte le compte général que vous sélectionnez ici comme valeur **Compte principal** du projet d’avoir financier.

### <a name="set-up-the-settle-approved-deductions-periodic-task"></a>Configurer la tâche périodique des déductions approuvées de règlement

Pour les déductions créées à l’aide de la commande **Nouvelle déduction** sur le workbench des déductions, le règlement client ou la page client, vous pouvez paramétrer la tâche périodique *Régler les déductions approuvées* pour faire correspondre automatiquement les déductions et les crédits qui ont des valeurs et des montants **ID de déduction** correspondants.

Pour planifier cette tâche, accédez à **Ventes et Marketing \> Tâches périodiques \> Régler les déductions approuvées**, et configurez des options, des filtres et un calendrier, comme pour les autres types de tâches périodiques.

> [!NOTE]
> Si l’option **Règlement automatique** est définie sur *Oui* sur l’onglet **Règlement** de la page **Paramètres des comptes clients** (**Comptabilité client \> Configurer \> Paramètres de la Comptabilité client**), la tâche périodique *Régler les déductions approuvées* ne fera rien, car le crédit sera automatiquement réglé.

## <a name="create-a-deduction"></a>Créer une déduction

### <a name="create-a-deduction-journal-entry-by-using-the-customer-payment-journal"></a>Créer une entrée de journal des déductions à l’aide du journal des paiements client

Pour créer une entrée de journal de déduction, procédez comme suit.

1. Accédez à **Comptabilité client \> Paiements \> Journal des paiements client**.
1. Cliquez sur **Nouveau** pour ajouter une ligne à la grille.
1. Dans le champ **Nom** pour la nouvelle ligne, sélectionnez le nom du journal.
1. Dans le volet Action, sélectionnez **Lignes**.
1. Entrez la date, le compte société et le numéro de compte client.
1. Dans le champ **Facture**, sélectionnez la facture à laquelle la déduction est associée.
1. Dans le champ **Crédit**, entrez le montant que le client a payé.
1. Cliquez sur **OK** pour confirmer que le montant est inférieur au montant total de la transaction marquée.
1. Sélectionnez le type de compte de contrepartie et le compte de contrepartie.
1. Dans la barre d’outils au-dessus de la grille, sélectionnez **Déductions**.
1. Dans la page **Déductions**, sur le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Le champ **ID de déduction** pour la nouvelle ligne est automatiquement défini.
1. Dans le champ **Type**, sélectionnez le type de déductions.
1. Dans le champ **Montant**, entrez le montant affiché dans le champ **Solde** au-dessous de la liste de déduction. Ce montant représente le montant que le client a déduit du paiement.
1. Fermez la page **Déduction**. Vous êtes renvoyé à la page **Paiements clients**, qui affiche maintenant une nouvelle ligne pour la déduction.
1. Sur le volet Action, sélectionnez **Valider \> Valider**. Vous devez recevoir le message suivant : « Le journal est correct. »
1. Dans le volet Actions, sélectionnez **Valider**.

### <a name="create-a-deduction-by-using-the-deduction-workbench"></a>Créer une déduction à l’aide du workbench de déduction

Créer une déduction sur le workbench de déduction, procédez comme suit.

1. Aller à **Ventes et marketing \> Reprises \> Déductions \> Workbench de déduction**.
1. Sur le volet Action, sélectionnez **Tenir à jour \> Nouvelle déduction**.

    Dans la boîte de dialogue **Nouvelle déduction**, le champ **ID de déduction** est défini en fonction de la séquence de nombres **ID de déduction** définie sur la page **Paramètres de Gestion des reprises** (**Ventes et marketing \> Configurer \> Reprises \> Paramètres Gestion des reprises**).

1. Définissez les champs suivants :

    - **Compte client** – Sélectionnez le compte client auquel s’applique la déduction.
    - **Numéro de réclamation externe** – Saisissez la référence de la réclamation du client.
    - **Montant de la réclamation** – Saisissez le montant de la réclamation TTC. La valeur doit être positive.
    - **Devise** – Sélectionnez la devise de la déduction. La valeur par défaut est la devise définie pour le compte client sélectionné.
    - **Base de réclamation** – Sélectionnez la base de réclamation. La base de réclamation détermine le type de transaction de crédit qui est créé après l’approbation de la déduction ou de la réclamation.

        - *Basé sur le prix* – Un projet de facture financière sera créé.
        - *Basé sur la quantité* – Une commande client négative ou un ordre de retour sera créé.

    - **Date de réclamation** – Sélectionnez la date de la réclamation. La valeur par défaut est la date actuelle.
    - **Motif de la réclamation** – Sélectionnez le code de motif qui s’applique à la déduction actuelle. La base de réclamation que vous avez sélectionnée affecte les options qui s’appliquent. Pour plus d’informations sur la création et la configuration des motifs de réclamation qui peuvent être sélectionnés ici, consultez la section [Créer des motifs de déduction](#deduction-reasons) plus haut dans cette rubrique.
    - **Remarques** – Ajoutez toutes les remarques qui s’appliquent. Une fois la réclamation approuvée, l’approbateur pourra modifier ou compléter les notes de la réclamation.
    - **Créer un journal des réclamations** – Définissez cette option pour spécifier si le journal des réclamations doit être créé lors de la création de la réclamation ou de la déduction :

        - *Oui* – Le système créera et publiera un journal général en utilisant le journal des réclamations configuré sur la page **Paramètres de la Comptabilité client**. (Pour plus d’informations, consultez la section [Configurer la Comptabilité client et les déductions](#accounts-receivable-deductions) plus haut dans cette rubrique.) Lorsqu’une facture est jointe à la réclamation, le journal des réclamations est utilisé pour réduire le solde de la facture applicable. Si la réclamation est rejetée par la suite, le journal des réclamations et les règlements (si une facture était jointe) seront annulés.
        - *Non* – Aucun journal des réclamations n’est créé pour le moment. Il sera créé lorsque la demande sera approuvée. Une facture peut toujours être jointe à la nouvelle réclamation, même si aucun journal des réclamations n’est créé. Cependant, le règlement ne peut se faire sans le journal des réclamations.

1. Cliquez sur **OK**.

    Une nouvelle déduction est créée. Si vous définissez l’option **Créer un journal des réclamations** sur *Oui*, les transactions suivantes sont enregistrées :

    - **Deux nouvelles transactions clients** – Une transaction compense le montant de la réclamation par rapport à la facture originale. L’autre transaction enregistre la dette d’un client sur le montant de la réclamation, car la réclamation n’a pas encore été approuvée. La transaction de facture d’origine et la transaction de demande de compensation seront automatiquement marquées pour règlement lorsque vous joignez la facture en sélectionnant **Tenir à jour \> Joindre la facture** dans le volet Actions.
    - **Deux transactions compensatoires** – Ces transactions sont enregistrées dans le compte général **Déduction compensée**.
    - **Journal des réclamations** – Pour afficher le journal des réclamations pour chaque déduction qui est affichée sur le Workbench des déductions, sélectionnez l’onglet **Références**. Le journal des réclamations est affiché dans le champ **Numéro de lot du journal**. Vous pouvez également consulter le journal des réclamations sur l’onglet **Événements de déduction**. Là, il aura une valeur **Type de mise à jour** de *Mettre en correspondance*.

### <a name="create-a-deduction-from-a-customer-settlement"></a>Créer une déduction d’un règlement client

Le processus de création d’une déduction à partir d’un règlement client ressemble au processus de création d’une déduction au moyen du workbench de déduction. Cependant, le client et la devise de facturation sont définis automatiquement et la facture est jointe. Vous n’avez pas à sélectionner **Tenir à jour \> Joindre la facture** dans le volet Actions lorsque vous créez une réclamation ou une déduction au moyen de la page de règlement client.

1. Allez dans **Comptabilité client \> Clients \> Tous les clients**.
1. Sélectionnez le client pour lequel créer une déduction.
1. Dans le volet Actions, sous l’onglet **Collecter**, dans le groupe **Règlement**, sélectionnez **Régler des transactions**.
1. Dans la boîte de dialogue **Paramétrage des transactions**, sur l’onglet **Présentation**, sélectionnez la facture sur laquelle créer la déduction.
1. Dans la barre d’outils, sélectionnez **Déductions \> Nouvelle déduction**.

    Dans la boîte de dialogue **Nouvelle déduction**, le champ **ID de déduction** est défini en fonction de la séquence de nombres **ID de déduction** définie sur la page **Paramètres de Gestion des reprises** (**Ventes et marketing \> Configurer \> Reprises \> Paramètres Gestion des reprises**). Le champ **Compte client** est défini sur le compte client auquel s’applique la déduction.

1. Définissez les champs suivants :

    - **Numéro de réclamation externe** – Saisissez la référence de la réclamation du client.
    - **Montant de la réclamation** – Saisissez le montant de la réclamation TTC. La valeur doit être positive.
    - **Devise** – Sélectionnez la devise de la déduction. La valeur par défaut est la devise définie pour le compte client sélectionné.
    - **Base de réclamation** – Sélectionnez la base de réclamation. La base de réclamation détermine le type de transaction de crédit qui est créé après l’approbation de la déduction ou de la réclamation.

        - *Basé sur le prix* – Un projet de facture financière sera créé.
        - *Basé sur la quantité* – Une commande client négative ou un ordre de retour sera créé.

    - **Date de réclamation** – Sélectionnez la date de la réclamation. La valeur par défaut est la date actuelle.
    - **Motif de la réclamation** – Sélectionnez le code de motif qui s’applique à la déduction actuelle. La base de réclamation que vous avez sélectionnée affecte les options qui s’appliquent. Pour plus d’informations sur la création et la configuration des motifs de réclamation qui peuvent être sélectionnés ici, consultez la section [Créer des motifs de déduction](#deduction-reasons) plus haut dans cette rubrique.
    - **Remarques** – Ajoutez toutes les remarques qui s’appliquent. Une fois la réclamation approuvée, l’approbateur pourra modifier ou compléter les notes de la réclamation.
    - **Créer un journal des réclamations** – Définissez cette option pour spécifier si le journal des réclamations doit être créé lors de la création de la réclamation ou de la déduction :

        - *Oui* – Le système créera et publiera un journal général en utilisant le journal des réclamations configuré sur la page **Paramètres de la Comptabilité client**. (Pour plus d’informations, consultez la section [Configurer la Comptabilité client et les déductions](#accounts-receivable-deductions) plus haut dans cette rubrique.) Lorsqu’une facture est jointe à la réclamation, le journal des réclamations est utilisé pour réduire le solde de la facture applicable. Si la réclamation est rejetée par la suite, le journal des réclamations et les règlements (si une facture était jointe) seront annulés.
        - *Non* – Aucun journal des réclamations n’est créé pour le moment. Il sera créé lorsque la demande sera approuvée. Une facture peut toujours être jointe à la nouvelle réclamation, même si aucun journal des réclamations n’est créé. Cependant, le règlement ne peut se faire sans le journal des réclamations.

1. Cliquez sur **OK**.

    Une nouvelle déduction est créée. Si vous définissez l’option **Créer un journal des réclamations** sur *Oui*, les transactions suivantes sont enregistrées :

    - **Deux nouvelles transactions clients** – Une transaction compense le montant de la réclamation par rapport à la facture originale. L’autre transaction enregistre la dette d’un client sur le montant de la réclamation, car la réclamation n’a pas encore été approuvée. La transaction de facture d’origine et la transaction de demande de compensation seront automatiquement marquées pour règlement lorsque vous joignez la facture en sélectionnant **Tenir à jour \> Joindre la facture** dans le volet Actions.
    - **Deux transactions compensatoires** – Ces transactions sont enregistrées dans le compte général **Déduction compensée**.
    - **Journal des réclamations** – Pour afficher le journal des réclamations pour chaque déduction qui est affichée sur le Workbench des déductions, sélectionnez l’onglet **Références**. Le journal des réclamations est affiché dans le champ **Numéro de lot du journal**. Vous pouvez également consulter le journal des réclamations sur l’onglet **Événements de déduction**. Là, il aura une valeur **Type de mise à jour** de *Mettre en correspondance*.

    Vous êtes renvoyé à la page **Régler les opérations**, qui affiche maintenant la facture sélectionnée comme marquée. Le bouton **Valider** n’est disponible que si vous définissez l’option **Créer un journal des réclamations** sur *Oui*. S’il est disponible, sélectionnez **Valider** pour réduire le solde de la facture de la valeur **Montant de la réclamation**.

### <a name="create-a-deduction-from-a-customer-page"></a>Créer une déduction d’une page client

Le processus de création d’une déduction à partir d’une page client ressemble au processus de création d’une déduction au moyen du workbench de déduction. Cependant, le client est automatiquement défini.

1. Allez dans **Comptabilité client \> Clients \> Tous les clients**.
1. Sélectionnez le client pour lequel créer une déduction.
1. Dans le volet Actions, sous l’onglet **Collecter**, dans le groupe **Déductions**, sélectionnez **Créer des déductions**.

    Dans la boîte de dialogue **Nouvelle déduction**, le champ **ID de déduction** est défini en fonction de la séquence de nombres **ID de déduction** définie sur la page **Paramètres de Gestion des reprises** (**Ventes et marketing \> Configurer \> Reprises \> Paramètres Gestion des reprises**). Le champ **Compte client** est défini sur le compte client auquel s’applique la déduction.

1. Définissez les champs suivants :

    - **Numéro de réclamation externe** – Saisissez la référence de la réclamation du client.
    - **Montant de la réclamation** – Saisissez le montant de la réclamation TTC. La valeur doit être positive.
    - **Devise** – Sélectionnez la devise de la déduction. La valeur par défaut est la devise définie pour le compte client sélectionné.
    - **Base de réclamation** – Sélectionnez la base de réclamation. La base de réclamation détermine le type de transaction de crédit qui est créé après l’approbation de la déduction ou de la réclamation.

        - *Basé sur le prix* – Un projet de facture financière sera créé.
        - *Basé sur la quantité* – Une commande client négative ou un ordre de retour sera créé.

    - **Date de réclamation** – Sélectionnez la date de la réclamation. La valeur par défaut est la date actuelle.
    - **Motif de la réclamation** – Sélectionnez le code de motif qui s’applique à la déduction actuelle. La base de réclamation que vous avez sélectionnée affecte les options qui s’appliquent. Pour plus d’informations sur la création et la configuration des motifs de réclamation qui peuvent être sélectionnés ici, consultez la section [Créer des motifs de déduction](#deduction-reasons) plus haut dans cette rubrique.
    - **Remarques** – Ajoutez toutes les remarques qui s’appliquent. Une fois la réclamation approuvée, l’approbateur pourra modifier ou compléter les notes de la réclamation.
    - **Créer un journal des réclamations** – Définissez cette option pour spécifier si le journal des réclamations doit être créé lors de la création de la réclamation ou de la déduction :

        - *Oui* – Le système créera et publiera un journal général en utilisant le journal des réclamations configuré sur la page **Paramètres de la Comptabilité client**. (Pour plus d’informations, consultez la section [Configurer la Comptabilité client et les déductions](#accounts-receivable-deductions) plus haut dans cette rubrique.) Lorsqu’une facture est jointe à la réclamation, le journal des réclamations est utilisé pour réduire le solde de la facture applicable. Si la réclamation est rejetée par la suite, le journal des réclamations et les règlements (si une facture était jointe) seront annulés.
        - *Non* – Aucun journal des réclamations n’est créé pour le moment. Il sera créé lorsque la demande sera approuvée. Une facture peut toujours être jointe à la nouvelle réclamation, même si aucun journal des réclamations n’est créé. Cependant, le règlement ne peut se faire sans le journal des réclamations.

1. Cliquez sur **OK**.

    Une nouvelle déduction est créée. Si vous définissez l’option **Créer un journal des réclamations** sur *Oui*, les transactions suivantes sont enregistrées :

    - **Deux nouvelles transactions clients** – Une transaction compense le montant de la réclamation par rapport à la facture originale. L’autre transaction enregistre la dette d’un client sur le montant de la réclamation, car la réclamation n’a pas encore été approuvée. La transaction de facture d’origine et la transaction de demande de compensation seront automatiquement marquées pour règlement lorsque vous joignez la facture en sélectionnant **Tenir à jour \> Joindre la facture** dans le volet Actions.
    - **Deux transactions compensatoires** – Ces transactions sont enregistrées dans le compte général **Déduction compensée**.
    - **Journal des réclamations** – Pour afficher le journal des réclamations pour chaque déduction qui est affichée sur le Workbench des déductions, sélectionnez l’onglet **Références**. Le journal des réclamations est affiché dans le champ **Numéro de lot du journal**. Vous pouvez également consulter le journal des réclamations sur l’onglet **Événements de déduction**. Là, il aura une valeur **Type de mise à jour** de *Mettre en correspondance*.

## <a name="create-a-credit-note-for-a-customer"></a>Création d’un avoir pour un client

Lorsqu’une remise approuvée existe pour un client, vous pouvez créer un avoir dans le compte client pour représenter la remise, comme requis. Le crédit apparaît alors sur le workbench de déduction, dans lequel il peut être mis en correspondance avec une déduction.

Pour créer un avoir, procédez comme suit.

1. Allez dans **Ventes et marketing \> Clients \> Tous les clients**.
1. Sélectionnez le client
1. Dans le volet Actions, sous l’onglet **Collecter**, dans le groupe **Règlement**, sélectionnez **Régler des transactions**.
1. Dans la boîte de dialogue **Régler les transactions**, sélectionnez la transaction à laquelle la remise a été appliqué.
1. Dans la barre d’outils, sur le menu **Fonctions**, sélectionnez le type de programme de remises qui s’applique.
1. Sur la page **Remise**, sur l’onglet **Présentation**, cochez la case **Marquer** à côté de l’ID de remise pertinent.
1. Dans le volet Actions, sélectionnez **Fonctions \> Créer un avoir**.

## <a name="process-a-deduction-on-the-deduction-workbench"></a>Traiter une déduction sur le workbench de déduction

Sur le workbench de déduction, vous pouvez faire correspondre les déductions aux transactions de crédit en cours, déductions fractionnées, déductions refusées, et déductions annulées.

Selon la façon dont vous souhaitez traiter une déduction, exécutez une ou plusieurs des procédures des sous-sections suivantes. Vous pouvez combiner les procédures, au besoin. Par exemple, vous pouvez fractionner une déduction en deux parties, puis faire correspondre une partie à un crédit mais laisser la partie restante sur le workbench afin de la mettre en correspondance avec un autre crédit ultérieurement. Vous pouvez également mettre en correspondance une déduction avec un crédit inférieur au montant de déduction, puis refuser ou annuler le solde de la déduction.

### <a name="match-a-deduction-to-a-credit"></a>Faire correspondre une déduction à un crédit

Pour faire correspondre une déduction à un crédit, procédez comme suit.

1. Aller à **Ventes et marketing \> Reprises \> Déductions \> Workbench de déduction**.
1. Case à cocher **Marquer** en regard de la déduction à traiter.
1. Dans la section **Transactions ouvertes**, cochez la case **Marquer** pour que le crédit corresponde à la déduction. Si plusieurs crédits sont répertoriés, vous pouvez sélectionner plusieurs crédits à faire correspondre à la déduction. Si vous souhaitez que le système sélectionne automatiquement les crédits correspondant au montant de la déduction, dans la barre d’outils, sélectionnez une option appropriée sur le menu **Sélectionner le montant de la déduction**.
1. Dans le volet Actions, cliquez sur **Tenir à jour \> Mettre en correspondance**. Le système met en correspondance la déduction et le crédit. S’il reste un solde dans la déduction, il est indiqué dans le champ **Montant restant** sur l’onglet **Déductions**.

    > [!NOTE]
    > Pour les déductions qui ont été créées à l’aide de la commande **Nouvelle déduction** sur le workbench des déductions, le règlement client ou la page client, la commande **Tenir à jour \> Mettre en correspondance** n’est disponible que si le champ **Statut de la réclamation** est défini sur *Accepté*. Cette commande peut être utilisée pour faire correspondre manuellement la transaction basée sur le prix ou la quantité au crédit associé dans la section **Transactions ouvertes**. Ce crédit est créé soit au moment de l’approbation de la déduction (en utilisant la commande **Tenir à jour \> Approuver la déduction**), ou lorsqu’il est rattaché à un crédit existant tel que décrit dans la section [Crédits créés en dehors du processus d’approbation de déduction](#credits-outside-approval) plus loin dans cette rubrique. La tâche périodique *Régler les déductions approuvées* (**Ventes et Marketing \> Tâches périodiques \> Régler les déductions approuvées**) peut également être utilisée pour mettre automatiquement en correspondance les déductions et les crédits ayant des valeurs et montants **ID de déduction** correspondants.

### <a name="split-a-deduction"></a>Fractionner une déduction

Pour fractionner une déduction, procédez comme suit.

1. Aller à **Ventes et marketing \> Reprises \> Déductions \> Workbench de déduction**.
1. Case à cocher **Marquer** en regard de la déduction à traiter.
1. Dans le volet Actions, cliquez sur **Tenir à jour \> Fractionner**.
1. Dans la boîte de dialogue **fractionner**, dans le champ **Montant fractionné**, saisissez le montant à fractionner de la déduction principale. Puis sélectionnez **OK**.
1. Sous l’onglet **Déductions**, notez qu’un nouvel enregistrement s’affiche pour le montant fractionné. L’enregistrement de déduction d’origine contient le reste du solde de déduction. Vous pouvez désormais gérer les deux parties de la remise d’origine séparément.
1. Sélectionnez l’enregistrement de déduction d’origine, puis sélectionnez l’onglet **Références**. Le champ **Montant fractionné** indique le montant fractionné du montant d’origine.

### <a name="attach-an-invoice-to-a-deduction"></a>Joindre une facture à une déduction

Vous pouvez joindre une facture à une déduction si la déduction a été créée en utilisant la commande **Nouvelle déduction** sur le Workbench des déductions, le règlement client ou la page client, et si aucune facture n’y est actuellement jointe (c’est-à-dire la colonne **Facture** est vide).

Pour joindre une facture à une déduction, procédez comme suit.

1. Aller à **Ventes et marketing \> Reprises \> Déductions \> Workbench de déduction**.
1. Case à cocher **Marquer** en regard de la déduction à traiter.
1. Sur le volet Action, sélectionnez **Tenir à jour \> Joindre une facture**.
1. Dans la boîte de dialogue **Joindre une facture**, sélectionnez une facture, puis sélectionnez **OK**.
1. Dans la boîte de dialogue **Régler les transactions**, suivez l’une de ces étapes, selon qu’un journal des réclamations a été comptabilisé ou non lors de la création de la déduction :

    - Si un journal des réclamations a été validé, la facture que vous avez sélectionnée et la transaction de crédit client du journal des réclamations affichent une coche dans la colonne **Marquer**. Sélectionnez **Valider**. Le solde restant sur la facture jointe est déduit du montant de la réclamation.
    - Si un journal des réclamations n’a pas été enregistré, aucune transaction n’affiche une coche dans la colonne **Marquer**. Étant donné que vous ne pouvez pas contrepasser avec un journal des réclamations tant que la déduction n’est pas approuvée, sélectionnez **Annuler**.

### <a name="detach-an-invoice-from-a-deduction"></a>Détacher une facture d’une déduction

Vous pouvez détacher une facture d’une déduction si la déduction a été créée en utilisant la commande **Nouvelle déduction** sur le Workbench des déductions, le règlement client ou la page client, et si une facture n’y est actuellement jointe (c’est-à-dire la colonne **Facture** affiche un numéro facture) et si le champ **Statut de la réclamation** est défini sur *Ouvert*. Vous pouvez effectuer cette tâche, car une facture incorrecte a été jointe. La facture est supprimée de la déduction, et son solde restant est mis à jour s’il a été réduit lorsque la facture a été jointe.

Pour détacher une facture, procédez comme suit.

1. Aller à **Ventes et marketing \> Reprises \> Déductions \> Workbench de déduction**.
1. Case à cocher **Marquer** en regard de la déduction à traiter.
1. Sur le volet Action, sélectionnez **Tenir à jour \> Détacher une facture**.

### <a name="approve-a-deduction"></a>Approuver une déduction

Vous pouvez approuver les déductions créées en utilisant la commande **Nouvelle déduction** sur le Workbench des déductions, le règlement client ou la page client. Cependant, vous ne pouvez approuver que les déductions lorsque le champ **Statut de la réclamation** est défini sur *Ouvert*.

Pour approuver une déduction, procédez comme suit.

1. Aller à **Ventes et marketing \> Reprises \> Déductions \> Workbench de déduction**.
1. Case à cocher **Marquer** en regard de la déduction à traiter.
1. Sur le volet Action, sélectionnez **Tenir à jour \> Approuver la déduction**.
1. Dans la boîte de dialogue **Approuver la déduction**, modifiez ou ajoutez des informations à la valeur **Note** au besoin.
1. Si la déduction est basée sur le prix et qu’aucune facture n’y a été jointe, sélectionnez un groupe de taxe d’article. En règle générale, le groupe d’articles de taxe est défini sur la facture. Par conséquent, le code article de taxe doit être spécifié lorsqu’il n’est pas joint à une facture.
1. Cliquez sur **OK**.

    À ce stade, aucune autre modification ne peut être apportée à la déduction. Si l’option **Créer un journal des réclamations** a été définie sur *Non* lorsque la déduction a été créée, le journal des réclamations est créé et enregistré lorsque la déduction est approuvée. Une fois la déduction approuvée, le crédit est automatiquement créé et ouvert. Le type dépend de la valeur **Base de réclamation** de la déduction :

    - *Basé sur le prix* – Si la déduction est basée sur le prix, une facture financière est créée pour le compte client. Vous pouvez ajouter une description et publier le crédit. Les champs suivants sont remplis par la déduction lors de la création du brouillon :

        - **ID déduction** – Ce champ est ajouté à l’en-tête pour permettre la traçabilité jusqu’à la déduction.
        - **Compte principal** – La valeur est déterminée par la valeur **Compte validation réclamation** qui est définie pour le motif de la déduction qui est affecté à la déduction.
        - **Groupe de taxe d’article** – La valeur est déterminée par la facture jointe ou par la valeur que vous avez sélectionnée lorsque vous avez approuvé la déduction.
        - **Prix unitaire** – La valeur est le crédit du montant réclamé de la déduction.
        - **Texte de la facture** – Par défaut, ce champ est défini sur la valeur **Notes** de la déduction.

    - *Basé sur la quantité* – Si la déduction est basée sur la quantité, une commande client ou un ordre de retour en cours est créé. Le paramètre **Créer un ordre de retour** sur la page **[Paramètres des comptes clients](#accounts-receivable-deductions)** détermine si une commande client ou un ordre de retour est créé lorsque la déduction est approuvée. La page **Copier les commandes** apparaît et est filtrée pour afficher les lignes où le champ **Compte de facturation** est défini sur le compte client de la déduction. Procédez comme suit :

        1. Sur le raccourci **Factures**, la section **En-têtes** affiche les factures de vente où la valeur **Compte de facturation** correspond au compte client de la déduction. Sélectionnez une facture de vente applicable.
        1. La section **Lignes** affiche les lignes de la facture de vente sélectionnée. Cochez la case **Sélectionner** des lignes que vous souhaitez copier. Sinon, dans la section **En-têtes**, cochez la case **Sélectionner tout** de la commande client pour sélectionner toutes ses lignes.
        1. Ajustez la valeur **Quantité** pour une ou plusieurs lignes selon les besoins.

            Toutes les lignes que vous avez sélectionnées jusqu’à présent sont répertoriées sur le raccourci **Lignes sélectionnées ou en-tête à copier**.

        1. Répétez les deux étapes précédentes au besoin jusqu’à ce que toutes les lignes requises soient répertoriées sur le raccourci **Lignes sélectionnées ou en-tête à copier**.
        1. Cliquez sur **OK**.

            Le nouvel ordre de retour est ouvert et les champs suivants sont automatiquement définis :

            - **ID déduction** – Ce champ est ajouté à l’en-tête pour permettre la traçabilité jusqu’à la déduction.
            - **Code de motif de retour** – Par défaut, ce champ est défini sur la valeur **Code de motif de retour** qui est définie pour le motif de la déduction qui est affecté à la déduction.

Une fois le crédit facturé, il apparaît dans la section **Opérations ouvertes** du Workbench des déductions par rapport à la valeur **ID déduction**, et son champ **Type de réclamation** est défini sur *Autres crédits*. Le crédit sera disponible jusqu’à ce qu’il soit réglé avec la déduction de l’une des manières suivantes :

- Vous le réglez manuellement en sélectionnant **Tenir à jour \> Mettre en correspondance** dans le volet Actions.
- Il est automatiquement réglé par la tâche périodique *Régler les réclamations approuvées* (**Ventes et marketing \> Tâches périodiques \> Régler les réclamations approuvées**).
- Il est réglé automatiquement parce que l’option **Règlement automatique** sur l’onglet **Règlement** de la page **Paramètres des comptes clients** est définie sur *Oui*.

Pour consulter le crédit qui est créé lorsque la déduction est approuvée, vous pouvez également utiliser le bouton **Crédit ouvert** dans la section **Opérations ouvertes** du Workbench de déduction.

### <a name="create-a-return-order"></a>Création d’un ordre de retour

Vous pouvez créer un ordre de retour pour les déductions créées en utilisant la commande **Nouvelle déduction** sur le Workbench des déductions, le règlement client ou la page client. Toutefois, toutes les conditions suivantes doivent être remplies :

- Le champ **Base de réclamation** est défini sur *Basé sur la quantité*.
- Le champ **Statut de la réclamation** est défini sur *Ouvert*.
- L’option **Créer un ordre de retour** sur l’onglet **Déductions** de la page **[Paramètres des comptes clients](#accounts-receivable-deductions)** est définie sur *Oui*.
- L’option **Créer un ordre de retour avant l’approbation de la déduction** sur l’onglet **Déductions** de la page **[Paramètres des comptes clients](#accounts-receivable-deductions)** est définie sur *Oui*.

Pour créer un ordre de retour, procédez comme suit.

1. Aller à **Ventes et marketing \> Reprises \> Déductions \> Workbench de déduction**.
1. Case à cocher **Marquer** en regard de la déduction à traiter.
1. Dans le volet Actions, sélectionnez **Tenir à jour \> Créer ordre de retour**.
1. Dans la boîte de dialogue **Approuver la déduction**, modifiez ou ajoutez des informations à la valeur **Notes** existante au besoin, puis cliquez sur **OK**.
1. Dans la boîte de dialogue **Copier les commandes** sur le raccourci **Factures**, la section **En-têtes** affiche les factures de vente où la valeur **Compte de facturation** correspond au compte client de la déduction. Sélectionnez une facture de vente applicable.
1. La section **Lignes** affiche les lignes de la facture de vente sélectionnée. Cochez la case **Sélectionner** des lignes à copier. Sinon, dans la section **En-têtes**, cochez la case **Sélectionner tout** de la commande client pour sélectionner toutes ses lignes.
1. Ajustez la valeur **Quantité** pour une ou plusieurs lignes selon les besoins.

    Toutes les lignes que vous avez sélectionnées jusqu’à présent sont répertoriées sur le raccourci **Lignes sélectionnées ou en-tête à copier**.

1. Répétez les deux étapes précédentes au besoin jusqu’à ce que toutes les lignes requises soient répertoriées sur le raccourci **Lignes sélectionnées ou en-tête à copier**.
1. Cliquez sur **OK**.

    Le nouvel ordre de retour est ouvert et les champs suivants sont automatiquement définis :

    - **ID déduction** – Ce champ est ajouté à l’en-tête pour permettre la traçabilité jusqu’à la déduction.
    - **Code de motif de retour** – Par défaut, ce champ est défini sur la valeur **Code de motif de retour** qui est définie pour le motif de la déduction qui est affecté à la déduction.

### <a name="deny-a-deduction"></a>Refuser une déduction

Pour refuser une déduction, procédez comme suit.

1. Aller à **Ventes et marketing \> Reprises \> Déductions \> Workbench de déduction**.
1. Case à cocher **Marquer** en regard de la déduction à traiter.
1. Dans le volet Actions, cliquez sur **Tenir à jour \> Refuser**.
1. Dans la boîte de dialogue **Refuser**, sélectionnez le code de motif du refus, puis sélectionnez **OK**.
1. Dans le champ **Afficher** en dessous du volet Actions, sélectionnez *Clôturé*.

    L’onglet **Déductions** affiche la déduction refusée, et le champ **Montant restant** pour la déduction est défini sur *0,00*.

    Pour les déductions créées en utilisant la commande **Nouvelle déduction** sur le Workbench des déductions, le règlement client ou la page client, les événements suivants se produisent.

    - Sur l’onglet **Références**, les champs dans la section **Refus** sont mis à jour.
    - Si vous avez choisi de créer le journal des réclamations lors de la création de la déduction, et si une facture a été jointe à la déduction qui a réduit le solde de la facture, la facture est détachée et le solde restant de la facture précédemment jointe est augmenté du montant de la réclamation rejetée.
    - Le champ **Statut** de la déduction est défini sur *Clôturé*.
    - Le champ **Statut de la réclamation** de la déduction est défini sur *Rejeté*.

Pour annuler un refus, procédez comme suit.

1. Sur l’onglet **Déductions**, sélectionnez une déduction refusée.
1. Dans le volet Actions, sélectionnez **Annuler le refus**.

    Pour les déductions créées en utilisant la commande **Nouvelle déduction** sur le Workbench des déductions, le règlement client ou la page client, les événements suivants se produisent.

    - Sur l’onglet **Références**, les champs dans la section **Refus** sont mis à jour.
    - Le champ **Statut** de la déduction est défini sur *Ouvert*.
    - Le champ **Statut de la réclamation** de la déduction est défini sur *Ouvert*.

### <a name="write-off-a-deduction"></a>Annulation d’une déduction

Pour annuler une déduction, procédez comme suit.

1. Aller à **Ventes et marketing \> Reprises \> Déductions \> Workbench de déduction**.
1. Case à cocher **Marquer** en regard de la déduction à traiter.
1. Dans le volet Actions, cliquez sur **Tenir à jour \> Annuler**.
1. Dans la boîte de dialogue **Annuler**, sélectionnez le code de motif de l’annulation, puis sélectionnez **OK**.
1. Dans le champ **Afficher**, sélectionnez *Clôturé*.

    L’onglet **Déductions** affiche la déduction annulée, et le champ **Montant restant** pour la déduction est défini sur *0,00*.

    Pour les déductions créées en utilisant la commande **Nouvelle déduction** sur le Workbench des déductions, le règlement client ou la page client, les événements suivants se produisent.

    - Sur l’onglet **Références**, les champs dans la section **Annulation** sont mis à jour.
    - Si vous avez créé le journal des réclamations au moment de la création de la déduction, un journal des réclamations est enregistré dans le code de motif d’annulation de la déduction. Vous pouvez consulter cette écriture sur l’onglet **Événements de déduction**, où il comporte une valeur **Mettre à jour le type** de *Annuler*.
    - Le champ **Statut** de la déduction est défini sur *Clôturé*
    - Le champ **Statut de la réclamation** de la déduction est défini sur *Annulé*.

Pour restaurer une annulation, procédez comme suit.

1. Sur l’onglet **Déductions**, sélectionnez une déduction refusée.
1. Dans le volet Actions, cliquez sur **Restaurer une annulation**.

    Pour les déductions créées en utilisant la commande **Nouvelle déduction** sur le Workbench des déductions, le règlement client ou la page client, les événements suivants se produisent.

    - Sur l’onglet **Références**, les champs dans la section **Annulation** sont mis à jour.
    - Si vous avez créé le journal des réclamations au moment de la création de la déduction, un journal des réclamations est enregistré dans le code de motif d’annulation de la déduction. Vous pouvez consulter cette écriture sur l’onglet **Événements de déduction**, où il comporte une valeur **Mettre à jour le type** de *Restaurer une annulation*.
    - Le champ **Statut** de la déduction est défini sur *Ouvert*.
    - Le champ **Statut de la réclamation** de la déduction est défini sur *Ouvert*.

## <a name="credits-created-outside-the-approve-deduction-process"></a><a name="credits-outside-approval"></a>Crédits créés en dehors du processus d’approbation de déduction

Cette section s’applique uniquement aux déductions créées en utilisant la commande **Nouvelle déduction** sur le Workbench des déductions, le règlement client ou la page client.

Différents utilisateurs peuvent déjà avoir créé une facture financière, un ordre de retour ou une commande client négative pour la réclamation d’un client en dehors du processus **Approuver la déduction**. Lorsque la déduction existante est approuvée sur le Workbench des déductions, le système crée automatiquement une autre facture financière, un ordre de retour ou une commande client négative. Cette section décrit comment rattacher des crédits existants à une déduction avant que la déduction ne soit approuvée, afin d’éviter les crédits en double.

### <a name="attach-a-credit-to-deduction"></a>Joindre un crédit à une déduction

Cette section décrit comment vous pouvez attacher un crédit à une déduction du crédit.

Une fois un crédit joint à la déduction, vous pouvez l’afficher à l’aide du bouton **Crédit ouvert** sur la barre d’outils de la section **Opérations ouvertes** du Workbench de déduction.

Une fois un crédit facturé et que la déduction est approuvée, le crédit apparaît dans la section **Opérations ouvertes** du Workbench des déductions par rapport à la valeur **ID déduction**, et son champ **Type de réclamation** est défini sur *Autres crédits*.

#### <a name="attach-a-free-text-invoice-to-a-deduction"></a>Joindre une facture financière à une déduction

Pour joindre une facture financière à une déduction, procédez comme suit.

1. Allez dans **Comptabilité client \> Factures \> Toutes factures financières**.
1. Sélectionnez la facture pouvant être lettrée.
1. Dans le volet Actions, sous l’onglet **Facture**, sélectionnez **Joindre un crédit à la déduction**. Cet bouton est uniquement disponible si le champ **ID déduction** de la facture financière est vide. Un champ vide indique que la facture financière n’est pas déjà associée à une déduction.
1. Sur la page **Joindre le crédit à la déduction**, vous pouvez sélectionner *une* déduction. Seules les déductions *basées sur les prix* ouvertes sont disponibles pour la sélection.
1. Cliquez sur **OK**. Le champ **ID déduction** est défini sur l’en-tête de la facture financière.

#### <a name="attach-a-return-order-to-a-deduction"></a>Joindre un ordre de retour à une déduction

Pour joindre un ordre de retour à une déduction, procédez comme suit.

1. Allez dans **Comptabilité client \> Commandes \> Tous les ordres de retour**.
1. Sélectionnez le numéro d’autorisation de retour de marchandise (RMA) reçu ou ouvert applicable.
1. Dans le volet Actions, sous l’onglet **Ordre de retour**, sélectionnez **Joindre un crédit à la déduction**. Cet bouton est uniquement disponible si le champ **ID déduction** de l’ordre de retour est vide. Un champ vide indique que l’ordre de retour n’est pas déjà associé à une déduction.
1. Sur la page **Joindre le crédit à la déduction**, vous pouvez sélectionner *une* déduction. Seules les déductions *basées sur la quantité* ouvertes sont disponibles pour la sélection.
1. Cliquez sur **OK**. Le champ **ID déduction** est défini sur l’en-tête de l’ordre de retour.

#### <a name="attach-a-sales-order-to-a-deduction"></a>Joindre une commande client à une déduction

Pour joindre une commande client à une déduction, procédez comme suit.

1. Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client**.
1. Sélectionnez la commande client ouverte, livrée ou facturée applicable.
1. Dans le volet Actions, sous l’onglet **Facture**, sélectionnez **Joindre un crédit à la déduction**. Cet bouton est uniquement disponible si le champ **ID déduction** de la commande client est vide. Un champ vide indique que la commande client n’est pas déjà associé à une déduction.
1. Sur la page **Joindre la déduction**, vous pouvez sélectionner *une* déduction. Seules les déductions *basées sur la quantité* ouvertes sont disponibles pour la sélection.
1. Cliquez sur **OK**. Le champ **ID déduction** est défini sur l’en-tête de la commande client.

#### <a name="detach-a-deduction-from-a-credit"></a>Détacher une déduction d’un crédit

Si la déduction incorrecte a été jointe, vous pouvez la détacher du crédit. Toutefois, toutes les conditions suivantes doivent être remplies :

- Un crédit est attaché à la déduction.
- Le champ **Statut de la réclamation** est défini sur *Ouvert*.

Pour détacher une déduction d’un crédit, suivez l’une de ces étapes, selon le type de crédit :

- **Factures financières :** Sur la page **Toutes les factures financières**, sélectionnez une facture. Ensuite, dans le volet Actions, sous l’onglet **Facture**, sélectionnez **Détacher un crédit de la déduction**.
- **Ordres de retour :** Sur la page **Tous les ordres de retour**, sélectionnez un ordre. Ensuite, dans le volet Actions, sous l’onglet **Ordre de retour**, sélectionnez **Détacher un crédit de la déduction**.
- **Commandes client :** Sur la page **Toutes les commandes client**, sélectionnez une commande. Ensuite, dans le volet Actions, sous l’onglet **Facture**, sélectionnez **Détacher un crédit de la déduction**.

### <a name="attach-a-deduction-to-a-credit"></a>Joindre une déduction à un crédit

Cette section décrit comment vous pouvez attacher une déduction à un crédit depuis une déduction.

#### <a name="attach-a-deduction-to-a-free-text-return-order-or-sales-order-credit"></a>Joindre une déduction à un crédit financier, d’ordre de retour ou de commande client

Pour joindre une déduction à un crédit financier, d’ordre de retour ou de commande client, procédez comme suit.

1. Aller à **Ventes et marketing \> Reprises \> Déductions \> Workbench de déduction**.
1. Sélectionnez la déduction ouverte applicable.
1. Sur le volet Action, sélectionnez **Tenir à jour \> Joindre la déduction au crédit**. Ce bouton n’est disponible que si le champ **Statut de la réclamation** est défini sur *Ouvert*.
1. Sur la page **Joindre le crédit**, vous pouvez sélectionner *un* crédit. Le type de crédits affiché dépend de la valeur **Base de réclamation** de la déduction :

    - *Basé sur le prix* – La page affiche les factures financières pour le compte client où le champ **ID de déduction** est vide. Les demandes des clients sont également affichées, car la facture financière peut ne pas être validée. Par conséquent, il se peut qu’il n’ait pas de numéro référencé.
    - *Basé sur la quantité* – Le type de crédits affiché dépend du paramètre de l’option **Créer un ordre de retour** sur la page **[Paramètres de la Comptabilité client](#accounts-receivable-deductions)**  :

        - *Oui* – La page affiche les ordres de retour pour le compte client où le champ **ID de déduction** est vide.
        - *Non* – La page affiche les commandes client pour le compte client où le champ **ID de déduction** est vide.

1. Cliquez sur **OK**. Le champ **ID déduction** est défini sur l’en-tête du crédit.

Une fois un crédit joint à la déduction, vous pouvez l’afficher à l’aide du bouton **Crédit ouvert** sur la barre d’outils de la section **Opérations ouvertes** du Workbench de déduction.

Une fois un crédit facturé et que la déduction est approuvée, le crédit apparaît dans la section **Opérations ouvertes** du Workbench des déductions par rapport à la valeur **ID déduction**, et son champ **Type de réclamation** est défini sur *Autres crédits*.

#### <a name="detach-a-credit-from-the-deduction"></a>Détacher un crédit d’une déduction

Si la crédit incorrect a été joint, vous pouvez la détacher de la déduction. Dans le volet Actions, Dans le groupe **Tenir à jour**, sélectionnez **Détacher une déduction d’un crédit**. La valeur **ID déduction** est déduite du crédit.

Le bouton **Détacher la déduction du crédit** n’est disponible que si les conditions suivantes sont remplies :

- Un crédit est attaché à la déduction.
- Le champ **Statut de la réclamation** est défini sur *Ouvert*.

## <a name="create-a-one-time-promotion"></a>Créer une promotion unique

Parfois, vous n’avez pas de remise approuvée que vous pouvez mettre en correspondance avec une déduction. Dans ce cas, vous pouvez utiliser la fonctionnalité *promotion unique* pour mettre en correspondance la déduction à une reprise associée au client. La fonctionnalité *Promotion unique* crée un accord de reprise et un événement de promotion des ventes forfaitaires. Elle met ensuite en correspondance le montant forfaitaire à la déduction et effectue les validations nécessaires pour fermer la déduction.

Cette fonctionnalité est utile si vous utilisez les reprises. Pour plus d’informations sur les remises commerciales, voir [Gestion des allocations commerciales](../sales-marketing/trade-allowance.md).

Tout d’abord, vous devez paramétrer un modèle pour créer l’accord de reprise. Pour paramétrer un modèle, suivez les étapes suivantes.

1. Aller à **Ventes et marketing \> Indemnités commerciales \> Modèles**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans les champs, entrez les informations qui doivent apparaître dans les accords créés à partir du modèle.
1. Sur le raccourci **Clients**, dans le champ **Hiérarchie**, sélectionnez un niveau de hiérarchie.
1. Dans la liste de hiérarchie, sélectionnez le client qui a une déduction sans correspondance, puis sélectionnez le bouton de flèche vers la droite (**\>**). Le client est ajouté à la liste **Clients de l’accord d’allocation commerciale**.
1. Définissez les champs restants comme vous le souhaitez et fermez la page.
1. Aller à **Ventes et marketing \> Configurer \> Indemnité commerciale \> Paramètres de gestion des transactions**.
1. Sur l’onglet **Aperçu**, dans le champ **Modèle de promotion unique**, sélectionnez le nom du modèle à utiliser pour créer des promotions ponctuelles.

Ensuite, vous pouvez créer une promotion unique dans le Workbench de déduction. Pour créer une promotion unique, procédez comme suit.

1. Aller à **Ventes et marketing \> Reprises \> Déductions \> Workbench de déduction**.
1. Cochez la case **Marquer** en regard de la déduction à traiter.
1. Dans le volet Actions, sélectionnez **Tenir à jour \> Déduction de règlement en tant que promotion unique**.
1. Dans la boîte de dialogue **Promotion unique**, suivez ces étapes pour associer la déduction à un ou plusieurs fonds :

    1. Cliquez sur **Nouveau**, puis, dans le champ **ID fonds**, sélectionnez un ID fonds. Répétez cette étape pour ajouter autant de fonds que nécessaire.
    1. Dans le champ **Pourcentage** en regard de chaque ID fonds, entrez le pourcentage de la déduction à attribuer aux fonds. Les montants que vous entrez dans les champs **Pourcentage** doivent atteindre un total de 100 %.

1. Cliquez sur **OK**. Le système crée un accord de reprise ayant un événement de promotion des ventes forfaitaires et met en correspondance le montant forfaitaire à la déduction.

## <a name="do-a-mass-update-of-deductions"></a>Effectuer une mise à jour collective des déductions

Si vous devez effectuer la même modification sur plusieurs déductions, vous pouvez sélectionner ces déductions et effectuer une mise à jour en bloc de leurs champs.

Pour effectuer une mise à jour collective, procédez comme suit.

1. Aller à **Ventes et marketing \> Reprises \> Déductions \> Workbench de déduction**.
1. Dans le champ **Afficher** sous le volet Actions, sélectionnez le type de déductions à afficher.
1. Cochez la case en regard de chaque déduction à mettre à jour. Ensuite, sur le volet Action, sélectionnez **Tenir à jour \> Mise à jour collective**.
1. La boîte de dialogue **Mise à jour collective** affiche les déductions sélectionnées. Mettez à jour les champs selon vos besoins, puis sélectionnez **OK** pour accepter les changements.
