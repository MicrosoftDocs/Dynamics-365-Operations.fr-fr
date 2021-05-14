---
title: Mise en route de la facturation électronique pour l’Égypte
description: Cette rubrique donne des informations qui vous aideront à démarrer la Facturation électronique pour l’Égypte dans Finance et Supply Chain Management.
author: gionoder
ms.date: 04/20/2021
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
ms.openlocfilehash: abae35db7e37e65950c05c8e21b8e8555edbf3be
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920779"
---
# <a name="get-started-with-electronic-invoicing-for-egypt"></a>Mise en route de la facturation électronique pour l’Égypte

[!include [banner](../includes/banner.md)]

Cette rubrique donne des informations qui vous aideront à démarrer la Facturation électronique pour l’Égypte. La rubrique vous guide tout au long des étapes de configuration qui dépendent du pays dans Regulatory Configuration Services (RCS) et complètent les étapes décrites dans la rubrique [Mise en route de la facturation électronique](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Configuration spécifique au pays pour la fonctionnalité de facturation électronique pour l’Égypte (EG)

Certains des paramètres de la **Fonctionnalité de Facturation électronique de facture électronique (EG) pour l’Égypte** sont publiés avec des valeurs par défaut. Passez en revue les valeurs et, si nécessaire, mettez à jour les valeurs pour mieux répondre aux besoins de votre entreprise avant de déployer la fonctionnalité de Facturation électronique dans l’environnement de service.

Cette section complète la section **Configuration spécifique au pays pour la fonctionnalité de facturation électronique** de la rubrique [Mise en route de la Facturation électronique](e-invoicing-get-started.md).

### <a name="prerequisites"></a>Conditions préalables

Pour pouvoir effectuer la procédure de cette section, vous devez :

- Créer un secret de certificat numérique, comme décrit dans la section **Créer un secret de certificat numérique** dans [Prise en main de l’administration du service de Facturation électronique](e-invoicing-get-started-service-administration.md). À des fins de test, l’administration fiscale égyptienne fournit des certificats numériques de test spécifiques qui ne doivent être utilisés que pendant les phases de test et de validation de la solution. Pour plus d’informations, consultez le site web de l’administration fiscale égyptienne en utilisant le lien fourni dans le [SDK de facturation électronique pour l’Égypte](https://sdk.sit.invoicing.eta.gov.eg/faq/).

1. Dans RCS, dans la section **Fonctionnalités** de l’espace de travail **Fonctionnalité de globalisation**, sélectionnez la vignette **Facturation électronique**.
2. Sur la page **Fonctionnalités de Facturation électronique**, vérifiez que la fonctionnalité de Facturation électronique **Facture électronique pour l’Égypte (EG)** que vous avez créée est sélectionnée.
3. Sur l’onglet **Versions**, vérifiez que la version **Brouillon** est sélectionnée.
4. Sur l’onglet **Paramétrages**, dans la grille, sélectionnez le paramétrage de la fonctionnalité **Facture client**.
5. Sélectionnez **Modifier** et, sur l’onglet **Actions**, dans le groupe de champs **Actions**, sélectionnez **Signer un document JSON pour l’administration fiscale égyptienne**.
6. Dans le groupe de champs **Paramètres**, sélectionnez le paramètre **Nom du certificat** et sélectionnez le nom du certificat numérique créé à utiliser avec la fonctionnalité de facturation électronique.
7. Dans le groupe de champs **Actions**, sélectionnez **Intégration avec le service ETA égyptien**. Répétez cette étape pour les deux occurrences de cette action.
8. Dans le groupe de champs **Paramètres**, sélectionnez **URL de service Web** et **URL de service de connexion** et, si nécessaire, vérifiez les paramètres d’URL. Consultez le site web de l’administration fiscale égyptienne pour obtenir l’URL de test et de production, en utilisant le lien fourni dans le [kit SDK de facturation électronique pour l’Égypte](https://sdk.sit.invoicing.eta.gov.eg/faq/).
9. Cliquez sur **Enregistrer**, puis fermez la page.
10. Pour déployer la fonctionnalité de facturation électronique dans l’environnement de service, voir [Prise en main de la Facturation électronique](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-the-application-setup-for-the-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Configuration spécifique au pays du paramétrage de l’application pour la fonctionnalité de facturation électronique de facture électronique pour l’Égypte (EG)

Effectuez ces étapes avant de déployer la configuration de l’application sur votre application connectée Finance ou Supply Chain Management.

Cette section complète la section **Configuration du paramétrage de l’application spécifique au pays** de la rubrique [Mise en route de la Facturation électronique](e-invoicing-get-started.md).

1. Dans RCS, dans la section **Fonctionnalités** de l’espace de travail **Fonctionnalité de globalisation**, sélectionnez la vignette **Facturation électronique**.
2. Sur la page **Fonctionnalités de Facturation électronique**, vérifiez que la fonctionnalité de Facturation électronique **Facture électronique pour l’Égypte (EG)** est sélectionnée.
3. Sur l’onglet **Versions**, vérifiez que la version **Brouillon** est sélectionnée.
4. Sur l’onglet **Paramétrages**, sélectionnez **Paramétrage de l’application** et, dans le champ **Application connectée**, sélectionnez l’application sur laquelle vous souhaitez déployer.
5. Dans le champ **Nom de la table**, vérifiez que le journal des factures client est sélectionné.
6. Sélectionnez **Types de réponse**, puis sélectionnez **Nouveau**.
7. Dans le champ **Type de réponse**, entrez « Réponse » et, dans le champ **Description**, entrez « Description ».
8. Dans le champ **Statut d’envoi**, sélectionnez **En attente**.
9. Dans le champ **Mise en correspondance des modèles**, sélectionnez **Mise en correspondance des modèles du message de réponse**, avec **(Aperçu) Format d’importation du message de réponse**, puis sélectionnez **Enregistrer**.
10. Sélectionnez **Nouveau**, puis, dans dans le champ **Type de réponse**, entrez « ResponseData » comme valeur fixe. Dans le champ **Description**, entrez « Description ».
11. Dans le champ **Statut d’envoi**, sélectionnez **En attente**.
12. Dans le champ **Nom de l’entité de données**, sélectionnez **En-têtes de facture client V2**.
13. Dans le champ **Mise en correspondance des modèles**, sélectionnez **Importation des données de réponse pour l’Égypte** avec **(Aperçu) Importation des données de réponse pour l’Égypte**, puis sélectionnez **Enregistrer**.
14. Pour déployer le paramétrage de l’application sur l’application connectée Finance ou Supply Chain Management, voir [Mise en route de la Facturation électronique](e-invoicing-get-started.md).

## <a name="privacy-notice"></a>Avis de confidentialité

L’activation de la fonctionnalité **Facture électronique pour l’Égypte (EG)** peut nécessiter l’envoi de données limitées, y compris l’ID d’enregistrement fiscal de l’organisation. Ces données seront transmises à des organismes tiers autorisés par l’administration fiscale aux fins d’envoi de factures électroniques à cette administration fiscale dans le format prédéfini requis pour l’intégration avec le service web du gouvernement. Un administrateur peut activer et désactiver la fonctionnalité en accédant à **Administration de l’organisation** > **Paramétrage** > **Paramètres des documents électroniques**. Sur l’onglet **Fonctionnalités**, sélectionnez la ligne qui contient la fonctionnalité **Facture électronique pour l’Égypte (EG)**, puis effectuez la sélection appropriée. Les données importées depuis ces systèmes externes vers ce service en ligne Dynamics 365 sont soumises à notre [déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=512132). Pour plus d’informations, consultez les sections Déclaration de confidentialité dans la documentation de la fonctionnalité spécifique au pays.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble de la Facturation électronique](e-invoicing-service-overview.md)
- [Mise en route de l’administration du service de Facturation électronique](e-invoicing-get-started-service-administration.md)
- [Mise en route de la Facturation électronique](e-invoicing-get-started.md)
- [Factures électroniques client en Égypte](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
