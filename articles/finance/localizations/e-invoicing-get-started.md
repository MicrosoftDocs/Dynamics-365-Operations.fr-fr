---
title: Démarrage du module complémentaire de facturation électronique
description: Cette rubrique donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 07954c5c96f390bc651794f8b6c61f2a1a17ab8b
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111218"
---
# <a name="get-started-with-the-electronic-invoicing-add-on"></a>Démarrage du module complémentaire de facturation électronique

[!include [banner](../includes/banner.md)]

Cette rubrique donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique.

Le tableau suivant répertorie les fonctionnalités de facturation électronique et les documents commerciaux auxquels elles peuvent être appliquées.

| Nom de la fonction                         | Document commercial |
|--------------------------------------|-------------------|
| Factures électroniques autrichiennes (AT)    | <p>Facture client</p><p>Facture de projet</p> |
| Facture électronique belge (BE)      | <p>Facture client</p><p>Facture de projet</p> |
| NF-e (BR) pour le Brésil                  | <p>Modèle 55 du document fiscal</p><p>Lettre de correction</p> |
| NFS-e ABRASF Curitiba (BR) pour le Brésil | Document fiscal |
| NFS-e São Paulo (BR) pour le Brésil       | Document fiscal |
| Facture électronique danoise (DK)       | <p>Facture client</p><p>Facture de projet</p> |
| Facture électronique pour l'Égypte (EG)     | <p>Facture client</p><p>Facture de projet</p> |
| Facture électronique estonienne (EE)     | <p>Facture client</p><p>Facture de projet</p> |
| Facture électronique pour la Finlande (FI)       | <p>Facture client</p><p>Facture de projet</p> |
| Facture électronique française (FR)       | <p>Facture client</p><p>Facture de projet</p> |
| Facture électronique allemande (DE)       | <p>Facture client</p><p>Facture de projet</p> |
| FatturaPA (IT)                       | <p>Facture client</p><p>Facture de projet</p> |
| CFDI Interfactura (MX) pour le Mexique       | <p>Facture client</p><p>Bon de livraison</p><p>Transfert de stock</p><p>Complément de paiement</p> |
| Facture électronique néerlandaise (NL)        | <p>Facture client</p><p>Facture de projet</p> |
| Facture électronique norvégienne (NO)    | <p>Facture client</p><p>Facture de projet</p> |
| Facture électronique espagnole (ES)      | <p>Facture client</p><p>Facture de projet</p> |
| Facture électronique PEPPOL            | <p>Facture client</p><p>Facture de projet</p> |

## <a name="prerequisites"></a>Conditions préalables

Avant d’effectuer les étapes de cette rubrique, les conditions préalables suivantes doivent être remplies :

- Configurez votre service de configuration réglementaire (RCS) et l'environnement Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management afin de pouvoir effectuer des soumissions au module complémentaire de facturation électronique.
- Créez un environnement de service et publiez-le dans le module complémentaire de facturation électronique. Pour plus d'informations, consultez [Prise en main de l'administration du service du module complémentaire de facturation électronique](e-invoicing-get-started-service-administration.md).
- Créez une application connectée. Pour plus d'informations, consultez [Prise en main de l'administration du service du module complémentaire de facturation électronique](e-invoicing-get-started-service-administration.md).
- Créez un fournisseur de configuration pour votre organisation. Pour plus d'informations, consultez [Créer des fournisseurs de configuration et les marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider"></a>Importer une fonctionnalité de facturation électronique à partir du fournisseur de configuration Microsoft 

1. Connectez-vous à votre compte RCS (Regulatory Configuration Service).
2. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.
3. Sélectionnez **Importer**, puis **Synchroniser**.
4. Filtrez la colonne **Fournisseur de configuration** par le terme **Microsoft**.
5. Sélectionnez le nom d'une fonction de facturation électronique dans le tableau au début de cette rubrique, puis sélectionnez **Importer**.

## <a name="create-an-electronic-invoicing-feature-under-your-organization-provider"></a>Créer une fonctionnalité de facturation électronique sous votre fournisseur d'organisation

1. Dans RCS, dans la section **Fonctionnalités** de l’espace de travail **Fonctionnalité de globalisation**, sélectionnez la vignette **Facturation électronique**.
2. Sélectionnez **Ajouter** > **Basé sur la fonctionnalité existante**, et dans le champ **Nom**, entrez le nom de la fonctionnalité de facturation électronique.
3. Dans le champ **Description**, entrez la description de la fonctionnalité.
4. Dans le **Champ de fonction de base**, sélectionnez la fonction de facturation électronique importée à partir du fournisseur de configuration Microsoft.
5. Sélectionnez **Créer une fonctionnalité**.

## <a name="configure-the-electronic-invoicing-feature"></a>Configurer la fonctionnalité de facturation électronique

Selon le pays ou la région, la fonctionnalité de facturation électronique peut nécessiter une configuration supplémentaire. Pour connaître les étapes spécifiques, consultez la documentation de mise en route disponible pour votre pays ou région.

## <a name="configure-the-application-setup"></a>Configurer le paramétrage de l'application

1. Sélectionnez la fonctionnalité de facturation électronique que vous avez créée.
2. Sur l'onglet **Version**, vérifiez que la version **Brouillon** est sélectionnée.
3. Dans l'onglet **Paramétrages**, sélectionnez **Paramétrage de l'application**.

    > [!NOTE]
    > Vérifiez que votre organisation est définie comme fournisseur de configuration **Actif**. Pour plus d'informations, consultez [Créer des fournisseurs de configuration et les marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

4. Sélectionnez **Paramétrage de fonctionnalité**, puis **Application connectée**.
5. Dans la section **Types de document électronique**, sélectionnez **Ajouter**.
6. Pour chaque document commercial pris en charge par la fonctionnalité, sélectionnez et entrez une valeur **Nom de table** selon le tableau suivant.

    | Nom de la fonction                         | Document commercial | Nom de la table |
    |--------------------------------------|-------------------|------------|
    | Factures électroniques autrichiennes (AT)    | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
    | Facture électronique belge (BE)      | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
    | NF-e (BR) pour le Brésil                  | <p>Document fiscal</p><p>Lettre de correction</p> | Document fiscal |
    | NFS-e ABRASF Curitiba (BR) pour le Brésil | Document fiscal | Document fiscal |
    | NFS-e São Paulo (BR) pour le Brésil       | Document fiscal | Document fiscal |
    | Facture électronique danoise (DK)       | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
    | Facture électronique pour l'Égypte (EG)     | <p>Facture client</p><p>Facture de projet</p> | <p>Journal des factures client</p><p>Facture de projet</p> |
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

7. Pour chaque document commercial pris en charge par la fonctionnalité, sélectionnez et entrez une valeur **Contexte** selon le tableau suivant.

    | Nom de la fonction                         | Document commercial | Contexte |
    |--------------------------------------|-------------------|---------|
    | Factures électroniques autrichiennes (AT)    | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | Facture électronique belge (BE)      | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | NF-e (BR) pour le Brésil                  | <p>Document fiscal</p><p>Lettre de correction</p> | <p>Modèle de contexte de facture client – Contexte du document fiscal</p><p>Modèle de contexte de facture client - Contexte de lettre de correction FD</p> |
    | NFS-e ABRASF Curitiba (BR) pour le Brésil | Document fiscal du service| Modèle de contexte de facture client – Contexte du document fiscal |
    | NFS-e São Paulo (BR) pour le Brésil       | Document fiscal du service| Modèle de contexte de facture client – Contexte du document fiscal |
    | Facture électronique danoise (DK)       | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
    | Facture électronique pour l'Égypte (EG)     | <p>Facture client</p><p>Facture de projet</p> | <p>Modèle de contexte de facture client – Contexte de la facture client</p><p>Modèle de contexte de facture client – Contexte de la facture de projet</p> |
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

8. Pour chaque document commercial pris en charge par la fonctionnalité, sélectionnez et entrez une valeur **Mappage de document commercial** selon le tableau suivant.

    | Nom de la fonction                         | Document commercial | Mise en correspondance du document commercial |
    |--------------------------------------|-------------------|---------------------------|
    | Factures électroniques autrichiennes (AT)    | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture - Facture client</p><p>Mappage de modèle de facture - Facture projet</p> |
    | Facture électronique belge (BE)      | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture - Facture client</p><p>Mappage de modèle de facture - Facture projet</p> |
    | NF-e (BR) pour le Brésil                  | <p>Document fiscal</p><p>Lettre de correction</p> | <p>Mappage des documents fiscaux - Mappage des documents fiscaux</p><p>Mappage des documents fiscaux - Mappage des lettres de correction</p> |
    | NFS-e ABRASF Curitiba (BR) pour le Brésil | Document fiscal du service | Mappage des documents fiscaux - Mappage des documents fiscaux |
    | NFS-e São Paulo (BR) pour le Brésil       | Document fiscal du service | Mappage des documents fiscaux - Mappage des documents fiscaux |
    | Facture électronique danoise (DK)       | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture - Facture client</p><p>Mappage de modèle de facture - Facture projet</p> |
    | Facture électronique pour l'Égypte (EG)     | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture - Facture client</p><p>Mappage de modèle de facture - Facture projet</p> |
    | Facture électronique estonienne (EE)     | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture - Facture client</p><p>Mappage de modèle de facture - Facture projet</p> |
    | Facture électronique pour la Finlande (FI)       | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture - Facture client</p><p>Mappage de modèle de facture - Facture projet</p> |
    | Facture électronique française (FR)       | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture - Facture client</p><p>Mappage de modèle de facture - Facture projet</p> |
    | Facture électronique allemande (DE)       | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture - Facture client</p><p>Mappage de modèle de facture - Facture projet</p> |
    | FatturaPA (IT)                       | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture - Facture client</p><p>Mappage de modèle de facture - Facture projet</p> |
    | CFDI Interfactura (MX) pour le Mexique       | <p>Facture client</p><p>Bon de livraison</p><p>Transfert de stock</p><p>Complément de paiement</p> | Mappage de modèle de facture - Facture client |
    | Facture électronique néerlandaise (NL)        | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture - Facture client</p><p>Mappage de modèle de facture - Facture projet</p> |
    | Facture électronique norvégienne (NO)    | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture - Facture client</p><p>Mappage de modèle de facture - Facture projet</p> |
    | Facture électronique espagnole (ES)      | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture - Facture client</p><p>Mappage de modèle de facture - Facture projet</p> |
    | Facture électronique PEPPOL            | <p>Facture client</p><p>Facture de projet</p> | <p>Mappage de modèle de facture - Facture client</p><p>Mappage de modèle de facture - Facture projet</p> |

Selon le pays ou la région, la fonctionnalité de facturation électronique peut nécessiter une configuration supplémentaire. Pour connaître les étapes spécifiques, consultez la documentation de mise en route disponible pour votre pays ou région.

## <a name="deploy-the-electronic-invoicing-feature"></a>Déployer la fonctionnalité de facturation électronique

1. Sur l'onglet **Versions**, sélectionnez la version de la fonctionnalité de facturation électronique que vous souhaitez déployer.
2. Sélectionnez **Modifier le statut** \> **Terminé**.
3. Sélectionnez **Modifier le statut** \> **Publier**.
4. Sélectionnez **Déployer**.
5. Définissez l'option **Déployer sur une application connectée** sur **Oui**.
6. Sur la page **Connecter l'application**, sélectionnez la connexion associée à votre instance Finance ou Supply Chain Management.
7. Définissez l'option **Déployer sur un environnement de service** sur **Oui**.
8. Dans le champ **Environnement de service**, sélectionnez l'environnement de service complémentaire de facturation électronique dans lequel vous souhaitez déployer la fonctionnalité de facturation électronique.
9. Dans le champ **Date de début**, sélectionnez la date à laquelle la fonctionnalité de facturation électronique doit entrer en vigueur dans le module complémentaire Facturation électronique.
10. Cliquez sur **OK**.

## <a name="turn-on-the-electronic-invoicing-feature-in-finance-or-supply-chain-management"></a>Activer la fonctionnalité de facturation électronique dans Finance ou Supply Chain Management

1. Connectez-vous à Finance ou Supply Chain Management et vérifiez que vous êtes dans la bonne entité juridique.
2. Allez dans **Administration de l’organisation** \> **Paramétrage** \> **Paramètres des documents électroniques**.
3. Sur l'onglet **Fonctionnalités**, sélectionnez la ou les références de fonctionnalité répertoriées dans le tableau suivant pour activer la fonctionnalité de facturation électronique pour Finance ou Supply Chain Management.

    | Nom de la fonction                         | Pays/région  | Référence de la fonctionnalité |
    |--------------------------------------|-----------------|-------------------|
    | Factures électroniques autrichiennes (AT)    | Autriche         | EUR-00023 |
    | Facture électronique belge (BE)      | Belgique         | EUR-00023 |
    | NF-e (BR) pour le Brésil                  | Brésil          | BR-00053 |
    | NFS-e ABRASF Curitiba (BR) pour le Brésil | Brésil          | BR-00095 |
    | NFS-e São Paulo (BR) pour le Brésil       | Brésil          | BR-00095 |
    | Facture électronique danoise (DK)       | Danemark         | <p>EUR-00023</p><p>DK-00001</p> |
    | Facture électronique néerlandaise (NL)        | Pays-Bas | EUR-00023 |
    | Facture électronique pour l'Égypte (EG)     | Égypte           | EG-00008 |
    | Facture électronique estonienne (EE)     | Estonie         | EUR-00023 |
    | Facture électronique finlandaise (DK)      | Finlande         | EUR-00023 |
     Facture électronique française (FR)       | France           | EUR-00023 |
    | Facture électronique allemande (DE)       | Allemagne         | EUR-00023 |
    | CFDI Interfactura (MX) pour le Mexique       | Mexique          | <p>MX-00010</p><p>MX-00016</p> |
    | Facture électronique norvégienne (NO)    | Norvège          | <p>EUR-00023</p><p>NO-00010</p> |
    | Facture électronique espagnole (ES)      | Espagne           | <p>EUR-00023</p><p>ES-00025</p> |
    | Facture électronique italienne (IT)      | Italie           | <p>EUR-00023</p><p>IT-00036</p> |
    | Facture électronique PEPPOL            | Europe          | EUR-00023 |

4. Sélectionnez **Enregistrer**.

## <a name="issue-electronic-invoices"></a>Émettre des factures électroniques

1. Allez dans **Administration de l’organisation** \> **Périodique** \> **Documents électroniques** \> **Envoyer des documents électroniques**.
2. Dans l’organisateur **Enregistrement à inclure**, sélectionnez **Filtre**.
3. Sélectionnez **Ajouter** pour ajouter un nom de table au filtre de requête.
4. Sélectionnez la table qui contient les factures.

    > [!NOTE]
    > Le nom de la table doit être répertorié dans le tableau de la section précédente [Configurer le paramétrage de l'application](#configure-the-application-setup) dans cette rubrique.

5. Sélectionnez le nom de champ dans la table que vous souhaitez interroger.
6. Entrez le nom de la table et le nom du champ pour les critères à interroger.
7. Répétez les étapes 5 et 6 pour ajouter d'autres champs et critères à la requête, puis cliquez sur **OK**.
8. Cliquez sur **OK**.

## <a name="view-submission-logs"></a>Afficher les journaux d’envoi

1. Allez dans **Administration de l’organisation** \> **Périodique** \> **Documents électroniques** \> **Journal d’envoi de documents électroniques**.
2. Dans le champ **Type de document**, sélectionnez la table contenant les factures.

    > [!NOTE]
    > Le nom de la table doit être répertorié dans le tableau de la section précédente [Configurer le paramétrage de l'application](#configure-the-application-setup) dans cette rubrique.

3. Sélectionnez une facture dans la grille, puis sélectionnez **Recherches** \> **Détails de l’envoi**.

Selon le pays ou la région, la fonctionnalité de facturation électronique peut nécessiter une configuration supplémentaire. Pour connaître les étapes spécifiques, consultez la documentation de mise en route disponible pour votre pays ou région.

## <a name="related-topics"></a>Rubriques connexes

- [Vue d’ensemble du module complémentaire de facturation électronique](e-invoicing-service-overview.md)
- [Démarrage du module complémentaire de facturation électronique pour le Brésil](e-invoicing-bra-get-started.md)
- [Démarrage du module complémentaire de facturation électronique pour le Mexique](e-invoicing-mex-get-started.md)
- [Démarrage du module complémentaire de facturation électronique pour l’Italie](e-invoicing-ita-get-started.md)
- [Factures électroniques client en Égypte](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]