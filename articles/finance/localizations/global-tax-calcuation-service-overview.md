---
title: Calcul de la taxe (version préliminaire)
description: Cette rubrique explique la portée et les fonctionnalités générales de la fonctionnalité de calcul des taxes.
author: wangchen
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9daa6e001200d03a2639974fb6de618d77ddf09d
ms.sourcegitcommit: cb282e8d2306ab71adf80a84346a6863d2d019e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2021
ms.locfileid: "6184099"
---
# <a name="tax-calculation-preview"></a>Calcul de la taxe (version préliminaire)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Le calcul des taxes est un service multi-locataire hyper évolutif qui permet au moteur Global Tax Engine d’automatiser et de simplifier le processus de détermination et de calcul des taxes. Le moteur de taxe est entièrement configurable. Les éléments qui peuvent être configurés incluent, mais sans s’y limiter, le modèle de données taxables, le code taxe, la matrice d’applicabilité de la taxe et la formule de calcul de la taxe. Le moteur de taxe fonctionne sur la plateforme des services essentiels Microsoft Azure, et offre une technologie moderne et une évolutivité exponentielle.

Le calcul des taxes s’intègre à Dynamics 365 Finance et Dynamics 365 Supply Chain Management. À terme, il s’intégrera également avec Dynamics 365 Project Operations, Dynamics 365 Commerce et d’autres applications propriétaires et tierces.

> [!IMPORTANT]
> Lorsque vous activez le service de calcul des taxes, certaines opérations sur les données associées peuvent être effectuées dans un centre de données autre que le centre de données qui gère vos données de service. Consultez les [Conditions générales d’utilisation](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) avant d’activer le service de calcul des taxes. La protection de votre vie privée est importante pour nous. Pour en savoir plus, lisez notre [Déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=521839).

Le calcul des taxes est un moteur de taxe à base de microservices qui offre une évolutivité exponentielle. Il peut vous aider à exécuter les tâches suivantes :

- Configurer le calcul des taxes via Regulatory Configuration Service (RCS). RCS est une version améliorée du concepteur de rapports électroniques (ER) et est disponible en tant que service autonome.
- Configurer la matrice de taxe pour déterminer automatiquement les codes et les taux de taxe.
- Configurer la matrice de taxe pour déterminer automatiquement le numéro d’immatriculation fiscale.
- Configurer le concepteur de calcul de taxe pour définir des formules et des conditions.
- Partager la solution de détermination et de calcul des taxes entre les entités juridiques.

Pour utiliser le service de calcul des taxes, installez le complément de service de calcul des taxes à partir de votre projet dans Microsoft Dynamics Lifecycle Services (LCS). Terminez ensuite la configuration dans RCS et activez le service de calcul des taxes dans Finance and Supply Chain Management. Pour plus d’informations, voir [Prise en main du service de taxe](./global-get-started-with-tax-calculation-service.md).

## <a name="availability"></a>Disponibilité

Le calcul des taxes est disponible uniquement dans les environnements bac à sable et pour certains clients, via un programme de version préliminaire publique. À terme, il deviendra généralement disponible pour tous les clients et dans les environnements de production.

De nouvelles fonctionnalités seront publiées régulièrement. Assurez-vous donc de consulter régulièrement la documentation la plus à jour pour en savoir plus sur la couverture et l’étendue des fonctionnalités prises en charge.

Le calcul des taxes est déployé dans les zones géographiques Azure suivantes. Il sera également déployé dans davantage de zones géographiques Azure, en fonction des besoins des clients :

- Etats-Unis
- Europe

> [!NOTE]
> Le calcul des taxes ne prend pas en charge les déploiements sur site de Dynamics 365. Il ne prend pas non plus en charge les versions antérieures, telles que Dynamics AX 2012.

## <a name="feature-highlights"></a>Principales fonctionnalités

- Une matrice de taxe configurable pour déterminer et calculer automatiquement les taxes
- Prise en charge de plusieurs numéros d’immatriculation de taxe
- Prise en charge des ordres de transfert pour la détermination et le calcul des taxes
- Prise en charge des ordres de transfert pour la détermination de plusieurs numéros d’immatriculation de taxe

## <a name="supported-transactions"></a>Transactions prises en charge

Le calcul des taxes peut être activé par entité juridique et par transaction. Les transactions suivantes sont prises en charge :

- Processus de vente

    - Devis de vente
    - Commandes client
    - Confirmation
    - Prélèvements
    - Bon de livraison
    - Facture client
    - Avoir
    - Ordre de retour
    - Frais divers d’en-tête
    - Frais divers de ligne

- Processus d’achat

    - Commande fournisseur
    - Confirmation
    - Préparation de réception
    - Accusé de réception des produits
    - Facture d’achat
    - Frais divers d’en-tête
    - Frais divers de ligne
    - Avoir
    - Ordre de retour
    - Demande d’achat
    - Frais divers de ligne de demande d’achat
    - Appel d’offre
    - Frais divers d’en-tête d’appel d’offre
    - Frais divers de ligne d’appel d’offre

- Processus d’inventaire

    - Ordre de transfert – Expédition
    - Ordre de transfert – Réception

## <a name="related-resources"></a>Ressources associées

[Prise en main du service de taxe](./global-get-started-with-tax-calculation-service.md)

[Plusieurs numéros d’immatriculation de TVA](./emea-multiple-vat-registration-numbers.md)

[Prise en charge de la fonction de taxe pour les ordres de transfert](./tasks/tax-feature-support-for-transfer-order.md)

[Comment créer une extension dans le service de taxe](./tax-service-add-data-fields-tax-integration-by-extension.md)
