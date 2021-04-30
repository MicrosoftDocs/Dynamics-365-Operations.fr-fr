---
title: FAQ sur la Facturation électronique
description: Cette rubrique fournit des informations sur les questions fréquemment posées concernant la Facturation électronique.
author: gionoder
ms.date: 03/17/2021
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
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 1ba1a6c5542c10306d4b7494d33e7ff04504fa95
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893776"
---
# <a name="electronic-invoicing-faq"></a>FAQ sur la Facturation électronique

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des réponses aux questions fréquemment posées sur la Facturation électronique. La Facturation électronique étend les capacités de facturation électronique qui existent dans Dynamics 365 Finance, Dynamics 365 Supply Chain Management et Dynamics 365 Project Operations. 

## <a name="what-is-important-about-electronic-invoicing-and-why-should-it-matter-to-my-organization"></a>Qu’est-ce qui est important dans la facturation électronique et pourquoi est-ce important pour mon organisation ?

La complexité opérationnelle et les risques continuent de s’intensifier à mesure que les organisations se développent à l’échelle mondiale et étendent leur implantation dans différentes régions. Le maintien de la conformité et l’adaptation à des réglementations en constante évolution constituent un défi croissant et revêtent une importance particulière en matière de facturation. La facturation a toujours été coûteuse et sujette aux erreurs, car les entreprises s’appuient sur des documents papier et des processus manuels laborieux.  

Les organisations ont commencé à abandonner les factures papier pour réduire les coûts et accélérer le processus de bout en bout. Les administrations se tournent de plus en plus vers la facturation électronique en tant qu’élément clé de la numérisation fiscale. En exigeant des organisations qu’elles soumettent numériquement des informations fiscales en temps réel aux autorités fiscales, les administrations peuvent minimiser l’évasion et la manipulation fiscales et réduire la fraude. 

Le monde passe au traitement des documents sans papier et sans la mise en œuvre de la facturation électronique, les clients s’exposent à des risques de conformité, à des coûts inutiles et à se faire distancer par leurs concurrents. 

## <a name="doesnt-finance-supply-chain-management-and-project-operations-already-include-electronic-invoicing-functionality-what-value-does-this-provide-to-me-as-a-customer"></a>Finance, Supply Chain Management et Project Operations n’incluent-ils pas déjà la fonctionnalité de facturation électronique ? Quelle valeur cela m’apporte-t-il en tant que client ? 

La Facturation électronique étend les capacités de facturation électronique qui existent dans Finance, Supply Chain Management et Project Operations. La fonctionnalité simplifie également le respect des dernières normes de facturation électronique et offre des expériences cohérentes pour différentes géographies dans les domaines du traitement et de l’échange des factures électroniques. Les fonctionnalités de Facturation électronique offrent large un éventail d’avantages, notamment : 

   - Une adoption rapide et facile des exigences spécifiques au pays/à la région.
   - La standardisation des mises en œuvre de la solution de facturation électronique. 
   - Une traçabilité améliorée du traitement des factures électroniques.  
   - Une maintenance plus facile pour respecter l’évolution des exigences légales et des pratiques commerciales locales. 
   - Un conditionnement de la solution plus simple.
   - Des possibilités d’évolutivité pour un grand volume de documents soumis, qui se traduisent par un délai d’exécution plus rapide.
   - La possibilité de partager vos solutions avec d’autres entreprises.

## <a name="does-electronic-invoicing-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>La Facturation électronique prend-elle en charge les installations sur site de Finance, Supply Chain Management et Project Operations ? 

La plateforme actuelle n’autorise pas l’utilisation de la version sur site et il n’est pas prévu de la prendre en charge à l’avenir.

## <a name="does-electronic-invoicing-interface-with-the-vendor-import-automation-feature"></a>La Facturation électronique s’interface-t-elle avec la fonction d’automatisation d’importation des fournisseurs ?

Non. Il existe des projets pour cette interface, mais aucune échéance n’est prévue. Lorsque des échéances seront prévues, les dates seront annoncées dans les [Programmes de lancement](/dynamics365/release-plans/).

## <a name="how-does-electronic-invoicing-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>Comment la Facturation électronique gère-t-elle les pièces jointes dans la facture électronique ? Un serveur SharePoint est-il nécessaire lors de l’incorporation de fichiers PDF dans le fichier XML ?

Les fichiers joints à la facture électronique sont traités comme des données binaires intégrées dans un élément XML. Un serveur SharePoint n’est pas nécessaire pour intégrer des fichiers PDF, mais la pièce jointe doit être stockée dans le système de gestion des documents de Finance, Supply Chain Management et Project Operations.

## <a name="is-electronic-invoicing-available-according-to-the-regulations-of-my-countryregion"></a>La Facturation électronique est-elle disponible conformément aux réglementations de mon pays ou ma région ?

La Facturation électronique est une plateforme de microservice qui sera disponible dans le monde entier.

Microsoft prévoit de publier les formats et intégrations de factures électroniques pour les pays bénéficiant de la localisation fonctionnelle par Microsoft. Pour plus d’informations, consultez [Disponibilité des fonctionnalités de facturation électronique](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

Si le format de facturation électronique de votre pays ou de votre région n’est pas répertorié, la plateforme vise à prendre en charge ce scénario à l’avenir. Vous pouvez toujours bénéficier des fonctionnalités de configuration de la Facturation électronique et configurer vous-même le format de facturation électronique, ou vous pouvez travailler avec un partenaire/éditeur de logiciels indépendants pour les configurer pour votre organisation.

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>Dynamics 365 for Regulatory Services est-il un nouveau module, comme Human Resources ou Project Operations, lié à Finance ou à Supply Chain Management ? Entraîne-t-il des coûts supplémentaires ?

Dynamics 365 for Regulatory Services (RCS) est un service cloud permettant de configurer les ressources de globalisation. RCS est gratuit pour tous les détenteurs de licences Finance, Supply Chain Management et Project Operations.

Pour vous inscrire à RCS, accédez à <https://marketing.configure.global.dynamics.com/>.

Pour plus d’informations, voir [Regulatory Configuration Services (RCS) – Fonctionnalités de globalisation](rcs-globalization-feature.md).

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing--or-just-turn-it-on-in-feature-management"></a>Dois-je m’inscrire pour obtenir la Facturation électronique, ou simplement l’activer dans la Gestion des fonctionnalités ?

Si vous disposez d’une licence Finance, Supply Chain Management et Project Operations, reportez-vous à [Mise en route de l’administration du service du module complémentaire de Facturation électronique](e-invoicing-get-started-service-administration.md) pour vous inscrire à la Facturation électronique.

## <a name="does-electronic-invoicing-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>La Facturation électronique fonctionne-t-elle avec les machines virtuelles de niveau 1 ? Quel est l’environnement minimal requis ?

L’intégration de la Facturation électronique nécessite au moins une machine virtuelle de niveau 2 pour héberger Finance ou Supply Chain Management. Pour plus d’informations sur la planification de l’environnement, voir [Planification de l’environnement](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

## <a name="does-electronic-invoicing-have-a-test-mode-for-testing-invoice-submission"></a>La Facturation électronique dispose-t-elle d’un mode de test pour tester la soumission des factures ?

Ceci peut être obtenu par la configuration. Pour tester la soumission des factures, vous pouvez vous connecter à Finance ou Supply Chain Management à partir d’un environnement de test d’acceptation utilisateur (UAT) et soumettre les factures de test. La Facturation électronique prend en charge la configuration de certificats numériques de test et, dans le cas de factures électroniques nécessitant une approbation numérique, la configuration d’une URL à partir de services Web de test publiés par l’administration fiscale.

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>Existe-t-il une documentation sur les fonctionnalités de Facturation électronique prêtes à l’emploi spécifiques à chaque pays ?

Oui. Pour plus d’informations sur la disponibilité des fonctionnalités de Facturation électronique et les formats qu’elles prennent en charge, voir [Disponibilité des fonctionnalités de facturation électronique](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

> [!NOTE] 
> Si vous ne trouvez pas la réponse que vous recherchez, envoyez votre question par e-mail à l’équipe de développement produit à l’adresse <D365EInvoicePreview@microsoft.com>. Nous vous contacterons, ou améliorerons la couverture de cette FAQ.