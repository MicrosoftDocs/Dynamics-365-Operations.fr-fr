---
title: Mise en route de la Facturation électronique pour le Brésil
description: Cette rubrique donne des informations qui vous aideront à démarrer la Facturation électronique pour le Brésil dans Finance et Supply Chain Management.
author: gionoder
ms.date: 03/29/2021
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
ms.openlocfilehash: fd37c98b64e6074d54b40e20f87f24912abcdd75575aa92e1e2b7345d3cce5a5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730475"
---
# <a name="get-started-with-electronic-invoicing-for-brazil"></a>Mise en route de la Facturation électronique pour le Brésil 

[!include [banner](../includes/banner.md)]

Cette rubrique donne des informations qui vous aideront à démarrer la Facturation électronique pour le Brésil. La rubrique vous guide tout au long des étapes de configuration qui dépendent du pays dans Regulatory Configuration Services (RCS) et complètent les étapes décrites dans la rubrique [Mise en route de la Facturation électronique](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Configuration spécifique au pays pour la fonctionnalité de Facturation électronique NF-e (BR) pour le Brésil

Certains des paramètres de la **Fonctionnalité de Facturation électronique NF-e (BR) pour le Brésil** sont publiés avec des valeurs par défaut. Passez en revue les valeurs et, si nécessaire, mettez à jour les valeurs pour mieux répondre aux besoins de votre entreprise avant de déployer la fonctionnalité de Facturation électronique dans l’environnement de service.

Cette section complète la section **Configuration spécifique au pays pour la fonctionnalité de Facturation électronique** de la rubrique [Mise en route de la Facturation électronique](e-invoicing-get-started.md).

1. Dans RCS, dans la section **Fonctionnalités** de l’espace de travail **Fonctionnalité de globalisation**, sélectionnez la vignette **Facturation électronique**.
2. Sur la page **Fonctionnalités de Facturation électronique**, vérifiez que la fonctionnalité de Facturation électronique **NF-e (BR) pour le Brésil** que vous avez créée est sélectionnée.
3. Sur l’onglet **Versions**, vérifiez que la version **Brouillon** est sélectionnée.
4. Sur l’onglet **Paramétrages**, sélectionnez **Soumettre** dans la grille, puis sélectionnez **Modifier**.
5. Sur l’onglet **Actions**, dans le groupe de champs **Actions**, sélectionnez l’action **(Aperçu) Signer le document XML**.
6. Dans le groupe de champs **Paramètres**, sélectionnez **Nom du certificat** et, dans le champ **Valeur**, entrez le nom du certificat associé à votre paramètre de coffre de clés.
7. Sur l’onglet **Actions**, dans le groupe de champs **Actions**, sélectionnez l’action **(Aperçu) Appeler le service SEFAZ brésilien**.
8. Dans le groupe de champs **Paramètres**, sélectionnez le paramètre **Adresse URL**.
9. Dans le champ **Valeur**, si nécessaire, vérifiez et mettez à jour l’URL des services web publiés par la documentation SEFAZ pour votre état, puis sélectionnez **Enregistrer**.
10. Sur l’onglet **Règles d’applicabilité**, dans le groupe de champs **Configuration de la règle d’applicabilité**, vérifiez et mettez à jour le critère du champ **État** comme il se doit pour le même état auquel l’URL des services web fait référence.
11. Cliquez sur **Enregistrer**, puis fermez la page.
12. Pour déployer la fonctionnalité de facturation électronique dans l’environnement de service, voir [Prise en main de la Facturation électronique](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Configuration spécifique au pays du paramétrage de l’application pour la fonctionnalité de Facturation électronique NF-e (BR) pour le Brésil

Effectuez ces étapes avant de déployer la configuration de l’application sur votre application connectée Finance ou Supply Chain Management.

Cette section complète la section **Configuration du paramétrage de l’application spécifique au pays** de la rubrique [Mise en route de la Facturation électronique](e-invoicing-get-started.md).

1. Dans RCS, dans la section **Fonctionnalités** de l’espace de travail **Fonctionnalité de globalisation**, sélectionnez la vignette *Facturation électronique*.
2. Sur la page **Fonctionnalités de Facturation électronique**, vérifiez que la fonctionnalité de Facturation électronique **NF-e (BR) pour le Brésil** est sélectionnée.
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
13. Pour déployer le paramétrage de l’application sur l’application connectée Finance ou Supply Chain Management, voir [Mise en route de la Facturation électronique](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Configuration spécifique au pays pour la fonctionnalité de Facturation électronique NFS-e ABRASF Curitiba (BR) pour le Brésil

Certains des paramètres de la **Fonctionnalité de Facturation électronique NFS-e ABRASF Curitiba (BR) pour le Brésil** sont publiés avec des valeurs par défaut. Passez en revue et, si nécessaire, mettez à jour les valeurs pour mieux répondre aux besoins de votre entreprise avant de déployer la fonctionnalité de Facturation électronique dans l’environnement de service.

Cette section complète la section **Configuration spécifique au pays pour la fonctionnalité de Facturation électronique** de la rubrique [Mise en route de la Facturation électronique](e-invoicing-get-started.md).

1. Dans RCS, dans la section **Fonctionnalités** de l’espace de travail **Fonctionnalité de globalisation**, sélectionnez la vignette **Facturation électronique**.
2. Sur la page **Fonctionnalités de Facturation électronique**, vérifiez que la fonctionnalité de Facturation électronique **NFS-e ABRASF Curitiba (BR) pour le Brésil** que vous avez créée est sélectionnée.
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
18. Pour déployer la fonctionnalité de facturation électronique dans l’environnement de service, voir [Prise en main de la Facturation électronique](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Configuration spécifique au pays du paramétrage de l’application pour la fonctionnalité de facturation électronique NFS-e ABRASF Curitiba (BR) pour le Brésil

Effectuez ces étapes avant de déployer la configuration de l’application sur votre application connectée Finance ou Supply Chain Management.

Cette section complète la section **Configuration du paramétrage de l’application spécifique au pays** de la rubrique [Mise en route de la Facturation électronique](e-invoicing-get-started.md).

1. Dans RCS, dans la section **Fonctionnalités** de l’espace de travail **Fonctionnalité de globalisation**, sélectionnez la vignette **Facturation électronique**.
2. Sur la page **Fonctionnalités de Facturation électronique**, vérifiez que la fonctionnalité de Facturation électronique **NFS-e ABRASF Curitiba (BR) pour le Brésil** est sélectionnée.
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
16. Cliquez sur **Enregistrer**, puis fermez la page.
17. Pour déployer le paramétrage de l’application sur l’application connectée Finance ou Supply Chain Management, voir [Mise en route de la Facturation électronique](e-invoicing-get-started.md).

## <a name="privacy-notice"></a>Avis de confidentialité
L’activation des fonctionnalités **NF-e Federal – Facture électronique pour le Brésil (BR)** et **NFS-e – Facture électronique pour le service (ville) pour le Brésil** peut nécessiter l’envoi de données limitées, y compris l’ID d’enregistrement fiscal de l’organisation. Ces données sont transmises à des organismes tiers autorisés par l’administration fiscale aux fins d’envoi de factures électroniques à cette administration fiscale dans le format prédéfini requis pour l’intégration avec le service web du gouvernement. En tant qu’administrateur, vous pouvez activer ou désactiver les fonctionnalités **NF-e Federal – Facture électronique pour le Brésil (BR)** et **NFS-e – Facture électronique pour le service (ville) pour le Brésil**. Les étapes suivantes vous indiquent comment procéder : 

1. Accédez à **Administration de l’organisation** > **Paramétrage** > **Paramètres des documents électroniques**. 
2. Sur l’onglet **Fonctionnalités**, sélectionnez la ligne qui contient la fonctionnalité **NF-e Federal – Facture électronique pour le Brésil (BR)** ou **NFS-e – Facture électronique pour le service (ville) pour le Brésil** et sélectionnez-la. Les données importées depuis ces systèmes externes vers ce service en ligne Dynamics 365 sont soumises à notre [déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=512132). Pour plus d’informations, consultez les sections Déclaration de confidentialité dans la documentation de la fonctionnalité spécifique au pays.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble de la Facturation électronique](e-invoicing-service-overview.md)
- [Mise en route de l’administration du service de Facturation électronique](e-invoicing-get-started-service-administration.md)
- [Mise en route de la Facturation électronique](e-invoicing-get-started.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
