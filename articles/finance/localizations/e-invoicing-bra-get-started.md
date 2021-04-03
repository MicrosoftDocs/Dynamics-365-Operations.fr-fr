---
title: Démarrage du module complémentaire de facturation électronique pour le Brésil
description: Cette rubrique donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique pour le Brésil dans Finance et Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
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
ms.openlocfilehash: eaf9433ad2d9ccf3d3c5632d0f2d4fe772ff8bde
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592668"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-brazil"></a>Démarrage du module complémentaire de facturation électronique pour le Brésil 

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment démarrer avec le module complémentaire de facturation électronique pour le Brésil. Les procédures de cette rubrique vous guident tout au long des étapes de configuration qui dépendent du pays dans Regulatory Configuration Services (RCS) et complètent les étapes décrites dans la rubrique [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Configuration spécifique au pays pour la fonctionnalité de facturation électronique NF-e (BR) pour le Brésil

La configuration de la fonctionnalité de facturation électronique NF-e (BR) pour le Brésil nécessite que des étapes spécifiques soient effectuées. Certains des paramètres des configurations sont publiés avec des valeurs par défaut. Ils doivent donc être examinés et mis à jour pour mieux s’adapter à votre opération d’entreprise.

### <a name="prerequisites"></a>Conditions préalables

Avant de terminer la procédure de cette section, créez une fonctionnalité de facturation électronique NF-e (BR) pour le Brésil pour votre organisation, comme décrit dans la section **Créer une fonctionnalité de facturation électronique sous votre fournisseur d’organisation** de la rubrique [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md).

1. Dans RCS, dans la section **Fonctionnalités** de l’espace de travail **Fonctionnalités de globalisation**, sélectionnez la vignette **Module complémentaire de facturation électronique**.
2. Sur la page **Fonctionnalités complémentaires de facturation électronique**, vérifiez que la fonctionnalité de facturation électronique **NF-e (BR) pour le Brésil** que vous avez créée est sélectionnée.
3. Sur l’onglet **Versions**, vérifiez que la version **Brouillon** est sélectionnée.
4. Sur l’onglet **Paramétrages**, sélectionnez **Soumettre** dans la grille, puis sélectionnez **Modifier**.
5. Sur l’onglet **Actions**, dans le groupe de champs **Actions**, sélectionnez l’action **(Aperçu) Signer le document XML**.
6. Dans le groupe de champs **Paramètres**, sélectionnez **Nom du certificat** et, dans le champ **Valeur**, entrez le nom du certificat associé à votre paramètre de coffre de clés.
7. Sur l’onglet **Actions**, dans le groupe de champs **Actions**, sélectionnez l’action **(Aperçu) Appeler le service SEFAZ brésilien**.
8. Dans le groupe de champs **Paramètres**, sélectionnez le paramètre **Adresse URL**.
9. Dans le champ **Valeur**, si nécessaire, vérifiez et mettez à jour l’URL des services web publiés par la documentation SEFAZ pour votre état, puis sélectionnez **Enregistrer**.
10. Sur l’onglet **Règles d’applicabilité**, dans le groupe de champs **Configuration de la règle d’applicabilité**, vérifiez et mettez à jour le critère du champ **État** comme il se doit pour le même état auquel est référencée l’URL des services web.
11. Cliquez sur **Enregistrer**, puis fermez la page.
12. Pour configurer le paramétrage de l’application, voir [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Configuration spécifique au pays du paramétrage de l’application pour la fonctionnalité de facturation électronique NF-e (BR) pour le Brésil

La configuration du paramétrage de l’application de la fonctionnalité de facturation électronique NF-e (BR) pour le Brésil nécessite que des étapes spécifiques soient effectuées. Effectuez ces étapes avant de déployer votre fonctionnalité de facturation électronique dans votre environnement de service complémentaire de facturation électronique.

### <a name="prerequisites"></a>Conditions préalables

Avant de terminer la procédure de cette section, créez et lancez le paramétrage de l’application de la fonctionnalité de facturation électronique NF-e (BR) pour le Brésil, comme décrit dans la section **Configurer le paramétrage de l’application** de la rubrique [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md).

1. Dans RCS, dans la section **Fonctionnalités** de l’espace de travail **Fonctionnalités de globalisation**, sélectionnez la vignette **Module complémentaire de facturation électronique**.
2. Sur la page **Fonctionnalités complémentaires de facturation électronique**, vérifiez que la fonctionnalité de facturation électronique **NF-e (BR) pour le Brésil** est sélectionnée.
3. Sur l’onglet **Versions**, vérifiez que la version **Brouillon** est sélectionnée.
4. Sur l’onglet **Paramétrages**, sélectionnez **Paramétrage de l’application** et, dans le champ **Application connectée**, sélectionnez l’application sur laquelle vous souhaitez déployer.
5. Dans le champ **Nom de la table**, vérifiez si **En-tête du document fiscal** est sélectionné.
6. Sélectionnez **Types de réponse**, puis sélectionnez **Nouveau**.
7. Dans le champ **Type de réponse**, entrez « Réponse » comme valeur fixe et, dans le champ **Description**, entrez « Description ».
8. Dans le champ **Statut d’envoi**, sélectionnez **En attente**.
9. Dans le champ **Mise en correspondance des modèles**, sélectionnez **Mise en correspondance des modèles du message de réponse** avec **(Aperçu) Format d’importation du message de réponse**, puis sélectionnez **Enregistrer**.
10. Sélectionnez **Nouveau** et, dans le champ **Type de réponse**, entrez « ResponseData » comme valeur fixe et, dans le champ **Description**, entrez « Description ».
11. Dans le champ **Statut d’envoi**, sélectionnez **En attente**.
12. Dans le champ **Mise en correspondance des modèles**, sélectionnez **Importation des données de réponse** avec **(Aperçu) Format d’importation des données de réponse NF-e (BR)**, puis sélectionnez **Enregistrer**.
13. Pour déployer la fonctionnalité de facturation électronique, voir [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Configuration spécifique au pays pour la fonctionnalité de facturation électronique NFS-e ABRASF Curitiba (BR) pour le Brésil

La configuration de la fonctionnalité de facturation électronique NFS-e ABRASF Curitiba (BR) pour le Brésil nécessite que des étapes spécifiques soient effectuées. Certains des paramètres des configurations sont publiés avec des valeurs par défaut. Ils doivent donc être examinés et mis à jour pour mieux s’adapter à votre opération d’entreprise.

### <a name="prerequisites"></a>Conditions préalables

Avant de terminer la procédure de cette section, créez une fonctionnalité de facturation électronique NFS-e ABRASF Curitiba (BR) pour le Brésil dans votre organisation. Cette procédure est décrite dans la section **Configurer la fonctionnalité de facturation électronique** dans la rubrique [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md).

1. Dans RCS, dans la section **Fonctionnalités** de l’espace de travail **Fonctionnalités de globalisation**, sélectionnez la vignette **Module complémentaire de facturation électronique**.
2. Sur la page **Fonctionnalités complémentaires de facturation électronique**, vérifiez que la fonctionnalité de facturation électronique **NFS-e ABRASF Curitiba (BR) pour le Brésil** que vous avez créée est sélectionnée.
3. Sur l’onglet **Versions**, vérifiez que la version **Brouillon** est sélectionnée, et sur l’onglet **Paramétrages**, dans la grille, sélectionnez **Soumettre**.
4. Sélectionnez **Modifier** et, sur l’onglet **Actions**, dans le groupe de champs **Actions**, sélectionnez la première occurrence de **(Aperçu) Signer le document XML**.
5. Dans le groupe de champs **Paramètres**, sélectionnez **Nom du certificat**.
6. Dans le champ **Valeur**, entrez le nom du certificat associé à votre paramètre de coffre de clés.
7. Dans le groupe de champs **Actions**, sélectionnez la deuxième occurrence de **(Aperçu) Signer le document XML**.
8. Dans le groupe de champs **Paramètres**, sélectionnez **Nom du certificat**.
9. Dans le champ **Valeur**, entrez le nom du certificat associé à votre paramètre de coffre de clés.
10. Sur l’onglet **Actions**, dans le groupe de champs **Actions**, sélectionnez l’action **(Aperçu) Appeler le service SEFAZ brésilien**.
11. Dans le groupe de champs **Paramètres**, sélectionnez le paramètre **Adresse URL**.
12. Dans le champ **Valeur**, si nécessaire, vérifiez et mettez à jour l’URL des services web publiés par le service des taxes pour la ville de Curitiba, puis sélectionnez **Enregistrer**.
13. Sur l’onglet **Paramétrages**, sélectionnez **Demander** dans la grille, puis sélectionnez **Modifier**.
14. Sur l’onglet **Actions**, dans le groupe de champs **Actions**, sélectionnez l’action **(Aperçu) Appeler le service SEFAZ brésilien**.
15. Dans le groupe de champs **Paramètres**, sélectionnez le paramètre **Adresse URL**.
16. Dans le champ **Valeur**, si nécessaire, vérifiez et mettez à jour l’URL des services web publiés par le service des taxes pour la ville de Curitiba.
17. Sélectionnez **Enregistrer**, puis fermez la page.
18. Pour configurer le paramétrage de l’application, voir [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Configuration spécifique au pays du paramétrage de l’application pour la fonctionnalité de facturation électronique NFS-e ABRASF Curitiba (BR) pour le Brésil

La configuration du paramétrage de l’application pour la fonctionnalité de facturation électronique NFS-e ABRASF Curitiba (BR) pour le Brésil nécessite que des étapes spécifiques soient effectuées avant de déployer votre fonctionnalité de facturation électronique dans votre environnement de service complémentaire de facturation électronique.

### <a name="prerequisites"></a>Conditions préalables

Avant de terminer la procédure de cette section, créez et lancez la fonctionnalité de facturation électronique NFS-e ABRASF Curitiba (BR) pour le Brésil, comme décrit dans la section **Configurer le paramétrage de l’application** de la rubrique [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md).

1. Dans RCS, dans la section **Fonctionnalités** de l’espace de travail **Fonctionnalités de globalisation**, sélectionnez la vignette **Module complémentaire de facturation électronique**.
2. Sur la page **Fonctionnalités complémentaires de facturation électronique**, vérifiez que la fonctionnalité de facturation électronique **NFS-e ABRASF Curitiba (BR) pour le Brésil** est sélectionnée.
3. Sur l’onglet **Versions**, vérifiez que la version **Brouillon** est sélectionnée, et sur l’onglet **Paramétrages**, dans la grille, sélectionnez **Paramétrage de l’application**.
4. Dans le champ **Application connectée**, sélectionnez l’application sur laquelle vous souhaitez déployer.
5. Dans le champ **Nom de la table**, vérifiez que l’en-tête du document fiscal est sélectionné.
6. Sélectionnez **Types de réponse** et sélectionnez **Nouveau**.
7. Dans le champ **Type de réponse**, entrez « ABRASFCuritibaSubmitResponse » comme valeur fixe et, dans le champ **Description**, entrez « Description ».
8. Dans le champ **Statut d’envoi**, sélectionnez **En attente**.
9. Dans le champ **Mise en correspondance des modèles**, sélectionnez **Importation du message de réponse** avec **(Aperçu) Importation du message de réponse NFS-e ABRASF Curitiba**, puis sélectionnez **Enregistrer**.
10. Sélectionnez **Nouveau** et, dans le champ **Type de réponse**, entrez « ABRASFCuritibaSubmitResponseData » comme valeur fixe et, dans le champ **Description**, entrez « Description ».
11. Dans le champ **Statut d’envoi**, sélectionnez **En attente**.
12. Dans le champ **Mise en correspondance des modèles**, sélectionnez **Importation des données de réponse**, avec **(Aperçu) Format d’importation des données de réponse NFS-e ABRASF (BR)** et sélectionnez **Enregistrer**.
13. Sélectionnez **Nouveau** et, dans le champ **Type de réponse**, entrez « ABRASFCuritibaInquireResponse » comme valeur fixe et, dans le champ **Description**, entrez « Description ».
14. Dans le champ **Statut d’envoi**, sélectionnez **En attente**.
15. Dans le champ **Mise en correspondance des modèles**, sélectionnez **Importation du message de réponse** avec **(Aperçu) Importation du message de réponse NFS-e ABRASF Curitiba**.
16. Sélectionnez **Enregistrer**, puis revenez à la rubrique [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md) pour déployer la fonctionnalité de facturation électronique.

## <a name="privacy-notice"></a>Avis de confidentialité
L’activation des fonctionnalités **NF-e Federal - Facture électronique pour le Brésil (BR)** et **NFS-e - Facture électronique pour le service (ville) pour le Brésil** peut nécessiter l’envoi de données limitées, y compris l’ID d’enregistrement fiscal de l’organisation. Ces données sont transmises à des organismes tiers autorisés par l’administration fiscale aux fins d’envoi de factures électroniques à cette administration fiscale dans le format prédéfini requis pour l’intégration avec le service web du gouvernement. En tant qu’administrateur, vous pouvez activer ou désactiver les fonctionnalités **NF-e Federal - Facture électronique pour le Brésil (BR)** et **NFS-e - Facture électronique pour le service (ville) pour le Brésil**. Les étapes suivantes vous indiquent comment procéder : 

1. Accédez à **Administration de l’organisation** > **Paramétrage** > **Paramètres des documents électroniques**. 
2. Sur l’onglet **Fonctionnalités**, sélectionnez la ligne qui contient la fonctionnalité **NF-e Federal - Facture électronique pour le Brésil (BR)** ou **NFS-e - Facture électronique pour le service (ville) pour le Brésil** et sélectionnez-la. Les données importées depuis ces systèmes externes vers ce service en ligne Dynamics 365 sont soumises à notre [déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=512132). Pour plus d’informations, consultez les sections Déclaration de confidentialité dans la documentation de la fonctionnalité spécifique au pays.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble du module complémentaire de facturation électronique](e-invoicing-service-overview.md)
- [Mise en route de l’administration du service du module complémentaire de facturation électronique](e-invoicing-get-started-service-administration.md)
- [Prise en main du module complémentaire de facturation électronique](e-invoicing-get-started.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
