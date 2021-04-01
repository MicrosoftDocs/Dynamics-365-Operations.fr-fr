---
title: Factures QR pour la Suisse
description: Cette rubrique offre des informations sur la façon de générer des factures QR (bons de livraison QR) et de traiter les factures QR entrantes.
author: neserovleo
manager: AnnBe
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Switzerland
ms.author: v-lenest
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 3c45ae72127f5446cf8264a7625432e54653a145
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236317"
---
# <a name="swiss-qr-bills"></a>Factures QR pour la Suisse

[!include [banner](../includes/banner.md)]


À partir de juillet 2020, les factures QR (bons de livraison QR) devront être traitées et émises en plus des factures. Cette rubrique explique comment générer les factures QR et traiter les factures QR entrantes dans Microsoft Dynamics 365 Finance.

Pour rendre la fonctionnalité Facture QR disponible, vous devez activer les fonctionnalités suivantes dans le module **Gestion des fonctionnalités** :

- ID paiement configurable
- (Switzerland) QR-bills

> [!NOTE]
> Lorsque vous activez la fonctionnalité Facture QR pour la Suisse, elle devient également disponible dans d’autres pays. Selon l’adresse de l’entité juridique, ces pays incluent la Suisse (CH), l’Allemagne (DE), l’Autriche (AT), la France (FR) et l’Italie (IT).

## <a name="electronic-reporting-configurations"></a>Configurations de la gestion des états électroniques

Les versions les plus récentes des configurations de gestion des états électroniques (ER) suivantes doivent être importées depuis Microsoft Dynamics Lifecycle Services (LCS) :

- Texte Facture QR pour la Suisse
- Information structurée Facture QR pour la Suisse
- Virement ISO20022 (CH)
- ISO20022 pain.002
- ISO20022 Camt.054

Toutes les configurations de modèle et de mappage de modèle requises seront importées automatiquement.

## <a name="setup-of-company-bank-accounts"></a>Configuration des comptes bancaires de l’entreprise

Sur la page **Compte bancaire** (**Gestion de la trésorerie et de la banque** \> **Comptes bancaires** \> **Comptes bancaires**), dans le champ **IBAN QR**, spécifiez l’IBAN QR. Ce numéro peut être utilisé simultanément avec le numéro de compte bancaire international ordinaire (IBAN) et a des validations similaires dans le système.

### <a name="cash-discount-and-tax-code-descriptions"></a>Description de l’escompte de règlement et du code fiscal

Le champ pour la description de la facture QR doit être rempli pour tous les escomptes en espèces et les codes fiscaux. Cette description est utilisée lors de l’impression des factures QR.

## <a name="setup-of-the-legal-entity-registration-ids"></a>Configuration des ID d’enregistrement d’entité juridique

Pour que l’identifiant unique soit correctement renseigné sur la facture QR générée, la valeur d’identifiant unique doit être saisie dans le champ **ID d’enregistrement** dans la configuration de l’entité juridique. En outre, la valeur dans le champ **Catégorie d’inscription** doit correspondre à la valeur **ID de TVA**.

## <a name="accounts-receivable-setup"></a>Paramétrage du module Ventes

### <a name="payment-id"></a>ID paiement

Sur la page **ID de paiement**, vous pouvez configurer la structure d’ID de paiement qui est appliquée lorsque des factures QR sortantes sont générées à partir du module **Comptabilité client**. La longueur de l’ID de paiement doit être définie sur 27 chiffres et le chiffre de contrôle doit être généré à l’aide de l’algorithme **Modulo11**. Les symboles non numériques sont exclus des ID de paiement lors de l’exécution de l’algorithme. Par conséquent, les souches de numéros utilisées pour les comptes clients et les factures ne doivent comporter que des chiffres.

Par défaut, le type d’ID de paiement appliqué sur la facture peut utiliser la hiérarchie de niveaux suivante :

- Page **Paramètres de la comptabilité client** \> onglet **Comptabilité et taxe**
- Page **Groupes de clients**
- Page **Compte client** \> onglet **Valeurs par défaut de paiement**
- Page **Mode de paiement** \> onglet **Contrôle des paiements**

### <a name="methods-of-payment--customers"></a>Modes de paiement - Clients

Le mode de paiement doit être configuré sur les comptes clients qui utilisent des factures QR, pour définir les détails du compte bancaire de l’entreprise vers lequel une facture QR est émise. Pour traiter les paiements entrants au format camt.054, vous devez configurer la configuration Gestion des états électroniques-Importer les configurations.

### <a name="customer-account"></a>Compte client

Le mode de paiement par défaut doit être sélectionné et le type d’ID de paiement doit être renseigné s’il n’est pas déjà spécifié dans la configuration par défaut pour les groupes de clients sur la page **Paramètres de la comptabilité client**.

Dans le groupe de champ **Document de paiement associé**, le nouveau type, **Facture QR**, est ajouté. Lorsqu’elle est sélectionnée, la facture QR sera imprimée lors de l’impression du document de type dédié.

### <a name="giro-report-processing-group"></a>Groupe de traitement de l’état de virement

Les informations sur les paramètres fournies dans les groupes de traitement des états Giro déterminent comment la fonction **Informations de facturation** d’une facture QR est remplie. Au besoin, vous pouvez configurer et utiliser différentes parties de cette section sur la facture QR dans les états électroniques. Voici quelques exemples :

- **Code de compte** - Format spécifique dédié au compte client spécifique.
- **Relation client** - Valeur du compte client ou du groupe de clients spécifique.
- **Informations facture QR** - Configuration de format ER chargée de renseigner les informations de facturation.
- **Imprimer le symbole Ciseaux** - Inclusion du symbole Ciseaux sur le rapport imprimé. L’inclusion de ce symbole peut être importante lorsque vous choisissez d’envoyer une version imprimée de la facture QR ou une version électronique.

## <a name="accounts-payable-setup"></a>Paramétrage du module Comptabilité fournisseur

### <a name="methods-of-payment--vendors"></a>Modes de paiement - Fournisseurs

Pour les modes de paiement fournisseur, vous devez spécifier le compte bancaire associé, sélectionner les configurations de gestion des états électroniques (ER) requises pour l’exportation et l’importation en vue du traitement du fichier de paiement et configurer les spécifications de paiement. Une nouvelle valeur de paramètre de spécification de paiement, **Tp3.QR**, est disponible pour les paiements correspondant aux factures QR entrantes. De plus, une option disponible sur le compte bancaire du fournisseur peut être utilisée pour redéfinir le paramètre **Spécification**.

L’ID de paiement doit être activé sur l’onglet **Attributs de paiement**, afin que l’ID de paiement puisse être hérité lors de la proposition de paiement pour les paiements associés aux factures QR.

### <a name="return-format-error-codes-and-return-format-status-mapping"></a>Codes d’erreur de format de retour et mappage d’état du format de retour

Si pain.002 est utilisé comme format de fichier de retour, les codes d’erreur de format de retour et le mappage d’état du format de retour doivent être configurés. Pour plus d’informations, voir la section [Importation de fichiers ISO20022](emea-iso20022-file-formats.md).

### <a name="vendor-account"></a>Compte fournisseur

La configuration standard du compte fournisseur pour les paiements ISO20022 est prévue. Pour en savoir plus, voir [Paramétrer les fournisseurs et les comptes bancaires fournisseur pour les virements ISO20022](tasks/set-up-vendor-iso20022-credit-transfers.md).

### <a name="vendor-bank-account"></a>Compte bancaire fournisseur

Un IBAN QR doit être attribué aux comptes bancaires des fournisseurs. Il est prévu que d’autres champs soient définis conformément à la procédure de paiement type pour le type de paiement 3 en Suisse.

De plus, il existe une option pour sélectionner un paramètre de spécification de paiement directement sur le compte bancaire du fournisseur. Si une spécification de paiement a été effectuée, la valeur reçoit une priorité supérieure à la méthode de spécification de paiement lorsqu’un fichier de virement est généré.

## <a name="accounts-receivable-process"></a>Traitement de la comptabilité client

### <a name="generate-the-qr-bills"></a>Générer les factures QR

Pour générer la facture QR d’un document, tel qu’une facture client, imprimez le document. La facture QR sera automatiquement générée en tant que rapport supplémentaire. Vous pouvez ensuite exporter la facture QR sous forme de fichier PDF, et l’imprimer ou l’envoyer électroniquement.

Voici quelques exemples de documents qui prennent en charge cette fonctionnalité :

- Factures de commande client
- Factures financières
- Factures de projet
- Notes d’intérêt
- Lettres de relance
- Relevés de compte

### <a name="import-payments-in-camt054-format"></a>Importer des paiements au format camt.054

Pour importer un relevé bancaire au format camt.054 depuis la banque, ouvrez la ligne du journal de paiement client et exécutez la fonction **Importer le paiement**. La référence à 27 chiffres est prévue dans l’onglet **Réf.** de la section **RmtInf**. Après l’importation, les transactions de paiement seront créées et réglées avec les transactions client en fonction de l’ID de paiement. Pour plus d’informations, voir la section [Importation de fichiers ISO20022](emea-iso20022-file-formats.md).

## <a name="accounts-payable-process"></a>Traitement de la comptabilité fournisseurs

L’étendue des fonctionnalités prises en charge couvre le processus d’importation manuelle des valeurs de code QR dans la boîte de dialogue d’entrée. Cette importation peut être effectuée à l’aide de dispositifs de numérisation qui transmettent la valeur textuelle du code QR. La structure des informations dans le code QR doit suivre les normes disponibles sur le site Web de SIX group au moment de la sortie de la fonctionnalité. Toute dérivation de la structure des informations chiffrées dans le code QR, ou tout changement de format requis pour suivre le comportement spécifique à l’appareil, peut être configuré à l’aide du module **Gestion des états électroniques** (ER). Aucune modification de code n’est requise.

### <a name="import-qr-bills"></a>Importer des factures QR

Vous pouvez importer les factures QR dans le journal des factures ou dans les destinations de factures fournisseur en attente.

Pour importer les factures QR dans le journal des factures, exécutez la fonction **Importer la facture QR** disponible sur la page **Lignes de journal des factures**.

Dans la boîte de dialogue **Importation**, le champ **Facture QR** affiche le nom de la configuration du format de gestion des états électroniques qui sera utilisée. Vous pouvez spécifier un format de gestion des états électroniques différent. Dans le texte brut du champ **Facture QR**, entrez la valeur du code QR. Puis sélectionnez **OK**.

Sur la page suivante, l’onglet **Facture QR** affiche les valeurs analysées de la facture QR. Sur l’onglet **Général**, vous pouvez afficher les valeurs du fournisseur reconnu, du compte bancaire, du montant et d’autres détails qui seront importés dans le système. Après avoir sélectionné **OK**, les lignes du journal des factures sont créées. Si cette facture QR a déjà été importée, un message d’avertissement vous en informe. Les informations de la facture QR importée sont stockées et disponibles pour consultation sur la page **Factures QR importées**.

Pour les factures associées aux bons de commande, vous pouvez créer des en-têtes de facture fournisseur en attente basés sur des informations de facture QR. Pour importer la facture QR, sur la page **Factures fournisseur en attente**, sur l’onglet **Processus**, sélectionnez **Importer une facture QR**. La procédure d’ajout, de révision et d’importation du code QR ressemble à la procédure décrite dans le paragraphe précédent.

Vous pouvez également importer la facture QR lorsque la facture fournisseur est ouverte à partir de la page **Commande fournisseur**. La procédure d’importation est la même que celle des factures fournisseur en attente. Si la facture est associée à une commande fournisseur, l’importation se produit automatiquement.

Pour traiter la facture QR en l’absence de destination prédéfinie ou pour utiliser une destination personnalisée, vous pouvez utiliser une option spéciale disponible sous **Tâches périodiques** dans le module **Comptabilité fournisseur**. Dans ce cas, vous devez sélectionner la destination manuellement.

Lorsque le texte brut de la facture QR est laissé vide, vous pouvez exécuter l’importation à partir du fichier texte situé dans le dossier SharePoint, selon la configuration de la source de gestion des états électroniques (ER).

Une fois la facture validée, la transaction fournisseur avec l’ID de paiement importé est disponible pour le règlement dans le journal des paiements.

## <a name="payment-file-processing"></a>Traitement du fichier de paiement

Créez des lignes de journal des paiements fournisseur en utilisant la fonctionnalité de proposition de paiement. Pour en savoir plus, voir [Créer et exporter des paiements fournisseur à l’aide du format de paiement ISO20022](tasks/create-export-vendor-payments-iso20022-payment-format.md).

Pour les paiements liés aux factures QR, le fichier de virement est généré en fonction de la valeur de l’ID de paiement. Cette valeur est extraite du code QR.

Vous pouvez importer les fichiers pain.002 et camt.054 à partir de la page **Transferts de paiement**. Pour plus d’informations, voir la section [Importation de fichiers ISO20022](emea-iso20022-file-formats.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]