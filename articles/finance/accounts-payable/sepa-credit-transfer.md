---
title: Vue d’ensemble des virements SEPA
description: Cet article fournit des informations générales sur les virements ISO 20022, notamment les virements SEPA (Single Euro Payments Area) et tous les autres moyens de paiement électronique des fournisseurs. Le virement SEPA est un type particulier de paiement en euros d’une société ou d’une personne à une société ou une autre personne. Cette rubrique explique également comment paramétrer et transmettre un fichier de paiement par virement.
author: sunfzam
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "11124"
- intro-internal
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fc37dde8829abdd26a224adbd788538834f4d320
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7984025"
---
# <a name="sepa-credit-transfer-overview"></a>Vue d’ensemble des virements SEPA

[!include [banner](../includes/banner.md)]

Cet article fournit des informations générales sur les virements ISO 20022, notamment les virements SEPA (Single Euro Payments Area) et tous les autres moyens de paiement électronique des fournisseurs. Le virement SEPA est un type particulier de paiement en euros d’une société ou d’une personne à une société ou une autre personne. Cette rubrique explique également comment paramétrer et transmettre un fichier de paiement par virement.

## <a name="what-is-a-credit-transfer-message"></a>Qu’est-ce qu’un message de virement ?
Le message de virement est une demande qu’une partie initiatrice (votre société) envoie pour déplacer des fonds depuis son propre compte vers celui d’un créditeur. Il existe de nombreuses implémentations des messages de virement, spécifiques à chaque banque et à chaque pays ou région. Certains d’entre elles sont utilisés au sein d’une pays ou d’une région, et d’autres sont en passe de devenir la norme. Une norme bien établie au niveau mondial est la norme ISO 20022 et ses messages d’initiation, tels que le Virement. L’illustration suivante présente les relations et la couverture des messages de virement sélectionnés. 
![Virement.](./media/credit-transfer.jpg) Messages de virement 

## <a name="what-are-iso-20022-and-sepa-payments"></a>Que sont les paiements ISO 20022 et SEPA ?
L’Espace unique de paiement en euro (SEPA) est défini par la Commission européenne et stipule que tous les paiements électroniques sont considérés comme locaux, quel que soit le pays/la région où la personne, l’entreprise ou l’organisation et la banque sont localisées. Il n’existe aucune différence entre les paiements nationaux et transfrontières. Le SEPA inclut les 28 états membres de l’Union européenne (EU), plus l’Islande, le Liechtenstein, la Norvège, la Suisse, Monaco et San Marin. Le SEPA permet de former un marché unique pour les transactions de paiement dans l’Espace économique européen. Enfin, le SEPA est supposé réduire le nombre de formats de paiement pour les banques, les entreprises et les personnes. La Commission européenne a établi les fondements légaux des paiements SEPA dans la Directive sur les Services de Paiement (PSD, Payment Services Directive). Le Conseil européen des paiements (EPC) assure le fonctionnement du SEPA par les activités suivantes :

-   il fixe les normes pour les paiements électroniques SEPA à l’aide du format XML ISO 20022 Schéma universel de messages pour l’industrie financière ;
-   il établit les règles et les instructions relatives sur la gestion des paiements en euro.

L’EPC, qui est constitué de banques européennes, développe les infrastructures commerciales et techniques pour les instruments de paiement SEPA. Trois types de paiements SEPA sont utilisés :

-   les virements ;
-   les prélèvements.
-   Cartes

## <a name="what-is-a-sepa-credit-transfer"></a>Qu’est-ce qu’un virement SEPA ?
Le virement SEPA est un paiement d’une société ou d’une personne à une société ou une autre personne. Les paiements doivent être en euro, et doivent inclure le numéro de compte international (IBAN) et le code d’identificateur de la banque (BIC, Bank Identifier Code) pour les deux parties. (Le code BIC est également appelé SWIFT Society for Worldwide Interbank Financial Telecommunication \[SWIFT\].) En outre, les coûts des transactions doivent être partagés entre les deux parties. Les virements bancaires qui surviennent entre les pièces doivent utiliser des fichiers XML conformes aux normes de traitement des paiements ISO 20022 et au format XML, tels qu’ils sont spécifiés par le CEP.

## <a name="how-is-a-credit-transfer-implemented"></a>Comment est implémenté un virement ?
Le format de virement pour les pays européens est implémenté à l’aide de la fonctionnalité Génération d’états électroniques (ER) et de modes de paiement dans Microsoft Dynamics 365 Finance. Quelques formats de virement utilisés dans d’autres régions utilisent toujours l’ancienne structure de paiement. Parmi de nombreux autres formats, il existe douze formats de virement ISO 20022 disponibles. Ces formats d’exportation sont conformes à la norme SEPA ISO 20022 XML. Ils sont utilisés pour générer des transferts de paiement non en euros pour les pays ou régions où ils sont utilisés et des paiements en euros comme spécifié dans la version 8.2 du Règlement des schémas de virement SEPA publié par l’EPC. Avant de pouvoir implémenter les virements, vous devez contacter votre banque pour obtenir le logiciel requis afin de télécharger les fichiers d’opérations bancaires électroniques. Vous l’utiliserez pour transférer les fichiers XML contenant les ordres de paiement à votre banque.

## <a name="what-credit-transfer-formats-are-currently-supported"></a>Quels formats de transfert de crédit sont actuellement pris en charge ?
Vous devez toujours aller dans la bibliothèque d’actifs partagés de Microsoft Dynamics Lifecycle Services (LCS) et afficher la liste la plus récente des fichiers disponibles dont le type d’actif est **Configuration GER**. La section suivante, « Que je dois paramétrer ? », fournit un lien vers une rubrique qui explique comment créer un référentiel LCS pour examiner les configurations disponibles et importer les configurations sélectionnées.

## <a name="what-do-i-have-to-set-up"></a>Que dois-je paramétrer ?
-   Avant de créer des de virement, vous devez importer au moins une configuration de virement active dans vos configurations ER. Pour plus d’instructions, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   Quand vous configurez les modes de paiement de la comptabilité fournisseur, cochez la case **États électroniques génériques** et sélectionnez le format de virement approprié (par exemple, **Virement ISO 20022 (AT)**) comme configuration de format d’exportation.
-   Vous devez également paramétrer l’entité juridique et les informations de compte bancaire.
-   Les numéros de compte bancaire, IBAN, est parfois les codes SWIFT (BIC) ou d’autres identifiants sont nécessaires pour créer des paiements valides par virement. Par conséquent, vous devez les paramétrer pour le compte bancaire fournisseur et le compte bancaire de l’organisation qui demande le virement.
-   D’autres informations peuvent être demandées, comme les numéros de TVA pour les parties qui sont mentionnées dans le message de virement. Ces informations doivent être paramétrée pour les fournisseurs et pour l’entité juridique lorsqu’elles sont demandées.
-   Certains modes de paiement de la comptabilité fournisseur, pour la plupart des modes de paiement fondés sur la norme ISO 20022, nécessitent un paramétrage supplémentaire pour les **Ensembles de codes de format de paiement**, tels que **Type de service** = **SLEV**. Ces codes sont utilisés comme référence supplémentaires pour les transactions de paiement lors de leur traitement. Les valeurs par défaut des codes de paiement, comme **Objectif de la catégorie**, **Entité prenant en charge les frais**, **Instrument local** et **Niveau de service** peuvent être définies à deux endroits. Le premier est l’**En-tête du journal des paiements de la comptabilité fournisseur** et le second est **Modes de paiement de la comptabilité fournisseur**. À la création des lignes de journal des paiements, les valeurs du code de paiement définies dans l’en-tête du journal des paiements sont transférées vers une ligne de journal. Si elles ne sont pas définies, les valeurs issues des Modes de paiement sont utilisées.

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>Quels sont les paramètres disponibles pour générer les paiements par virement ?
La liste des paramètres spécifiques dépend du format de virement. Le tableau suivant répertorie les paramètres disponibles lorsque vous générez un fichier de virement ISO 20022 pour l’Allemagne dans un journal des paiements fournisseur. À l’aide des options disponibles sous l’onglet **Exécuter à l’arrière-plan**, vous pouvez exécuter la génération de paiement en mode de traitement par lots.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Champ</th>
<th>description ;</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Réservation de traitement par lots</td>
<td>Activez cette case à cocher pour inclure la balise de réservation de traitement par lots dans le fichier XML.</td>
</tr>
<tr class="even">
<td>Date de traitement</td>
<td>Entrez la date à laquelle la banque doit traiter les paiements.</td>
</tr>
<tr class="odd">
<td>Format</td>
<td>Sélectionnez le format des informations de remise, selon les exigences de votre pays/région ou de votre banque :
<ul>
<li><strong>Strd</strong> – Sélectionnez cette option pour utiliser le format structuré lorsqu’une ligne de paiement est réglée par rapport à une facture. Cette option n’est pas disponible pour les formats d’exportation spécifiques de pays/région pour la France, l’Allemagne ou les Pays-Bas.</li>
<li><strong>Ustrd</strong> – Sélectionnez cette option pour utiliser le format non structuré lorsque le paiement est réglée par rapport à plusieurs factures. Les numéros de facture pour les factures réglées sont concaténés et utilisés comme informations de remise. Conformément aux directives des relevés ISO 20022, les informations de remise non structurée sont limitées à 140 caractères.</li>
</ul></td>
</tr>
<tr class="even">
<td>Nombre de factures</td>
<td>Entrez le nombre de factures à partir desquelles l’<strong>Avis de paiement</strong> est imprimé.</td>
</tr>
<tr class="odd">
<td>Souche de N°</td>
<td>Entrez un numéro de souche pour identifier le fichier. Le numéro de souche s’affiche dans l’état <strong>Note de participation</strong>.</td>
</tr>
<tr class="even">
<td>Imprimer une note de participation</td>
<td>Activez cette case à cocher pour imprimer l’état <strong>Note de participation</strong>.</td>
</tr>
<tr class="odd">
<td>Imprimer l’état de contrôle</td>
<td>Activez cette case à cocher pour imprimer un état contenant les informations de paiement.</td>
</tr>
<tr class="even">
<td>Imprimer la lettre explicative</td>
<td>Activez cette case à cocher pour imprimer l’état <strong>Avis de paiement</strong>.</td>
</tr>
</tbody>
</table>

## <a name="what-are-ibans-and-bics"></a>Que sont les codes IBAN et BIC ?
Le numéro de compte bancaire international (IBAN) et le code identificateur de banque (BIC) permettent d’identifier n’importe quel compte dans de nombreux pays ou régions du monde entier. Cela inclut les 34 pays ou régions SEPA. Entrez le code BIC dans le champ **Code SWIFT** et le code IBAN dans le champ **IBAN**. Pour le compte bancaire du créditeur et le compte bancaire du client, ces champs sont situés dans l’organisateur **Identification supplémentaires** sous l’onglet **Compte bancaire** dans la page **Comptes bancaires**. L’utilisation du code BIC pour les paiements SEPA n’est plus en vigueur.

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>Comment puis-je communiquer un fichier de paiement à la banque ?
Lorsque vous générez des paiements, le fichier de paiement est généré, et vous êtes invité à l’enregistrer de votre navigateur Web dans n’importe quel emplacement disponible. L’étape suivante consiste à envoyer le fichier XML à votre banque. Ce processus varie d’une banque à l’autre. Suivez les instructions de votre banque pour envoyer les fichiers à la banque aux fins de traitement.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
