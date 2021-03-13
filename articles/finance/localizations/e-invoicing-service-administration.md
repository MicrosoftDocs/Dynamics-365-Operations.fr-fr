---
title: Composants d'administration du module complémentaire de facturation électronique
description: Cette rubrique fournit des informations sur les composants liés à l'administration du module complémentaire de facturation électronique.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
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
ms.openlocfilehash: 6f630ebb694217c3bd52378a649933a670c090f2
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104380"
---
# <a name="electronic-invoicing-add-on-administration-components"></a>Composants d'administration du module complémentaire de facturation électronique

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Cette rubrique fournit des informations sur les composants liés à l'administration du module complémentaire de facturation électronique. Elle fournit également des informations sur la configuration du service du module complémentaire de facturation électronique.

## <a name="azure"></a>Azure

Utilisez Microsoft Azure pour créer les secrets du coffre de clés et du compte de stockage. Utilisez ensuite les secrets dans la configuration du module complémentaire de facturation électronique.

## <a name="lifecycle-services"></a>Lifecycle Services

Utilisez Microsoft Dynamics Lifecycle Services (LCS) pour activer le module complémentaire pour les microservices de votre projet de déploiement LCS.

Dans LCS, sélectionnez la vignette **Gestion des fonctionnalités d'aperçu**, puis activez la fonctionnalité **Service de facturation électronique**.

## <a name="regulatory-configuration-services"></a>Regulatory Configuration Services

Dynamics 365 Regulatory Configuration Services (RCS) est l'interface utilisée pour configurer le module complémentaire de facturation électronique. Des ressources telles que des environnements et des fonctionnalités de facturation électronique sont créées, gérées et hébergées dans RCS. Lorsque les ressources sont prêtes, elles sont publiées dans le service du module complémentaire de facturation électronique.

Pour plus d’informations sur RCS, voir [Regulatory Configuration Services (RCS) - Fonctionnalités de globalisation](rcs-globalization-feature.md).

### <a name="integration-with-the-electronic-invoicing-add-on"></a>Intégration avec le module complémentaire de facturation électronique

Avant de pouvoir utiliser RCS pour configurer des factures électroniques, vous devez le configurer pour permettre la communication avec le module complémentaire de facturation électronique. Vous devez effectuer cette configuration sur l'onglet **Module complémentaire de facturation électronique** de la page **Paramètres de la gestion des états électroniques**.

#### <a name="service-endpoint"></a>Point de terminaison de service

L'URL du point de terminaison du module complémentaire de facturation électronique peut varier en fonction de l'emplacement géographique du centre de données Azure. Le tableau suivant répertorie la disponibilité par région :

| Emplacement géographique du centre de données Azure | URL du point de terminaison de service                                                       |
|----------------------------|----------------------------------------------------------------------------|
| Est des États-Unis                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
| Ouest des États-Unis                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
| Nord de l'UE                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
| Ouest de l'UE                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

#### <a name="application-id"></a>ID candidature

L'ID de l'application est l'ID de l'application du module complémentaire de facturation électronique. Dans le cas présent, la valeur est fixe : **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

#### <a name="lcs-environment-id"></a>ID d'environnement LCS

L'ID d'environnement LCS est l'ID de l'abonnement LCS de votre organisation.

### <a name="service-environments"></a>Environnements de service

Les environnements de service sont des partitions logiques créées pour prendre en charge l'exécution des fonctionnalités de facturation électronique dans le module complémentaire de facturation électronique. Les secrets de sécurité et les certificats numériques, ainsi que la gouvernance (c'est-à-dire les autorisations d'accès), doivent être configurés au niveau de l'environnement de service.

Les clients peuvent créer autant d'environnements de service qu'ils le souhaitent. Tous les environnements de service créés par un client sont indépendants les uns des autres.

Les environnements de service doivent être créés et gérés dans RCS. Lorsque les environnements de service sont prêts, ils doivent être publiés dans le module complémentaire de facturation électronique.

#### <a name="service-environment-status"></a>Statut de l'environnement de service

Les environnements de service peuvent être gérés via leur statut. Les options possibles sont :

- **Non publié** - L'environnement a été créé, mais il n'a pas encore été publié.
- **Publié** - L'environnement a été publié dans le module complémentaire de facturation électronique.
- **Modifié** - Les attributs d'un environnement publié ont été modifiés, mais les modifications n'ont pas encore été publiées.

#### <a name="customer-secrets"></a>Secrets clients

Le service complémentaire de facturation électronique a la responsabilité de stocker toutes vos données métier dans les ressources Azure appartenant à votre société. Pour vous assurer que le service fonctionne correctement et que toutes les données métier nécessaires et générées par le module complémentaire de facturation électronique ne sont accessibles que par ce dernier, vous devez créer deux ressources Azure principales :

- Un compte de stockage Azure (stockage Blob) qui va stocker les factures électroniques
- Un coffre de clés Azure qui va stocker les certificats et l’Uniform Resource Identifier (URI) du compte de stockage

> [!NOTE]
> Une ressource de coffre de clés dédiée et un compte de stockage client doivent être alloués spécifiquement pour une utilisation avec le module complémentaire de facturation électronique.

Pour plus d’informations, voir [Créer un compte de stockage Azure et un coffre de clés](e-invoicing-create-azure-storage-account-key-vault.md).

#### <a name="users"></a>Utilisateurs

Chaque environnement de service doit répertorier les utilisateurs qui peuvent se connecter à partir de Dynamics 365 Finance et Dynamics 365 Supply Chain Management dans le module complémentaire Facturation électronique.

#### <a name="publication"></a>Publication

Les environnements de service doivent être publiés dans le module complémentaire de facturation électronique avant de pouvoir être utilisés. Seuls les environnements publiés sont accessibles par Finance et Supply Chain Management. De plus, un environnement de service doit être publié avant que toute mise à jour de ses attributs ne prenne effet sur le service de facturation électronique.

### <a name="connected-applications"></a>Applications connectées

Les applications connectées sont les instances de Finance et Supply Chain Management que vous souhaitez peut-être atteindre via RCS. Outre l'URL de l'application et son client, une application connectée contient les informations d'identification qui permettent à RCS de se connecter à l'environnement.

Grâce aux applications connectées, vous pouvez configurer une partie de la fonction de facturation électronique dans Finance et Supply Chain Management pour faire fonctionner l'ensemble de la fonction de facturation électronique.

## <a name="finance-and-supply-chain-management"></a>Finance et Supply Chain Management

### <a name="integration-with-electronic-invoicing-add-on"></a>Intégration avec le module complémentaire de facturation électronique

Avant de pouvoir utiliser Finance et Supply Chain Management pour émettre des factures électroniques via le module complémentaire de facturation électronique, le module complémentaire doit être configuré pour permettre la communication avec le service.

#### <a name="electronic-invoicing-add-on-integration-feature"></a>Fonctionnalité d'intégration du module complémentaire de facturation électronique

Pour activer la communication entre Finance et Supply Chain Management et le module complémentaire de facturation électronique, vous devez activer la fonctionnalité **Intégration du module complémentaire de facturation électronique** dans l'espace de travail **Gestion des fonctionnalités**.

#### <a name="service-endpoint"></a>Point de terminaison de service

Le point de terminaison du service est l'URL où se trouve le module complémentaire de facturation électronique. Pour pouvoir émettre des factures électroniques, le point de terminaison de service doit être configuré dans Finance et Supply Chain Management pour permettre la communication avec le service.

Pour configurer le point de terminaison du service, accédez à **Administration d'organisation \> Paramétrage \> Paramètres des documents électroniques**, puis, sur l'onglet **Services de soumission**, dans le champ **URL du module complémentaire de facturation électronique**, entrez l'URL comme décrit dans le tableau de la section **Point de terminaison du service**.

#### <a name="environments"></a>Environnements

Le nom de l'environnement entré dans Finance et Supply Chain Management fait référence au nom de l'environnement créé dans RCS et publié dans le module complémentaire de facturation électronique.

L'environnement doit être configuré sur l'onglet **Services de soumission** de la page **Paramètres des documents électroniques**, de sorte que chaque demande d'émission de factures électroniques contienne l'environnement dans lequel le module complémentaire de facturation électronique peut déterminer quelle fonction de facturation électronique doit traiter la demande.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Configurer des factures électroniques dans RCS](e-invoicing-configuration-rcs.md)
- [Émettre des factures électroniques dans Finance et Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)
