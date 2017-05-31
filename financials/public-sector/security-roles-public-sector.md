---
title: "Rôles de sécurité dans le secteur public"
description: "Cet article décrit la fonctionnalité des rôles de sécurité du secteur public. Cette fonctionnalité inclut les rôles de chef de projet et d&quot;acheteurs dans le secteur public."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: UserRequestListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19721
ms.assetid: e26a6d93-851e-46be-8543-de2798909350
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c47486fa12a985797373c9d0e3b766fd69157366
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="security-roles-in-the-public-sector"></a>Rôles de sécurité dans le secteur public

[!include[banner](../includes/banner.md)]


Cet article décrit la fonctionnalité des rôles de sécurité du secteur public. Cette fonctionnalité inclut les rôles de chef de projet et d'acheteurs dans le secteur public.

Pour que les utilisateurs puissent accéder à Microsoft Dynamics 365 for Operations, au moins un rôle de sécurité doit leur être affecté. Les rôles de sécurité déterminent les responsabilités que les utilisateurs peuvent exercer et les parties de l'interface utilisateur qu'ils peuvent afficher.

## <a name="what-are-the-prerequisites-for-assigning-security-roles-in-the-public-sector"></a>Quelles sont les conditions préalables à affecter des l'affectation des rôles de sécurité dans le secteur public ?
Pour que vous puissiez affecter des utilisateurs à des rôles, ils doivent exister dans Microsoft Dynamics 365 for Operations. Même si vous utilisez l'affectation automatique des rôles, les utilisateurs eux-mêmes ne sont pas automatiquement ajoutés à Microsoft Dynamics 365 for Operations.

## <a name="which-roles-do-i-have-to-assign"></a>Quelles rôles dois-je affecter ?
Une fois que les utilisateurs sont dans le système, il existe deux rôles que vous devrez peut-être paramétrer pour les organisations du secteur public :

-   Chef de projet
-   Acheteurs

### <a name="what-is-the-project-manager---public-sector-role"></a>Qu'est-ce que le rôle Gestionnaire de projets - Secteur public ?

Le rôle de sécurité **Gestionnaire de projets - Secteur public** prend en charge les extensions de secteur public pour la gestion de projets. Affectez ce rôle en sus du rôle **Chef de projet** pour donner aux gestionnaires de projets l'accès à la fonctionnalité de gestion de projets. Par défaut, les responsabilités suivantes sont affectées à ce rôle de sécurité dans Microsoft Dynamics 365 for Operations.

| Nom de droits de douane                                                         | Droit de douane (nom AOA)                           | Description du droit                                                                |
|-------------------------------------------------------------------|-----------------------------------------|---------------------------------------------------------------------------------|
| Se renseigner sur la progression des commandes fournisseur à facturer pour le secteur public | PurchOrderToInvoiceProgressInquire\_PSN | Répondre aux demandes de renseignements sur le statut du processus « de la commande fournisseur à la facture ». |

### <a name="what-is-the-purchasing-agent---public-sector-role"></a>Qu'est-ce que le rôle Agent des achats - Secteur public ?

Le rôle de sécurité **Agent des achats - Secteur public** prend en charge les extensions de secteur public pour la gestion de projets. Affectez ce rôle en sus du rôle **Acheteurs** pour donner aux acheteurs l'accès à la fonctionnalité d'achat. Par défaut, les responsabilités suivantes sont affectées à ce rôle de sécurité dans Microsoft Dynamics 365 for Operations.

| Nom de droits de douane                                                       | Droit de douane (nom AOA)                            | Description du droit                                                                                        |
|-----------------------------------------------------------------|------------------------------------------|---------------------------------------------------------------------------------------------------------|
| Mettre à jour les données principales de contrat d'achat                              | AgreementPurchaseAgreementMasterMaintain | Mettre à jour les détails de contrats d'achat.                                                            |
| Configurer la synchronisation EIA                                   | AifSyncConfigure                         | Spécifier des filtres sur les ports.                                                                               |
| Se renseigner sur la progression des dossiers d'achat                           | CasePurchasingCaseProgressInquire        | Répondre aux demandes de renseignements sur le statut des dossiers d'achat.                                              |
| Tenir les catalogues à jour                                               | CatProcurementCatalogMasterMaintain      | Mettre à jour tous les types de catalogues.                                                                         |
| Mettre à jour tous les détails de la hiérarchie de catégories                         | EcoResCategoryMasterMaintain             | Mettre à jour les catégories.                                                                                    |
| Effectuer une recherche sur les données principales de définition des produits                         | EcoResProductDefinitionMasterInquire     | Répondre aux demandes concernant les données principales pour les définitions de produits                                         |
| Se renseigner sur les données de configuration du configurateur                 | PBAProductBuilderConfigStatusInquire     | Ouvrir et réviser les configurations du configurateur.                                                         |
| Mettre à jour la configuration du configurateur                          | PBAProductBuilderConfigurationMaintain   | Modifier et mettre à jour les configurations du configurateur.                                                         |
| Tenir à jour la configuration du produit                                  | PCProductConfigConfigurationMaintain     | Mettre à jour une configuration basé sur les contraintes pour les modèles de configuration de produit.                             |
| Examiner la configuration du produit                              | PCProductConfigConfigurationStatInquir   | Répondre aux demandes de renseignements sur les données principales de configuration pour les modèles de configuration de produits basée sur les contraintes. |
| Mettre à jour les paramètres de gestion d'impression de configuration des achats               | PrintMgmtPurchaseSettingsMaintain        | Mettre à jour les paramètres de gestion d'impression pour le paramétrage des achats.                                                 |
| Mettre à jour les paramètres de gestion d'impression des documents d'achats            | PrintMgmtPurchDocumentSettingsMaintain   | Mettre à jour les paramètres de gestion d'impression des documents d'achat.                                              |
| Se renseigner sur les politiques d'achat                                | ProcPurchasingProcessInquire             | Répondre aux demandes de renseignements sur les stratégies régissant le processus d'achat.                                 |
| Se renseigner sur les politiques d'achat pour le secteur public              | ProcPurchasingProcessInquire\_PSN        | Répondre aux demandes de renseignements sur les stratégies du secteur public régissant le processus d'achat.                   |
| Approuver le contrat d'achat                                      | PurchaseAgreementWFMaintain              | Réviser et approuver les contrats d'achat dans un workflow.                                                   |
| Tenir à jour les commandes fournisseur                                        | PurchOrderMaintain                       | Documenter et enregistrer les commandes fournisseur                                                                    |
| Tenir à jour la consolidation des demandes d'achat                     | PurchReqConsolidationMaintain            | Mettre à jour le processus de consolidation des demandes d'achat.                                                |
| Tenir à jour la création de commandes fournisseur à partir de demandes d'achat | PurchReqOrderFromRequisitionMaintain     | Lancer les commandes fournisseur à partir de demandes d'achat.                                                     |
| Approuver les demandes d'achat                                   | PurchReqPurchaseRequisitionApprove       | Approuver et autoriser les demandes d'achat.                                                            |
| Mettre à jour toutes les demandes d'achat                              | PurchReqPurchaseRequisitionMaintainAll   | Modifier et mettre à jour les demandes d'achat.                                                                  |
| Afficher les demandes d'achat en attente                              | PurchReqTableView                        | Ouvrir et réviser les demandes d'achat en attente.                                                 |
| Mettre à jour le questionnaire d'appel d'offre                    | PurchRFQQuestionnaireMaintain            | Modifier et mettre à jour les questionnaires d'appel d'offre.                                             |
| Mettre à jour l'appel d'offre                                  | PurchRFQRequestForQuoteMaintain          | Modifier et mettre à jour les appels d'offre.                                                                                   |
| Tenir à jour les réponses aux appels d'offre                          | PurchRFQRequestForQuoteReplyMaintain     | Modifier et mettre à jour les réponses aux appels d'offre.                                                                            |
| Tenir à jour les offres scellées                                            | PurchRFQSealedBids                       | Modifier et mettre à jour les offres scellées.                                                                            |
| Se renseigner sur le statut de paiement des factures fournisseur                | VendInvoice4paymentStatusInquire\_RU     | Répondre aux demandes de renseignements sur le statut de paiement des factures fournisseur.                                      |
| Tenir à jour les factures fournisseur pour le paiement                            | VendInvoice4PaymMaintain\_RU             | Modifier et mettre à jour les factures fournisseur pour paiement.                                                            |
| Mettre à jour les données principales de fournisseur potentiel                              | VendProspectiveVendorMasterMaintain      | Modifier et mettre à jour les données principales de fournisseur potentiel.                                                          |
| Mettre à jour les demandes fournisseur initiées par les employés                     | VendRequestEmployeeVendorRequestMaintain | Documenter et enregistrer les demandes fournisseur initiées par les employés.                                                 |
| Se renseigner sur le statut des demandes initiées par les fournisseurs                    | VendRequestVendorInitiateRequestInquire  | Répondre aux demandes de renseignements sur le statut des demandes initiées par les fournisseurs.                                     |
| Effectuer une recherche sur les données principales de fournisseur non sollicité                          | VendUnsolicitedVendorMasterInquire       | Répondre aux demandes concernant les données principales de fournisseur non sollicité.                                              |
| Mettre à jour les demandes utilisateur fournisseur                                   | VendUserRequestMaintain                  | Mettre à jour et soumettre les demandes de l'utilisateur fournisseur.                                                               |
| Mettre à jour les données principales sur le fournisseur                                          | VendVendorMasterMaintain                 | Modifier et mettre à jour les données principales de fournisseur                                                                      |
| Mettre à jour les questionnaires fournisseur                                  | VendVendorQuestionnaireMaintain          | Créer et mettre à jour les informations du questionnaire fournisseur.                                                     |
| Se renseigner sur les performances du workflow                               | WorkflowViewWorkflowPerf                 | Afficher les états sur les performances des workflows.                                                        |

## <a name="what-do-i-do-next"></a>Que faire ensuite ?
Une fois les utilisateurs créés, vous les affectez à des rôles sur la page **Affecter des utilisateurs aux rôles**.

<a name="see-also"></a>Voir également :
--------

[Sécurité basée sur les rôles](/dynamics365/operations/dev-itpro/sysadmin/role-based-security)




