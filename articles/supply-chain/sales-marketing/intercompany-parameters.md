---
title: Paramètres intersociétés
description: Cette rubrique explique les paramètres intersociétés
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder, InterCompanyTradingRelationSetupCustomer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: face3cbd21998edcba528548ec4ae52354330aa3
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2021
ms.locfileid: "7778495"
---
# <a name="intercompany-parameters"></a>Paramètres intersociétés

[!include [banner](../../includes/banner.md)]

Dans une organisation intersociétés, vous pouvez définir des paramètres déterminant la manière dont vous gérez les échanges commerciaux entre différentes entités juridiques. Ces paramètres sont déterminés par les champs sélectionnés. Vous pouvez sélectionner différentes combinaisons afin de refléter les différents scénarios commerciaux.

Les deux exemples suivants décrivent des scénarios pour les organisations intersociétés, l’un à deux niveaux et l’autre à trois niveaux.

## <a name="example-1-two-level-intercompany-chain"></a>Exemple 1 : chaîne intersociétés à deux niveaux

L’organisation intersociétés inclut les entités juridiques suivantes .

- L’entité juridique A vend aux clients externes. Elle ne dispose d’aucun stock. Elle achète des articles à l’entité juridique B.
- L’entité juridique B vend uniquement à l’entité juridique A.

Les deux entités juridiques effectuent des transactions l’une avec l’autre (achat et vente).

Dans cet exemple, la tarification de la commande client d’origine adressée au client externe est toujours basée sur le prix de vente. La tarification sur la commande client intersociétés et la commande fournisseur intersociétés est contrôlée par la tarification interne des ventes ou des transferts sur la commande client intersociétés dans l’entité juridique B.

Les informations d’en-tête de commande sont contrôlées depuis la commande client d’origine jusqu’au client externe. Aucune modification de la commande client intersociétés n’est synchronisée avec la commande client d’origine.

Dans l’entité légale A, sur la page **Intersociété** pour les fournisseurs, sélectionnez **Politiques de bons de commande**. Sélectionnez les champs suivants dans le groupe de champs **Bon de commande d’origine (livraison directe)**  :

- **Imprimer automatiquement le bon de livraison**
- **Valider la facture automatiquement**
- **Imprimer la facture automatiquement**

Dans le groupe de champs **Commande fournisseur intersociétés (livraison directe)**, sélectionnez le champ suivant :

- **Valider la facture automatiquement**

Dans le groupe **Commande client d’origine<-> Commande fournisseur intersociétés**, sélectionnez les champs suivants :

- **Informations client**
- **Numéro RMA**

Dans le groupe **Commande fournisseur d’origine<-> Commande client intersociétés**, sélectionnez les champs suivants :

- **Informations client**
- **Numéro RMA**
- **Numéro du lot**
- **Numéro de série**

Dans l’entité légale B, sur la page **Intersociété** pour les clients, sélectionnez **Stratégies pour les commandes client**. Sélectionnez les champs suivants dans le groupe de champs **Création de commandes client intersociétés** :

- **Numérotation des bons de commande** : **Entreprise + numéro d’origine**
- **Autoriser la mise à jour récapitulative de documents pour le client original**

Dans le groupe de champs **Prix de la commande client intersociétés**, sélectionnez les champs suivants :

- **Recherche de prix et de remise**
- **Autoriser l’édition de prix**
- **Autoriser la modification de remises**

Dans le groupe de champs **Commande client intersociétés \> Commande fournisseur intersociétés**, sélectionnez les champs suivants :

- **Numéro du lot**
- **Numéro de série**

## <a name="example-2-three-level-intercompany-chain"></a>Exemple 2 : chaîne intersociétés à trois niveaux

L’organisation intersociétés inclut les entités juridiques suivantes .

- L’entité juridique de vente A vend aux clients externes et achète des articles à l’entité juridique B.
- L’entité juridique de distribution ou de fabrication B ne peut pas livrer de produits et en achète à l’entité juridique C.
- L’entité juridique de distribution ou de fabrication C livre les produits à l’entité juridique B.

La tarification interne entre les entités juridiques B et C correspond aux frais de l’entité juridique vendeuse au début de la chaîne. et à ceux de l’entité juridique A qui vend aux clients externes. Toutefois, la tarification sur la commande client originale pour le client externe est toujours basée sur le prix de vente.

La tarification sur les commandes client intersociétés et les commandes fournisseur intersociétés est contrôlée sur la commande client intersociétés, au début de la chaîne. C’est pourquoi, l’entité juridique C qui vend à l’entité juridique B contrôle le prix. La tarification sur la commande client intersociétés est basée sur la tarification interne des ventes ou des transferts définie dans l’entité juridique C.

Les informations d’en-tête de commande sont contrôlées depuis la commande client d’origine jusqu’au client externe. Aucune modification des commandes intersociétés n’est synchronisée avec la commande client d’origine.

Les paramètres suivants doivent être sélectionnés :

Dans l’entité légale A, sur la page **Intersociété** pour les fournisseurs, sélectionnez **Politiques de bons de commande**. Sélectionnez les champs suivants dans le groupe de champs **Bon de commande d’origine (livraison directe)**  :

- **Imprimer automatiquement le bon de livraison**
- **Valider la facture automatiquement**
- **Imprimer la facture automatiquement**

Dans le groupe de champs **Commande fournisseur intersociétés (livraison directe)**, sélectionnez le champ suivant :

- **Valider la facture automatiquement**

Dans le groupe de champs **Commande client d’origine<-> Commande fournisseur intersociétés**, sélectionnez les champs suivants :

- **Informations client**
- **Numéro RMA**

Dans le groupe **Commande fournisseur d’origine<-> Commande client intersociétés**, sélectionnez les champs suivants :

- **Informations client**
- **Numéro RMA**
- **Numéro du lot**
- **Numéro de série**

Dans l’entité légale B, sur la page **Intersociété** pour les clients, sélectionnez **Stratégies pour les commandes client**. Sélectionnez les champs suivants dans le groupe de champs **Création de commandes client intersociétés** :

- **Numérotation des bons de commande** : **Entreprise + numéro d’origine**
- **Autoriser la mise à jour récapitulative de documents pour le client original**

Dans le groupe de champs **Commande client intersociétés \> Commande fournisseur intersociétés**, sélectionnez les champs suivants :

- **Numéro du lot**
- **Numéro de série**

Dans le groupe de champs **Validation de la facture client intersociétés**, sélectionnez les champs suivants :

- **Prix unitaire égal au prix de revient**
- **Lancer la validation de la facture client originale**

Dans l’entité légale B, sur la page **Intersociétés** pour les fournisseurs, sélectionnez **Politiques de bons de commande**. Sélectionnez les champs suivants dans le groupe de champs **Bon de commande d’origine (livraison directe)**  :

- **Imprimer automatiquement le bon de livraison**
- **Valider la facture automatiquement**
- **Imprimer la facture automatiquement**

Dans le groupe de champs **Commande fournisseur intersociétés (livraison directe)**, sélectionnez le champ suivant :

- **Valider la facture automatiquement**

Dans le groupe de champs **Commande client d’origine<-> Commande fournisseur intersociétés**, sélectionnez les champs suivants :

- **Informations client**
- **Numéro RMA**
- **Prix et remise**

Dans le groupe **Commande fournisseur d’origine<-> Commande client intersociétés**, sélectionnez les champs suivants :

- **Informations client**
- **Numéro RMA**
- **Numéro du lot**
- **Numéro de série**

Dans l’entité légale C, sur la page **Intersociété** pour les clients, sélectionnez **Stratégies pour les commandes client**. Sélectionnez les champs suivants dans le groupe de champs **Création de commandes client intersociétés** :

- **Numérotation des bons de commande** : **Code souche de numéros**
- **Autoriser la mise à jour récapitulative de documents pour le client original**

Dans le groupe de champs **Prix de la commande client intersociétés**, sélectionnez le champ suivant :

- **Recherche de prix et de remise**

Dans le groupe de champs **Validation de la facture client intersociétés**, sélectionnez les champs suivants :

- **Prix unitaire égal au prix de revient**
- **Lancer la validation de la facture client originale**

Dans le groupe **Commande client intersociétés<-> Commande fournisseur intersociétés**, sélectionnez les champs suivants :

- **Numéro du lot**
- **Numéro de série**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
