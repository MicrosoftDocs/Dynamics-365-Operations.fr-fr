---
title: Espace de travail d’automatisation des factures fournisseur
description: Cette rubrique explique comment configurer l’espace de travail lié aux factures fournisseur et qui affiche les informations disponibles via Microsoft Power BI.
author: abruer
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2020-09-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: dde77a19fae9af8f40af8b14259a29db80f4a80cf8be75233a463d6fec2dac46
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722717"
---
# <a name="vendor-invoice-automation-workspace"></a>Espace de travail d’automatisation des factures fournisseur

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique explique comment configurer l’espace de travail lié aux factures fournisseur et qui affiche les informations disponibles via Microsoft Power BI. Les informations de facture fournisseur dans cet espace de travail sont filtrées pour des utilisateurs spécifiques et sont affichées dans un format graphique.

## <a name="overview"></a>Vue d’ensemble

L’espace de travail **Automatisation des factures fournisseur** affiche les informations associées au traitement des factures fournisseur. Il contient une vue **Mon travail** et une page **Analyses – Toutes les sociétés**. La vue **Mon travail** affiche les vignettes récapitulatives, les grilles de transaction fournisseur et les informations fournisseur associées. La page **Analyses – Toutes les sociétés** utilise les fonctionnalités de Power BI pour afficher les visualisations associées aux factures fournisseur.

## <a name="set-up-the-workspace-to-show-power-bi-content"></a>Configurer l’espace de travail pour afficher le contenu Power BI

Vous devez terminer cette configuration avant de pouvoir afficher les données dans les visualisations Power BI dans l’espace de travail **Automatisation des factures fournisseur**.

1. Dans l’espace de travail **Gestion des fonctionnalités**, filtrez la liste pour trouver la fonctionnalité **Automatisation des factures fournisseurs** .
3. Sélectionnez **Activer maintenant**.
4. Pour vous assurer que les factures peuvent être traitées du début à la fin sans intervention manuelle, configurez un workflow de facturation fournisseur. Pour configurer un workflow, accédez à **Comptabilité fournisseur \> Paramétrage \> Workflows de la comptabilité fournisseur**.
5. Accédez à **Comptabilité fournisseur \> Configuration \> Paramètres de la comptabilité fournisseur**, et sélectionnez l’onglet **Automatisation des factures fournisseurs**. Pour plus d’informations, consultez [Options de configuration pour l’automatisation des factures fournisseur](vnd-invoice-set-up-options.md).
6. Définissez l’option **Envoyer automatiquement les factures importées au workflow** sur **Oui**.
7. Si les réceptions de marchandises doivent correspondre automatiquement, définissez l’option **Faire correspondre automatiquement les réceptions de marchandises avec les lignes de facture** sur **Oui**.
8. Passez en revue les paramètres facultatifs restants et configurez-les en fonction des exigences de votre organisation.
9. Accédez à **Administration système \> Paramétrage \> Paramètres système** et définissez les champs **Devise système** et **Taux de change système**.
10. Accédez à **Comptabilité \> Paramétrage \> Comptabilité** et définissez les champs **Devise comptable** et **Type de taux de change**.
11. Accédez à **Comptabilité \> Devises \> Taux de change des devises** et saisissez les taux de change entre la devise de transaction et la devise comptable, et entre la devise comptable et la devise système.
12. Accédez à **Administration système \> Paramétrage \> Magasin des entités**, et recherchez **Mesure d’automatisation de la facture fournisseur**. Sélectionnez **Actualiser**.

Pour afficher les informations affichées dans l’espace de travail, vous devez disposer du rôle de sécurité Responsable Comptabilité fournisseur ou Adjoint à la comptabilité fournisseur.

## <a name="my-work-view"></a>Vue Mon travail

### <a name="company-selection"></a>Sélection des sociétés

Quand la fonction **Automatisation des factures fournisseur** est activée, un champ **Compagnie** apparaît en haut de l’espace de travail. La sélection dans le champ **Compagnie** affecte toutes les informations affichées dans l’espace de travail. Par défaut, la vue affiche les informations de l’entreprise à laquelle vous vous êtes connecté. En sélectionnant une autre entreprise dans le champ **Compagnie**, vous pouvez afficher les informations de cette société sur l’espace de travail. Vous pouvez ensuite sélectionner une vignette dans l’espace de travail pour accéder à la page associée dans l’entreprise sélectionnée.

### <a name="summary-tiles"></a>Vignettes récapitulatives

Les vignettes dans la section **Récapitulatif des factures en attente** de la vue **Mon travail** donne un aperçu de l’état de vos factures fournisseurs. Vous pouvez voir les journaux qui ne sont pas encore validés et les factures qui sont en attente. En outre, il existe quatre vignettes associées à la fonction d’automatisation des factures fournisseur :

- Correspondance de réception manuelle nécessaire
- Validation du rapprochement non réussie
- Factures non envoyées au workflow
- Factures non importées

(Ces quatre vignettes nécessitent que la fonction d’automatisation des factures fournisseur soit activée dans Gestion des fonctionnalités.)

Pour utiliser la vignette **Récupérer les factures fournisseurs**, la fonctionnalité doit être activée dans les paramètres de la comptabilité fournisseurs. Accédez à **Comptabilité fournisseur \> Paramètres de la comptabilité fournisseur**, puis, sur l’onglet **Facture**, définissez l’option **Autoriser la récupération des factures fournisseur** sur **Oui**.

Lorsque la fonctionnalité est activée, vous aurez également trois vignettes regroupées sur l’espace de travail dans une section appelée **Journaux**. Les vignettes sont intitulées **Journaux**, **Journaux – Affecté à moi** et **Registre des factures**. 

Les informations dans le **Récapitulatif des factures en attente** sont pour la société définie comme société par défaut pour votre connexion.

### <a name="creating-new-records"></a>Création d’enregistrements

Pour créer un nouvel enregistrement de facture, sélectionnez **Nouveau**, puis sélectionnez l’un des types d’enregistrement suivants dans la liste :

- Facture fournisseur
- Journal des factures
- Journal des factures global
- Registre des factures
- Approbation de facture

Notez que l’enregistrement que vous créez est basé sur le filtre d’entreprise et non sur l’entreprise à laquelle vous êtes connecté. Par exemple, vous êtes connecté à la société **UMSF**, mais le filtre société est défini sur **GBSI**. Dans ce cas, lorsque vous sélectionnez **Nouveau**, puis sélectionnez un type d’enregistrement dans la liste, l’enregistrement est créé dans la société GBSI.

### <a name="documents-not-invoiced-grids"></a>Grilles de documents non facturés

La section **Documents non facturés** contient des grilles qui montrent les documents en attente de factures fournisseurs.

La grille **Commandes fournisseur en cours** affiche toutes les commandes fournisseur qui ne sont pas encore entièrement facturées. Vous pouvez utiliser le bouton **Facturer maintenant** pour créer une facture fournisseur pour une commande fournisseur. Vous pouvez utiliser le bouton **Facture d’acompte maintenant** pour créer une facture d’acompte pour une commande fournisseur.

La grille **Réception de marchandises** affiche les transactions de réception d’achat qui ne sont pas encore entièrement facturées. Vous pouvez utiliser le bouton **Facturer maintenant** pour créer une facture fournisseur pour une commande fournisseur.

La grille **Factures fournisseur en attente** affiche toutes les factures fournisseur qui n’ont pas été soumises au système de workflow. Vous pouvez utiliser le champ **Rechercher** et / ou le filtre d’entreprise pour rechercher une facture fournisseur spécifique. Vous pouvez utiliser le bouton **Modifier** pour modifier une transaction qui apparaît dans la grille.

Sur la grille **Rechercher une commande fournisseur**, vous pouvez utiliser le champ **Rechercher** pour rechercher une commande fournisseur spécifique.

### <a name="related-information"></a>Informations associées

Vous pouvez afficher des informations sur les factures validées en utilisant les liens sur le côté droit de l’espace de travail. Ces liens incluent **Factures fournisseur en cours**, **Journal des factures** et **Historique des factures et détails de rapprochement**. Dans la section **Fournisseurs**, vous pouvez accéder à une liste filtrée qui montre tous les fournisseurs qui sont en attente, ou vous pouvez utiliser le lien **Tous les fournisseurs**. Les liens **Toutes les commandes fournisseur** et **Acomptes en cours** sont également disponibles.

### <a name="analytics--all-companies-page"></a>Page Analyses – Toutes les sociétés

Quand l’option **Envoyer automatiquement les factures importées au workflow** est définie sur **Oui** sur la page **Paramètres de la comptabilité fournisseur**, vous pouvez afficher les analyses de l’automatisation. La page **Analyses – Toutes les entreprises** fournit des mesures importantes, telles que les factures fournisseur approuvées par l’approbateur et par l’entreprise. Cette page contient cinq pages d’état. Une page donne une vue d’ensemble, et les autres pages fournissent des détails sur les mesures de l’automatisation de la comptabilité fournisseur.

Le tableau suivant indique les visualisations qui sont disponibles sur chaque page d’état.

| Page d’état                    | Visualisations |
|--------------------------------|----------------|
| Vue d’ensemble de facture fournisseur        | <ul><li>Factures fournisseur en attente dans l’automatisation dans la devise du système</li><li>Factures dont l’importation a échoué</li><li>Factures dans le workflow</li><li>Factures sans contact au cours des 30 derniers jours</li><li>Total des factures automatisées des 30 derniers jours</li><li>Solde des factures en cours dans la devise du système</li><li>Raisons des échecs, 30 derniers jours</li><li>Pourcentage de factures validées qui ont été traitées automatiquement</li><li>Jours pour traiter une facture</ul></li> |
| Statut de l’automatisation              | <ul><li>Factures sans contact au cours des 30 derniers jours</li><li>Factures sans contact au cours des 30 derniers jours par société</li><li>Factures sans contact au cours des 30 derniers jours par groupe de fournisseurs</li><li>Pourcentage de factures validées qui ont été traitées automatiquement</li><li>Jours pour traiter une facture</li></ul> |
| Factures dont l’importation a échoué | <ul><li>Factures dont l’importation a échoué</li><li>Factures dont l’importation a échoué par société</li></ul> |
| Raisons de l’échec de l’automatisation | <ul><li>Factures ayant échoué</li><li>Factures ayant échoué par entreprise</li><li>Factures ayant échoué par groupe de fournisseurs</li></ul> |
| Statut du flux de travail                | <ul><li>Factures dans le workflow</li><li>Instances de workflow de facture fournisseur</li><li>Affectation par approbateur</li><li>Workflow de facture fournisseur par entreprise</li><li>Nombre moyen de jours dans le workflow par approbateur</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
