---
title: Créer un classeur Excel pour modifier les transactions de vente au détail
description: Cette rubrique décrit la procédure de création d’un classeur Excel afin que vous puissiez modifier les transactions de vente au détail dans Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: a2d41dd0470a4abae1a8238be8f1549fb094a026
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795737"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a>Créer un classeur Excel pour modifier les transactions de vente au détail

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la procédure de création d’un classeur Excel afin que vous puissiez modifier les transactions de vente au détail dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Il existe un modèle Excel prédéfini auquel les clients peuvent accéder à partir de différentes parties du système et utiliser pour modifier et vérifier les transactions de vente au détail. Cependant, les clients peuvent également créer un classeur Excel personnalisé à cet effet.

## <a name="create-and-configure-an-excel-workbook"></a>Créer et configurer un classeur Excel

Pour créer et configurer un classeur Excel afin de pouvoir modifier les transactions de vente au détail, procédez comme suit.

1. Ouvrez Excel et créez un classeur vierge.
1. Dans l’onglet **Insérer**, sélectionnez **Mes compléments**.
1. Dans le volet droit, sélectionnez le lien **Ajouter des informations sur le serveur**.
1. Entrez l’URL du serveur, puis sélectionnez **OK**.
1. Si vous recevez le message d’erreur « Aucun enregistrement d’applet trouvé », procédez comme suit pour résoudre le problème :

    1. Dans Commerce, accédez à **Administration du système \> Paramétrage \> Paramètres des applications Office**.
    1. Dans le raccourci **Paramètres d’application**, sélectionnez **Initialiser les paramètres d’application**.
    1. Dans la zone de message de confirmation, sélectionnez **OK**.
    1. Dans le raccourci **Applets enregistrées**, sélectionnez **Initialiser l’enregistrement de l’applet**.
    1. Si nécessaire, répétez les trois étapes précédentes.

1. Sélectionnez **Design**, puis sélectionnez **Ajouter une table**.
1. En fonction des données à modifier, sélectionnez les entités qui doivent être modifiées afin de les ajouter au classeur Excel. Utilisez la table suivante comme référence.

    | Type de transaction | Entités de données à utiliser |
    |------------------|----------------------|
    | Transactions au comptant sans livraison, commandes en ligne, commandes client asynchrones, devis clients asynchrones | Transaction (vérifiable), transaction de vente (vérifiable), transactions de paiement (vérifiables), transactions de taxe (vérifiables), transactions de remise (vérifiables), transactions de frais (vérifiables) |
    | Remise en banque | Transaction (vérifiable), transactions de paiement remises en banque (vérifiables) |
    | Mise en coffre-fort | Transaction (vérifiable), transactions de paiements remises en coffre-fort (vérifiables) |
    | Comptage de caisse | Transaction (vérifiable), transactions de comptage de caisse (vérifiables) |
    | Revenu/dépense | Transaction (vérifiable), transactions de revenus/dépenses (vérifiables), transactions de paiement (vérifiables) |
    | Déclarer le montant de départ, Vider la caisse, Entrée de fond de caisse, Rendu-monnaie, Facture à payer, Dépôt client | Transaction (vérifiable), transactions de paiement (vérifiables) |

    > [!NOTE]
    > Il est important que vous n’ajoutiez qu’une seule entité de données à chaque classeur Excel. En outre, tous les champs marqués par un symbole de clé doivent être ajoutés au classeur approprié.

1. Une fois le classeur configuré, appliquez les filtres requis. Assurez-vous d’appliquer les mêmes filtres à toutes les feuilles de calcul du fichier. Évitez de charger de très grandes quantités de données dans le fichier Excel. Sinon, les performances pourraient être affectées, entraînant un ralentissement d’Excel et de votre système. Nous vous recommandons de toujours utiliser les filtres « Société » ainsi que « Numéro de relevé » ou « Numéro de transaction » pour votre fichier.
1. Une fois les filtres configurés, sélectionnez **Rafraîchir** pour charger les données.
1. Modifiez les données requises, puis publiez-les. Si le bouton **Publier** n’est pas disponible, certains champs clés n’ont probablement pas été ajoutés au classeur Excel.

## <a name="additional-resources"></a>Ressources supplémentaires

[Modifier et vérifier les transactions de gestion des disponibilités et des paiements au comptant sans livraison](edit-cash-trans.md)

[Modifier et vérifier les commandes en ligne et les transactions de commandes client asynchrones](edit-order-trans.md)

[Modifier les dimensions financières des transactions de vente au détail](edit-financial-dim.md)

[Ajouter des champs à un classeur Excel pour modifier les transactions de vente au détail](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]