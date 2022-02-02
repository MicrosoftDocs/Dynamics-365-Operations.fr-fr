---
title: Mise en route de la Facturation électronique
description: Cette rubrique donne des informations qui vous aideront à démarrer la Facturation électronique dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 11/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ba9f6ca08af0647f4519726894b1c9dfcc9cce24
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7983860"
---
# <a name="get-started-with-electronic-invoicing"></a>Mise en route de la Facturation électronique

[!include [banner](../includes/banner.md)]

Cette rubrique donne des informations qui vous aideront à démarrer la Facturation électronique. Cette rubrique vous guide à travers les étapes de configuration courantes dans Regulatory Configuration Services (RCS) et Dynamics 365 Finance, et indique les étapes à suivre pour soumettre des documents commerciaux et examiner les résultats du traitement.

## <a name="prerequisites"></a>Conditions préalables

Avant d’effectuer les étapes de cette rubrique, les conditions préalables suivantes doivent être remplies :

- Configurez Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS) et votre environnement Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management. Pour plus d’informations, consultez [Prise en main de l’administration du service de Facturation électronique](e-invoicing-get-started-service-administration.md).
- Créez un fournisseur de configuration pour votre organisation. Pour plus d’informations, consultez [Créer un fournisseur de configuration et le marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider"></a>Importer une fonctionnalité de facturation électronique à partir du fournisseur de configuration Microsoft 

1. Connectez-vous à votre compte RCS (Regulatory Configuration Service).
2. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.
3. Sélectionnez **Importer**, puis **Synchroniser**.
4. Filtrez la colonne **Fournisseur de configuration** par le terme **Microsoft**.
5. Sélectionnez le nom d’une fonctionnalité de facturation électronique dans le tableau, puis sélectionnez **Importer**.

## <a name="create-an-electronic-invoicing-feature-under-your-organization-provider"></a>Créer une fonctionnalité de facturation électronique sous votre fournisseur d’organisation

1. Dans RCS, dans la section **Fonctionnalités** de l’espace de travail **Fonctionnalités de globalisation**, sélectionnez la vignette **Facturation électronique**.
2. Sélectionnez **Ajouter** > **Basé sur la fonctionnalité existante**, et dans le champ **Nom**, entrez le nom de la fonctionnalité de facturation électronique.
3. Dans le champ **Description**, entrez la description de la fonctionnalité.
4. Dans le **Champ de fonction de base**, sélectionnez la fonction de facturation électronique importée à partir du fournisseur de configuration Microsoft.
5. Sélectionnez **Créer une fonctionnalité**.

## <a name="country-specific-configuration-for-electronic-invoicing-feature"></a>Configuration spécifique au pays pour la fonctionnalité de Facturation électronique

Selon le pays ou la région, la fonctionnalité de Facturation électronique peut nécessiter une configuration particulière. 

> [!NOTE]
> Lorsque vous activez la fonctionnalité de facturation électronique pour la Finlande, les paramètres spécifiques à l’application dans les recherches ne sont pas pris en charge. Pour résoudre ce problème, dans le module **Déclaration électronique**, passez en revue les configurations des formats de facture client et de facture de projet. Configurez manuellement le champ calculé pour le mappage **$PaymentMethodSubstitution**, puis lier ce champ au champ **EpiPaymentMeansCode** à partir des formats de facture client et de facture de projet.
>
> Lorsque vous activez la fonctionnalité de facturation électronique pour l’Italie, les paramètres spécifiques à l’application dans les recherches ne sont pas pris en charge. Pour résoudre ce problème, dans le module **Déclaration électronique**, configurez manuellement le champ calculé pour le mappage **$NaturaReverseCharge**.
>
> Pour connaître les étapes spécifiques associées à d’autres emplacements, consultez la documentation « Mise en route » disponible pour votre pays ou région.

## <a name="import-the-model-mapping-configurations-from-electronic-reporting"></a>Importer les configurations de mappage de modèle pour la gestion des états électroniques

1. Dans RCS, sélectionnez l’espace de travail **Gestion des états électroniques**.
2. Dans la liste des fournisseurs de configuration **Microsoft**, sélectionnez **Référentiels**.
3. Sélectionnez **Global** et dans le volet Actions, sélectionnez **Ouvrir**.
4. Importez les configurations de mappage de modèle selon le tableau suivant par nom de fonction.

| Nom de la fonction                         | Configuration de mappage de modèle |
|--------------------------------------|-----------------------------|
| Factures électroniques autrichiennes (AT)    | <p>Modèle de contexte de facture client</p><p>Modèle de facture</p> |
| Facture électronique belge (BE)      | <p>Modèle de contexte de facture client</p><p>Modèle de facture</p> |
| NF-e (BR) pour le Brésil                  | <p>Modèle de contexte de facture client</p><p>Documents fiscaux</p><p>Modèle de message de réponse</p> |
| NFS-e ABRASF Curitiba (BR) pour le Brésil | <p>Modèle de contexte de facture client</p><p>Documents fiscaux</p><p>Modèle de message de réponse</p> |
| Facture électronique danoise (DK)       | <p>Modèle de contexte de facture client</p><p>Modèle de facture</p> |
| Facture électronique pour l’Égypte (EG)     | <p>Modèle de contexte de facture client</p><p>Modèle de facture</p><p>Modèle de message de réponse</p> |
| Facture électronique estonienne (EE)     | <p>Modèle de contexte de facture client</p><p>Modèle de facture</p> |
| Facture électronique pour la Finlande (FI)       | <p>Modèle de contexte de facture client</p><p>Modèle de facture</p> |
| Facture électronique française (FR)       | <p>Modèle de contexte de facture client</p><p>Modèle de facture</p> |
| Facture électronique allemande (DE)       | <p>Modèle de contexte de facture client</p><p>Modèle de facture</p> |
| FatturaPA (IT)                       | <p>Modèle de contexte de facture client</p><p>Modèle de facture</p> |
| CFDI Interfactura (MX) pour le Mexique       | <p>Modèle de contexte de facture client</p><p>Modèle de facture</p><p>Modèle de message de réponse</p> |
| Facture électronique néerlandaise (NL)        | <p>Modèle de contexte de facture client</p><p>Modèle de facture</p> |
| Facture électronique norvégienne (NO)    | <p>Modèle de contexte de facture client</p><p>Modèle de facture</p> |
| Facture électronique espagnole (ES)      | <p>Modèle de contexte de facture client</p><p>Modèle de facture</p> |
| Facture électronique PEPPOL            | <p>Modèle de contexte de facture client</p><p>Modèle de facture</p> |
| Facture électronique saoudienne (SA)| <p>Modèle de contexte de facture client</p><p>Modèle de facture</p> |


## <a name="configure-the-application-setup"></a>Configurer le paramétrage de l’application

1. Sélectionnez la fonctionnalité de facturation électronique que vous avez créée.
2. Dans l’onglet **Paramétrages**, sélectionnez **Paramétrage de l’application**.
3. Dans le champ **Connecter l’application**, sélectionnez la connexion associée à votre instance Finance ou Supply Chain Management.
4. Dans la section **Types de document électronique**, sélectionnez **Ajouter**.
5. Sélectionnez et entrez une valeur **Nom de la table** selon le tableau suivant.

    | Nom de la fonction                         | Document commercial | Nom de la table |
    |--------------------------------------|-------------------|------------|
    | Factures électroniques autrichiennes (AT)    | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
    | Facture électronique belge (BE)      | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
    | NF-e (BR) pour le Brésil                  | <p>Document fiscal</p><p>Lettre de correction</p> | Document fiscal |
    | NFS-e ABRASF Curitiba (BR) pour le Brésil | Document fiscal | Document fiscal |
    | Facture électronique danoise (DK)       | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
    | Facture électronique pour l’Égypte (EG)     | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
    | Facture électronique estonienne (EE)     | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
    | Facture électronique pour la Finlande (FI)       | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
    | Facture électronique française (FR)       | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
    | Facture électronique allemande (DE)       | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
    | FatturaPA (IT)                       | <p>Facture client</p><p>Facture de projet | <p>Journal des factures client</p><p>Facture de projet</p> |
    | CFDI Interfactura (MX) pour le Mexique       | <p>Facture client</p><p>Bon de livraison</p><p>Transfert de stock</p><p>Complément de paiement</p> | Journal des factures client |
    | Facture électronique néerlandaise (NL)        | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
    | Facture électronique norvégienne (NO)    | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
    | Facture électronique espagnole (ES)      | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
    | Facture électronique PEPPOL            | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
    | Facture électronique saoudienne (SA)| <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |

6. Pour chaque nom de table que vous créez, sélectionnez et entrez une valeur de contexte selon le tableau suivant.

    | Nom de la fonction                         | Document commercial | Contexte |
    |--------------------------------------|-------------------|---------|
    | Factures électroniques autrichiennes (AT)    | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | Facture électronique belge (BE)      | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | NF-e (BR) pour le Brésil                  | <p>Document fiscal</p><p>Lettre de correction</p> | <p>Modèle de contexte de facture client – Contexte du document fiscal</p><p>Modèle de contexte de facture client – Contexte de lettre de correction FD</p> |
    | NFS-e ABRASF Curitiba (BR) pour le Brésil | Document fiscal| Modèle de contexte de facture client – Contexte du document fiscal |
    | Facture électronique danoise (DK)       | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | Facture électronique pour l’Égypte (EG)     | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | Facture électronique estonienne (EE)     | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | Facture électronique pour la Finlande (FI)       | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | Facture électronique française (FR)       | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | Facture électronique allemande (DE)       | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | FatturaPA (IT)                       | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | CFDI Interfactura (MX) pour le Mexique       | <p>Facture client</p><p>Bon de livraison</p><p>Transfert de stock</p><p>Complément de paiement</p> | Modèle de contexte de facture client – Contexte de la facture client |
    | Facture électronique néerlandaise (NL)        | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | Facture électronique norvégienne (NO)    | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | Facture électronique espagnole (ES)      | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | Facture électronique PEPPOL            | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | Facture électronique saoudienne (SA)| <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |

7. Pour chaque nom de table et contexte, sélectionnez et entrez un mappage de document commercial selon le tableau suivant.

    | Nom de la fonction                         | Document commercial | Mise en correspondance du document commercial |
    |--------------------------------------|-------------------|---------------------------|
    | Factures électroniques autrichiennes (AT)    | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture – Facture client</p><p>Mappage de modèle de facture – Facture projet</p> |
    | Facture électronique belge (BE)      | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture – Facture client</p><p>Mappage de modèle de facture – Facture projet</p> |
    | NF-e (BR) pour le Brésil                  | <p>Document fiscal</p><p>Lettre de correction</p> | <p>Mappage des documents fiscaux – Mappage des documents fiscaux</p><p>Mappage des documents fiscaux – Mappage des lettres de correction</p> |
    | NFS-e ABRASF Curitiba (BR) pour le Brésil | Document fiscal | Mappage des documents fiscaux – Mappage des documents fiscaux |
    | Facture électronique danoise (DK)       | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture – Facture client</p><p>Mappage de modèle de facture – Facture projet</p> |
    | Facture électronique pour l’Égypte (EG)     | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture – Facture client</p><p>Mappage de modèle de facture – Facture projet</p> |
    | Facture électronique estonienne (EE)     | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture – Facture client</p><p>Mappage de modèle de facture – Facture projet</p> |
    | Facture électronique pour la Finlande (FI)       | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture – Facture client</p><p>Mappage de modèle de facture – Facture projet</p> |
    | Facture électronique française (FR)       | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture – Facture client</p><p>Mappage de modèle de facture – Facture projet</p> |
    | Facture électronique allemande (DE)       | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture – Facture client</p><p>Mappage de modèle de facture – Facture projet</p> |
    | FatturaPA (IT)                       | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture – Facture client</p><p>Mappage de modèle de facture – Facture projet</p> |
    | CFDI Interfactura (MX) pour le Mexique       | <p>Facture client</p><p>Bon de livraison</p><p>Transfert de stock</p><p>Complément de paiement</p> | Mappage de modèle de facture – Facture client |
    | Facture électronique néerlandaise (NL)        | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture – Facture client</p><p>Mappage de modèle de facture – Facture projet</p> |
    | Facture électronique norvégienne (NO)    | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture – Facture client</p><p>Mappage de modèle de facture – Facture projet</p> |
    | Facture électronique espagnole (ES)      | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture – Facture client</p><p>Mappage de modèle de facture – Facture projet</p> |
    | Facture électronique PEPPOL            | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture – Facture client</p><p>Mappage de modèle de facture – Facture projet</p> |
    | Facture électronique saoudienne (SA)| <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture – Facture client</p><p>Mappage de modèle de facture – Facture projet</p> |


## <a name="country-specific-configuration-of-application-setup"></a>Configuration du paramétrage de l’application spécifique au pays

Selon le pays ou la région, le paramétrage de l’application peut nécessiter une configuration particulière. 

Pour connaître les étapes spécifiques, consultez la documentation de mise en route disponible pour votre pays ou région.

## <a name="deploy-the-electronic-invoicing-feature-to-service-environment"></a>Déployer la fonctionnalité de Facturation électronique dans l’environnement de service

1. Sur l’onglet **Versions**, sélectionnez la version de la fonctionnalité de facturation électronique que vous souhaitez déployer.
2. Sélectionnez **Modifier le statut** \> **Terminé**.
3. Sélectionnez **Modifier le statut** \> **Publier**.
4. Sélectionnez **Déployer**.
5. Définissez l’option **Déployer sur une application connectée** sur **Non**.
6. Définissez l’option **Déployer sur un environnement de service** sur **Oui**.
7. Dans le champ **Environnement de service**, sélectionnez l’environnement de service de Facturation électronique dans lequel vous souhaitez déployer la fonctionnalité de Facturation électronique.
8. Dans le champ **Date de début**, sélectionnez la date à laquelle la fonctionnalité de Facturation électronique doit entrer en vigueur dans la Facturation électronique.
9. Cliquez sur **OK**.

## <a name="deploy-the-electronic-invoicing-feature-to-connected-application"></a>Déployer la fonctionnalité de Facturation électronique dans une application connectée

1. Sur l’onglet **Versions**, sélectionnez une version de la fonctionnalité de Facturation électronique que vous souhaitez déployer.
2. Sélectionnez **Déployer**.
3. Définissez l’option **Déployer sur une application connectée** sur **Oui**.
4. Dans le champ **Connecter l’application**, sélectionnez la connexion associée à votre instance Finance ou Supply Chain Management.
5. Définissez l’option **Déployer sur un environnement de service** sur **Non**.
6. Cliquez sur **OK**.

## <a name="turn-on-the-electronic-invoicing-feature-in-finance-or-supply-chain-management"></a>Activer la fonctionnalité de facturation électronique dans Finance ou Supply Chain Management

1. Connectez-vous à Finance ou Supply Chain Management et vérifiez que vous êtes dans la bonne entité juridique.
2. Allez dans **Administration de l’organisation** \> **Paramétrage** \> **Paramètres des documents électroniques**.
3. Dans l’onglet **Fonctionnalités**, sélectionnez la fonctionnalité spécifique au pays/à la région pour activer la fonctionnalité de facturation électronique pour Finance ou Supply Chain Management. Le tableau suivant fournit une liste des fonctionnalités de facturation électronique disponibles pour des pays/régions spécifiques. 

    | Nom de la fonction                                          | Pays/région  |
    |-------------------------------------------------------|-----------------|
    | Factures électroniques autrichiennes (AT)                     | Autriche         |
    | Facture électronique belge (BE)                       | Belgique         |
    | Facture électronique CFDI pour le Mexique (MX)                  | Mexique          |
    | Facture électronique danoise (DK)                        | Danemark         |
    | Facture électronique néerlandaise (NL)                         | Pays-Bas |
    | Facture électronique pour l’Égypte (EG)                      | Égypte           |
    | Facture électronique estonienne (EE)                      | Estonie         |
    | Facture électronique finlandaise (DK)                       | Finlande         |
    | Facture électronique française (FR)                        | France          |
    | Facture électronique allemande (DE)                        | Allemagne         |
    | Facture électronique italienne (IT)                       | Italie           |
    | NF-e Federal – Facture électronique pour le Brésil (BR)      | Brésil          |
    | NFS-e – Facture électronique du service brésilien (ville)   | Brésil          |
    | Facture électronique norvégienne (NO)                     | Norvège          |
    | Facture électronique PEPPOL                             | Général          |
    | Facture électronique espagnole (ES)                       | Espagne           |
    | Facture électronique saoudienne (SA)                 | Arabie saoudite    |
    

4. Sélectionnez **Enregistrer**.

## <a name="issue-electronic-invoices"></a>Émettre des factures électroniques

1. Allez dans **Administration de l’organisation** \> **Périodique** \> **Documents électroniques** \> **Envoyer des documents électroniques**.
2. Dans l’organisateur **Enregistrements à inclure**, sélectionnez **Filtre**.
3. Sélectionnez **Ajouter** pour ajouter un nom de table au filtre de requête.
4. Sélectionnez la table qui contient les factures.

    > [!NOTE]
    > Le nom de la table doit être répertorié dans le tableau de la section précédente [Configurer le paramétrage de l’application](#configure-the-application-setup) dans cette rubrique.

5. Sélectionnez le nom de champ dans la table que vous souhaitez interroger.
6. Entrez le nom de la table et le nom du champ pour les critères à interroger.
7. Répétez les étapes 5 et 6 pour ajouter d’autres champs et critères à la requête, puis cliquez sur **OK**.
8. Cliquez sur **OK**.

## <a name="view-submission-logs"></a>Afficher les journaux d’envoi

1. Allez dans **Administration de l’organisation** \> **Périodique** \> **Documents électroniques** \> **Journal d’envoi de documents électroniques**.
2. Dans le champ **Type de document**, sélectionnez la table contenant les factures.

    > [!NOTE]
    > Le nom de la table doit être répertorié dans le tableau de la section précédente [Configurer le paramétrage de l’application](#configure-the-application-setup) dans cette rubrique.

3. Sélectionnez une facture dans la grille, puis sélectionnez **Recherches** \> **Détails de l’envoi**.

## <a name="download-an-electronic-document-file"></a>Télécharger un fichier de document électronique

1. Allez dans **Administration de l’organisation** \> **Périodique** \> **Documents électroniques** \> **Journal d’envoi de documents électroniques**.
2. Dans le champ **Type de document**, sélectionnez la table contenant les factures.
3. Sélectionnez un document dans la grille, puis sélectionnez **Document électronique** \> **Télécharger un fichier**. Une archive contenant le fichier du document électronique sera proposée au téléchargement.

> [!NOTE]
> Avant de pouvoir télécharger des fichiers, l’option **Exporter le résultat** doit être activée pour l’action associée dans la configuration de la fonctionnalité Facturation électronique dans RCS.

## <a name="related-topics"></a>Rubriques connexes

- [Vue d’ensemble de la Facturation électronique](e-invoicing-service-overview.md)
- [Mise en route de l’administration du service de Facturation électronique](e-invoicing-get-started-service-administration.md)
- [Mise en route de la Facturation électronique pour le Brésil](e-invoicing-bra-get-started.md)
- [Mise en route de la Facturation électronique pour le Mexique](e-invoicing-mex-get-started.md)
- [Mise en route de la facturation électronique pour l’Italie](e-invoicing-ita-get-started.md)
- [Factures électroniques client en Égypte](emea-egy-e-invoices.md)
- [Factures électroniques client en Arabie saoudite](emea-sau-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
