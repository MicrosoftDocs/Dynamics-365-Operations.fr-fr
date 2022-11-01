---
title: Vue d’ensemble de la Facturation électronique
description: Cet article donne un aperçu de la Facturation électronique dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 01/21/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: d219863d793c837e2346d66d6b95d38191933bcc
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709179"
---
# <a name="electronic-invoicing-overview"></a>Vue d’ensemble de la Facturation électronique

[!include [banner](../includes/banner.md)]

La Facturation électronique pour Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management est un service multilocataire ultra-évolutif qui permet le traitement configurable des documents de facture électronique et l’échange configurable de documents. Les règles de traitement et d’intégration sont entièrement configurables et la logique est exécutée en dehors de Finance et Supply Chain Management. Le service est principalement destiné au traitement des documents de facturation électronique dans des scénarios d’entreprise à gouvernement. Cependant, il peut être configuré de manière personnalisée à d’autres fins, telles que des scénarios interentreprises pour différents types de documents.

La Facturation électronique peut vous aider à atteindre les objectifs suivants :

- Adoption rapide et facile des exigences spécifiques au pays/à la région
- Implémentations standardisées d’une solution de Facturation électronique
- Traçabilité améliorée de l’historique des documents
- Cycle d’implémentation plus court
- Réduction du coût total de possession (TCO)
- Configurations facilement ajustables qui ne nécessitent pas de modifications du code
- Package de configuration simplifié
- Exportation, importation et intégration intégrées et extensibilité facile dans le traitement des documents de facture électronique
- Réutilisation facile des mêmes configurations d’exportation, d’importation et d’intégration dans différentes sociétés

## <a name="service-availability"></a>Disponibilité du service

Actuellement, la fonctionnalité de facturation électronique est disponible pour les clients Finance et Supply Chain Management. Pour plus d’informations, consultez les conditions générales de la licence de votre application.

Étant donné que les fonctionnalités qui répondent aux exigences spécifiques au pays/à la région peuvent être limitées à différentes phases de la version, vous devez toujours consulter la documentation la plus récente qui met en évidence la couverture et l’étendue des solutions spécifiques au pays/à la région prises en charge.

La Facturation électronique est déployée dans les zones géographiques Azure suivantes :

- Etats-Unis
- Europe
- Royaume-Uni
- Asie
- Japon
- Suisse
- Brésil
- Émirats arabes unis
- Australie
- Canada
- France
- Inde
- Norvège
- Afrique du Sud

> [!NOTE]
> La Facturation électronique ne prend pas en charge les déploiements sur site.

## <a name="feature-highlights"></a>Principales fonctionnalités

- Intégration prédéfinie avec Finance et Supply Chain Management
- Une expérience utilisateur cohérente pour la configuration et la surveillance du processus de facture électronique pour tous les pays ou toutes les régions
- Adoption plus rapide, plus facile et moins coûteuse des solutions de Facturation électronique dans les nouveaux pays ou les nouvelles régions
- Configuration du service via la configuration de Regulatory Configuration Service (RCS) et les fonctionnalités de globalisation
- Transformation des données métier dans plusieurs formats de facture électronique (XML, JavaScript Object Notation \[JSON\], TXT et valeurs séparées par des virgules \[CSV\]) en utilisant les configurations définies dans RCS :

    - Formats de gestion des états électroniques disponibles pour les pays ou les régions où la configurabilité de la transformation de facture électronique n’est pas disponible

- Envoi configurable de factures électroniques à des services web externes, y compris la gestion de la certification via des signatures numériques :

    - Intégration intégrée, facilement extensible et configurable avec du contenu supplémentaire pour plusieurs pays et régions

- Gestion des réponses des services web, y compris la gestion configurable des messages d’exception
- Prise en charge des signatures électroniques (par exemple, les signatures électroniques qui utilisent l’algorithme de signature XMLDSig)
- La possibilité d’envoyer des documents à des e-mails et de les stocker dans SharePoint
- Traitement par lots des messages de facture électronique
- Transformation configurable des documents entrants et traitement de ces documents dans Finance et Supply Chain Management
- La possibilité de recevoir des documents entrants à partir de canaux tels que le courrier électronique et SharePoint

## <a name="privacy-notice"></a>Avis de confidentialité

Activer et utiliser la fonctionnalité Facture électronique peut nécessiter l’envoi de données limitées. Ces données incluent le numéro d’identification fiscale de l’organisation. Ces données seront transmises à des organismes tiers autorisés par les administrations fiscales aux fins d’envoi de factures électroniques dans les formats prédéfinis requis pour l’intégration avec les services web de ces gouvernements. Les données qui sont importées depuis ces systèmes externes vers ce service en ligne Dynamics 365 sont soumises à notre [déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=512132). Pour plus d’informations, consultez la section "Déclaration de confidentialité" dans la documentation de la fonctionnalité spécifique au pays/région.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
