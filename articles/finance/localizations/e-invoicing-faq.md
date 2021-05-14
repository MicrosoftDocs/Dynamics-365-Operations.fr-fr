---
title: FAQ sur la Facturation électronique
description: Cette rubrique fournit des informations sur les questions fréquemment posées concernant la Facturation électronique.
author: gionoder
ms.date: 04/21/2021
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
ms.openlocfilehash: 2efad243044304b895726ab763fd3744282abd16
ms.sourcegitcommit: 9283caad2d0636f98579c995784abec19fda2e3f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935631"
---
# <a name="electronic-invoicing-faq"></a>FAQ sur la facturation électronique

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

## <a name="does-electronic-invoicing-service-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>La Facturation électronique prend-elle en charge les installations sur site de Finance, Supply Chain Management et Project Operations ? 

La plateforme actuelle n’autorise pas l’utilisation de la version sur site et il n’est pas prévu de la prendre en charge à l’avenir.

## <a name="does-electronic-invoicing-service-interface-with-the-vendor-import-automation-feature"></a>La Facturation électronique s’interface-t-elle avec la fonction d’automatisation d’importation des fournisseurs ?

Non. Il existe des projets pour cette interface, mais aucune échéance n’est prévue. Lorsque des échéances seront prévues, les dates seront annoncées dans les [Programmes de lancement](/dynamics365/release-plans/).

## <a name="how-does-electronic-invoicing-service-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>Comment la Facturation électronique gère-t-elle les pièces jointes dans la facture électronique ? Un serveur SharePoint est-il nécessaire lors de l’incorporation de fichiers PDF dans le fichier XML ?

Les fichiers joints à la facture électronique sont traités comme des données binaires intégrées dans un élément XML. Un serveur SharePoint n’est pas nécessaire pour intégrer des fichiers PDF, mais la pièce jointe doit être stockée dans le système de gestion des documents de Finance, Supply Chain Management et Project Operations.

## <a name="is-electronic-invoicing-service-available-according-to-the-regulations-of-my-countryregion"></a>La Facturation électronique est-elle disponible conformément aux réglementations de mon pays ou ma région ?

La Facturation électronique est une plateforme de microservice qui sera disponible dans le monde entier.

Microsoft prévoit de publier les formats et intégrations de factures électroniques pour les pays bénéficiant de la localisation fonctionnelle par Microsoft. Pour plus d’informations, consultez [Disponibilité des fonctionnalités de facturation électronique](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

Si le format de facturation électronique de votre pays ou de votre région n’est pas répertorié, la plateforme vise à prendre en charge ce scénario à l’avenir. Vous pouvez toujours bénéficier des fonctionnalités de configuration de la Facturation électronique et configurer vous-même le format de facturation électronique, ou vous pouvez travailler avec un partenaire/éditeur de logiciels indépendants pour les configurer pour votre organisation.

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>Dynamics 365 for Regulatory Services est-il un nouveau module, comme Human Resources ou Project Operations, lié à Finance ou à Supply Chain Management ? Entraîne-t-il des coûts supplémentaires ?

Dynamics 365 for Regulatory Services (RCS) est un service cloud permettant de configurer les ressources de globalisation. RCS est gratuit pour tous les détenteurs de licences Finance, Supply Chain Management et Project Operations.

Pour vous inscrire à RCS, accédez à <https://marketing.configure.global.dynamics.com/>.

Pour plus d’informations, voir [Regulatory Configuration Services (RCS) – Fonctionnalités de globalisation](rcs-globalization-feature.md).

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing-service-or-just-turn-it-on-in-feature-management"></a>Dois-je m’inscrire pour obtenir la Facturation électronique, ou simplement l’activer dans la Gestion des fonctionnalités ?

Si vous disposez d’une licence Finance, Supply Chain Management et Project Operations, reportez-vous à [Mise en route de l’administration du service du module complémentaire de Facturation électronique](e-invoicing-get-started-service-administration.md) pour vous inscrire à la Facturation électronique.

## <a name="does-electronic-invoicing-service-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>La Facturation électronique fonctionne-t-elle avec les machines virtuelles de niveau 1 ? Quel est l’environnement minimal requis ?

L’intégration de la Facturation électronique nécessite au moins une machine virtuelle de niveau 2 pour héberger Finance ou Supply Chain Management. Pour plus d’informations sur la planification de l’environnement, voir [Planification de l’environnement](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

## <a name="does-electronic-invoicing-service-have-a-test-mode-for-testing-invoice-submission"></a>La Facturation électronique dispose-t-elle d’un mode de test pour tester la soumission des factures ?

Ceci peut être obtenu par la configuration. Pour tester la soumission des factures, vous pouvez vous connecter à Finance ou Supply Chain Management à partir d’un environnement de test d’acceptation utilisateur (UAT) et soumettre les factures de test. La Facturation électronique prend en charge la configuration de certificats numériques de test et, dans le cas de factures électroniques nécessitant une approbation numérique, la configuration d’une URL à partir de services Web de test publiés par l’administration fiscale.

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>Existe-t-il une documentation sur les fonctionnalités de Facturation électronique prêtes à l’emploi spécifiques à chaque pays ?

Oui. Pour plus d’informations sur la disponibilité des fonctionnalités de Facturation électronique et les formats qu’elles prennent en charge, voir [Disponibilité des fonctionnalités de facturation électronique](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

## <a name="does-the-electronic-invoicing-service-allow-a-legal-entity-in-finance-or-supply-chain-management-that-is-configured-for-a-specific-country-to-consume-electronic-invoicing-features-from-different-countryregions"></a>Le service Facturation électronique permet-il à une entité juridique de Finance ou de Supply Chain Management qui est configurée pour un pays spécifique d'utiliser les fonctionnalités de facturation électronique de différents pays/régions ?

Oui. Les fonctionnalités de facturation électronique peuvent être utilisées pour traiter les soumissions de documents commerciaux indépendamment du pays de l'entité juridique, si ce qui suit est vrai :

   - Le document commercial généré utilise le mappage de modèle de document approprié.
   - Il existe une correspondance entre le document commercial et les règles d'applicabilité configurées dans la fonction de facturation électronique.

## <a name="does-the-electronic-invoicing-service-use-the-same-configuration-and-design-experience-provided-by-the-electronic-reporting-module-in-finance-and-supply-chain-management"></a>Le service de facturation électronique offre-t-il la même expérience de configuration et de conception que celle fournie par le module de reporting électronique de Finance et Supply Chain Management ? 

Oui. Les mêmes outils de conception que ceux utilisés dans le module de reporting électronique (ER) de Finance et Supply Chain Management sont utilisés pour créer et configurer le mappage de modèles de données et les configurations de format de fichier. Ces outils de conception sont également utilisés dans Regulatory Configuration Services (RCS) pour créer et configurer le mappage du modèle de données et les configurations de format de fichier qui sont utilisées dans la configuration des fonctionnalités de facturation électronique.

## <a name="can-the-applicability-rules-be-extended-and-configured-so-that-they-arent-tied-to-any-specific-parameter-such-as-a-legal-entity"></a>Les règles d'applicabilité peuvent-elles être étendues et configurées de manière à ne pas être liées à un paramètre spécifique, tel qu'une entité juridique ?

Oui. Les règles d'applicabilité sont entièrement configurables. Vous pouvez ajouter ou supprimer des clauses, créer des opérations logiques et regrouper et dissocier des clauses. Pour plus d’informations, voir [Règles d'applicabilité](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#applicability-rules).

## <a name="does-the-electronic-invoicing-service-support-adding-other-er-format-configurations-to-generate-other-types-of-documents-does-it-support-sending-the-documents-electronically-to-customers-such-as-a-delivery-note"></a>Le service de facturation électronique prend-il en charge l'ajout d'autres configurations de format ER pour générer d'autres types de documents ? Prend-il en charge l'envoi électronique des documents aux clients, comme une note de livraison ?

Vous pouvez utiliser d'autres configurations de format ER pour produire les fichiers de sortie souhaités. Cependant, la configuration du format ER doit être dérivée du même mappage de modèle de facture ER qui est configuré dans Finance ou Supply Chain Management pour générer des documents commerciaux. L'envoi du fichier de sortie directement au client en tant que transaction EDI n'est pas pris en charge par la facturation électronique.

## <a name="does-the-electronic-invoicing-service-support-exchanging-electronic-invoices-with-customers-does-it-support-configuring-different-invoice-formats-for-the-same-invoice"></a>Le service de facturation électronique prend-il en charge l'échange de factures électroniques avec les clients ? Prend-il en charge la configuration de différents formats de facture pour la même facture ?

La capacité de recevoir et d'importer les factures électroniques des fournisseurs fait partie de la feuille de route, mais l'envoi automatique des factures électroniques aux clients n'est actuellement pas pris en charge.

## <a name="does-the-electronic-invoicing-service-extend-to-support-exchanging-edi-messages-with-other-companies"></a>Le service de facturation électronique s’étend-il à la prise en charge de l’échange de messages EDI avec d’autres entreprises ?

L'objectif du service de facturation électronique est d'échanger des types de messages de facturation électronique en fonction des exigences de conformité réglementaire. La réception et l'importation des factures électroniques des fournisseurs font partie de la feuille de route, mais l'envoi de fichiers de factures électroniques aux clients n'est actuellement pas pris en charge immédiatement, sauf dans les scénarios où l'envoi de la facture électronique au client est une exigence réglementaire.

## <a name="does-the-electronic-invoicing-service-support-importing-or-merging-customizations-made-in-the-er-format-configurations-from-the-legacy-electronic-invoicing-feature"></a>Le service de facturation électronique prend-il en charge l'importation ou la fusion des personnalisations effectuées dans les configurations au format ER à partir de l'ancienne fonctionnalité de facturation électronique ?

Vous pouvez réutiliser les configurations de format ER dans le service de facturation électronique. Cependant, la configuration du format ER doit être dérivée du même mappage de modèle de facture ER que la fonction de facture électronique utilise et qui est configuré dans Finance ou Supply Chain Management pour générer des documents commerciaux.

## <a name="does-the-electronic-invoicing-service-support-issuing-electronic-invoices-from-custom-made-tables-if-so-how-do-you-create-the-er-data-model-configurations-for-these-new-tables-and-entities"></a>Le service de facturation électronique prend-il en charge l'émission de factures électroniques à partir de tables personnalisées ? Si tel est le cas, comment créer les configurations de modèle de données ER pour ces nouvelles tables et entités ?

Oui. Cependant, cela nécessite la personnalisation du mappage du modèle de facture et l'ajout des références nécessaires aux tables personnalisées ou, en fonction de la complexité, la création d'un nouveau mappage de modèle de facture.

## <a name="does-the-electronic-invoicing-service-support-different-web-service-endpoints"></a>Le service de facturation électronique prend-il en charge différents points de terminaison de service Web ?

La facturation électronique prend en charge différents points de terminaison de service Web. Vous pouvez utiliser l'intégration configurable avec les services Web REST ou un certain nombre d'intégrations de services Web paramétrées spécifiques au pays. Différents points de terminaison peuvent être configurés pour les mêmes services Web et API en utilisant différentes versions de configurations. Pour plus d’informations, consultez la section [Liste des paramètres par action](e-invoicing-setup.md#list-of-parameters-by-action).

## <a name="is-electronic-invoicing-integrated-with-the-various-invoice-operators-apis-from-the-nordic-countries-or-should-that-be-handled-on-a-case-by-case-basis"></a>La facturation électronique est-elle intégrée aux API des différents opérateurs de facturation des pays nordiques, ou devrait-elle être traitée au cas par cas ?

Microsoft étend en permanence la couverture fonctionnelle pour fournir des intégrations prêtes à l'emploi en utilisant les fonctionnalités de facturation électronique. Pour plus d'informations sur les formats et les intégrations pris en charge, voir [Disponibilité des fonctionnalités de facturation électronique](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#availability-of-electronic-invoicing-features).

> [!NOTE] 
> Si vous ne trouvez pas la réponse que vous recherchez, envoyez votre question par e-mail à l’équipe de développement produit à l’adresse <D365EInvoicePreview@microsoft.com>. Nous vous contacterons, ou améliorerons la couverture de cette FAQ.
