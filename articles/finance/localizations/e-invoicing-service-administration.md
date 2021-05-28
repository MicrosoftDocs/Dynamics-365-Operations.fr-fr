---
title: Composants d’administration de la Facturation électronique
description: Cette rubrique fournit des informations sur les composants liés à l’administration de la Facturation électronique.
author: gionoder
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 081d23c85d3555210b54597920a49e800ffe284b
ms.sourcegitcommit: 35fdcc6501e099c54a58583b1e3aba16f02a5ccc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5980921"
---
# <a name="electronic-invoicing-administration-components"></a>Composants d’administration de la Facturation électronique

[!include [banner](../includes/banner.md)]


Cette rubrique fournit des informations sur les composants liés à l’administration de la Facturation électronique. Elle fournit également des informations sur la configuration du service de Facturation électronique.

## <a name="azure"></a>Azure

Utilisez Microsoft Azure pour créer les secrets du compte de stockage et du compte Key Vault. Utilisez ensuite les secrets dans la configuration de la Facturation électronique.

## <a name="lifecycle-services"></a>Lifecycle Services

Utilisez Microsoft Dynamics Lifecycle Services (LCS) pour activer les microservices de votre projet de déploiement LCS.

> [!NOTE]
> L’installation du microservice dans LCS nécessite au moins une machine virtuelle de niveau 2. Pour plus d’informations sur la planification de l’environnement, voir [Planification de l’environnement](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
 

## <a name="regulatory-configuration-services"></a>Regulatory Configuration Services

Dynamics 365 Regulatory Configuration Services (RCS) est l’interface utilisée pour configurer la Facturation électronique. Des ressources telles que des environnements et des fonctionnalités de facturation électronique sont créées, gérées et hébergées dans RCS. Lorsque les ressources sont prêtes, elles sont publiées dans le service de Facturation électronique.

Pour l’inscription au RCS, voir [Regulatory services](https://marketing.configure.global.dynamics.com/).

Pour plus d’informations sur RCS, voir [Regulatory Configuration Services (RCS) – Fonctionnalités de globalisation](rcs-globalization-feature.md).

### <a name="integration-with-electronic-invoicing"></a>Intégration avec la Facturation électronique 

Avant de pouvoir utiliser RCS pour configurer des factures électroniques, vous devez le configurer pour permettre la communication avec la Facturation électronique. Vous devez effectuer cette configuration sur l’onglet **Facturation électronique** de la page **Paramètres de la gestion des états électroniques**.

#### <a name="service-endpoint"></a>Point de terminaison de service

La Facturation électronique est disponible dans plusieurs emplacements géographiques du centre de données Azure. Le tableau suivant répertorie la disponibilité par région.

| Emplacement géographique du centre de données Azure |
|----------------------------|
| Etats-Unis              |
| Europe                     |
| Royaume-Uni             |
| Asie                       |

### <a name="service-environments"></a>Environnements de service

Les environnements de service sont des partitions logiques créées pour prendre en charge l’exécution des fonctionnalités de facturation électronique dans la Facturation électronique. Les secrets de sécurité et les certificats numériques, ainsi que la gouvernance (c’est-à-dire les autorisations d’accès), doivent être configurés au niveau de l’environnement de service.

Les clients peuvent créer autant d’environnements de service qu’ils le souhaitent. Tous les environnements de service créés par un client sont indépendants les uns des autres.

Les environnements de service doivent être créés et gérés dans RCS. Lorsque les environnements de service sont prêts, ils doivent être publiés dans la Facturation électronique.

#### <a name="service-environment-status"></a>Statut de l’environnement de service

Les environnements de service peuvent être gérés via leur statut. Les options possibles sont :

- **Non publié** – L’environnement a été créé, mais il n’a pas encore été publié.
- **Publié** – L’environnement a été publié dans la Facturation électronique.
- **Modifié** – Les attributs d’un environnement publié ont été modifiés, mais les modifications n’ont pas encore été publiées.

#### <a name="customer-secrets"></a>Secrets clients

Le service de Facturation électronique a la responsabilité de stocker toutes vos données métier dans les ressources Azure appartenant à votre société. Pour vous assurer que le service fonctionne correctement et que toutes les données métier requises et générées par la Facturation électronique ne sont accessibles que de manière appropriée, vous devez créer deux ressources Azure principales :

- Un compte de stockage Azure (stockage Blob) qui va stocker les factures électroniques
- Un compte Azure Key Vault qui va stocker les certificats et l’Uniform Resource Identifier (URI) du compte de stockage


Un compte Key Vault dédié et un compte de stockage client doivent être alloués spécifiquement pour utiliser la Facturation électronique. Pour plus d’informations, voir [Créer un compte de stockage Azure et un Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).

Pour surveiller l'intégrité de votre compte Key Vault et recevoir des alertes, configurez Azure Monitor pour Key Vault. En activant la journalisation de Key Vault, vous pouvez surveiller comment, quand et qui accède à vos comptes Key Vault. Pour plus d'informations, consultez [Surveillance et alertes pour Azure Key Vault](/azure/key-vault/general/alert) et [Comment activer la journalisation de Key Vault](/azure/key-vault/general/howto-logging?tabs=azure-cli).

En tant que meilleure pratique, modifiez régulièrement les secrets. Pour plus d’informations, voir la [Documentation sur les secrets](/azure/key-vault/secrets/).

#### <a name="users"></a>Utilisateurs

Chaque environnement de service doit répertorier les utilisateurs qui peuvent se connecter à partir de Dynamics 365 Finance et Dynamics 365 Supply Chain Management à la Facturation électronique.

#### <a name="publication"></a>Publication

Les environnements de service doivent être publiés dans la Facturation électronique avant de pouvoir être utilisés. Seuls les environnements publiés sont accessibles par Finance et Supply Chain Management. De plus, un environnement de service doit être publié avant que toute mise à jour de ses attributs ne prenne effet sur le service de facturation électronique.

### <a name="connected-applications"></a>Applications connectées

Les applications connectées sont les instances de Finance et Supply Chain Management que vous souhaitez peut-être atteindre via RCS. Outre l’URL de l’application et son client, une application connectée contient les informations d’identification qui permettent à RCS de se connecter à l’environnement.

Grâce aux applications connectées, vous pouvez configurer une partie de la fonction de facturation électronique dans Finance et Supply Chain Management pour faire fonctionner l’ensemble de la fonction de facturation électronique.

## <a name="finance-and-supply-chain-management"></a>Finance et Supply Chain Management

### <a name="integration-with-electronic-invoicing"></a>Intégration avec la Facturation électronique

Avant de pouvoir utiliser Finance et Supply Chain Management pour émettre des factures électroniques via la Facturation électronique, ils doivent être configurés pour permettre la communication avec le service.

#### <a name="electronic-invoicing-integration-feature"></a>Fonctionnalité d’intégration de la Facturation électronique

Pour activer la communication entre Finance et Supply Chain Management et la Facturation électronique, vous devez activer la fonctionnalité **Intégration de la Facturation électronique** dans l’espace de travail **Gestion des fonctionnalités**.

#### <a name="service-endpoint"></a>Point de terminaison de service

Le point de terminaison du service est l’URL où se trouve la Facturation électronique. Pour pouvoir émettre des factures électroniques, le point de terminaison de service doit être configuré dans Finance et Supply Chain Management pour permettre la communication avec le service.

Pour configurer le point de terminaison du service, accédez à **Administration d’organisation \> Paramétrage \> Paramètres des documents électroniques**, puis, sur l’onglet **Services de soumission**, dans le champ **URL de la Facturation électronique**, entrez l’URL comme décrit dans le tableau de la section **Point de terminaison du service**.

#### <a name="environments"></a>Environnements

Le nom de l’environnement entré dans Finance et Supply Chain Management fait référence au nom de l’environnement créé dans RCS et publié dans la Facturation électronique.

L’environnement doit être configuré sur l’onglet **Services de soumission** de la page **Paramètres des documents électroniques**, de sorte que chaque demande d’émission de factures électroniques contienne l’environnement dans lequel la Facturation électronique peut déterminer quelle fonction de facturation électronique doit traiter la demande.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Configurer des factures électroniques dans RCS](e-invoicing-configuration-rcs.md)
- [Émettre des factures électroniques dans Finance et Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
