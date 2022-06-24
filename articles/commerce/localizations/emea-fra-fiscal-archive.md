---
title: Archives fiscales pour la France
description: Cet article fournit des informations sur les archives fiscales et l’outil de vérification de l’intégrité des archives fiscales qui sont disponibles dans la localisation de Microsoft Dynamics 365 Commerce pour la France.
author: EvgenyPopovMBS
manager: annbe
ms.date: 05/17/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailGrandTotalJournalTable
audience: Application User
ms.reviewer: v-chgri
ms.search.region: France
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2021-2-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8aacb21788d85d256c64e64117af112a16085445
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885420"
---
# <a name="fiscal-archive-for-france"></a>Archives fiscales pour la France

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur les archives fiscales et l’outil de vérification de l’intégrité des archives fiscales qui sont disponibles dans la localisation de Microsoft Dynamics 365 Commerce pour la France. L’archive fiscale fait partie de la [fonctionnalité de caisse enregistreuse pour la France](./emea-fra-cash-registers.md).

Une archive fiscale est un fichier XML qui contient les données de vente d’un magasin et d’une période fiscale. Elle comprend les totaux de la période clôturée, et des données détaillées sur les transactions de vente et les événements.

Une archive fiscale peut être exportée à partir d’un journal de total général de période clôturée. (Pour plus d’informations sur l’utilisation des journaux de total général de période, voir [Journal du total général de la période](./emea-fra-cash-registers.md#period-grand-total-journal) .) Le fichier XML d’archive fiscale exporté est signé numériquement et la signature numérique est contenue dans un fichier séparé. Les archives fiscales exportées doivent être conservées sur des supports externes sécurisés pendant la durée légale de conservation.

Vous pouvez vérifier l’intégrité de l’archive fiscale et de ses données en utilisant l’[Outil de vérification de l’intégrité des archives fiscales](#fiscal-archive-integrity-verification-tool).

Le format XML de l’archive fiscale est implémenté à l’aide de la [gestion des états électroniques (ER)](../../dev-itpro/analytics/general-electronic-reporting.md). Pour plus d’informations sur l’importation et l’application des configurations ER requises pour exporter les archives fiscales, consultez [Configurer les formats d’exportation des archives et des Z de caisse](./emea-fra-cash-registers.md#configure-the-z-report-and-archive-export-formats).

## <a name="fiscal-archive-structure"></a>Structure des archives fiscales

Une archive fiscale a la structure suivante.

``` xml
<AchivePeriod> <!-- The identification of the period of the archive and the archive creation date. -->
    <Company/> <!-- The identification of the company, including the SIRET code, the NAF code, and the VAT ID of the company. -->
    <Store/> <!-- The identification of the store, including its address. -->
    <PeriodGrandTotal/> <!-- The data of the period grand total journal that the archive was exported from. -->
    <Shifts/> <!-- A collection of all shifts that were closed in the store during the period of the archive. -->
        <Shift/> <!-- The data of a shift. -->
    <Receipts/> <!-- A collection of all sales receipts that were registered in the shifts included in the archive. -->
        <Receipt/> <!-- The data of a sales receipt. -->
    <ReceiptCopies/> <!-- A collection of all sales receipt copies that were printed in the shifts included in the archive. -->
        <ReceiptCopy> <!-- The data of a sales receipt copy. -->
    <AuditEvents> <!-- A collection of all signed audit events that were registered in the shifts included in the archive. -->
        <AuditEvent/> <!-- The data of a signed audit event. -->
```

### <a name="periodgrandtotal-node"></a>Nœud PeriodGrandTotal

Le nœud **PeriodGrandTotal** d’une archive fiscale contient les éléments suivants.

| Élément/nœud                     | Commentaire |
|----------------------------------|---------|
| SequentialNumber                 | Numéro séquentiel du journal du total général de la période signée pour le magasin. |
| FromDate                         | Date de début de la période du journal. |
| ToDate                           | Date de fin de la période du journal. |
| TotalCashSales                   | Montant total des ventes, taxes comprises, pour la période. |
| TotalCashReturns                 | Valeur absolue du montant total des retours, taxes comprises, pour la période. |
| GrandTotal                       | Montant total des ventes, taxes comprises, moins la valeur absolue du montant total des retours, taxes comprises, pour la période. |
| PerpetualGrandTotal              | Total général perpétuel cumulé pour la période. Autrement dit, le total général perpétuel cumulé de la période précédente, plus le montant total des ventes TTC de la période, moins la valeur absolue du montant total des retours TTC de la période. |
| PerpetualGrandTotalAbsoluteValue | Le total général perpétuel cumulé (valeur absolue) pour la période. Autrement dit, le total général perpétuel cumulé (valeur absolue) de la période précédente, plus le montant total des ventes TTC de la période, plus la valeur absolue du montant total des retours TTC de la période. |
| PeriodGrandTotalLines            | Collection de montants totaux généraux par taux d’imposition. |
| PeriodGrandTotalLine             | Nœud pour le montant total général d’un taux d’imposition. |
| TotalInclTax                     | Montant total général d’un taux d’imposition pour la période. |
| TaxRate                          | Taux d’imposition. |
| TaxAmount                        | Montant total général d’une taxe pour le taux d’imposition. |
| DataToSign                       | Chaîne [créée à partir des éléments de l’enregistrement du journal du total général de la période](./emea-fra-cash-registers.md#period-grand-total-journal) et utilisée pour la signature. |
| DataToSignFormatVersion          | Version interne du format de données qui a été utilisé pour la signature. |
| Signature                        | Signature numérique de l’enregistrement du journal du total général de la période. |
| HashAlgorithm                    | Algorithme de code de hachage utilisé pour hacher les données avant signature. |
| CertificateThumbprint            | Empreinte numérique du certificat utilisée pour la signature. |

### <a name="shift-node"></a>Shift node

Nœud **Shift** d’une archive fiscale contient les éléments suivants.

| Élément/nœud                     | Commentaire |
|----------------------------------|---------|
| RegisterNumber                   | Identification du registre sur lequel l’équipe a été ouverte. |
| Date                             | Date de l’équipe. |
| TotalCashSales                   | Montant total des ventes, taxes comprises, pour l’équipe. |
| TotalCashReturns                 | Valeur absolue du montant total des retours, taxes comprises, pour l’équipe. |
| GrandTotal                       | Montant total des ventes, taxes comprises, moins la valeur absolue du montant total des retours, taxes comprises, pour l’équipe. |
| PerpetualGrandTotal              | Total général perpétuel cumulé pour l’équipe. Autrement dit, le total général perpétuel cumulé de l’équipe précédente du même registre, plus le montant total des ventes TTC pour l’équipe, moins la valeur absolue du montant total des retours TTC de l’équipe. |
| PerpetualGrandTotalAbsoluteValue | Total général perpétuel cumulé pour l’équipe. Autrement dit, le total général perpétuel cumulé de l’équipe précédente du même registre, plus le montant total des ventes TTC pour l’équipe, plus la valeur absolue du montant total des retours TTC de l’équipe. |
| ShiftLines                       | Collection de montants totaux généraux par taux d’imposition. |
| ShiftLine                        | Nœud pour le montant total général d’un taux d’imposition. |
| TotalInclTax                     | Montant total général d’un taux d’imposition pour l’équipe. |
| TaxRate                          | Taux d’imposition. |
| TaxAmount                        | Montant total général d’une taxe pour le taux d’imposition. |
| SequentialNumber                 | Numéro séquentiel de l’équipe ayant signé pour le registre. |
| DataToSign                       | Chaîne [créée à partir des éléments de l’enregistrement de l’équipe](./emea-fra-cash-registers.md#digital-signing-of-closed-shifts) et utilisée pour la signature. |
| DataToSignFormatVersion          | Version interne du format de données qui a été utilisé pour la signature. |
| Signature                        | Signature numérique de l’enregistrement de l’équipe. |
| HashAlgorithm                    | Algorithme de code de hachage utilisé pour hacher les données avant signature. |
| CertificateThumbprint            | Empreinte numérique du certificat utilisée pour la signature. |

### <a name="receipt-node"></a>Receipt node

Nœud **Receipt** d’une archive fiscale contient les éléments suivants.

| Élément/nœud            | Commentaire |
|-------------------------|---------|
| AppVersion              | Identification de la version du logiciel de caisse utilisé pour émettre le ticket de caisse. |
| Date                    | Date et heure du ticket de caisse, au format AAAAMMJJHHMMSS. |
| NumberOfCopies          | Nombre de fois qu’une copie a été imprimée pour le ticket de caisse. |
| OperatorCode            | Code de l’opérateur ayant délivré le ticket de caisse. |
| OperatorName            | Nom de l’opérateur ayant délivré le ticket de caisse. |
| RegisterNumber          | Identification du registre sur lequel le ticket de caisse a été émis. |
| CustomerAccount         | Identification du client pour lequel le ticket de caisse a été émis. |
| LineCount               | Nombre de lignes de vente sur le ticket de caisse. |
| Total                   | Nœud Total du ticket de caisse. |
| ExclTax                 | Montant total du ticket de caisse, hors taxes. |
| InclTax                 | Montant total du ticket de caisse, taxes incluses. |
| PaymentLines            | Collection de lignes de paiement du ticket de caisse. |
| PaymentLine             | Nœud pour un paiement. |
| Type                    | Identification du type de paiement, tel que configuré dans la caisse enregistreuse. |
| Nom                    | Nom du type de paiement, tel que configuré dans la caisse enregistreuse. |
| Montant                  | Montant du paiement dans la devise du magasin. |
| AmountCur               | Montant du paiement dans la devise du paiement. |
| Devise                | Identification de la devise de paiement. |
| CurrencyRate            | Taux de change multiplié par 100 et arrondi à un nombre entier. |
| ReceiptLines            | Collection de lignes de ticket de caisse. |
| ReceiptLine             | Nœud pour une ligne de ticket de caisse. |
| Produit                 | Identification du produit sur la ligne de ticket de caisse. |
| Nom                    | Nom du produit sur la ligne de ticket de caisse. |
| TaxRates                | Collection de lignes de taxe liées à la ligne de ticket de caisse. |
| LineTaxRate             | Nœud pour une ligne de taxe. |
| TaxRate                 | Taux d’imposition de la ligne d’imposition. |
| TaxAmount               | Montant de la taxe pour la ligne de taxe. |
| Quantité                | Quantité de produit vendu. |
| UnitId                  | Identification de l’unité de produit vendu. |
| UnitPriceExclTax        | Prix unitaire du produit, hors taxes. |
| UnitPriceInclTax        | Prix unitaire du produit, taxes incluses. |
| TotalExclTax            | Montant total de la ligne de ticket de caisse, hors taxes. |
| TotalInclTax            | Montant total de la ligne de ticket de caisse, taxes incluses. |
| Remises               | Collection de remises appliquées à la ligne de ticket de caisse. |
| FooterLines             | Collection de montants totaux de ticket de caisse par taux d’imposition. |
| FooterLine              | Nœud pour le montant total de ticket de caisse d’un taux d’imposition. |
| TotalExclTax            | Montant total de la ligne de ticket caisse, hors taxes pour le taux d’imposition. |
| TotalInclTax            | Montant total de la ligne de ticket de caisse, taxes pour le taux d’imposition incluses. |
| TaxRate                 | Taux d’imposition. |
| TaxAmount               | Montant total d’une taxe pour le taux d’imposition. |
| SequentialNumber        | Numéro séquentiel de la transaction de vente signée pour le registre. |
| DataToSign              | Chaîne [créée à partir des éléments de l’enregistrement de la transaction de vente](./emea-fra-cash-registers.md#digital-signing-of-sales-and-return-transactions) et utilisée pour la signature. |
| DataToSignFormatVersion | Version interne du format de données qui a été utilisé pour la signature. |
| Signature               | Signature numérique de l’enregistrement de la transaction de vente. |
| HashAlgorithm           | Algorithme de code de hachage utilisé pour hacher les données avant signature. |
| CertificateThumbprint   | Empreinte numérique du certificat utilisée pour la signature. |

### <a name="receiptcopy-node"></a>ReceiptCopy node

Nœud **ReceiptCopy** d’une archive fiscale contient les éléments suivants.

| Élément/nœud                    | Commentaire |
|---------------------------------|---------|
| RegisterNumber                  | Numéro du registre à partir duquel la copie du ticket de caisse a été imprimée. |
| CopyNumber                      | Numéro de copie de ticket de caisse pour la transaction de vente. |
| SequentialNumber                | Numéro séquentiel de l’événement de copie de ticket de caisse signée pour le registre. |
| OriginalReceiptNumber           | Numéro de ticket de caisse imprimé de la transaction de vente originale.|
| OriginalReceiptSequentialNumber | Numéro séquentiel de la transaction de vente d’origine. |
| Date                            | Date et heure de l’événement de copie de ticket de caisse, au format AAAAMMJJHHMMSS. |
| OperatorCode                    | Code de l’opérateur ayant imprimé la copie du ticket de caisse. |
| OperatorName                    | Nom de l’opérateur ayant imprimé la copie du ticket de caisse. |
| DataToSign                      | Chaîne [créée à partir des éléments de l’enregistrement de la copie de ticket de caisse](./emea-fra-cash-registers.md#digital-signing-of-receipt-copies) et utilisée pour la signature. |
| DataToSignFormatVersion         | Version interne du format de données qui a été utilisé pour la signature. |
| Signature                       | Signature numérique de l’enregistrement de la copie de ticket de caisse. |
| HashAlgorithm                   | Algorithme de code de hachage utilisé pour hacher les données avant signature. |
| CertificateThumbprint           | Empreinte numérique du certificat utilisée pour la signature. |

### <a name="auditevent-node"></a>AuditEvent node

Nœud **AuditEvent** d’une archive fiscale contient les éléments suivants.

| Élément/nœud            | Commentaire |
|-------------------------|---------|
| Code                    | Code d’événement prédéfini. |
| EventType               | Type d’événement prédéfini. |
| Date                    | Date et heure de l’événement d’audit, au format AAAAMMJJHHMMSS. |
| RegisterNumber          | Numéro de registre sous lequel l’événement d’audit a été enregistré. |
| OperatorCode            | Code de l’opérateur ayant enregistré l’événement d’audit. |
| OperatorName            | Nom de l’opérateur ayant enregistré l’événement d’audit. |
| SequentialNumber        | Numéro séquentiel de l’événement d’audit signé pour le registre. |
| DataToSign              | Chaîne [créée à partir des éléments de l’enregistrement de l’événement d’audit](./emea-fra-cash-registers.md#digital-signing-of-events) et utilisée pour la signature. |
| DataToSignFormatVersion | Version interne du format de données qui a été utilisé pour la signature. |
| Signature               | Signature numérique de l’enregistrement de l’événement d’audit. |
| HashAlgorithm           | Algorithme de code de hachage utilisé pour hacher les données avant signature. |
| CertificateThumbprint   | Empreinte numérique du certificat utilisée pour la signature. |

## <a name="fiscal-archive-integrity-verification-tool"></a>Outil de vérification de l’intégrité des archives fiscales

L’outil de vérification de l’intégrité des archives fiscales peut être utilisé pour vérifier l’intégrité d’une archive fiscale et pour détecter les violations de la signature de l’archive et des chaînes d’enregistrements signés dans l’archive. L’outil doit être appliqué à un fichier d’archive fiscale et au fichier de signature correspondant. Lorsqu’il est exécuté, l’outil effectue les actions suivantes :

1. Vérifiez la signature du fichier d’archive fiscale.
1. Vérifiez les signatures et les chaînes de signature de tous les enregistrements d’archives fiscales. (Ces enregistrements sont le journal du total général de la période, de l’équipe, du ticket de caisse, de la copie du ticket de caisse et des enregistrements d’événement d’audit.) Pour chaque enregistrement, l’outil effectue les actions suivantes :

    1. Créer une chaîne de texte à partir des éléments de données de l’enregistrement, selon les [règles de signature numérique](./emea-fra-cash-registers.md#digital-signing-overview) et la version interne du format des données qui a été utilisé pour signer le dossier. Ces éléments comprennent la signature de l’enregistrement précédent du même type.
    1. Calculer un code de hachage de la chaîne en utilisant l’algorithme de hachage qui a été utilisé pour hacher les données de l’enregistrement avant signature.
    1. Déchiffrer la signature de l’enregistrement à l’aide de la clé publique du certificat numérique qui a été utilisé pour signer l’enregistrement.
    1. Comparer le résultat avec le code de hachage qui a été calculé précédemment.

1. Imprimer toutes les violations d’intégrité identifiées.

L’outil de vérification de l’intégrité des archives fiscales prend la forme d’un script Windows PowerShell et est publié via le kit de développement logiciel (SDK) Commerce.

Pour obtenir l’outil de vérification de l’intégrité des archives fiscales et l’exécuter par rapport à une archive fiscale, procédez comme suit.

1. Téléchargez l’outil à partir du SDK Commerce :

    1. Ouvrez le référentiel [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Ouvrez la dernière branche de version disponible (par exemple, **[version/9.30](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.30)**).
    1. Ouvrez **src \> FiscalIntegration \> SequentialSignatureFrance \> FiscalArchiveIntegrityVerificationTool**.
    1. Consultez les termes de la licence de l’outil.
    1. Téléchargez le contenu du dossier sur votre ordinateur local.

1. Exportez les fichiers de clé publique pour tous les certificats numériques utilisés pour la signature numérique des enregistrements.
1. Placez le fichier d’archive fiscale, son fichier de signature et tous les fichiers de clé publique dans un seul dossier.
1. Exécutez Windows PowerShell.
1. Exécutez le script de l’outil **verify.ps1**, et précisez le nom du fichier d’archive fiscale. Incluez le chemin d’accès complet du fichier.
1. Passez en revue toutes les violations d’intégrité identifiées.
