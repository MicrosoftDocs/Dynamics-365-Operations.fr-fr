---
title: Démarrage du module complémentaire de facturation électronique pour la France
description: Cet article donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique pour la France.
author: dkalyuzh
ms.date: 07/07/2022
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2022-00-02
ms.dyn365.ops.version: AX 10.0.29
ms.openlocfilehash: 365316b204b6d76fa6ee6b2402fefee50c8ff3ef
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220652"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-france"></a>Démarrage du module complémentaire de facturation électronique pour la France

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Cet article donne des informations qui vous aideront à démarrer la Facturation électronique pour la France. Elle vous guide tout au long des étapes de configuration spécifiques au pays dans Regulatory Configuration Service (RCS). Ces étapes complètent les étapes décrites dans le module complémentaire [Démarrer la facturation électronique](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-french-chorus-pro-submission-fr-electronic-invoicing-feature"></a>Configuration spécifique au pays pour la fonctionnalité de facturation électronique du service de soumission Chorus Pro français

Certaines étapes sont nécessaires pour configurer la fonctionnalité de facturation électronique du **service de soumission Chorus Pro français**. Certains paramètres de la configuration ont été publiés avec les valeurs par défaut. Ces valeurs doivent être examinées et mises à jour afin de mieux refléter vos opérations commerciales.

### <a name="prerequisites"></a>Conditions préalables

Avant d’effectuer les étapes de cet article, les conditions préalables suivantes doivent être validées :

- Familiarisez-vous avec la facturation électronique. Pour plus d’informations, voir [Présentation générale de la facturation électronique](e-invoicing-service-overview.md).
- Inscrivez-vous à RCS et configurez la facturation électronique. Pour plus d’informations, voir l’article suivant :

    - [S’inscrire et installer le service de facturation électronique](e-invoicing-sign-up-install.md)
    - [Paramétrer les ressources Azure pour la facturation électronique](e-invoicing-set-up-azure-resources.md)
    - [Installer le module complémentaire pour les microservices dans Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md)
    - [Activer et configurer l’intégration avec la facturation électronique](e-invoicing-activate-setup-integration.md) – Utilisez les informations contenues dans cet article pour activer l’intégration entre l’application Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management et le service de facturation électronique.
    - [Codes NAF et numéros Siret](emea-fra-naf-codes-siret-numbers.md) et [Configurer les codes NAF et les numéros Siret](tasks/fr-00003-naf-codes-siret-numbers.md) – Utilisez les informations contenues dans ces articles pour configurer les codes NAF et les numéros Siret de vos entités juridiques. 

- Votre organisation doit être enregistrée pour fonctionner avec Chorus Pro. Microsoft fournit une intégration avec Chorus Pro en mode OAuth2 via une interface de programmation d’application (API). Pour plus d’informations sur l’inscription à Chorus Pro et l’activation de l’application, consultez la [documentation officielle](https://communaute.chorus-pro.gouv.fr/documentation/help-for-api-developers-in-oauth2-mode/).

    Pour vous enregistrer à Chorus Pro, procédez comme suit.

    1. Accédez au [portail PISTE](https://piste.gouv.fr/en/component/apiportal/registration) pour commencer votre inscription. 
    2. Enregistrez une application et activez les informations d’identification Open Authorization (OAuth).
    3. Copiez et enregistrez l’ID client des informations d’identification OAuth et la clé secrète. Vous utiliserez ces informations dans les étapes suivantes.
    4. Accédez au [portail Chorus Pro](https://portail.chorus-pro.gouv.fr/aife_csm/?id=aife_enrollment) pour vous enregistrer. 
    5. Créez un compte technique pour l’accès à l’API. Pour plus d’informations, voir [Création d’un compte technique pour l’accès à API en production](https://communaute.chorus-pro.gouv.fr/documentation/creation-of-a-technical-account-for-an-api-access-in-production/).
    6. Copiez l’ID utilisateur du compte technique et le mot de passe. Vous utiliserez ces informations dans les étapes suivantes.

## <a name="country-specific-configuration-of-the-application-setup-for-the-french-chorus-pro-submission-fr-electronic-invoicing-feature"></a>Configuration spécifique au pays du paramétrage de l’application pour la fonctionnalité de facturation électronique du service de soumission Chorus Pro français

Certains des paramètres de la **fonctionnalité de facturation électronique du service de soumission Chorus Pro français** sont publiés avec des valeurs par défaut. Avant de déployer la fonctionnalité de facturation électronique dans l’environnement de service, passez en revue et mettez à jour les valeurs si nécessaire, pour mieux répondre aux besoins de votre entreprise.

1. Dans Azure Key Vault, créez des secrets et la référence correspondante à ceux-ci. Pour plus d’informations, voir [Certificats et secrets des clients](e-invoicing-customer-certificates-secrets.md).
2. Importez la dernière version de la fonctionnalité de globalisation du **service de soumission Chorus Pro français** comme décrit dans [Importer des fonctionnalités depuis le référentiel global](e-invoicing-import-feature-global-repository.md).
3. Créez une copie de la fonctionnalité de globalisation importée et sélectionnez votre fournisseur de configuration. Pour plus d’informations, voir [Création d ’une fonctionnalité de globalisation](e-invoicing-create-new-globalization-feature.md).
4. Sur l’onglet **Versions**, vérifiez que la version **Brouillon** est sélectionnée.
5. Sur l’onglet **Paramétrages**, dans la grille, sélectionnez la configuration de la fonctionnalité provenant de **Facture client UBL**.
6. Sélectionnez **Modifier**, puis dans l’onglet **Pipeline de traitement**, à la section **Pipeline de traitement**, sélectionnez **(Version préliminaire) Intégration avec le service Chorus Pro** avec le nom de l’action **Soumission du service Chorus Pro français**.
7. Dans la section **Paramètres**, dans le champ **Nom secret de l’ID client**, sélectionnez le nom du secret que vous avez créé pour l’ID client dans le coffre de clés.
8. Dans le champ **Nom secret de la clé secrète client**, sélectionnez le nom du secret que vous avez créé pour la clé secrète client dans le coffre de clés.
9. Dans le champ **Nom secret de la connexion technique**, sélectionnez le nom du secret que vous avez créé pour la connexion au compte technique dans le coffre de clés.
10. Dans le champ **Nom secret du mot de passe**, sélectionnez le nom du secret que vous avez créé pour le mot de passe du compte technique dans le coffre de clés.
11. Dans l’onglet **Pipeline de traitement**, à la section **Pipeline de traitement**, sélectionnez **Intégration avec le service Chorus Pro français** avec le nom de l’action **État de la demande du service Chorus Pro français**.
12. Dans la section **Paramètres**, dans le champ **Nom secret de l’ID client**, sélectionnez le nom du secret que vous avez créé pour l’ID client dans le coffre de clés.
13. Dans le champ **Nom secret de la clé secrète client**, sélectionnez le nom du secret que vous avez créé pour la clé secrète client dans le coffre de clés.
14. Dans le champ **Nom secret de la connexion technique**, sélectionnez le nom du secret que vous avez créé pour la connexion au compte technique dans le coffre de clés.
15. Dans le champ **Nom secret du mot de passe**, sélectionnez le nom du secret que vous avez créé pour le mot de passe du compte technique dans le coffre de clés.
16. Sélectionnez **Sauvegarder**, puis fermez la page.
17. Répétez les étapes 6 à 16 pour configurer les fonctionnalités **Facture de projet UBL dérivée**, **Avoir sur vente UBL dérivé** et **Avoir de projet UBLdérivé**.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble du module complémentaire de facturation électronique](e-invoicing-service-overview.md)
- [Mise en route de l’administration du service du module complémentaire de facturation électronique](e-invoicing-get-started-service-administration.md)
- [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md)
