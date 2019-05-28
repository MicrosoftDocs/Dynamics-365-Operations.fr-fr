---
title: Facturation intersociétés
description: Cet article fournit des informations et des exemples sur la facturation intersociétés de projets dans Microsoft Dynamics 365 for Finance and Operations.
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 94153
ms.assetid: 33e98da7-01c1-4369-923d-aa1c8326cb80
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 857aee796db2a4743cdbd91da3eb1cf6f996f9d1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557258"
---
# <a name="intercompany-invoicing"></a>Facturation intersociétés

[!include [banner](../includes/banner.md)]

Cet article fournit des informations et des exemples sur la facturation intersociétés de projets dans Microsoft Dynamics 365 for Finance and Operations.

Votre organisation peut avoir plusieurs divisions, filiales, ainsi que d'autres entités juridiques qui transfèrent des produits et des services entre elles pour des projets. L’entité juridique qui fournit le service ou le produit est appelée l'*entité juridique prêteuse*, et l’entité juridique qui reçoit le service ou le produit est appelée l'*entité juridique emprunteuse*. 

L’illustration suivante montre un scénario classique où deux entités juridiques, SI FR (l’entité juridique emprunteuse) et SI USA (l’entité juridique prêteuse), partagent des ressources pour fournir un projet au client A. Dans ce scénario, SI FR est engagée pour fournir le travail au client A. 

[![Exemple de facturation intersociétés](./media/interco.invoicing-01.jpg)](./media/interco.invoicing-01.jpg) 

L’objectif est de rendre le contrôle des coûts, la constatation du produit, les impôts et le prix de transfert des transactions de projet intersociétés plus flexibles et plus puissants. En outre, les fonctionnalités suivantes sont fournies :

-   Créer des factures client par rapport à un projet dans une entité juridique emprunteuse à l’aide de feuilles de temps intersociétés, de dépenses et de factures fournisseur dans une entité juridique prêteuse.
-   Prendre en charge les calculs de taxe et les coûts indirects.
-   Reporter la constatation du produit dans une entité juridique prêteuse et à quel moment une entité juridique emprunteuse doit constater le coût.
-   Provisionner le produit des travaux en cours de l’entité juridique prêteuse.
-   Définir des prix de transfert qui peuvent être basés sur divers modèles de tarification. Voici quelques exemples :
    -   **Quantité** : le montant entré dans le champ **Tarification** est le coût réel par quantité ou unité.
    -   **Montant des frais** : le prix/coût par transaction auquel s'ajoute le montant des frais entré dans le champ .**Tarification**.
    -   **Pourcentage de frais** : le prix de transfert est le prix/coût par transaction, multiplié par le pourcentage de frais entré dans le champ **Tarification**.
    -   **Pourcentage du prix de vente** : pourcentage du prix de vente transféré à l’entité juridique prêteuse.
    -   **Montant inférieur au prix de vente** : montant que l’entité juridique emprunteuse retient sur les prix de vente avant le transfert à l’entité juridique prêteuse.
    -   **Taux de contribution** : le nombre entré dans le champ **Tarification** est le taux de contribution exprimé en pourcentage du prix de vente.

## <a name="example-1-set-up-parameters-for-intercompany-invoicing"></a>Exemple 1 : Définir les paramètres de facturation intersociétés
Dans cet exemple, USSI est une entité juridique prêteuse et ses ressources déclarent le temps par rapport à l’entité juridique emprunteuse, FRSI, qui possède un contrat avec le client final. Les heures et les dépenses que les employés d'USSI déclarent peuvent être inclus dans la facture du projet générée par FRSI. En outre, il existe une troisième source de transactions qui peuvent provenir de l’entité juridique prêteuse (USSI dans cet exemple) lorsqu’elle fournit des services de fournisseurs partagés aux filiales (par exemple, FRSI) et transmet ensuite ces coûts aux projets au sein de ces filiales. Tous les documents de facture et les calculs de taxes correspondants sont effectués par Finance and Operations. 

Pour cet exemple, FRSI doit être un client dans l’entité juridique USSI et USSI doit être un fournisseur dans l’entité juridique FRSI. Puis, vous pouvez définir une relation intersociétés entre les deux entités juridiques. La procédure suivante montre comment définir les paramètres afin que les deux entités juridiques puissent participer à la facturation intersociétés.

1. Configurez l’entité juridique FRSI en tant que cliente de l'entté juridique USSI et configurez USSI comme fournisseur dans l’entité juridique FRSI. Il existe trois points d’entrée pour les étapes qui sont requises pour cette tâche.

   | Etape |                                                       Point d'entrée                                                        |                                                                                                                                                                                               description ;                                                                                                                                                                                               |
   |------|--------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  A   | Dans USSI, cliquez sur <strong>Comptabilité client</strong> &gt; <strong>Clients</strong> &gt; <strong>Tous les clients</strong>. |                                                                                                                                                                  Créez un enregistrement de client pour FRSI et sélectionnez le groupe de clients.                                                                                                                                                                  |
   |  B   |    Dans FRSI, cliquez sur <strong>Comptabilité fournisseur</strong> &gt; <strong>Fournisseurs</strong> &gt; <strong>Tous les fournisseurs</strong>.     |                                                                                                                                                                    Créez un enregistrement de fournisseur pour USSI et sélectionnez le groupe de fournisseurs.                                                                                                                                                                    |
   |  C   |                                  Dans FRSI, ouvrez l’enregistrement du fournisseur que vous venez de créer.                                  | Dans le volet Actions, sous l'onglet <strong>Général</strong>, dans le groupe <strong>Paramétrer</strong>, cliquez sur <strong>Intersociétés</strong>. Dans la page <strong>Intersociétés</strong>, sur l'onglet <strong>Relation commerciale</strong>, définissez le curseur <strong>Actif</strong> sur <strong>Oui</strong>. Dans le champ <strong>Société du client</strong>, sélectionnez l’enregistrement de client que vous avez créé à l’étape A. |


2. Cliquez sur **Gestion et comptabilité du projet** &gt; **Paramétrage** &gt; **Paramètres de gestion et comptabilité des projets**, puis cliquez sur l'onglet **Intersociétés**. La façon dont vous définissez les paramètres varie selon que vous êtes l'entité juridique emprunteuse ou l'entité juridique prêteuse.
   -   Si vous êtes l’entité juridique emprunteuse, sélectionnez la catégorie d’approvisionnement qui doit être utilisée pour correspondre aux factures fournisseur, qui sont automatiquement générées.
   -   Si vous êtes l’entité juridique prêteuse, pour chaque entité emprunteuse, sélectionnez une catégorie de projet par défaut pour chaque type de transaction. Les catégories de projet sont utilisées pour la configuration de taxe lorsque la catégorie facturée dans les transactions intersociétés existe uniquement dans l’entité juridique emprunteuse. Vous pouvez choisir de provisionner le produit pour les transactions intersociétés. Cette régularisation est effectuée lorsque les transactions sont validées, et elle est ensuite inversée lors de la validation de la facture intersociétée.

3. Cliquez sur **Gestion de projets et comptabilité** &gt; **Paramétrer** &gt; **Prix** &gt; **Prix de transfert**.
4. Sélectionnez une devise, le type de transaction et le modèle de prix de transfert. La devise utilisée sur la facture est la devise configurée dans l’enregistrement du client pour l’entité juridique emprunteuse dans l’entité juridique prêteuse. La devise est utilisée pour correspondre aux entrées de la table de prix de transfert.
5. Cliquez sur **Comptabilité** &gt; **Paramétrage de la validation** &gt; **Comptabilité intersociétés** et paramétrez une relation pour USSI et FRSI.

## <a name="example-2-create-and-post-an-intercompany-timesheet"></a>Exemple 2 : Créer et valider une feuille de temps intersociétés
USSI, l’entité juridique prêteuse, doit créer et valider la feuille de temps pour un projet de FRSI, l’entité juridique emprunteuse. Il existe deux points d’entrée pour les étapes qui sont requises pour cette tâche.

| Etape | Point d'entrée                                                                       | description ;                                                                                                                                                                                       |
|------|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Gestion de projets et comptabilité** &gt; **Feuilles de temps** &gt; **Toutes les feuilles de temps** | Créez une nouvelle feuille de temps. Sur la ligne de la feuille de temps, dans le champ **Entité juridique**, sélectionnez **FRSI**. Dans le champ **ID projet**, sélectionnez le projet dans FRSI. Spécifiez le nombre d'heures de chaque jour de la semaine. |
| G    | Page **Feuille de temps**                                                                | Après l’exécution du workflow, validez la feuille de temps et prenez note du numéro de document.                                                                                                               |

## <a name="example-3-create-and-post-an-intercompany-vendor-invoice"></a>Exemple 3 : Créer et valider une facture fournisseur intersociétés
USSI, l’entité juridique prêteuse, doit créer et valider la facture fournisseur intersociétés pour un projet de FRSI, l’entité juridique emprunteuse. Cette facture fournisseur représente le personnel sous-traité et les dépenses effectuées par les fournisseurs qui sont payés par USSI. Il existe deux points d’entrée pour les étapes qui sont requises pour cette tâche.

| Etape | Point d'entrée                                                                                      | description ;                                                                                                                                                                                                                                                                          |
|------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Comptabilité fournisseur** &gt; **Factures** &gt; **Factures fournisseur en cours** &gt; **Nouvelle facture fournisseur** | Créez une facture fournisseur et entrez les services qui ont été achetés au nom du projet du FRSI.                                                                                                                                                                                  |
| G    | Page **Facture fournisseur**                                                                      | Permet d’entrer des lignes qui représentent les services externalisés au nom de FRSI. Sur l'organisateur **Détails de ligne**, sur l'onglet **Projet** pour la ligne de facture, dans le champ **Société du projet**, saisissez **FRSI**. Entrez le projet et les informations correspondantes. Puis validez la facture fournisseur. |

## <a name="example-4-create-and-post-the-intercompany-invoice"></a>Exemple 4 : Créer et valider la facture intersociétés
USSI, l’entité juridique prêteuse, doit créer et valider la facture intersociétée. Il existe deux points d’entrée pour les étapes qui sont requises pour cette tâche.

| Etape | Point d'entrée                                                                                             | description ;                                                                                                                                      |
|------|---------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Gestion et comptabilité des projets** &gt; **Factures de projets** &gt; **Facture client intersociétés**  | Cliquez sur **Nouveau** pour ouvrir la page **Créer une facture intersociétés**.                                                                                  |
| B    | **Gestion et comptabilité des projets** &gt; **Factures de projets** &gt; **Factures client intersociétés** | Sur la page **Créer une facture intersociétés**, entrez l’entité juridique, spécifiez la transaction qui doit être incluse, puis cliquez sur **Rechercher**. |
| C    | **Gestion et comptabilité des projets** &gt; **Factures de projets** &gt; **Factures client intersociétés** | Sélectionnez les transactions à facturer, ou cliquez sur **Sélectionner tout** pour facturer toutes les transactions dans la liste, puis cliquez sur **OK**.                  |
| D    | Page **Facture intersociétés**                                                                       | La proposition de facture client intersociétés est affichée.                                                                                             |
| E    | Page **Facture intersociétés**                                                                       | Cliquez sur **Valider**.                                                                                                                                  |

## <a name="example-5-post-the-vendor-invoice-and-invoice-the-customer"></a>Exemple 5 : Valider la facture fournisseur et facturer le client
Lorsque l’entité juridique prêteuse, USSI, enregistre la facture client intersociétés, une facture fournisseur en attente correspondante est créée dans l’entité juridique emprunteuse, FRSI. Après que cette facture fournisseur est validée, FRSI facture également le client du projet pour les heures que USSI entrées. Il existe trois points d’entrée pour les étapes qui sont requises pour cette tâche.

| Etape | Point d'entrée                                                                                        | description ;                                                                                                             |
|------|----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| A    | **Comptabilité fournisseur** &gt; **Factures** &gt; **Factures fournisseur en attente**                            | Vérifiez la facture pour vous assurer que les valeurs de la feuille de temps sont incluses, puis validez la facture fournisseur.                  |
| B    | **Gestion et comptabilité des projets** &gt; **Factures de projets** &gt; **Propositions de facture du projet** | Créez une facture de projet pour le projet et vérifiez que les transactions horaires validées apparaissent.            |
| C    | Page **Facture du projet**                                                                       | Sélectionnez la facture de projet, puis cliquez sur **Afficher les détails** pour examiner le coût et le montant des ventes. Puis validez la facture. |


Pour plus d'informations, voir [Configurer la facturation de projets intersociétés](tasks/configure-intercompany-project-invoicing.md).


