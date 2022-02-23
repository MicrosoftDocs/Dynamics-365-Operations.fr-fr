---
title: Personnaliser les configurations ER pour générer un document électronique
description: Cette rubrique explique comment personnaliser les configurations de gestion des états électroniques (ER) fournies par Microsoft qui permettent de générer un document électronique personnalisé.
author: NickSelin
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 47bb8a2a9adab4ec963a1d0b95e783299aab3819
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683013"
---
# <a name="customize-electronic-reporting-configurations-to-generate-an-electronic-document"></a>Personnaliser les configurations ER pour générer un document électronique

[!include[banner](../includes/banner.md)]

La [structure de gestion des états électroniques (ER)](general-electronic-reporting.md) vous permet de télécharger les [configurations](general-electronic-reporting.md#Configuration) ER que Microsoft fournit dans votre instance Microsoft Dynamics 365 Finance. De cette manière, les configurations fournies par Microsoft peuvent servir de solution ER utilisée pour générer des factures clients électroniques (factures électroniques). Vous pouvez utiliser cette solution ER pour configurer votre solution ER personnalisée afin d’accéder à vos champs de base de données personnalisés et de générer des factures électroniques conformes à vos exigences spécifiques, sans avoir à modifier le code source.

## <a name="overview"></a>Vue d’ensemble

Pour l’exemple de cette rubrique, vous devez spécifier un code d’identification fiscale fédérale comme nouvel attribut personnalisé de chaque client que vous facturez électroniquement. Par conséquent, vous devez personnaliser la structure de la facture actuellement utilisée, en ajoutant un nouvel élément qui doit être rempli avec le code taxe dans chaque facture électronique qui est générée.

Les procédures de cette rubrique expliquent comment un utilisateur doté du rôle Administrateur système, Développeur d’états électroniques ou Consultant fonctionnel ER peut effectuer les tâches suivantes dans votre instance de Finance :

- [Configurer l’ensemble minimal de paramètres ER requis pour commencer à utiliser la structure ER](#ConfigureER).
- [Importez les versions initiales des configurations ER standard fournies pour générer des factures électroniques](#ImportERConfigurations1).
- [Configurer les paramètres de la comptabilité client pour commencer à utiliser les configurations ER standard](#ConfigureAR1).
- [Configurer les paramètres d’entité juridique pour facturer les clients](#ConfigureLE).
- [Préparer un enregistrement client pour la facturation électronique](#ConfigureCustomer1).
- [Ajouter, valider et envoyer une facture client à l’aide des configurations ER standard](#ProcessInvoice1).
- [Ajouter un champ de base de données personnalisé pour gérer un code d’identification fiscale fédérale pour les clients](#AddCustomField).
- [Actualiser les métadonnées ER pour activer les modifications de base de données pour le concepteur de mappage de modèle ER](#RefreshERMetadata).
- [Concevoir les configurations ER personnalisées pour générer des factures électroniques contenant le nouveau code taxe](#DesignCustomERConfigurations).
- [Configurer les paramètres de la comptabilité client pour commencer à utiliser les configurations ER personnalisées](#ConfigureAR2).
- [Mettre à jour un enregistrement client pour la facturation électronique](#ConfigureCustomer2).
- [Ajouter, valider et envoyer une facture client à l’aide des configurations ER personnalisées](#ProcessInvoice2).
- [Importez les nouvelles versions des configurations ER standard fournies pour générer des factures électroniques](#ImportERConfigurations2).
- [Adopter les modifications apportées aux nouvelles versions des configurations ER standard dans vos configurations ER personnalisées](#RebaseCustomERConfigurations).
- [Ajouter, valider et envoyer une facture client à l’aide des nouvelles versions des configurations ER personnalisées](#ProcessInvoice3).

Toutes ces procédures peuvent être effectuées dans la société **DEMF**.

## <a name="configure-the-er-framework"></a><a name="ConfigureER"></a>Configurer la structure de gestion des états électroniques

En tant qu’utilisateur ayant le rôle de consultant fonctionnel ER ou de développeur de rapports électroniques, vous devez configurer l’ensemble minimal de paramètres ER. Vous pouvez ensuite commencer à utiliser la structure ER pour concevoir des versions personnalisées des configurations standard de la solution ER utilisée pour générer des factures électroniques.

### <a name="configure-er-parameters"></a>Configurer les paramètres ER

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Paramètres de gestion des états électroniques**.
3. Sur la page **Paramètres de gestion des états électroniques**, sous l’onglet **Général**, définissez l’option **Activer le mode de configuration** sur **Oui**.
4. Sur l’onglet **Pièces jointes**, dans le champ **Configurations**, sélectionnez **Fichier**.
5. Dans les champs **Archive de tâche**, **Temporaire**, **Référence** et **Autres**, sélectionnez le type **Fichier**.

Pour plus d’informations sur les paramètres de gestion des états électroniques, voir [Configurer la structure de gestion des états électroniques](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a>Activer un fournisseur de configuration de gestion des états électroniques

Chaque configuration de gestion des états électroniques ajoutée est marquée comme appartenant à un fournisseur de configuration de gestion des états électroniques. Le fournisseur de configuration de gestion des états électroniques activé dans l’espace de travail **Gestion des états électroniques** est utilisé à cet effet. Par conséquent, vous devez activer un fournisseur de configuration de gestion des états électroniques dans l’espace de travail **Gestion des états électroniques** avant de commencer à ajouter ou modifier des configurations de gestion des états électroniques.

> [!NOTE]
> Seul le propriétaire d’une configuration de gestion des états électroniques peut la modifier. Par conséquent, avant qu’une configuration de gestion des états électroniques puisse être modifiée, le fournisseur de configuration de gestion des états électroniques approprié doit être activé dans l’espace de travail **Gestion des états électroniques**.

#### <a name="review-the-list-of-er-configuration-providers"></a>Consulter la liste des fournisseurs de configuration de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Fournisseurs de configuration**.
3. Sur la page **Table des fournisseurs de configuration**, chaque enregistrement de fournisseur a un nom et une URL uniques. Passez en revue le contenu de cette page. S’il existe déjà un enregistrement pour **Litware, Inc.** (`https://www.litware.com`), ignorez la procédure suivante, [Ajouter un nouveau fournisseur de configuration de gestion des états électroniques](#AddProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="AddProvider"></a>Ajouter un nouveau fournisseur de configuration de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Fournisseurs de configuration**.
3. Sur la page **Fournisseurs de configuration**, sélectionnez **Nouveau**.
4. Dans le champ **Nom**, entrez **Litware, Inc.**
5. Dans le champ **Adresse Internet**, entrez `https://www.litware.com`.
6. Sélectionnez **Enregistrer**.

#### <a name="activate-an-er-configuration-provider"></a>Activer un fournisseur de configuration de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Litware, Inc.**, puis sélectionnez **Activer**.

Pour plus d’informations sur les fournisseurs de configuration de gestion des états électroniques, voir [Créer des fournisseurs de configuration et les marquer comme actifs](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-initial-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations1"></a>Importer les versions initiales de configurations ER standard

Pour ajouter les configurations ER standard à votre instance actuelle de Finance, vous devez les importer depuis le [référentiel](general-electronic-reporting.md#Repository) ER qui a été configuré pour cette instance.

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**, puis sélectionnez **Référentiels** pour afficher la liste des référentiels du fournisseur Microsoft.
3. Sur la page **Référentiels de configuration**, sélectionnez le référentiel de type **Global**, puis sélectionnez **Ouvrir**. Si vous êtes invité à autoriser la connexion à Regulatory Configuration Service, suivez les instructions d’autorisation.
4. Sur la page **Référentiel de configuration**, dans l’arborescence de configuration du volet gauche, sélectionnez la configuration de format **Facture client Peppol**.
5. Dans l’organisateur **Versions**, sélectionnez la version **11.2.2**.
6. Cliquez sur **Importer** pour télécharger la version sélectionnée depuis le référentiel global.

![Page du référentiel de configuration](./media/er-quick-start3-import-solution1.png)

> [!TIP]
> Si vous ne parvenez pas à accéder au [Référentiel global](er-download-configurations-global-repo.md), vous pouvez [télécharger les configurations](download-electronic-reporting-configuration-lcs.md) depuis Microsoft Dynamics Lifecycle Services (LCS).

### <a name="review-the-imported-er-configurations"></a>Passer en revue les configurations de gestion des états électroniques importées

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation**, dans la section **Configurations**, sélectionnez la vignette **Configurations des états**.
3. Sur la page **Configurations**, développez le FastTab **Composants de configuration**.
4. Dans l’arborescence de configuration du volet gauche, développez **Modèle de facture**, puis développez **Facture client UBL**.

Notez qu’en plus du format ER **Facture client Peppol** sélectionné, d’autres configurations ER requises ont été importées. Parce que les nouvelles versions des configurations ER sont constamment publiées dans le référentiel global et LCS pour maintenir les solutions correspondantes conformes aux nouvelles exigences, les dernières versions de la configuration de [modèle de données](general-electronic-reporting.md#data-model-and-model-mapping-components) requise et ses configurations de [mise en correspondance des modèles](general-electronic-reporting.md#data-model-and-model-mapping-components) ont été importées.

![Page Configurations](./media/er-quick-start3-imported-solution1a.png)

Pour simuler l’état dans lequel se trouveraient les configurations ER dans l’instance de Finance actuelle si vous importiez la version **11.2.2** du format ER **Facture client Peppol** dans le passé (par exemple, le 7 août 2019), suivez ces étapes.

- Dans le volet Actions, sélectionnez **Supprimer** pour supprimer toutes les configurations ER publiées après le 7 août 2019. Seules les configurations **Modèle de facture**, **Mappage du modèle de facture** (initialement nommé **Mappage du modèle de facture client**), **Facture client UBL** et **Facture client Peppol** doivent être conservées.
- Pour les configurations ER restantes, sur le FastTab **Versions**, sélectionnez **Supprimer** pour supprimer toutes les versions des configurations ER publiées après le 7 août 2019.

Vérifiez ensuite que les configurations suivantes sont disponibles dans l’arborescence de configuration :

- Configuration du modèle de données ER **Modèle de facture** (initialement nommée **Modèle de facture client**) :

    - La version 11 contient la version 10 du composant ER [modèle de données](general-electronic-reporting.md#data-model-and-model-mapping-components) qui représente la structure de données du domaine métier de facturation. Cette configuration ER a été importée comme ancêtre du format ER **Facture client Peppol** sélectionné pour l’importation.
    - La version 50 contient la version 31 du composant ER de modèle de données. Cette configuration ER a été importée en tant qu’ancêtre de la version du 7 août 2019 de la configuration du mappage du modèle ER **Mappage du modèle de facture**.

    ![Configuration du modèle de données ER Modèle de facture sur la page Configurations](./media/er-quick-start3-imported-solution1b1.png)

    > [!TIP]
    > Si vous ne voyez pas la version 50 de ce modèle de données, ouvrez le référentiel global et importez la version 50.19 de la configuration ER **Mappage du modèle de facture**.

- Configuration du mappage de modèle ER **Mappage du modèle de facture** (initialement nommée **Mappage de modèle de facture client**) :

    - La version 50.19 a été importée en tant que dernière implémentation de la version 50 de la configuration du modèle de données ER **Modèle de facture**. Elle contient deux composants ER de [mappage du modèle](general-electronic-reporting.md#data-model-and-model-mapping-components) qui décrivent comment le modèle de données est rempli avec les données d’application au moment de l’exécution.

    ![Configuration du mappage du modèle ER Mappage du modèle de facture sur la page Configurations](./media/er-quick-start3-imported-solution1b2.png)

    > [!TIP]
    > Si vous ne voyez pas la version 50.19 de ce mappage du modèle, ouvrez le référentiel global et importez la version 50.19 de la configuration ER **Mappage du modèle de facture**.

- Configuration du format ER **Facture client UBL** :

    - La version 11.2 contient les composants de gestion des états électroniques [Format](general-electronic-reporting.md#FormatComponentOutbound) et Mise en correspondance des formats. Le composant Format spécifie la présentation de l’état. Le composant Mise en correspondance des formats contient la source de données du modèle et spécifie comment cette source de données est utilisée pour remplir la présentation de l’état au moment de l’exécution. Ce format ER a été configuré pour générer des factures électroniques au format UBL (Universal Business Language, langage universel des affaires). Il a été importé comme parent du format de gestion des états électroniques **Facture client Peppol** sélectionné pour l’importation.

- Configuration du format ER **Facture client Peppol** :

    - La version 11.2.2 contient les composants ER de format et de mappage de formats qui ont été configurés pour générer des factures électroniques au format PEPPOL (Pan-European Public Procurement OnLine).

    ![Configuration du format ER Facture client Peppol sur la page Configurations](./media/er-quick-start3-imported-solution1b3.png)

## <a name="configure-the-accounts-receivable-parameters"></a><a name="ConfigureAR1"></a>Configurer les paramètres de la comptabilité client

1. Accédez à **Comptabilité client** \> **Configuration** \> **Paramètres de la comptabilité client**.
2. Sur l’onglet **Documents électroniques**, sur le FastTab **Gestion des états électroniques**, dans le champ **Facture client et financière**, sélectionnez **Facture client Peppol**.
3. Sélectionnez **Enregistrer**.

![Onglet Documents électroniques sur la page Paramètres de la comptabilité client](./media/er-quick-start3-configure-ar1.png)

## <a name="configure-the-legal-entity-parameters"></a><a name="ConfigureLE"></a>Configurer les paramètres d’entité juridique

1. Allez dans **Administration d’organisation** \> **Organisations** \> **Entités juridiques**.
2. Pour l’entreprise sélectionné **DEMF**, sur le FastTab **Informations sur le compte en banque**, dans le champ **Numéro d’acheminement**, entrez **1234**.
3. Sélectionnez **Enregistrer**.
4. Fermez la page **Entités juridiques**.

## <a name="prepare-a-customer-record"></a><a name="ConfigureCustomer1"></a>Préparer un enregistrement client

1. Allez dans **Comptabilité client** \> **Clients** \> **Tous les clients**.
2. Sur la page **Tous les clients**, sélectionnez le lien de compte client **DE-014**.

### <a name="add-a-customer-contact"></a>Ajouter un contact client

1. Allez dans **Comptabilité client** \> **Clients** \> **Tous les clients**.
2. Dans le volet Actions, sous l’onglet **Client**, dans le groupe **Compte**, cliquez sur **Contacts**.
3. Sélectionnez **Ajouter des contacts**.
4. Sur la page **Contacts**, dans le champ **Prénom**, ouvrez la recherche, sélectionnez **Adam Carter**, puis sélectionnez **Sélectionner** pour fermer la recherche.
5. Sélectionnez **Enregistrer**.
6. Fermez la page **Contacts**.

### <a name="define-a-primary-contact"></a>Définir un contact principal

1. Allez dans **Comptabilité client** \> **Clients** \> **Tous les clients**.
2. Sur le FastTab **Démographie de vente**, dans le champ **Premier contact**, sélectionnez **Adam Carter**.

### <a name="set-the-e-invoicing-option"></a>Définir l’option de facturation électronique

1. Allez dans **Comptabilité client** \> **Clients** \> **Tous les clients**.
2. Sur le FastTab **Facture et livraison**, définissez l’option **Facture électronique** sur **Oui**.
3. Sélectionnez **Enregistrer**.
4. Fermez la page **Tous les clients**.

## <a name="process-a-customer-invoice-by-using-the-standard-er-configurations"></a><a name="ProcessInvoice1"></a>Traiter une facture client à l’aide des configurations de gestion des états électroniques standard

Vous pouvez désormais utiliser les configurations ER standard que vous avez importées pour envoyer électroniquement une facture financière à un client.

### <a name="add-a-new-invoice"></a>Ajouter une nouvelle facture

1. Allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.
2. Sur la page **Facture financière**, sélectionnez **Nouveau**.
3. Sur le FastTab **En-tête de facture financière**, dans le champ **Compte client**, sélectionnez **DE-014**.
4. Sur le FastTab **Lignes de facture**, une ligne de facture est automatiquement ajoutée. Sur cette ligne, définissez les champs suivants :

    - Dans le champ **Description**, entrez **Notebook**.
    - Dans le champ **Compte principal**, sélectionnez **401100**.
    - Dans le champ **Prix unitaire**, entrez **1000**.

5. Sélectionnez **Enregistrer**.

![Page Facture financière](./media/er-quick-start3-add-invoice.png)

Pour plus d’informations, voir [Créer une facture financière](../../../finance/accounts-receivable/create-free-text-invoice-new.md).

### <a name="post-a-new-invoice"></a>Valider une nouvelle facture

1. Allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.
2. Sur la page **Facture financière**, dans le volet Actions, sélectionnez **Valider**.
3. Dans la boîte de dialogue **Valider une facture financière**, sélectionnez **OK**.

![Page Détails de la facture financière](./media/er-quick-start3-post-invoice.png)

### <a name="send-a-posted-invoice"></a>Envoyer une facture validée

1. Allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.
2. Sur la page **Facture financière**, sur le volet Actions, dans le groupe **Document**, sélectionnez **Envoyer** \> **Original**.

    ![Aperçu de la facture originale](./media/er-quick-start3-send-invoice.png)

3. Fermez la page **Facture financière**.

### <a name="analyze-a-generated-e-invoice"></a>Analyser une facture électronique générée

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Tâches de gestion des états électroniques**.
2. Sur la page **Tâches de gestion des états électroniques**, sélectionnez l’enregistrement initial contenant la description de la tâche **Envoyer le fichier XML de facture électronique**.
3. Sélectionnez **Afficher les fichiers** pour accéder à la liste des fichiers générés.

    ![Page Tâches de gestion des états électroniques](./media/er-quick-start3-jobs-list.png)

4. Sélectionnez **Ouvrir** pour télécharger le fichier XML de facture électronique généré.
5. Analysez le fichier XML de facture électronique. Notez que le schéma de taxe client est actuellement représenté par les attributs XML **schemaID** et **schemaAgencyID**. Notez également que l’élément XML **cbc:CustomizationID** contient actuellement le texte suivant : `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0`.

    ![Aperçu du fichier XML de facture électronique généré](./media/er-quick-start3-e-invoice1.png)

## <a name="add-a-custom-database-field"></a><a name="AddCustomField"></a>Ajouter un champ de base de données personnalisé

Vous pouvez utiliser la fonctionnalité [Champ personnalisé](../../fin-ops/get-started/user-defined-fields.md) pour effectuer la personnalisation suivante dans l’instance Finance actuelle :

- Personnalisez la structure de la base de données en ajoutant un nouveau champ de base de données personnalisé qui stocke un code d’identification fiscale fédérale pour chaque client.
- Personnalisez la page **Client** en ajoutant un nouveau champ de saisie de données qui peut être utilisé pour entrer une valeur de code de taxe dans le nouveau champ de base de données personnalisé.

Suivez ces étapes pour effectuer la personnalisation.

1. Allez dans **Comptabilité client** \> **Clients** \> **Tous les clients**.
2. Sur la page **Tous les clients**, sélectionnez le lien de compte client **DE-014**.
3. Sur le FastTab **Général**, cliquez avec le bouton droit de la souris dans une zone vide sous le champ **Langue**, puis sélectionnez **Personnaliser : UpperGroup**.

    Le contenu du FastTab **Général** est mis en surbrillance et un menu **Personnaliser** apparaît.

4. Sur le menu **Personnaliser**, sélectionnez **Ajouter un champ**.
5. Dans la boîte de dialogue **Ajouter des colonnes**, sélectionnez **Créer un champ**.
6. Dans la boîte de dialogue **Créer un champ**, dans le champ **Nom de la table**, sélectionnez **Clients**.
7. Dans le champ **Préfixe du nom**, entrez **FederalTaxID**.

    > [!NOTE]
    > Le nom complet du champ a été automatiquement défini comme **FederalTaxID\_Personnalisé**.

8. Dans le champ **Libellé**, entrez **ID taxe fédérale**.
9. Dans le champ **Type**, sélectionnez **Texte**.
10. Dans le champ **Longueur**, entrez **20**.
11. Sélectionnez **Enregistrer**.
12. Dans la boîte de message qui apparaît, sélectionnez **Oui** pour confirmer que vous souhaitez créer une entrée de champ **FederalTaxID** pour la table **Clients**.
13. Sélectionnez **Insérer** pour <a name="insert_custom_field"></a>ajouter le champ **FederalTaxID\_Personnalisé** à la page actuelle.

    ![Page Tous les clients](./media/er-quick-start3-create-new-field.gif)

14. Fermez la page **Tous les clients**.

## <a name="refresh-the-er-metadata"></a><a name="RefreshERMetadata"></a>Actualiser les métadonnées ER

Vous devez actualiser les métadonnées ER pour rendre le champ personnalisé que vous avez ajouté [visible](electronic-reporting-er-configure-parameters.md#frequently-asked-questions) dans le concepteur de mappage de modèles ER.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Reconstruire les références des tables**.
2. Dans la boîte de dialogue **Mettre à jour le modèle de données**, sélectionnez **OK**.

## <a name="design-the-custom-er-configurations"></a><a name="DesignCustomERConfigurations"></a>Concevoir les configurations ER personnalisées

Vous pouvez utiliser les configurations ER fournies par Microsoft pour concevoir vos configurations ER personnalisées afin qu’elles génèrent des factures électroniques contenant le nouveau code taxe.

### <a name="customize-the-data-model-configuration"></a>Personnaliser la configuration du modèle de données

En tant qu’utilisateur doté du rôle de Consultant fonctionnel de gestion des états électroniques, vous pouvez concevoir votre modèle de données ER personnalisé.

#### <a name="add-a-custom-data-model-configuration"></a>Ajouter une configuration du modèle de données personnalisée

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, sélectionnez **Modèle de facture client**.
3. Dans le volet Actions, sélectionnez **Créer une configuration**.
4. Dans la boîte de dialogue déroulante, dans le champ **Nouveau**, sélectionnez **Provenant du nom : Modèle de facture client, Microsoft** pour indiquer que votre nouvelle configuration du modèle de données ER personnalisé doit être basée sur la configuration du modèle de données ER.
5. Dans le champ **Nom**, saisissez **Modèle de facture (Litware)**.
6. Sélectionnez **Créer une configuration** pour ajouter une nouvelle configuration ER.

Vous pouvez désormais utiliser le concepteur de modèle de données ER pour modifier la version 50.1 de la configuration ER **Modèle de facture (Litware)** au [statut](general-electronic-reporting.md#component-versioning) **Brouillon**.

![Version 50.1 de la configuration ER sur la page Configurations](./media/er-quick-start3-added-custom-model.png)

#### <a name="configure-a-custom-data-model"></a>Configurer un modèle de données personnalisé

Vous devez modifier votre modèle de données personnalisé en ajoutant un nouveau champ pour fournir la valeur d’un code d’identification fiscale fédérale. Ce code fait partie des données client pour chaque format ER qui utilisera ce modèle de données comme source de données.

1. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, sélectionnez **Modèle de facture (Litware)**.
2. Dans le FastTab **Versions**, sélectionnez la version **50.1** de la configuration du modèle de données ER sélectionnée au statut **Brouillon**.
3. Dans le volet Actions, sélectionnez **Concepteur** pour la version de configuration sélectionnée.
4. Sur la page **Concepteur de modèles de données**, dans l’arborescence du modèle de données, sélectionnez **Informations client (Client)**.
5. Sélectionnez **Nouveau**.
6. Dans la boîte de dialogue déroulante, dans le champ **Nouveau nœud en tant que**, acceptez la valeur par défaut, **Enfant d’un nœud actif**.
7. Dans le champ **Nom**, entrez **FederalTaxID\_Litware**.
8. Dans le champ **Type d’élément**, acceptez la valeur par défaut, **Chaîne**.
9. Sélectionnez **Ajouter**, puis sélectionnez **Enregistrer**.

    ![Page Concepteur de modèles de données](./media/er-quick-start3-add-data-model-field.png)

    > [!NOTE]
    > Les champs **Étiquette** et **Description** décrivent le but du nouveau champ. Vous pouvez remplir ces champs dans plusieurs langues. Pour plus d’informations, voir [Concevoir des états multilingues dans la gestion des états électroniques](er-design-multilingual-reports.md).

10. Fermez la page **Concepteur de modèle de données**.

#### <a name="complete-a-custom-data-model-configuration"></a>Achever une configuration du modèle de données personnalisée

Vous devez [achever](general-electronic-reporting.md#component-versioning) votre travail avec la version 50.1 de votre configuration du modèle de données ER personnalisé pour la rendre disponible afin que d’autres configurations ER personnalisées puissent être ajoutées.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de facture**, puis sélectionnez **Modèle de facture (Litware)**.
3. Dans l’organisateur **Versions**, sélectionnez **Modifier le statut** \> **Terminé**, puis cliquez sur **OK**.

Le statut de la version 50.1 passe de **Brouillon** à **Terminé** et la version devient en lecture seule. Une nouvelle version modifiable, 50.2, est ajoutée et son statut est **Brouillon**. Vous pouvez utiliser cette version pour apporter d’autres modifications à votre configuration du modèle de données ER personnalisé.

![Version 50.1 terminée sur la page Configurations](./media/er-quick-start3-completed-custom-model1.png)

### <a name="customize-the-model-mapping-configuration"></a>Personnaliser la configuration de mise en correspondance de modèles

En tant qu’utilisateur doté du rôle de Développeur d’états électroniques , vous pouvez concevoir votre mise en correspondance de modèle de gestion des états électroniques personnalisée.

#### <a name="add-a-custom-model-mapping-configuration"></a>Ajouter une configuration de mise en correspondance de modèles de données personnalisée

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de facture client**, puis sélectionnez **Mappage de modèle de facture client**.
3. Dans le volet Actions, sélectionnez **Créer une configuration**.
4. Dans la boîte de dialogue déroulante, dans le champ **Nouveau**, sélectionnez **Provenant du nom : Modèle de facture client, Microsoft** pour indiquer que votre nouvelle configuration de mappage de modèles ER personnalisée doit être basée sur la configuration de mappage de modèles ER.
5. Dans le champ **Nom**, saisissez **Mappage de modèle de facture (Litware)**.
6. Dans le champ **Modèle cible**, sélectionnez **Modèle de facture (Litware)**.

    > [!IMPORTANT]
    > Cette étape est très importante. Si vous l’omettez, vous ne pourrez pas utiliser votre modèle de données personnalisé dans le mappage de modèle configuré.

7. Sélectionnez **Créer une configuration** pour ajouter une nouvelle configuration ER.

![Ajout d’une configuration du mappage de modèle ER sur la page Configurations](./media/er-quick-start3-adding-custom-mapping.png)

#### <a name="configure-a-custom-model-mapping"></a>Configurer un mappage de modèle personnalisé

Vous devez modifier votre mappage de modèle personnalisé et spécifier comment le champ **FederalTaxID\_Litware** du modèle de données personnalisé doit être rempli avec les données d’application au moment de l’exécution.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de facture client** \> **Mappage de modèle de facture client**, puis sélectionnez **Mappage de modèle de facture (Litware)**.
3. Dans le volet Actions, sélectionnez **Concepteur**.
4. Sur la page **Mise en correspondance de modèles à la source de données**, sélectionnez le mappage **Facture client**.

    ![Page Mise en correspondance de modèle avec une source de données](./media/er-quick-start3-select-customer-mapping.png)

5. Sélectionnez **Concepteur**.
6. Sur la page **Concepteur de mappage de modèle**, dans le volet **Sources de données**, développez la source de données **CustInvoiceJour** qui représente la table d’application **CustInvoiceJour**.
7. Sous **CustInvoiceJour**, développez **Relations** pour revoir la liste des relations de type plusieurs-à-un (N : 1) pour la table **CustInvoiceJour**.
8. Sous **CustInvoiceJour** \> **Relations**, développez **Clients (CustTable)** pour accéder aux champs et aux relations de la table **Clients (CustTable)**.
9. Sélectionnez le champ de source de données **FederalTaxID\_Personnalisé** que vous avez implémenté [plus tôt](#insert_custom_field).
10. Dans le volet **Modèle de données**, développez **Informations client (client)**, et sélectionnez le champ de modèle de données **FederalTaxID\_Litware**.
11. Sélectionnez **Lier**.

    ![Page Concepteur de mise en correspondance de modèle](./media/er-quick-start3-customize-model-mapping.gif)

12. Sélectionnez **Enregistrer**.
13. Fermez la page **Concepteur de mise en correspondance des modèles**.
14. Fermez la page **Mise en correspondance de modèle avec une source de données**.

#### <a name="complete-a-custom-model-mapping-configuration"></a>Achever une configuration de mappage de modèle personnalisée

Vous devez [achever](general-electronic-reporting.md#component-versioning) votre travail avec la version 50.19.1 de votre configuration de mappage de modèle ER personnalisé pour la rendre disponible pour être utilisée.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de facture client** \> **Mappage de modèle de facture client**, puis sélectionnez **Mappage de modèle de facture (Litware)**.
3. Dans l’organisateur **Versions**, sélectionnez **Modifier le statut** \> **Terminé**, puis cliquez sur **OK**.

Le statut de la version 50.19.1 passe de **Brouillon** à **Terminé** et la version devient en lecture seule. Une nouvelle version modifiable, 50.19.2, est ajoutée et son statut est **Brouillon**. Vous pouvez utiliser cette version pour apporter d’autres modifications à votre configuration de mappage de modèle ER personnalisé.

![Version 50.19.1 terminée sur la page Configurations](./media/er-quick-start3-completed-custom-mapping1.png)

> [!NOTE]
> Le [cycle de vie](general-electronic-reporting-manage-configuration-lifecycle.md) de la configuration pris en charge ne couvre pas le cycle de vie des modifications de base de données. Si vous exportez la version 50.19.1 de la configuration **Mappage du modèle de facture (Litware)** de l’instance de Finance actuelle et essayez de l’importer dans une autre instance qui ne contient pas le champ **FederalTaxID\_Personnalisé** dans la table **CustTable**, une exception se produira. L’exception indiquera que la configuration ER importée n’est pas compatible avec les métadonnées de l’instance de Finance cible.

### <a name="customize-the-format-configuration"></a>Personnaliser la configuration du format

En tant qu’utilisateur doté du rôle de Consultant fonctionnel de gestion des états électroniques, vous pouvez concevoir votre format ER personnalisé.

#### <a name="add-a-custom-format-configuration"></a>Ajouter une configuration du format personnalisé

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de facture client** \> **Facture client UBL**, puis sélectionnez **Facture client Peppol**.
3. Dans le volet Actions, sélectionnez **Créer une configuration**.
4. Dans la boîte de dialogue déroulante, dans le champ **Nouveau**, sélectionnez **Provenant du nom : Facture client Peppol, Microsoft** pour indiquer que votre nouvelle configuration du format ER personnalisé doit être basée sur la configuration du format ER.
5. Dans le champ **Nom**, saisissez **Facture client Peppol (Litware)**.
6. Dans le champ **Modèle de données**, sélectionnez **Modèle de facture (Litware)** pour utiliser vos composants de modèle de données et de mappage de modèle personnalisés.

    > [!NOTE]
    > Cette étape est très importante. Si vous l’omettez, vous ne pourrez pas utiliser votre modèle de données personnalisé dans le format configuré.

7. Dans le champ **Modèle de données**, sélectionnez la définition racine **InvoiceCustomer**.
8. Sélectionnez **Créer une configuration** pour ajouter une nouvelle configuration ER.

![Ajout d’une configuration du format personnalisé sur la page Configurations](./media/er-quick-start3-adding-custom-format.png)

Vous pouvez désormais utiliser le concepteur d’opérations ER pour modifier la version 11.2.2.1 de la configuration ER **Facture client Peppol (Litware)** au [statut](general-electronic-reporting.md#component-versioning) **Brouillon**.

![Version 11.2.2.1 de la configuration ER sur la page Configurations](./media/er-quick-start3-added-custom-format.png)

#### <a name="configure-a-custom-format"></a>Configurer un format personnalisé

Vous devez modifier votre format personnalisé en ajoutant un nouvel élément de format pour renseigner la valeur du code d’identification fiscale fédérale d’un client facturé.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de facture client** \> **Facture client UBL** \> **Facture client Peppol**, puis sélectionnez **Facture client Peppol (Litware)**.
3. Dans le volet Actions, sélectionnez **Concepteur**.
4. Dans l’arborescence des formats, développez **XMLHeader** \> **Facture** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** et sélectionnez **cbc:ID**.
5. Sélectionnez **Ajouter**, puis sélectionnez **XML** \> **Attribut**.
6. Dans la boîte de dialogue **Propriété du composant**, dans le champ **Nom**, tapez **FederalTaxID**.
7. Sélectionner **OK** pour ajouter un nouvel élément de format pour créer un nouvel attribut XML **FederalTaxID** dans un fichier XML généré.
8. Dans l’arborescence des formats, sous **XMLHeader** \> **Facture** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** \> **cbc:ID**, sélectionnez **FederalTaxID**.
9. Sélectionnez **Déplacer vers le haut**.

![Nouvel élément de format sur la page Concepteur de format](./media/er-quick-start3-customized-format.png)

#### <a name="configure-a-custom-format-mapping"></a>Configurer un mappage de format personnalisé

1. Sur la page **Concepteur de format**, sous l’onglet **Mappage**, développez la source de données **Facture** du type **Modèle**.
2. Sous **Facture**, développez **Informations client (Client)** et sélectionnez **FederalTaxID\_Litware**.
3. Sélectionnez **Lier**.

    ![Page Concepteur de formats](./media/er-quick-start3-customized-format-mapping.png)

4. Sélectionnez la source de données **Facture** du type **Modèle**, puis sélectionnez **Modifier**.
5. Dans le champ **Version**, sélectionnez la version **1** de votre modèle de données personnalisé, puis sélectionnez **OK**.
6. Sélectionnez **Enregistrer**.
7. Fermez la page **Concepteur de format**.

#### <a name="complete-a-custom-format-configuration"></a>Achever une configuration du format personnalisé

Vous devez [achever](general-electronic-reporting.md#component-versioning) votre travail avec la version 11.2.2.1 de votre configuration du format ER personnalisé pour la rendre disponible pour être utilisée.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de facture client** \> **Facture client UBL** \> **Facture client Peppol**, puis sélectionnez **Facture client Peppol (Litware)**.
3. Dans l’organisateur **Versions**, sélectionnez **Modifier le statut** \> **Terminé**, puis cliquez sur **OK**.

Le statut de la version 11.2.2.1 passe de **Brouillon** à **Terminé** et la version devient en lecture seule. Une nouvelle version modifiable, 11.2.2.2, est ajoutée et son statut est **Brouillon**. Vous pouvez utiliser cette version pour apporter d’autres modifications à votre configuration du format de gestion des états électroniques personnalisé.

![Version 11.2.2.1 terminée sur la page Configurations](./media/er-quick-start3-completed-custom-format1.png)

## <a name="configure-the-accounts-receivable-parameters-to-start-to-use-custom-er-configurations"></a><a name="ConfigureAR2"></a>Configurer les paramètres de la comptabilité client pour commencer à utiliser les configurations de gestion des états électroniques personnalisées

1. Accédez à **Comptabilité client** \> **Configuration** \> **Paramètres de la comptabilité client**.
2. Sur l’onglet **Documents électroniques**, sur le FastTab **Gestion des états électroniques**, dans le champ **Facture client et financière**, sélectionnez **Facture client Peppol (Litware)**.
3. Sélectionnez **Enregistrer**.

![Page Paramètres de la comptabilité client, Onglet Documents électroniques, FastTab Gestion des états électroniques](./media/er-quick-start3-configure-ar2.png)

## <a name="update-a-customer-record-by-adding-a-federal-tax-identification-code"></a><a name="ConfigureCustomer2"></a>Mettre à jour un enregistrement client en ajoutant un code d’identification fiscale fédérale

1. Allez dans **Comptabilité client** \> **Clients** \> **Tous les clients**.
2. Sur la page **Tous les clients**, sélectionnez le lien de compte client **DE-014**.
3. Sur le FastTab **Général**, dans le champ **ID taxe fédérale** , entrez **LITWARE-6789**.
4. Sélectionnez **Enregistrer**.

    ![Page Détails du client DE-014](./media/er-quick-start3-added-tax-id-value.png)

5. Fermez la page **Tous les clients**.

## <a name="process-a-customer-invoice-by-using-custom-er-configurations"></a><a name="ProcessInvoice2"></a>Traiter une facture client à l’aide des configurations de gestion des états électroniques personnalisées

### <a name="select-and-send-a-posted-invoice"></a>Sélectionner et envoyer une facture validée

1. Allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.
2. Sur la page **Facture financière**, sélectionnez la facture que vous avez précédemment ajoutée et validée.
3. Sur le volet Actions, dans le groupe **Document**, sélectionnez **Envoyer** \> **Original**.
4. Fermez la page **Facture financière**.

### <a name="analyze-a-generated-e-invoice"></a>Analyser une facture électronique générée

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Tâches de gestion des états électroniques**.
2. Sur la page **Tâches de gestion des états électroniques**, sélectionnez le dernier enregistrement contenant la description de la tâche **Envoyer le fichier XML de facture électronique**.
3. Sélectionnez **Afficher les fichiers** pour accéder à la liste des fichiers générés.
4. Sélectionnez **Ouvrir** pour télécharger le fichier XML de facture électronique généré.
5. Analysez le fichier XML de facture électronique. Notez que, conformément à votre personnalisation, le schéma de taxe client inclut l’attribut XML **FederalTaxID** en plus des attributs XML **schemaID** et **schemaAgencyID**. La valeur de ce nouvel attribut XML est spécifiée par l’ID taxe fédérale **LITWARE-6789** saisi pour un client facturé.

    ![Aperçu du fichier XML de facture électronique généré avec vos personnalisations](./media/er-quick-start3-e-invoice2.png)

## <a name="import-the-latest-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations2"></a>Importer les dernières versions des configurations de gestion des états électroniques standard

Pour tenir l’ensemble des configurations ER standard dans votre instance de Finance [à jour](general-electronic-reporting-manage-configuration-lifecycle.md), vous devez en importer les nouvelles versions dès qu’elles sont disponibles dans le [référentiel](general-electronic-reporting.md#Repository) ER qui a été configuré pour cette instance.

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**, puis sélectionnez **Référentiels** pour afficher la liste des référentiels du fournisseur Microsoft.
3. Sur la page **Référentiels de configuration**, sélectionnez le référentiel de type **Global**, puis sélectionnez **Ouvrir**. Si vous êtes invité à autoriser la connexion à Regulatory Configuration Service, suivez les instructions d’autorisation.
4. Sur la page **Référentiel de configuration**, dans l’arborescence de configuration du volet gauche, sélectionnez la configuration de format **Facture client Peppol**.
5. Sur le FastTab **Versions**, sélectionnez la version **32.6.7** de la configuration de format ER sélectionnée qui a été lancée pour prendre en charge les factures électroniques des clients au format PEPPOL BIS 3. Pour plus d’informations, voir [KB4490320](https://support.microsoft.com/help/4490320/an-update-for-european-union-to-support-export-of-customers-electronic).
6. Sélectionnez **Importer** pour télécharger la version sélectionnée depuis le référentiel global vers l’instance actuelle de Finance.

![Version 32.6.7 sélectionnée sur la page Référentiel de configuration](./media/er-quick-start3-import-solution2.png)

Pour plus d’informations sur la manière dont ce processus peut être automatisé, voir [Importer des versions mises à jour des configurations ER](er-download-updated-versions-global-repo.md).

### <a name="review-the-imported-er-configurations"></a>Passer en revue les configurations de gestion des états électroniques importées

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation**, dans la section **Configurations**, sélectionnez la vignette **Configurations des états**.
3. Développez le FastTab **Composants de configuration**.
4. Dans l’arborescence de configuration du volet gauche, développez **Modèle de facture**. Notez que le nom de **Modèle de facture client** a été changé en **Modèle de facture** dans l’une des configurations du modèle de données ER importées.
5. Dans l’arborescence de configuration du volet gauche, développez **Mappage de modèle de facture**. Notez que le nom de **Mappage de modèle de facture client** a été changé en **Mappage de modèle de facture** dans l’une des configurations de mappage de modèle ER importées.
6. Développez **Facture client UBL** \> **Facture Peppol**.

Notez qu’en plus du format de gestion des états électroniques **Facture client Peppol** sélectionné, les dernières versions des configurations de gestion des états électroniques requises ont été importées. Parce que les nouvelles versions des configurations de gestion des états électroniques sont constamment publiées dans le référentiel global et LCS pour maintenir les solutions ER correspondantes conformes aux nouvelles exigences, les dernières versions de la configuration de modèle de données requise et ses configurations de mise en correspondance des modèles ont été importées.

Assurez-vous que les configurations de gestion des états électroniques suivantes sont finalement disponibles dans l’arborescence de configuration :

- Configuration du modèle de données ER **Modèle de facture** :

    - La version 206 (ou ultérieure) contient la version 24 (ou ultérieure) du composant ER de modèle de données qui représente la structure de données du domaine métier de facturation. Cette configuration ER a été importée en tant qu’ancêtre de la dernière version disponible de la configuration du mappage du modèle ER **Mappage du modèle de facture**.

    ![Version 206 sur la page Configurations](./media/er-quick-start3-imported-solution2b1.png)

- Configuration du mappage de modèle ER **Mappage de modèle de facture** :

    - La version 206.132 (ou ultérieure) a été importée en tant que dernière implémentation de la version 206 de la configuration du modèle de données ER **Modèle de facture**. Elle contient plusieurs composants ER de mappage du modèle qui décrivent comment le modèle de données est rempli avec les données d’application au moment de l’exécution.

    ![Version 206.132 sur la page Configurations](./media/er-quick-start3-imported-solution2b2.png)

- Configuration du format ER **Facture client UBL** :

    - La version 32.6 contient les composants ER Format et Mise en correspondance des formats. Le composant Format spécifie la présentation de l’état. Le composant Mise en correspondance des formats contient la source de données du modèle et spécifie comment cette source de données est utilisée pour remplir la présentation de l’état au moment de l’exécution. Ce format ER a été configuré pour générer des factures électroniques au format UBL. Il a été importé comme parent du format de gestion des états électroniques **Facture client Peppol** sélectionné pour l’importation.

- Configuration du format ER **Facture client Peppol** :

    - La version 32.6.7 contient les composants ER de format et de mappage de formats qui ont été configurés pour générer des factures électroniques au format PEPPOL.

    ![Version 32.6.7 sur la page Configurations](./media/er-quick-start3-imported-solution2b3.png)

## <a name="adopt-the-changes-to-the-new-standard-er-configurations-in-your-custom-er-configurations"></a><a name="RebaseCustomERConfigurations"></a>Adopter les modifications apportées aux nouvelles configurations de gestion des états électroniques standard dans vos configurations de gestion des états électroniques personnalisées

### <a name="adopt-your-custom-er-data-model"></a>Adopter votre modèle de données ER personnalisé

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de facture**, puis sélectionnez **Modèle de facture (Litware)**.
3. Dans le FastTab **Versions**, pour la version brouillon **50.2** de la configuration du format de données sélectionnée, sélectionnez **Redéfinir**.
4. Dans le champ **Version cible**, confirmez la sélection de la version **206** de la configuration du modèle de données ER de base, puis sélectionnez **OK**.

    La version provisoire de votre configuration du modèle de données ER personnalisé est renumérotée de **50.2** en **206.2** pour indiquer qu’elle contient désormais votre personnalisation qui a été fusionnée avec les modifications de la dernière version (206) de la configuration du modèle de données ER de base.

    > [!NOTE]
    > L’action de redéfinition est réversible. Pour annuler cette redéfinition, sélectionnez la version **50.1** du modèle **Modèle de facture (Litware)** dans le FastTab **Versions**, puis sélectionnez **Obtenir cette version**. La version 206.2 sera renumérotée **50.2** et le contenu de la version provisoire 50.2 correspondra au contenu de la version 50.1.

5. Dans l’organisateur **Versions**, sélectionnez **Modifier le statut** \> **Terminé**, puis cliquez sur **OK**.

Le statut de la version 206.2 passe de **Brouillon** à **Terminé** et la version devient en lecture seule. Une nouvelle version modifiable, 206.3, est ajoutée et son statut est **Brouillon**. Vous pouvez utiliser cette version pour apporter d’autres modifications à votre configuration du modèle de données ER personnalisé.

![Version 206.2 terminée sur la page Configurations](./media/er-quick-start3-completed-custom-model2.png)

### <a name="adopt-your-custom-er-model-mapping"></a>Adopter votre mappage de modèle de données ER personnalisé

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de facture** \> **Mappage de modèle de facture**, puis sélectionnez **Mappage de modèle de facture (Litware)**.
3. Dans le FastTab **Versions**, pour la version brouillon **50.19.2** de la configuration du mappage de modèle sélectionnée, sélectionnez **Redéfinir**.
4. Dans le champ **Version cible**, confirmez la sélection de la version **206.132** de la configuration du mappage de modèle ER de base, puis sélectionnez **OK**.

    La version provisoire de votre configuration du mappage de modèle ER personnalisé est renumérotée de **50.19.2** en **206.132.2** pour indiquer qu’elle contient désormais votre personnalisation qui a été fusionnée avec les modifications de la dernière version (206.132) de la configuration du mappage de modèle ER de base.

    Notez que certains conflits de redéfinition ont été découverts. Vous devez maintenant résoudre manuellement ces conflits.

    ![Message de conflit de redéfinition sur la page Configurations](./media/er-quick-start3-rebase-conflicts-model-mapping1.png)

5. Dans le volet Actions, sélectionnez **Concepteur**, puis, dans la liste des mappages, sélectionnez **Facture client**.
6. Pour chaque conflit de redéfinition, sélectionnez **Conserver sa propre valeur**, car vous devez conserver le numéro de version de votre modèle de données personnalisé pour chaque composant qui a été mentionné.

    ![Conflits de redéfinition sur la page Concepteur de mappage de modèles](./media/er-quick-start3-rebase-conflicts-model-mapping2.png)

7. Sélectionnez **Enregistrer**, puis fermez la page du **Concepteur de mappage de modèles**.
8. Dans la liste des mappages, sélectionnez **Facture de projet**.
9. Pour chaque conflit de redéfinition, sélectionnez **Conserver sa propre valeur**, car vous devez conserver le numéro de version de votre modèle de données personnalisé pour chaque composant qui a été mentionné.
10. Sélectionnez **Enregistrer**, puis fermez la page **Mappages de modèles**.

    > [!NOTE]
    > L’action de redéfinition est réversible. Pour annuler cette redéfinition, sélectionnez la version **50.19.1** du mappage de modèle **Mappage de modèle de facture (Litware)** dans le FastTab **Versions**, puis sélectionnez **Obtenir cette version**. La version 206.132.2 sera renumérotée **50.19.2** et le contenu de la version provisoire 50.19.2 correspondra au contenu de la version 50.19.1.

11. Dans l’organisateur **Versions**, sélectionnez **Modifier le statut** \> **Terminé**, puis cliquez sur **OK**.

Le statut de la version 206.132.2 passe de **Brouillon** à **Terminé** et la version devient en lecture seule. Une nouvelle version modifiable, 206.132.3, est ajoutée et son statut est **Brouillon**. Vous pouvez utiliser cette version pour apporter d’autres modifications à votre configuration de mappage de modèle ER personnalisé.

![Version 206.132.2 terminée sur la page Configurations](./media/er-quick-start3-completed-custom-mapping2.png)

### <a name="adopt-your-custom-er-format"></a>Adopter votre format ER personnalisé

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de facture** \> **Facture client UBL** \> **Facture client Peppol**, puis sélectionnez **Facture client Peppol (Litware)**.
3. Dans le FastTab **Versions**, pour la version brouillon **11.2.2.2** de la configuration du format sélectionnée, sélectionnez **Redéfinir**.
4. Dans le champ de version **Cible**, confirmez la sélection de la version **32.6.7** de la configuration du format ER de base, puis sélectionnez **OK**.

    La version provisoire de votre configuration du format ER personnalisé est renumérotée de **11.2.2.2** en **32.6.7.2** pour indiquer qu’elle contient désormais votre personnalisation qui a été fusionnée avec les modifications de la dernière version (32.6.7) de la configuration du format ER de base.

    Notez que certains conflits de redéfinition ont été découverts. Vous devez maintenant résoudre manuellement ces conflits.

5. Dans le volet Actions, sélectionnez **Concepteur**.
6. Pour chaque conflit de redéfinition, sélectionnez **Conserver sa propre valeur**, car vous devez conserver le numéro de version de votre modèle de données personnalisé pour chaque composant qui a été mentionné.
7. Sélectionnez **Enregistrer**.
8. Dans l’onglet **Mappage**, sélectionnez la source de données **Facture** du type **Modèle**, puis sélectionnez **Modifier**.
9. Dans le champ **Version**, sélectionnez la version **2** de votre modèle de données personnalisé, puis sélectionnez **OK**.
10. Sélectionnez **Enregistrer**.

    > [!NOTE]
    > L’action de redéfinition est réversible. Pour annuler cette redéfinition, sélectionnez la version **11.2.2.1** du format **Facture client Peppol** dans le FastTab **Versions**, puis sélectionnez **Obtenir cette version**. La version 32.6.7.2 sera renumérotée **11.2.2.2** et le contenu de la version provisoire 11.2.2.2 correspondra au contenu de la version 11.2.2.1.

11. Fermez la page **Concepteur de format**.
12. Dans l’organisateur **Versions**, sélectionnez **Modifier le statut** \> **Terminé**, puis cliquez sur **OK**.

Le statut de la version 32.6.7.2 passe de **Brouillon** à **Terminé** et la version devient en lecture seule. Une nouvelle version modifiable, 32.6.7.3, est ajoutée et son statut est **Brouillon**. Vous pouvez utiliser cette version pour apporter d’autres modifications à votre configuration du format de gestion des états électroniques personnalisé.

![Version 32.6.7.2 terminée sur la page Configurations](./media/er-quick-start3-completed-custom-format2.png)

## <a name="process-a-customer-invoice-by-using-new-versions-of-the-custom-er-configurations"></a><a name="ProcessInvoice3"></a>Traiter une facture client à l’aide de nouvelles versions des configurations ER personnalisées

### <a name="select-and-send-a-posted-invoice"></a>Sélectionner et envoyer une facture validée

1. Allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.
2. Sur la page **Facture financière**, sélectionnez la facture que vous avez précédemment ajoutée et validée.
3. Sur le volet Actions, dans le groupe **Document**, sélectionnez **Envoyer** \> **Original**.

    > [!NOTE] 
    > Parce que vous avez maintenant deux versions de la configuration du format ER **Facture client Peppol (Litware)**, et qu’aucune des deux versions n’a de valeur de [date effective](general-electronic-reporting.md#component-date-effectivity), la dernière version est utilisée pour générer une facture électronique.

4. Fermez la page **Facture financière**.

### <a name="analyze-a-generated-e-invoice"></a>Analyser une facture électronique générée

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Tâches de gestion des états électroniques**.
2. Sur la page **Tâches de gestion des états électroniques**, sélectionnez l’enregistrement le plus récent contenant la description de la tâche **Envoyer le fichier XML de facture électronique**.
3. Sélectionnez **Afficher les fichiers** pour accéder à la liste des fichiers générés.
4. Sélectionnez **Ouvrir** pour télécharger le fichier XML de facture électronique généré.
5. Analysez le fichier XML de facture électronique. Notez que, conformément à votre personnalisation, le schéma de taxe client contient toujours l’attribut XML **FederalTaxID** en plus des attributs XML **schemaID** et **schemaAgencyID**. De plus, parce que les changements dans la nouvelle version du format **Facture client UBL** de base ont été fusionnés avec votre personnalisation, le texte de l’élément XML **cbc:CustomizationID** a été modifié de `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0` en `urn:cen.eu:en16931:2017#compliant#urn:fdc:peppol.eu:2017:poacc:billing:3.0`.

    ![Aperçu du fichier XML de facture électronique généré avec des personnalisations](./media/er-quick-start3-e-invoice3.png)

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble des États électroniques](general-electronic-reporting.md)
- [Télécharger les configurations de gestion des états électroniques depuis Lifecycle Services](download-electronic-reporting-configuration-lcs.md)
- [Télécharger les configurations de gestion des états électroniques depuis le référentiel global du service de configuration](er-download-configurations-global-repo.md)
- [Créer une facture financière](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/create-free-text-invoice-new)
- [Créer et utiliser des champs personnalisés](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/user-defined-fields)
