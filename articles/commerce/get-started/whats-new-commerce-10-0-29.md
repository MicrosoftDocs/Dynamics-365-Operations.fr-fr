---
title: Version préliminaire de Dynamics 365 Commerce 10.0.29 (octobre 2022)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Commerce 10.0.29.
author: josaw1
ms.date: 08/17/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 1e05f53f9ecb0a1994828172f6999a0bd5c208bc
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306230"
---
# <a name="preview-of-dynamics-365-commerce-10029-october-2022"></a>Version préliminaire de Dynamics 365 Commerce 10.0.29 (octobre 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cet article répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans la version préliminaire 10.0.29 de Microsoft Dynamics 365 Commerce. Cette version a un numéro de build de 10.0.1326 et est disponible selon le programme suivant :

- **Version préliminaire :** Août 2022
- **Disponibilité générale de la version (mise à jour manuelle) :** Septembre 2022
- **Disponibilité générale de la version (mise à jour automatique) :** Octobre 2022

## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités incluses dans cette version. Il se peut que nous mettions à jour de cet article pour inclure des fonctionnalités intégrées à la version après la publication d’origine de cet article.

| Fonctionnalités | Fonction | Plus d’informations | Activé par |
|---------|------------------|----------------|--------------| 
| B2B | [Activez le suppport pour le contrat de vente sur les tous les canaux](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-b2b-sales-agreement-contract-based-pricing) | Cette fonctionnalité permet aux organisations de vendeurs interentreprises (B2B) d’utiliser des accords de vente au Commerce headquarters pour définir une tarification contractuelle pour leurs acheteurs. Lorsqu’un acheteur B2B achète sur le site Web de commerce électronique, la tarification basée sur le contrat configurée pour l’organisation de l’acheteur B2B est automatiquement appliquée à l’ensemble de l’expérience de découverte, d’achat et de paiement du produit. | Gestion des fonctions<p>*Prise en charge du contrat de vente sur les canaux commerciaux* |
| Customer Service | [Activer le service client avec Dynamics 365 Omnichannel for Customer Service](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/chat-dynamics-365-commerce-omnichannel-customer-service) | Une expérience de support client de première classe est essentielle pour offrir une expérience de commerce personnalisée et agréable aux consommateurs. Il existe actuellement plusieurs points de contact commerciaux, tels que des magasins physiques, des canaux en ligne et des canaux sociaux. Les consommateurs s’attendent à une expérience de support personnalisée dans tous ces points de contact. Cette fonctionnalité vous aide à augmenter les conversions de panier en ventes, à accroître l’engagement personnalisé avec les consommateurs et à améliorer le service client en s’intégrant à Dynamics 365 Omnichannel for Customer Service. | Activé par les administrateurs/décideurs |
| Commerce électronique | Support pour la comparaison de produits dans e-commerce | Permettez aux acheteurs de comparer les produits dans un large éventail de catégories afin qu’ils puissent prendre la bonne décision d’achat pour eux-mêmes. Cette fonctionnalité est disponible pour les sites entreprises-consommateurs (B2C) et B2B. | Générateur de site | 
| Cartes cadeaux | Support pour les tableaux de cartes-cadeaux de vente au détail pour le partage de données interentreprises | Le siège social de Dynamics prend en charge la possibilité d’activer le partage de données entre sociétés pour des tables spécifiques dans l’architecture Dynamics. Dans cette caractéristique, Dynamics 365 Commerce ajoute le support pour le partage de données interentreprises pour les tableaux de cartes-cadeaux de vente au détail. Par conséquent, une carte-cadeau dans une entreprise peut désormais voir ses données dupliquées dans une autre entreprise de l’environnement. Les modifications apportées au tableau des cartes-cadeaux de l’entreprise d’origine seront partagées avec le tableau des cartes-cadeaux de l’entreprise dupliquée. | Développeurs |
| Globalisation | [Activer les fonctionnalités de localisation de Commerce pour le nouveau SDK Commerce](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-commerce-localization-features-new-commerce-sdk) | La nouvelle fonctionnalité offre la possibilité d’activer les fonctionnalités de localisation de Commerce à partir de Commerce headquarters en utilisant le cadre ou les paramètres de gestion des fonctionnalités. Les exemples d’intégration fiscale sont désormais inclus dans le nouveau SDK de Commerce et prennent en charge les packages indépendants. Cette fonctionnalité permet également l’adoption de l’application Store Commerce par les clients de Commerce au plan mondial.<p><p>Cette version inclut des fonctionnalités de localisation de Commerce et des exemples d’intégration fiscale pour [l’Autriche](../localizations/emea-aut-fi-sample.md),[ la République tchèque](../localizations/emea-cze-fi-sample.md),[ la France](../localizations/emea-fra-cash-registers.md),[ l'Allemagne](../localizations/emea-deu-fi-sample.md),[ l'Italie](../localizations/emea-ita-fpi-sample.md),[ la Norvège](../localizations/emea-nor-cash-registers.md), et [la Pologne ](../localizations/emea-pol-fpi-sample.md). | Activé par les administrateurs/décideurs |
| Performances | Supprimer la dépendance RTS pour les scénarios « modifier le client » | La haute disponibilité et les hautes performances sont les attentes par défaut pour les points de vente (PDV) et les canaux e-commerce. Pour répondre à ces attentes, les canaux Dynamics 365 Commerce n’ont plus besoin de compter sur une communication en temps réel avec Commerce headquarters lorsque les informations client sont modifiées. La possibilité de modifier les informations client de manière asynchrone pour les clients asynchrones et non asynchrones peut aider à réduire les appels en temps réel au Commerce headquarters. | Activé par les administrateurs/décideurs |

## <a name="feature-state-changes-in-this-release"></a>Modifications de l’état de la fonctionnalité dans cette version

Le tableau suivant répertorie les fonctionnalités qui sont devenues obligatoires ou activées par défaut dans la version 10.0.29. Toutes ces fonctionnalités seront automatiquement activées pour votre système dès que vous effectuez la mise à jour vers la version 10.0.29. Les fonctionnalités obligatoires ne peuvent pas être désactivées, mais les fonctionnalités activées par défaut peuvent toujours être désactivées en utilisant [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Le tableau répertorie également les fonctionnalités qui étaient auparavant en version préliminaire publique, mais qui ont été modifiées pour devenir généralement disponibles dans la version 10.0.29. Cette modification indique que les fonctionnalités sont désormais recommandées pour utilisation dans des environnements de production. Ces fonctionnalités sont désactivées par défaut, sauf indication contraire. Vous devez donc utiliser [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour les activer si vous souhaiter les utiliser.

| Fonction | Titre | Statut de la nouvelle fonctionnalité |
| --- | --- | --- |
| BrazilRetailLocalizationFeature_BR |(Brésil) Fonctionnalité de Commerce spécifique au Brésil | Activé par défaut |
| RetailAdvancedGTETaxAdjustmentFeature | (Inde) Appliquer la GST calculée pour les transactions de vente au détail dans Retail POS aux relevés de vente au détail | Activé par défaut |
| RetailChronologicalInvoicePostingFeature_IT | (Italie) Activer les factures de vente au détail validées sans ordre chronologique | Activé par défaut |
| RetailDiscountWithoutTaxAdjustingFeature_MX | (Mexique) Ajustement de la remise dans la fonctionnalité globale CFDI Retail | Activé par défaut |
| RetailFiscalIntegrationConfigurationEnhancementFeature | Remplacements du profil technique d’intégration fiscal | Activé par défaut |
| RetailFiscalIntegrationConnectorLocationFeature | Intégration fiscale directe à partir des caisses enregistreuses de PDV | Activé par défaut |
| RetailFiscalIntegrationLocalStorageBackupEnableFeature | Sauvegarde du stockage local de l’intégration fiscale | Activé par défaut |
| RetailFiscalIntegrationPostponeFiscalRegistrationFeature | Enregistrement différé de documents | Activé par défaut |
| RetailFiscalIntegrationRegistrationProcessTerminalExceptionFeature | État d’enregistrement fiscal des caisses enregistreuses des PDV | Activé par défaut |
| RetailGSTInvoiceAddressTaxCalculationFeature_IN | (Inde) Calculer la GST en fonction de l’adresse de facturation pour les commandes de commerce électronique | Activé par défaut |
| RetailInvoicesDefaultSalesDocumentStatusFeature_PL | (Pologne) Statut du document de vente par défaut pour les factures de vente au détail | Activé par défaut |
| RetailRecalculateRoundingOfTaxBaseAmountsFeature_MX | (Mexique) Recalcul de l'arrondi pour les montants de base de la taxe dans la fonctionnalité globale CFDI Retail. | Activé par défaut |
| RetailSupplementaryInvoiceFeature | Activer les factures supplémentaires pour les transactions au comptant sans livraison effectuées dans les magasins de vente au détail | Activé par défaut |
| RetailInventoryBufferAndInventoryLevelEnableFeature   |  Activer les tampons de stock et les niveaux de stock    |  Activé par défaut|
|RetailInboundOutboundInventoryValidationFeature|   Activer la validation dans l'opération de stock entrant et sortant de PDV   |   Activé par défaut   |
|  RetailInventoryChannelCalculationConsolidationFeature    |  Logique améliorée de calcul du stock côté canal d’e-commerce |   Activé par défaut   |
|RetailInventoryAdjustmentsInPointOfSaleFeature|    Ajustements de stock dans le point de vente   |  Activé par défaut  |
| RetailMultiplePickupDeliveryModeFeature |  Support pour plusieurs modes de retrait de livraison     |   Obligatoire    |
|  RetailProductAvailabilityOptimizationFeature |   Calcul optimisé de la disponibilité des produits  |  Obligatoire |
|   RetailPricingDataManagerV2Feature   |   Améliorer les performances du moteur de tarification du Commerce |   Obligatoire |
|  RetailPricingPreventUnintendedRecalculationFeature   | Empêcher le calcul involontaire des prix pour les commandes de commerce    |  Obligatoire  |
| RetailTeamsIntegration    |   Activer l’intégration de Microsoft Teams| Obligatoire   |  
| ConsumerEFDSyncProcessFeature_BR | (Brésil) Traitement synchrone NFC-e | Activé par défaut |
| RetailFiscalIntegrationInternalAndExternalServicesEnableFeature | Prise en charge des connecteurs internes et externes dans l'environnement d'intégration fiscale | Obligatoire |
| RetailTaxRegistrationIdEnableFeature_BR | (Brésil) Rechercher des clients dans Retail POS par numéros d'identification fiscale | Obligatoire |
| RetailTaxRegistrationIdEnableFeature_IN | (Inde) Rechercher des clients dans Retail POS par numéros d'identification fiscale | Obligatoire |
| RetailTaxRegistrationIdEnableFeature_IT | (Italie) Gestion des informations client dans Retail POS | Obligatoire |
| RetailTaxRegistrationIdEnableFeature_PL | (Pologne) Gestion des informations client dans Retail POS | Obligatoire |
| RetailUpdateReturnOriginalTransactionIdGlobalEnableFeature_IN | (Taxe sur les biens et services (GST) de vente au détail pour l'Inde) Mettre à jour les avoirs avec les références aux factures d'origine | Obligatoire |
| RetailUserDefinedCertificateProfileFeature | Profils de certificat définis par l’utilisateur pour les magasins de vente au détail | Obligatoire |
  

## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations

Microsoft Dynamics 365 Commerce 10.0.29 inclut les mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.29 (octobre 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-29.md). 

### <a name="bug-fixes"></a>Correctifs de bogue

Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de la version 10.0.29, connectez-vous à Lifecycle Services (LCS) et consultez l’ [Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=726559&dbType=3&qc=ec3e3846199f5d3a27a0c4949e3902ffdbc87560f0cf928c4838b3bdd421633c). 

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 et les clouds du secteur : plan de la vague 2 de lancement 2022

Vous souhaitez connaître les fonctionnalités à venir et récemment publiées dans nos applications ou notre plateforme d’entreprise ?

Consultez [Dynamics 365 et les clouds du secteur : plan de la 2e vague de lancement 2022](/dynamics365-release-plan/2022wave2/). Nous avons capturé tous les détails, de bout en bout, de haut en bas, dans un document unique que vous pouvez utiliser pour la planification.

### <a name="removed-and-deprecated-features"></a>Fonctions supprimées et déconseillées

Les [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Commerce](removed-deprecated-features-commerce.md) l’article décrivent les fonctionnalités qui ont été supprimées ou obsolètes pour Commerce.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Avant que toute fonctionnalité ne soit supprimée du produit, l’avis d’obsolescence sera annoncé dans l'article [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 mois avant le retrait.

Pour les dernières modifications qui n’affectent que le temps de compilation, mais qui sont compatibles d’un point de vue binaire avec les environnements sandbox et de production, le temps d’obsolescence sera inférieur à 12 mois. Ce sont généralement des mises à jour fonctionnelles qui doivent être apportées au compilateur.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
