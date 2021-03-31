---
title: Présentation du module complémentaire de facturation électronique
description: Cette rubrique donne des informations sur le module complémentaire de facturation électronique dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 01/22/2021
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
ms.openlocfilehash: 381f5ecdb3d6fc909a8350ba28af9fd21152da7a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228787"
---
# <a name="electronic-invoicing-add-on-overview"></a>Présentation du module complémentaire de facturation électronique

[!include [banner](../includes/banner.md)]

Le module complémentaire de facturation électronique pour Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management est un service multiclient ultra-évolutif qui permet le traitement configurable des documents de facture électronique et l’échange configurable de documents. Les règles de traitement et d’intégration sont entièrement configurables et la logique est exécutée en dehors de Finance et Supply Chain Management. Le service est principalement destiné au traitement de factures électroniques dans les scénarios entre entreprises et gouvernements, mais il peut être configuré sur mesure à d’autres fins.

Le module complémentaire de facturation électronique peut vous aider à atteindre les objectifs suivants :

- Adoption rapide et facile des exigences spécifiques au pays/à la région
- Implémentations standardisées d’une solution complémentaire de facturation électronique
- Traçabilité améliorée de l’historique des documents
- Cycle d’implémentation plus court
- Réduction du coût total de possession (TCO)
- Configurations facilement ajustables qui ne nécessitent pas de modifications du code
- Package de configuration simplifié
- Exportation, importation et intégration intégrées et extensibilité facile dans le traitement des documents de facture électronique
- Réutilisation facile des mêmes configurations d’exportation, d’importation et d’intégration dans différentes sociétés

Pour utiliser le module complémentaire de facturation électronique, vous devez l’installer à partir de votre projet dans Microsoft Dynamics Lifecycle Services (LCS). Ensuite, suivez la procédure de configuration pour activer l’intégration avec Finance ou Supply Chain Management. Pour plus d’informations, voir [Démarrage du module complémentaire de facturation électronique](e-invoicing-get-started.md).

## <a name="service-availability"></a><a name="availability"></a>Disponibilité du service

Actuellement, le module complémentaire de facturation électronique est disponible pour les clients via le programme en version préliminaire, et dans la phase suivante, le service sera disponible partout. Étant donné que les fonctionnalités qui répondent aux exigences spécifiques au pays/à la région peuvent être limitées à différentes phases de la version, vous devez toujours consulter la documentation la plus récente qui met en évidence la couverture et l’étendue des solutions spécifiques au pays/à la région prises en charge.

Le module complémentaire de facturation électronique est déployé dans les zones géographiques Azure suivantes :

- Etats-Unis
- Europe

> [!NOTE]
> Le module complémentaire de facturation électronique ne prend pas en charge les déploiements sur site.

## <a name="extended-configurability"></a>Configurabilité étendue

Le module complémentaire de facturation électronique peut être utilisé dans des scénarios où vous devez créer et envoyer un document électronique aux parties désignées. Il est spécialement conçu pour exécuter un flux configurable d’actions de traitement, en fonction des données reçues. Les options de configurabilité disponibles dans Finance et Supply Chain Management sont limitées à la transformation de documents. Le service étend ces options en ajoutant les intégrations configurables qui y sont disponibles. En outre, toutes les fonctionnalités de facture électronique qui étaient précédemment disponibles, telles que la Nota fiscal eletrônica (NF-e) brésilienne, le Comprobante Fiscal Digital por Internet (CFDI) mexicain, ou d’autres fonctionnalités (Universal Business Language (UBL) ouest-européen/Public Procurement OnLine (PEPPOL) paneuropéen) utiliseront des configurations pour l’exportation et l’importation, et pour permettre les intégrations avec des services web externes.

## <a name="feature-highlights"></a>Principales fonctionnalités

- Intégration prédéfinie avec Finance et Supply Chain management
- Expérience utilisateur cohérente pour la configuration et la surveillance du processus de facture électronique pour tous les pays ou toutes les régions
- Adoption plus rapide, plus facile et moins coûteuse des solutions complémentaires de facturation électronique dans les nouveaux pays ou les nouvelles régions
- Configuration du service via Regulatory Configuration Service (RCS) et le paramétrage de la fonctionnalité de globalisation
- Transformation des données métier dans plusieurs formats de facture électronique (XML, JavaScript Object Notation \[JSON\], TXT et valeurs séparées par des virgules \[CSV\]) en utilisant les configurations définies dans RCS :

    - Formats d’état électronique disponibles pour les pays ou les régions où la configurabilité de la transformation de facture électronique n’est pas disponible

- Envoi configurable de factures électroniques à des services web externes, y compris la gestion de la certification via des signatures numériques :

    - Intégration intégrée, facilement extensible et configurable avec du contenu supplémentaire pour plusieurs pays

    > [!NOTE]
    > Actuellement, un nombre limité d’envois directs est pris en charge. Pour plus d’informations, voir la section [Disponibilité du service](#availability) plus haut dans cette rubrique. La prise en charge sera étendue à l’avenir.

- Gestion des réponses des services web, y compris la gestion configurable des messages d’exception
- Prise en charge des signatures électroniques (par exemple, en utilisant l’algorithme de signature XMLDSig)
- Traitement par lots des messages de facture électronique

## <a name="architecture-and-data-flow"></a>Architecture et flux de données

Lorsque le module complémentaire de facturation électronique est installé à partir de LCS et que le paramétrage requis est terminé dans toutes les applications requises, une connexion sécurisée est établie. Le service est actuellement situé dans des centres de données aux États-Unis et en Europe. Par conséquent, l’emplacement du service peut différer de l’emplacement de l’instance Finance ou Supply Chain Management associée. Après avoir terminé le paramétrage du module complémentaire de facturation électronique et activé l’intégration, chaque fois qu’une facture électronique est envoyée, les données principales et les données transactionnelles associées à un document spécifique sont envoyées au module complémentaire de facturation électronique.

> [!NOTE]
> Si votre facture électronique ou tout autre document contient des données personnelles, vérifiez que votre utilisation de cette fonctionnalité est conforme au Règlement général sur la protection des données (RGPD) et autres réglementations liées au transfert de données personnelles.

### <a name="high-level-description-of-the-data-flow"></a>Description générale du flux de données

1. Le client envoie un document commercial canonique au service.
2. En fonction des informations de contexte reçues du client, le service sélectionne le flux de traitement applicable.
3. Le service exécute les actions de traitement. Ces actions peuvent inclure la transformation du document commercial en facture électronique, l’application d’une signature électronique et l’envoi du document à un service web externe.
4. Tous les documents reçus et traités sont stockés dans le stockage Blob Azure du client.
5. Tous les secrets et certificats client qui ont été utilisés pour le traitement sont stockés dans le coffre de clés Azure du client.
6. Le service fournit au client des informations à la demande concernant le statut de traitement du document commercial envoyé.
7. Le client reçoit des informations sur l’exécution du traitement et rend toutes les informations du journal disponibles. Il rend également disponible le document créé ou reçu lors du traitement du flux.

L’illustration suivante montre comment les données sont envoyées vers et depuis le module complémentaire de facturation électronique.

![Flux de données pour le module complémentaire de facturation électronique](media/e-invoicing-service-data-flow-diagram-overview.png)

## <a name="privacy-notice"></a>Avis de confidentialité
L’activation et l’utilisation du module complémentaire de facturation électronique peuvent nécessiter l’envoi de données limitées, notamment l’ID d’enregistrement fiscal de l’organisation. Ces données seront transmises à des organismes tiers autorisés par les administrations fiscales aux fins d’envoi de factures électroniques dans les formats prédéfinis requis pour l’intégration avec les services web de ces gouvernements. Les données importées depuis ces systèmes externes vers ce service en ligne Dynamics 365 sont soumises à notre [déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=512132). Pour plus d’informations, consultez les sections Déclaration de confidentialité dans la documentation de la fonctionnalité spécifique au pays.

## <a name="additional-resources"></a>Ressources supplémentaires
- [Administration du service](e-invoicing-service-administration.md)
- [Configurer des factures électroniques dans RCS](e-invoicing-configuration-rcs.md)
- [Émettre des factures électroniques dans Finance et Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]