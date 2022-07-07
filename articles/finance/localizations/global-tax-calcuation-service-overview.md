---
title: Vue d’ensemble du calcul de la taxe
description: Cet article explique la portée et les fonctionnalités générales de la fonctionnalité de calcul des taxes.
author: wangchen
ms.date: 03/02/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 24d4a722ee143dc0869f758475aaf377e7a9e084
ms.sourcegitcommit: 78576abe5c7cbab1bb69d26c999b038e8c24873a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954519"
---
# <a name="tax-calculation-overview"></a>Vue d’ensemble du calcul de la taxe

[!include [banner](../includes/banner.md)]

Le calcul des taxes est un service multi-locataire hyper évolutif qui permet au moteur Global Tax Engine d’automatiser et de simplifier le processus de détermination et de calcul des taxes. Le moteur de taxe est entièrement configurable. Les éléments qui peuvent être configurés incluent, mais sans s’y limiter, le modèle de données taxables, le code taxe, la matrice d’applicabilité de la taxe et la formule de calcul de la taxe. Le moteur de taxe fonctionne sur la plateforme des services essentiels Microsoft Azure, et offre une technologie moderne et une évolutivité exponentielle.

Le calcul des taxes s’intègre à Dynamics 365 Finance et Dynamics 365 Supply Chain Management. À terme, il s’intégrera également avec Dynamics 365 Project Operations, Dynamics 365 Commerce et d’autres applications propriétaires et tierces.

> [!IMPORTANT]
> Quand vous activez le calcul des taxes, certaines opérations sur les données associées peuvent être effectuées dans un centre de données autre que le centre de données qui gère vos données de service. Consultez les [Conditions générales d’utilisation](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) avant d’activer le calcul des taxes. La protection de votre vie privée est importante pour nous. Pour en savoir plus, lisez notre [Déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=521839).

Le calcul des taxes est un moteur fiscal basé sur des microservices qui offre une évolutivité exponentielle et peut vous aider à effectuer les tâches suivantes :

- Déterminez automatiquement le groupe de taxe de vente, le groupe de taxe d’article et les codes de taxe corrects grâce à un mécanisme de détermination amélioré.
- Prenez en charge plusieurs numéros d’immatriculation fiscale dans une entité juridique et déterminez automatiquement le numéro d’immatriculation fiscale correct sur les transactions imposables.
- Prenez en charge la détermination, le calcul, la comptabilisation et le règlement des taxes pour les ordres de transfert.
- Définissez des formules et des conditions de calcul des taxes configurables pour les besoins spécifiques de votre entreprise.
- Partagez la solution de détermination et de calcul des taxes entre les entités juridiques pour réduire les efforts de maintenance et éviter les erreurs.
- Prenez en charge la détermination du numéro d’enregistrement fiscal du client et du fournisseur.
- Prenez en charge la détermination du code liste.
- Prenez en charge les paramètres de calcul des taxes au niveau de la juridiction fiscale.

Pour utiliser le calcul des taxes, installez le module complémentaire de calcul des taxes à partir de votre projet dans Microsoft Dynamics Lifecycle Services. Terminez ensuite la configuration dans [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/) et activez le calcul des taxes dans Finance et Supply Chain Management. Pour plus d’informations, voir [Prise en main du service de taxe](global-get-started-with-tax-calculation-service.md).

## <a name="availability"></a>Disponibilité

Le calcul des taxes est en disponibilité générale dans les environnements de production pour tous les clients à partir de la version 10.0.21.

De nouvelles fonctionnalités continueront d’être livrées. Consultez régulièrement le plan de version le plus à jour pour en savoir plus sur la couverture et l’étendue des fonctionnalités prises en charge.

Le calcul des taxes est déployé dans les zones géographiques Azure suivantes. Davantage de zones géographiques Azure seront ajoutées, en fonction des besoins des clients.

- Asie-Pacifique
- Australie
- Canada
- Europe
- Japon
- Suisse
- Royaume-Uni
- Etats-Unis

> [!NOTE]
> Le calcul des taxes ne prend pas en charge les versions antérieures de Dynamics 365, telles que Dynamics AX 2012, ou les déploiements sur site de Dynamics 365.

## <a name="versions"></a>Versions
Nous vous recommandons d’importer et de paramétrer votre configuration de calcul des taxes avec la version qui correspond à votre version de Finance ou de Supply Chain Management.

| Version de Finance ou de Supply Chain Management | Version de la configuration de la taxe               |
| --------------- | --------------------------------------- |
| 10.0.18         | Configuration de taxe - Europe 30.12.82     |
| 10.0.19         | Configuration du calcul des taxes 36.38.193 |
| 10.0.20         | Configuration du calcul des taxes 40.43.208 |
| 10.0.21         | Configuration du calcul des taxes 40.48.215 |
| 10.0.22         | Configuration du calcul des taxes 40.48.215 |
| 10.0.23         | Configuration du calcul des taxes 40.50.221 |
| 10.0.24         | Configuration du calcul des taxes 40.50.225 |
| 10.0.25         | Configuration du calcul des taxes 40.50.225 |
| 10.0.26         | Configuration du calcul des taxes 40.54.234 |
| 10.0.27         | Configuration du calcul des taxes 40.54.234 |
| 10.0.28         | Configuration du calcul des taxes 40.54.234 |


## <a name="data-flow"></a>Flux de données

Voici un aperçu du processus de flux de données pour le calcul des taxes. 

1. Dans RCS, affichez et importez les configurations de modèle de document fiscal et les configurations de mappage de modèles. Si vous devez étendre les configurations pour un scénario avancé, consultez [Ajouter des champs de données dans les configurations de taxe](tax-service-add-data-fields-tax-configurations.md).
2. Dans RCS, créez ou gérez des fonctionnalités de taxe. Vous pouvez utiliser des fonctionnalités de taxe pour gérer les taux de taxe et les règles d’applicabilité des taxes.
3. Une fois la configuration des fonctionnalités de taxe terminée, publiez les configurations de taxe et les fonctionnalités de taxe de RCS dans le référentiel global.
4. Dans Finance, sélectionnez la version de configuration des fonctionnalités de taxe à utiliser pour une entité juridique spécifique.
5. Dans Finance et Supply Chain Management, effectuez les transactions comme d’habitude. Quand le calcul des taxes est nécessaire, le client collectera les informations de la transaction, telles que la commande client ou la commande fournisseur, et conditionnera les informations en tant que charge utile. Une demande sera alors envoyée pour calculer la taxe.
6. La demande de calcul des taxes est reçue du client et le calcul est effectué. Le résultat de taxe est ensuite retourné au client.
7. Le client Dynamics 365 reçoit le résultat de taxe et présente le résultat du calcul des taxes sur une page de taxe.

## <a name="supported-transactions"></a>Transactions prises en charge

Le calcul des taxes peut être activé par les transactions. 

Les transactions suivantes sont prises en charge dans la version 10.0.21 : 

- Vente

    - Devis de vente
    - Commande de vente
    - Confirmation
    - Prélèvements
    - Bon de livraison
    - Facture client
    - Avoir
    - Ordre de retour
    - Frais divers d’en-tête
    - Frais divers de ligne

- Achats

    - Commande fournisseur
    - Confirmation
    - Préparation de réception
    - Réception des produits
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

- Stock

    - Ordre de transfert – Expédition
    - Ordre de transfert – Réception

Les transactions suivantes sont prises en charge dans la version 10.0.23 : 

- Facture financière

Les transactions suivantes sont prises en charge dans la version 10.0.26 : 

- Journaux des opérations diverses
- Journal des factures fournisseur

Les transactions suivantes sont prises en charge dans la version 10.0.28 : 

- Journal des paiements fournisseur
- Journal des paiements client

## <a name="supported-countriesregions"></a>Pays/régions pris en charge

Le calcul des taxes peut être activé par entité juridique. 

Les pays/régions suivants pour l’adresse principale d’une entité juridique sont pris en charge dans la version 10.0.21 :

- Autriche
- Belgique
- Danemark
- Estonie
- Finlande
- France
- Allemagne
- Hongrie
- Islande
- Irlande
- Italie
- Lettonie
- Lituanie
- Pays-Bas
- Norvège
- Pologne
- Suède
- Suisse
- Royaume-Uni
- Etats-Unis

Les pays/régions suivants pour l’adresse principale d’une entité juridique sont pris en charge dans la version 10.0.22 :

- Australie
- Royaume de Bahreïn
- Canada
- Égypte
- Hong Kong (R.A.S.)
- Koweït
- Nouvelle-Zélande
- Oman
- Qatar
- Arabie saoudite
- Afrique du Sud
- Émirats arabes unis

Les pays/régions suivants pour l’adresse principale d’une entité juridique sont pris en charge dans la version 10.0.23 :

- Thaïlande
- Japon
- Malaisie
- Singapour

Les pays/régions suivants pour l’adresse principale d’une entité juridique sont pris en charge dans la version 10.0.24 :

- Mexique

Les pays/régions suivants pour l’adresse principale d’une entité juridique sont pris en charge dans la version 10.0.26 :

- Chine
- République tchèque
- Espagne

## <a name="related-resources"></a>Ressources associées

[Prise en main du service de taxe](./global-get-started-with-tax-calculation-service.md)

[Plusieurs numéros d’immatriculation de TVA](./emea-multiple-vat-registration-numbers.md)

[Prise en charge de la fonction de taxe pour les ordres de transfert](./tasks/tax-feature-support-for-transfer-order.md)

[Comment créer une extension dans le service de taxe](./tax-service-add-data-fields-tax-integration-by-extension.md)
