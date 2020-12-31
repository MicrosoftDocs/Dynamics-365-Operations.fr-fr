---
title: Générer des écrans FTI imprimables
description: Cette rubrique explique comment utiliser la structure de gestion des états électroniques pour générer des écrans de facture financière imprimables (FTI) en tant que documents Microsoft Office.
author: NickSelin
manager: AnnBe
ms.date: 07/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 168cef1b5f5d48cb739b08fa395c1bcd62089494
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686725"
---
# <a name="generate-printable-fti-forms"></a>Générer des écrans FTI imprimables

[!include[banner](../includes/banner.md)]

La structure de gestion des états électroniques vous permet de générer des écrans de facture financière imprimables (FTI) en tant que documents Microsoft Office. Cette rubrique fournit des informations sur la procédure pour générer vos propres configurations ainsi que des détails sur les modèles de configuration disponibles.

## <a name="overview"></a>Vue d’ensemble

Outre la capacité existante de générer des écrans FTI imprimables à l’aide de SSRS (Microsoft SQL Server Reporting Services), vous pouvez désormais utiliser la structure de gestion des états électroniques. Vous pouvez gérer des écrans FTI imprimables dans Microsoft Office Excel et Word. Vous pouvez également modifier la mise en page, le flux de données, et la mise en forme pour satisfaire à des exigences spécifiques sans effectuer de modifications de code.

> [!NOTE]
> Si vous souhaitez démarrer par une vue d’ensemble des configurations de gestion d’états électroniques pour cet exemple de solution d’écrans FTI imprimable, vous pouvez accéder directement à la section **Télécharger des exemple de configurations de gestion d’états électroniques pour générer des écrans FTI imprimables** plus loin dans cette rubrique.

## <a name="create-customized-configurations-for-fti-printable-forms"></a>Créer des configurations personnalisées pour les écrans FTI imprimables
Dans le cadre de votre solution personnalisée pour écrans FTI imprimables, vous devez créer un ensemble de configurations de gestion des états électroniques.

### <a name="configure-the-er-data-model"></a>Configurer le modèle de données de gestion des états électroniques
Votre application doit inclure la configuration du modèle de données de gestion des états électroniques qui contient un modèle de données qui décrit le domaine d’affaires de facturation client. Le nom du modèle de données doit être obligatoirement **CustomersInvoicing**. Pour en savoir plus sur la manière de concevoir des modèles de données de gestion des états électroniques, voir [ER Concevoir un modèle de données spécifiques au domaine](tasks/er-design-domain-specific-data-model-2016-11.md).

### <a name="configure-the-er-model-mapping"></a>Configurer la mise en correspondance de modèle de gestion des états électroniques
Votre application doit inclure la mise en correspondance de modèle de gestion des états électroniques pour le modèle de données CustomersInvoicing. La mise en correspondance de modèle peut se faire dans la configuration du modèle de données de gestion des états électroniques ou dans la configuration de mise en correspondance de modèle de gestion des états électroniques. Toutefois, le nom du descripteur racine de la mise en correspondance du modèle doit être **FreeTextInvoice**.

La mise en correspondance doit contenir les sources de données suivantes :

- Type de source de données : **Enregistrements de la table**

    - Cette source de données doit être nommée **CustInvoiceJour**.
    - Elle doit faire référence à la table d’application CustInvoiceJour.
    - Elle est utilisée au moment de l’exécution pour passer de l’application au modèle de gestion des états électroniques mettant en correspondance la liste des factures sélectionnées pour l’impression.

- Type de source de données : **Objet**

    - Cette source de données doit être nommée **PrintMgmtPrintSettingDetail**.
    - Elle doit faire référence à la classe d’application **PrintMgmtPrintSettingDetail**.
    - Elle est utilisée au moment de l’exécution pour passer de l’application au modèle de gestion des états électroniques mettant en correspondance les détails des paramètres de gestion de l’impression pour le format de gestion des états électroniques qui s’exécute.

Les détails de l’intégration d’application dans la structure de gestion des états électroniques se trouvent dans la classe **ERPrintMgmtReportFormatSubscriber** (modèle d’intégration de la suite d’applications de la gestion des états électroniques) dans le code source de l’application.

Pour plus d’informations sur la conception des mises en correspondance de modèle de gestion des états électroniques, voir [Définir les mappages de modèles et sélectionner des sources de données pour la gestion des états électroniques](tasks/er-define-model-mapping-select-data-sources-2016-11.md).

### <a name="configure-the-er-format"></a>Configurer le format de gestion des états électroniques
Dans votre instance d’application, vous devez disposer de la configuration du format de gestion des états électroniques qui sera utilisée pour générer des écrans FTI. 

> [!NOTE]
> Cette configuration de format doit être créée pour le modèle de données CustomersInvoicing, et elle doit utiliser la mise en correspondance de modèle avec le descripteur racine **FreeTextInvoice**.

Pour plus d’informations sur la configuration des formats de gestion des états électroniques, voir [ER Créer une configuration de format pour la gestion des états électroniques (novembre 2016)](tasks/er-format-configuration-2016-11.md). Pour plus d’informations sur la procédure de conception des formats de gestion des états électroniques pour générer des états au format OpenXML, voir [Définir une configuration pour générer des états au format OPENXML pour la gestion des états électroniques (novembre 2016)](tasks/er-design-reports-openxml-2016-11.md).

## <a name="configure-print-management"></a>Configurer la gestion de l’impression
Pour générer des écrans FTI à l’aide de la structure de gestion des états électroniques, vous pouvez affecter les formats de gestion des états électroniques de la même manière que vous affectez des états SSRS. Pour associer le format de gestion des états électroniques à tous les FTI de Comptabilité client, accédez à **Comptabilité client** \> **Paramétrage** \> **Écrans** \> **Paramétrage d’écran** \> **Général** \> **Gestion de l’impression** \> **Facture financière** \> **Original**. Pour associer le formate de gestion des états électroniques à un client ou à une facture spécifique, procédez comme suit.

1. Allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.
2. Sélectionnez la FTI à associer au format de gestion des états électroniques, et ouvrez la page **Paramétrage de la gestion de l’impression**.
3. Sélectionnez le niveau de document pour spécifier la portée des factures aux fins de traitement.
4. Sélectionnez le format de gestion des états électroniques pour le niveau de document spécifié.

![Paramétrage de la gestion de l’impression](media/FTIbyGER-PMSetting.png)

> [!NOTE]
> Seuls les formats de gestion des états électroniques qui utilisent le descripteur racine **FreeTextInvoice** du modèle de données **CustomersInvoicing** figurent dans le champ **Recherche de format d’état** pour le format sélectionné.

## <a name="generate-fti-forms"></a>Générer des écrans FTI
Les écrans FTI sont générés dans la structure de gestion des états électroniques de la même manière que les états SSRS sont générés.

Pour générer des écrans FTI, vous pouvez sélectionner des factures par plage ou par sélection. 

![Sélection de la facture](media/FTIbyGER-InvoiceSelection.png)

![Aperçu de la facture](media/FTIbyGER-InvoiceExcelPreview.png)

Lorsque vous utilisez des formats de gestion des états électroniques pour imprimer des écrans FTI de cette manière, les destinations de fichier de gestion des états électroniques par défaut sont utilisées. Vous ne pouvez pas modifier la destination. Pour plus d’informations sur la configuration des destinations de gestion des états électroniques pour les formats de gestion des états électroniques, voir [Destinations pour la gestion des états électroniques](electronic-reporting-destinations.md).

Vous pouvez également générer des écrans FTI lorsque vous validez une FTI, en activant **Imprimer la facture** et en désactivant **Utilisez la destination de la gestion de l’impression**.

> [!NOTE]
> Lorsque vous utilisez des formats de gestion des états électroniques pour imprimer des écrans FTI de cette manière, les destinations de fichier de gestion des états électroniques par défaut sont utilisées. Vous pouvez modifier la destination par défaut au moment de l’exécution si la destination a déjà été configurée. Pour modifier la destination, vous devez disposer du privilège de sécurité suivant :
>
> - **Nom :** ERFormatDestinationRuntimeMaintain
> - **Libellé :** Mettre à jour la destination du format de gestion des états électroniques durant l’exécution

![Destination de la gestion des états électroniques](media/FTIbyGER-ERFileDestinationSetting.png)

![Destination du format de gestion des états électroniques](media/FTIbyGER-ERFileDestinationUsage.png)

La structure de gestion des états électroniques prend en charge actuellement les destinations suivantes pour les documents générés :

- **Fichier téléchargé** – Les écrans générés sont proposés en tant que téléchargements que vous pouvez enregistrer à l’aide du navigateur.
- **Écran** – Microsoft 365 Excel est utilisé pour afficher un aperçu des écrans FTI générés au format Excel.
- **Dossier SharePoint** – Les écrans générés sont stockés selon les paramètres de la structure de gestion des documents.
- **Archives d’application** – Les écrans générés sont stockés en tant que pièces jointes des enregistrements de journal d’exécution dans le stockage Microsoft Azure.
- **E-mail** – Les écrans générés sont envoyés en tant que pièces jointes.

> [!NOTE]
> Vous ne pouvez pas envoyer les écrans FTI générés directement à l’imprimante, car l’impression directe utilisant l’agent d’acheminement d’impression Dynamics n’est actuellement pas prise en charge.

## <a name="download-sample-er-configurations-to-generate-printable-fti-forms"></a>Télécharger des exemple de configurations de gestion d’états électroniques pour générer des écrans FTI imprimables
Vous pouvez télécharger des exemples de configurations de gestion d’états électroniques à utiliser comme modèle pour votre solution FTI. Les configurations sont stockées dans la bibliothèque d’actif partagé de Microsoft Dynamics Lifecycle Services (LCS). Les configurations incluent :

- La configuration **Modèle de facturation client** contient la mise en correspondance requise du modèle de données et du modèle.
- La configuration **État FTI client (GER)** contient l’exemple de format.

> [!NOTE]
> Ces configurations ont été créées comme des exemples pour aider à clarifier les scénarios possibles. Le futur de ces configurations dépend des résultats de cette évaluation et de tout commentaire reçu.

### <a name="features-that-are-implemented-in-the-sample-er-format"></a>Fonctionnalités implémentées dans l’exemple de format de gestion d’états électroniques
Dans l’exemple de configuration du format de gestion d’états électroniques, un fichier Excel est utilisé comme modèle pour générer des écrans FTI.

![Concepteur de formats](media/FTIbyGER-ERFormat.png)

Actuellement, cet exemple de format de gestion d’états électroniques prend en charge les fonctionnalités suivantes pour générer des écrans FTI :

- Les écrans FTI sont générés pour des factures originales validées et des factures originales pas encore validées. Les factures et les avoirs corrigés ne sont pas pris en charge.
- Les écrans FTI sont générés dans la langue de la facture. Le format des valeurs et des dates des écrans générés dépend des paramètres du paramètre régional du client de l’utilisateur.
- Les factures générées affichent des notifications d’indisponibilité des données s’il n’existe aucune ligne dans les factures traitées.
- Les en-têtes de facture générées sont basés sur le format de papier sélectionné pour l’écran FTI sur la page **Paramètres de la Comptabilité client**. Les détails de la société s’affichent dans l’en-tête de l’écran de facture généré uniquement si le format de papier est vide.
- Les écrans de facture générés affichent les numéros d’exonération fiscale de la société et du client lorsque l’option appropriée a été activée pour l’écran FTI sur la page **Paramètres de la Comptabilité client**.
- Les sections de lignes de facture et de totaux de facture générés affichent les détails monétaires de la facture par défaut dans la devise d’enregistrement de la facture.
- La section des totaux de facture générée peut afficher les détails monétaires en euros et la devise d’enregistrement de facture lorsque l’option **Imprimer le montant dans la devise représentant l’euro** est activée sur la page **Paramètres de la Comptabilité client**.
- Les écrans de facture générés affichent toutes les notes de traitement de facture disponibles, selon les paramètres de la page **Paramètres de la Comptabilité client**. Les notes sont incluses dans la facture entière et à chaque ligne de facture.
- Les écrans de facture générés incluent des notes pour l’écran FTI du client et la langue de traitement de la facture lorsqu’elles ont été configurées dans la liste des notes d’écran de Comptabilité client.
- En fonction des paramètres de gestion de l’impression, les factures générées incluent un texte de pied de page personnalisé lorsqu’il a été configuré pour la langue de la facture, le format de gestion d’états électroniques, et la portée du document FTI.
- La section des totaux des écrans de facture générés inclut toutes les informations d’escompte de règlement disponibles.
- La section d’échéancier de paiement des écrans de facture générés inclut tous les détails de l’échéancier de paiement disponibles.
- La section de majoration des écrans de facture générés inclut toutes les transactions de frais disponibles.
- Les écrans de facture générés incluent les détails de taxe, selon le paramètre **Spécification de taxe** sur la page **Paramètres de la Comptabilité client**. Cette section peut afficher les détails de taxe dans la devise d’enregistrement de la facture uniquement, ou dans la devise d’enregistrement de la facture et dans la devise comptable de la société en même temps.
- Les écrans de facture générés affichent les détails sur la notification de débit direct. Par exemple, ils affichent quand le mode de paiement avec un ID de mandat de débit direct obligatoire a été sélectionné pour la facture, quand la traitement de facture a été enregistré dans la devise euro et, quand l’ID de mandat de débit direct a été défini pour la facture.
- Les factures générées affichent tous détails sur l’acompte disponibles pour les factures validées.
- Les écrans de facture générés peuvent être envoyés à un client d’une facture comme pièce jointe. La destination du fichier de gestion d’états électroniques appropriée doit être configurée pour le format de gestion d’états électroniques utilisé.

### <a name="countryregion-specific-features"></a>Fonctions spécifiques à un pays/une région 
Les fonctionnalités spécifiques au pays/à la région sont incluses dans l’exemple de format de gestion d’états électroniques pour afficher la manière dont les besoins spécifiques peuvent être traités dans des configurations de gestion d’états électroniques.

#### <a name="norway"></a>Norvège
Le terme Registre de la société est placé dans l’en-tête de l’écran de facture généré lorsque la facture est traitée pour une entité juridique configurée de la façon suivante :

- Le contexte de pays/région pour la Norvège est utilisé.
- Le paramètre **Imprimer Foretaksregisteret** est actif sur les documents de vente.

#### <a name="spain"></a>Espagne
Le terme **Régime spécial pour la méthode de comptabilité des disponibilités** est placé dans l’en-tête de l’écran de facture généré lorsque la facture est traitée pour une entité juridique configurée de la façon suivante :

- Le contexte de pays/région pour l’Espagne est utilisé.
- Le régime spécial pour la méthode de comptabilité avec disponibilités est activé à la date de traitement de la facture.

Lorsque les détails d’escompte de règlement, tels que le montant de l’escompte de règlement et le montant net de la ligne de facture, sont disponibles, ils sont présentés dans la section des totaux de la facture de l’écran de facture généré lors de son exécution pour une entité juridique configurée de la façon suivante :

- Le contexte de pays/région pour l’Espagne est utilisé.
- **L’escompte de règlement est appliqué dans la facture** est activé dans l’option de facture (**Paramètres de comptabilité** \> **Section de taxe**).

#### <a name="italy"></a>Italie
La marque de remise sur marchandises est incluse dans les lignes de facture de la facture générée lorsqu’elle est traitée pour une entité juridique configurée à l’aide du contexte de pays/région pour l’Italie.

#### <a name="finland"></a>Finlande
Outre l’écran de facture généré, des bordereaux de transfert d’argent peuvent être générés comme suit :

- Pour l’entité juridique utilisant le contexte de pays/région pour la Finlande, et disposant d’au moins un compte bancaire marqué comme **Compte de virement** et **Code-barres de la banque**. 
- Pour une facture marquée comme étant obligatoire pour le document de paiement joint associé au **Finnois**.

![Bordereau de virement](media/FTIbyGER-GiroSlip.PNG)

> [!NOTE]
> L’exemple de format de gestion des états électroniques a été configuré pour générer éventuellement des bordereaux de transfert d’argent dans la feuille de calcul distincte.

> [!NOTE]
> Vous devez d’abord installer la police utilisée pour générer le code-barres sur l’ordinateur local où l’écran de facture généré au format Excel sera prévisualisé.

### <a name="use-the-sample-er-format-to-configure-email-destinations"></a>Utilisez l’exemple de format de gestion des états électroniques pour configurer les destinations d’e-mail
Utilisez les éléments de l’exemple de format de gestion des états électroniques suivants pour configurer les destinations d’e-mail :

- L’adresse e-mail d’un contact client est accessible via l’expression de gestion des états électroniques suivante : **model.InvoiceBase.Contact.ElectronicMail**.
- Le texte de l’objet de l’e-mail est accessible via l’expression de gestion des états électroniques suivante : **Emailing.TxtToUse.Subject**.
- Le texte du corps de l’e-mail est accessible via l’expression de gestion des états électroniques suivante : **Emailing.TxtToUse.Body**.

![Paramètres de destination](media/FTIbyGER-ERFileDestinationSettingEmail.png)

Le texte par défaut de l’objet et du corps de l’e-mail est défini dans l’exemple de format de gestion des états électroniques. La langue dépend des libellés du format. Ce texte par défaut sera utilisé pour les e-mails si un modèle d’e-mail d’organisation personnalisé avec l’ID **ERFTITMP** prédéfini n’a pas été ajouté.

> [!NOTE]
> L’ID de modèle d’e-mail **ERFTITMP** a été défini dans l’exemple de format de gestion des états électroniques. Il peut être remplacé au besoin par un nouveau format de gestion des états électroniques créé à partir de cet exemple de format.

Si le modèle d’e-mail d’organisation ayant l’ID **ERFTITMP** prédéfini a été ajouté pour l’entité juridique pour laquelle vous traitez la facture, le modèle du texte du sujet et du corps de l’e-mail sera utilisé pour générer l’e-mail. 

![Modèles d’e-mail d’organisation](media/FTIbyGER-EmailTemplate.png)

![Télécharger le modèle d’e-mail](media/FTIbyGER-EmailTemplateBody.png)

L’expression de gestion des états électroniques **Emailing.TxtToUse.Subject** de l’exemple de format de gestion des états électroniques est configurée pour remplacer toutes les occurrences de l’espace réservé %1 par l’ID de traitement de la facture.

L’expression **Emailing.TxtToUse.Body** de l’exemple de format est configurée pour les substitutions suivantes des espaces réservés :

- « %1 » est remplacé par le nom de la personne à contacter chez le client.
- « %2 » est remplacé par le nom de la société.
- « %3 » est remplacé par le nom du client.
- « %4 » est remplacé par le nom de la personne à contacter dans la société.
- « %5 » est remplacé par la fonction de la personne à contacter dans la société.
- « %6 » est remplacé par l’adresse e-mail de la personne à contacter dans la société.

![Courrier électronique](media/FTIbyGER-Email.PNG)

## <a name="additional-resources"></a>Ressources supplémentaires
[Vue d’ensemble des états électroniques (ER)](general-electronic-reporting.md)
