---
title: Prise en main du module complémentaire de facturation électronique pour l’Égypte
description: Cette rubrique donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique pour l’Égypte dans Finance et Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 02/26/2021
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
ms.openlocfilehash: 68ee08226f440e850a080600dbf5e16768b45e43
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592596"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-egypt"></a>Prise en main du module complémentaire de facturation électronique pour l’Égypte

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Cette rubrique donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique pour l’Égypte. La rubrique vous guide tout au long des étapes de configuration qui dépendent du pays dans Regulatory Configuration Services (RCS) et complètent les étapes décrites dans [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Configuration spécifique au pays pour la fonctionnalité de facturation électronique pour l’Égypte (EG)

Pour configurer la fonctionnalité de facturation électronique de la facture électronique pour l’Égypte (EG), vous devez suivre plusieurs étapes. Certains des paramètres des configurations sont publiés avec des valeurs par défaut. Ils doivent donc être examinés et mis à jour pour mieux s’adapter à votre opération d’entreprise.

### <a name="prerequisites"></a>Conditions préalables

Pour pouvoir effectuer la procédure de cette section, vous devez :

- Créer un secret de certificat numérique, comme décrit dans la section **Créer un secret de certificat numérique** dans [Prise en main de l’administration du service du module complémentaire de facturation électronique](e-invoicing-get-started-service-administration.md). À des fins de test, l’administration fiscale égyptienne fournit des certificats numériques de test spécifiques qui ne doivent être utilisés que pendant les phases de test et de validation de la solution. Pour plus d’informations, consultez le site web de l’administration fiscale égyptienne en utilisant le lien fourni dans le [kit SDK de facturation électronique pour l’Égypte](https://sdk.sit.invoicing.eta.gov.eg/faq/).
- Créez une fonctionnalité de facturation de facture électronique pour l’Égypte (EG) pour votre organisation, comme décrit dans la section **Créer une fonctionnalité de facturation électronique sous votre fournisseur d’organisation** dans [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md).

1. Dans RCS, dans la section **Fonctionnalités** de l’espace de travail **Fonctionnalités de globalisation**, sélectionnez la vignette **Module complémentaire de facturation électronique**.
2. Sur la page **Fonctionnalités complémentaires de facturation électronique**, vérifiez que la fonctionnalité de facturation électronique **Facture électronique pour l’Égypte (EG)** que vous avez créée est sélectionnée.
3. Sur l’onglet **Versions**, vérifiez que la version **Brouillon** est sélectionnée.
4. Sur l’onglet **Paramétrages**, dans la grille, sélectionnez le paramétrage de la fonctionnalité **Facture client**.
5. Sélectionnez **Modifier** et, sur l’onglet **Actions**, dans le groupe de champs **Actions**, sélectionnez **Signer un document JSON pour l’administration fiscale égyptienne**.
6. Dans le groupe de champs **Paramètres**, sélectionnez le paramètre **Nom du certificat** et sélectionnez le nom du certificat numérique créé à utiliser avec la fonctionnalité de facturation électronique.
7. Dans le groupe de champs **Actions**, sélectionnez **Intégration avec le service ETA égyptien**. Répétez cette étape pour les deux occurrences de cette action.
8. Dans le groupe de champs **Paramètres**, sélectionnez **URL de service Web** et **URL de service de connexion** et, si nécessaire, vérifiez les paramètres d’URL. Consultez le site web de l’administration fiscale égyptienne pour obtenir l’URL de test et de production, en utilisant le lien fourni dans le [kit SDK de facturation électronique pour l’Égypte](https://sdk.sit.invoicing.eta.gov.eg/faq/).
9. Cliquez sur **Enregistrer**, puis fermez la page.
10. Pour configurer le paramétrage de l’application, voir [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-the-application-setup-for-the-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Configuration spécifique au pays du paramétrage de l’application pour la fonctionnalité de facturation électronique de facture électronique pour l’Égypte (EG)

La configuration du paramétrage de l’application pour la fonctionnalité de facturation électronique **Facture électronique pour l’Égypte (EG)** nécessite que des étapes spécifiques soient effectuées. Effectuez ces étapes avant de déployer votre fonctionnalité de facturation électronique dans votre environnement de service complémentaire de facturation électronique.

### <a name="prerequisites"></a>Conditions préalables

Avant de terminer la procédure de cette section, créez et lancez la fonctionnalité de facturation électronique **Facture électronique pour l’Égypte (EG)** pour configurer le paramétrage de l’application pour la fonctionnalité de facturation électronique **Facture électronique pour l’Égypte (EG)**, comme décrit dans la section **Configurer le paramétrage de l’application** dans la rubrique [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md).

1. Dans RCS, dans la section **Fonctionnalités** de l’espace de travail **Fonctionnalités de globalisation**, sélectionnez la vignette **Module complémentaire de facturation électronique**.
2. Sur la page **Fonctionnalités complémentaires de facturation électronique**, vérifiez que la fonctionnalité de facturation électronique **Facture électronique pour l’Égypte (EG)** est sélectionnée.
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
14. Pour déployer la fonctionnalité de facturation électronique, voir [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md).

## <a name="privacy-notice"></a>Avis de confidentialité

L’activation de la fonctionnalité **Facture électronique pour l’Égypte (EG)** peut nécessiter l’envoi de données limitées, y compris l’ID d’enregistrement fiscal de l’organisation. Ces données seront transmises à des organismes tiers autorisés par l’administration fiscale aux fins d’envoi de factures électroniques à cette administration fiscale dans le format prédéfini requis pour l’intégration avec le service web du gouvernement. Un administrateur peut activer et désactiver la fonctionnalité en accédant à **Administration de l’organisation** > **Paramétrage** > **Paramètres des documents électroniques**. Sur l’onglet **Fonctionnalités**, sélectionnez la ligne qui contient la fonctionnalité **Facture électronique pour l’Égypte (EG)**, puis effectuez la sélection appropriée. Les données importées depuis ces systèmes externes vers ce service en ligne Dynamics 365 sont soumises à notre [déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=512132). Pour plus d’informations, consultez les sections Déclaration de confidentialité dans la documentation de la fonctionnalité spécifique au pays.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble du module complémentaire de facturation électronique](e-invoicing-service-overview.md)
- [Mise en route de l’administration du service du module complémentaire de facturation électronique](e-invoicing-get-started-service-administration.md)
- [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md)
- [Factures électroniques client en Égypte](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
