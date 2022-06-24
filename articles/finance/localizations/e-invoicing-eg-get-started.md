---
title: Facturation électronique pour l’Égypte
description: Cet article donne des informations qui vous aideront à démarrer la Facturation électronique pour l’Égypte dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c2a46ef938c5dee62c0d0acd1648584df344c81a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904410"
---
# <a name="electronic-invoicing-for-egypt"></a>Facturation électronique pour l’Égypte

[!include [banner](../includes/banner.md)]

Cet article donne des informations qui vous aideront à démarrer la Facturation électronique pour l’Égypte. Elle vous guide tout au long des étapes de configuration spécifiques au pays dans Regulatory Configuration Service (RCS). Ces étapes complètent les étapes décrites dans [Configurer la facturation électronique](e-invoicing-set-up-overview.md).

## <a name="prerequisites"></a>Conditions préalables

Avant d’effectuer les étapes de cet article, les conditions préalables suivantes doivent être validées :

- Familiarisez-vous avec la facturation électronique telle qu’elle est décrite dans [Présentation de la facturation électronique](e-invoicing-service-overview.md).
- Inscrivez-vous à RCS et configurez la facturation électronique. Pour plus d’informations, voir les rubriques suivantes :

    - [S’inscrire et installer le service de facturation électronique](e-invoicing-sign-up-install.md)
    - [Paramétrer les ressources Azure pour la facturation électronique](e-invoicing-set-up-azure-resources.md)
    - [Installer le module complémentaire pour les microservices dans Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md)
    
- Activez l’intégration entre votre application Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management et le service de Facturation électronique tel que décrit dans [Activer et configurer l’intégration avec la facturation électronique](e-invoicing-activate-setup-integration.md).
- Créez une clé secrète de certificat numérique dans Azure Key Vault et configurez-la comme décrit dans [Certificats et clés secrètes client](e-invoicing-customer-certificates-secrets.md). À des fins de test, l’administration fiscale égyptienne fournit des certificats numériques de test spécifiques qui ne doivent être utilisés que pendant les phases de test et de validation de la solution. Pour plus d’informations, accédez au site web de l’administration fiscale égyptienne en utilisant le lien fourni dans le [SDK de facturation électronique pour l’Égypte](https://sdk.invoicing.eta.gov.eg/faq/).

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-feature"></a>Configuration spécifique au pays pour la fonctionnalité de facturation électronique pour l’Égypte (EG)

Certains des paramètres de la **Fonctionnalité de Facturation électronique de facture électronique (EG) pour l’Égypte** sont publiés avec des valeurs par défaut. Avant de déployer la fonctionnalité de facturation électronique dans l’environnement de service, passez en revue les valeurs et, si nécessaire, mettez à jour les valeurs pour mieux répondre aux besoins de votre entreprise.

1. Importez la dernière version de la fonctionnalité de **Facture électronique égyptienne (EG)** comme décrit dans [Importer des fonctionnalités depuis le référentiel global](e-invoicing-import-feature-global-repository.md).
2. Créez une copie de la fonctionnalité de globalisation importée et sélectionnez votre fournisseur de configuration pour celle-ci, comme décrit dans [Créer une fonctionnalité de globalisation](e-invoicing-create-new-globalization-feature.md).
3. Sur l’onglet **Versions**, vérifiez que la version **Brouillon** est sélectionnée.
4. Sur l’onglet **Paramétrages**, dans la grille, sélectionnez la configuration de la fonctionnalité provenant de **Facture client**.
5. Sélectionnez **Modifier**.
6. Sur l’onglet **Pipeline de traitement**, dans la section **Pipeline de traitement**, sélectionnez **Signer un document JSON pour l’administration fiscale égyptienne**.
7. Dans la section **Paramètres**, sélectionnez **Nom du certificat**, puis sélectionnez le nom du certificat numérique que vous avez créé.
8. Dans la section **Pipeline de traitement**, sélectionnez **Intégration avec le service ETA égyptien**. Répétez cette étape pour les deux occurrences de cette action.
9. Dans la section **Paramètres**, sélectionnez **URL du service Web** et **URL du service de connexion**. Puis examinez les paramètres de l’URL. Pour obtenir l’URL de test et de production accédez au site web de l’administration fiscale égyptienne en utilisant le lien fourni dans le [kit SDK de facturation électronique pour l’Égypte](https://sdk.invoicing.eta.gov.eg/faq/).
10. Cliquez sur **Enregistrer**, puis fermez la page.
11. Répétez les étapes 4 à 10 pour la configuration de la fonctionnalité provenant de **Facture de projet**.

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-application-setup"></a>Configuration spécifique au pays pour la configuration de l’application de facturation électronique pour l’Égypte (EG)

Certains paramètres doivent être configurés dans votre environnement Finance ou Supply Chain Management. Vous pouvez terminer cette configuration dans l’un des deux emplacements suivants :

- Directement dans votre environnement Finance ou Supply Chain Management. Pour plus d’informations, voir [Configuration des paramètres de facturation électronique](e-invoicing-set-up-parameters.md).
- Dans RCS. Dans le cadre de la configuration de la fonctionnalité de facturation électronique, vous pouvez définir tous les paramètres, puis les déployer directement dans votre environnement Finance ou Supply Chain Management quand vous déployez la fonctionnalité de facturation électronique.

Pour les deux options, les paramètres sont les mêmes. Si vous configurez votre première fonctionnalité dans le service de facturation électronique, nous vous recommandons de suivre ces étapes pour configurer les paramètres dans RCS, puis les déployer sur votre application connectée.

> [!NOTE]
> Certaines versions de la fonctionnalité de facturation électronique peuvent contenir un ensemble prédéfini de paramètres spécifiques à l’application pour Finance ou Supply Chain Management. Dans ce cas, vous devez vérifier que les données sont correctes. Sinon, définissez manuellement les paramètres.

1. Recherchez la copie de la fonctionnalité de globalisation **Facture électronique égyptienne (EG)** que vous avez créée.
2. Sur l’onglet **Versions**, vérifiez que la version **Brouillon** est sélectionnée.
3. Dans l’onglet **Paramétrages**, sélectionnez **Paramétrage de l’application**.
4. Dans le champ **Applications connectées**, sélectionnez l’application sur laquelle vous souhaitez déployer les paramètres.
5. Sur la page **Types de documents électroniques**, sélectionnez **Ajouter** pour créer un enregistrement.
6. Dans le champ **Nom de la table**, ajoutez **CustInvoiceJour**.
7. Dans le champ **Contexte**, ajoutez une référence au nom de mappage **Contexte facture client**. La configuration est **Modèle de contexte de facture client**.
8. Dans le champ **Mappage du document électronique**, ajoutez une référence au nom de mappage **Facture client**. La configuration est **Mappage de modèle de facture**.
9. Cliquez sur **Enregistrer**.
10. Sur la page **Types de réponse**, sélectionnez **Ajouter**.
11. Dans le champ **Type de réponse**, entrez **Réponse**.
12. Dans le champ **Description**, entrez **Réponse du processus**.
13. Dans le champ **Statut d’envoi**, sélectionnez **En attente**.
14. Dans le champ **Mappage de modèle**, sélectionnez **Importation des messages de réponse**. La configuration est **Importation des messages de réponse en Égypte (EG)**.
15. Cliquez sur **Enregistrer**.
16. Sélectionnez **Ajouter**.
17. Dans le champ **Type de réponse**, entrez **ResponseData**.
18. Dans le champ **Description**, entrez **Données de réponse du processus**.
19. Dans le champ **Statut d’envoi**, sélectionnez **En attente**.
20. Dans le champ **Nom de l’entité de données**, sélectionnez **SalesInvoiceHeaderV2Entity**.
21. Dans le champ **Mappage de modèle**, sélectionnez **Importation des données de réponse**. La configuration est **Format d’importation des données de réponse en Égypte (EG)**.
22. Cliquez sur **Enregistrer**, puis fermez la page.
23. Fermez la page.

Pour déployer une fonctionnalité dans l’environnement de service et une configuration d’application dans l’application connectée Finance ou Supply Chain Management, voir [Réaliser, publier et déployer une fonctionnalité de globalisation](e-invoicing-complete-publish-deploy-globalization-feature.md)

## <a name="privacy-notice"></a>Avis de confidentialité

Activer la fonctionnalité **Facture électronique égyptienne** peut nécessiter l’envoi de données limitées. Ces données incluent le numéro d’identification fiscale de l’organisation. Ces données seront transmises à des organismes tiers autorisés par l’administration fiscale aux fins d’envoi de factures électroniques à cette administration fiscale dans le format prédéfini requis pour l’intégration avec le service web du gouvernement. Un administrateur peut activer et désactiver la fonctionnalité en accédant à **Administration de l’organisation** \> **Paramétrage** \> **Paramètres des documents électroniques**. Sur l’onglet **Fonctionnalités**, sélectionnez la ligne qui contient la fonctionnalité **Facture électronique pour l’Égypte (EG)**, puis effectuez la sélection appropriée. Les données qui sont importées depuis ces systèmes externes vers ce service en ligne Dynamics 365 sont soumises à notre [déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=512132). Pour plus d’informations, consultez la section « Déclaration de confidentialité » dans la documentation de la fonctionnalité spécifique au pays.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble de la Facturation électronique](e-invoicing-service-overview.md)
- [Mise en route de l’administration du service de Facturation électronique](e-invoicing-get-started-service-administration.md)
- [Mise en route de la Facturation électronique](e-invoicing-get-started.md)
- [Factures électroniques client en Égypte](emea-egy-e-invoices.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
