---
title: Importer des fichiers ISO20022
description: Cette rubrique explique comment importer des fichiers de paiement au format camt.054 et pain.002 de la norme ISO 20022 dans Microsoft Dynamics 365 Finance.
author: neserovleo
manager: AnnBe
ms.date: 07/27/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, CustBankAccounts, VendPaymMode, VendBankAccounts
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Italy, Latvia, Lithuania, Norway, Poland, Spain, Sweden, Switzerland, United Kingdom
ms.author: v-lenest
ms.search.validFrom: 2017-06-01
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: b809ba8d92772d8f3f416d4854d4af322e6f954a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4407932"
---
# <a name="import-iso20022-files"></a>Importer des fichiers ISO20022

[!include [banner](../includes/banner.md)]

Vous pouvez importer les fichiers de paiement qui ont les formats suivants :

 - **Avis de crédit camt.054 ISO20022** : Importez des paiements entrants à partir d’un fichier dans ce format dans le journal des paiements client.
 - **Statut du retour pain.002 ISO20022** et **Avis de débit camt.054 ISO20022** : Importez des fichiers de retour dans ces formats dans le journal de transfert de paiement d’achats.

## <a name="prerequisites-for-importing-the-camt054-credit-advice-file"></a>Conditions préalables pour importer le fichier d’avis de crédit camt.054
Vous devez effectuer les tâches préalables suivantes pour importer les messages de notification bancaire au format camt.054.001.002 dans le journal des paiements client.

1. Importez la configuration de la gestion des états électroniques **camt.054 ISO20022** de Microsoft Dynamics Lifecycle Services (LCS). Puis, sur la page **Mode de paiement du client**, dans le champ **Importer la configuration du format**, sélectionnez cette configuration. Pour plus d’informations, voir [Formats de fichier des modes de paiement](emea-select-file-formats-for-the-method-of-payments.md).
2. Sur la page **Tous les clients**, entrez un nom et un numéro d’organisation pour chaque client.
3. Sur la page **Compte bancaire client**, paramétrez un enregistrement de compte bancaire client en entrant les informations suivantes : IBAN ou numéro de compte bancaire, et code SWIFT ou numéro d’acheminement.
4. Sur la page **Comptes bancaires**, paramétrez des comptes bancaires d’entité légale en entrant les informations suivantes : IBAN ou numéro de compte bancaire, et code SWIFT ou numéro d’acheminement, devise et adresse.

   > [!NOTE]
   > Si vous envisagez d’utiliser le rapprochement bancaire avancé, sous l’organisateur **Rapprochement**, définissez l’option **Rapprochement bancaire avancé** sur **Oui**. Si vous envisagez de rapprocher les paiements importés non validés, définissez l’option **Utiliser les relevés bancaires comme confirmation des paiements électroniques** sur **Oui**.

5. Facultatif : Sur la page **Mappage de code de transaction**, paramétrez la mise en correspondance entre les codes de transaction bancaire du fichier et les types de transaction bancaire.
6. Si le fichier contient des frais de transaction que vous souhaitez valider avec le paiement entrant, créez des frais de paiement sur la page **Frais de paiement client**. Puis, sur la page **Modes de paiement**, associez les frais de paiement au compte bancaire dans le paramétrage de frais de paiement.
7. Si les paiements ESR seront importés et contiendront des références ISR (applicables pour les entités juridiques en Suisse), effectuez la configuration suivante :

    - Dans le champ **Paiements client, longueur du compte**, entrez la longueur du code client utilisé dans les références ISR ou pour l’identification automatique du client.
    - Assurez-vous que le numéro client et le numéro de facture (souches de numéros) contiennent uniquement des chiffres. Ils ne doivent pas comporter d’autres caractères. Le numéro de facture ne doit pas comporter de zéros non significatifs.
    - Entrez l’ESR, le BESR et le numéro d’acheminement du compte bancaire de l’entité juridique. Pour plus d’informations, voir [Importation des paiements client ESR](emea-che-esr-customer-payments-import.md), car des paramètres similaires sont requis.
    
## <a name="import-the-camt054-credit-advice-file-into-the-customer-payment-journal"></a>Importer le fichier de l’avis de crédit camt.054 dans le journal des paiements client
1. Sur la page **Lignes du journal des paiements client**, cliquez sur **Fonctions** > **Importer les paiements**.
2. Sélectionnez le mode de paiement incluant les paramètres requis pour le format camt.054 ISO20022.
3. Indiquez les paramètres requis et le chemin d’accès du fichier, puis cliquez sur **OK**. Le fichier est importé.

## <a name="prerequisites-for-importing-files-in-the-pain002-status-return-and-camt054-debit-advice-formats-into-the-ap-payment-transfer-journal"></a>Conditions préalables pour l’importation de fichiers dans le statut du retour pain.002 et l’avis de débit camt.054 dans le journal de transfert de paiement d’achats
Vous devez effectuer les tâches préalables suivantes avant d’importer les messages de la banque aux formats ISO20022 suivants sur la page **Transfert de paiement fournisseur** : messages du statut du retour pain.002.001.003 et avis de débit camt.054.001.002.

1. Importez les configurations ER **camt.054 ISO20022** et **pain.002 ISO20022** de LCS.
2. Sur la page **Mode de paiement fournisseur**, dans les champs **Configuration du format de retour** et **Configuration secondaire du format de retour**, sélectionnez les configurations ER que vous avez importées. Vous devrez activer le format de retour électronique générique pour le mode de paiement sélectionné.
3. Sur la page **Mise en correspondance du statut du format de retour**, paramétrez la mise en correspondance des codes de statut entre les statuts pain.002 et les statuts de journal des paiements fournisseur.

    Voici un exemple de configuration de statut.

    Statut de retour | Statut de paiement
    --------------|---------------
    RJCT          | Rejeté
    ACCP          | Acceptée
    ACSP          | Reçu(e)

4. Sur la page **Codes d’erreur du format de retour**, configurez les codes d’erreur et les descriptions pain.002 conformément aux codes de motif du statut ISO20022 externes.

    Voici un exemple d’une partie de la configuration d’un code d’erreur.

    Code | Nom
    -----|-----
    AC01 | IncorrectAccountNumber
    AC02 | InvalidDebtorAccountNumber
    AC03 | InvalidCreditorAccountNumber
    AC04 | ClosedAccountNumber
    AC05 | ClosedDebtorAccountNumber
    AC06 | BlockedAccount

5. Si le fichier camt.054 contient des frais de transaction que vous souhaitez valider avec le paiement entrant, créez des frais de paiement sur la page **Frais de paiement fournisseur**. Puis, sur la page **Modes de paiement**, associez les frais de paiement au compte bancaire dans le paramétrage de frais de paiement.

## <a name="import-the-pain002-status-return-or-camt054-debit-advice-files-into-the-vendor-payment-journal"></a>Importez les fichiers de retour de statut pain.002 ou d’avis de débit camt.054 dans le journal des paiements fournisseur
1. Ouvrez la page **Transferts de paiement** dans le menu Comptabilité fournisseur.
2. Dans la page **Transferts de paiement**, cliquez sur **Fichier retourné - fournisseur**.
3. Sélectionnez le mode de paiement incluant les paramètres requis pour les fichiers ISO20022, puis cliquez sur **OK**.
4. Sélectionnez le format de fichier que vous envisagez d’importer, puis cliquez sur **OK**.
5. Indiquez les paramètres requis et le chemin d’accès du fichier, puis cliquez sur **OK**.

Si vous importez le fichier pain.002, le statut des lignes de paiement fournisseur est mis à jour, selon les informations du fichier importé.

Si vous importez le fichier camt.054, vous devez spécifier les paramètres supplémentaires suivants :

- **ID frais** : Entrez l’ID frais qui détermine les nouvelles lignes de frais de paiement, qui sont créées sur la ligne de journal des paiements fournisseur si un montant de frais est présent dans le fichier camt.054.
- **Nouveau nom de journal** et **Description nouveau journal** : Entrez le nom et la description du journal vers lequel les transactions traitées seront transférées. Après le transfert, de nouveaux n° document doivent être affectés dans le nouveau journal.
- **Importer des transactions de débits directs** : Définissez cette option sur **Oui** si les débits directs sortants doivent être importés dans le journal des paiements fournisseur.
- **Nom de journal** : Attribuez un nouveau nom de journal pour les transactions de débit direct importées.
- **Régler les transactions** : Définissez cette option sur **Oui** si les paiements fournisseur importés doivent être réglés avec des factures qui se trouvent dans le système.

Vous pouvez consultez les informations importées sur l’écran **Transferts de paiement**. 

## <a name="additional-details"></a>Détails supplémentaires

Lorsque vous importez une configuration de format à partir de LCS, vous importez toute l’arborescence de configuration, ce qui signifie que les configurations Modèle et Mise en correspondance des modèles sont incluses. Dans le modèle de paiement commençant à partir de la version 8, les mises en correspondance sont situées dans des configurations ER distinctes dans l’arborescence de la solution (mise en correspondance du modèle de paiement 1611, mise en correspondance du modèle de paiement avec la destination ISO20022, etc.) Il existe plusieurs formats de paiement dans un modèle (modèle de paiement), une gestion séparée des mises en correspondance est donc primordiale pour faciliter la maintenance de la solution. Par exemple, prenez le scénario suivant : vous utilisez les paiements ISO20022 pour générer des fichiers de transfert de crédit, puis vous importez les messages retournés par la banque. Dans ce scénario, vous devez utiliser les configurations suivantes :

 - **Modèle de paiement**
 - **Mise en correspondance du modèle de paiement 1611** – Cette mise en correspondance sera utilisée pour générer le fichier d’exportation
 - **Mise en correspondance du modèle de paiement avec la destination ISO20022** – Cette configuration inclut toutes les mises en correspondance qui seront utilisées pour importer les données (direction de mise en correspondance « vers la destination »)
 - **Transfert de crédit ISO20022** – Cette configuration inclut un composant de format qui doit générer le fichier d’exportation (pain.001) en fonction de la mise en correspondance du modèle de paiement 1611, ainsi qu’un composant de mise en correspondance du format avec le modèle qui sera utilisé avec la mise en correspondance du modèle de paiement avec la destination ISO20022 pour enregistrer les paiements exportés dans le système à des fins d’importation (importation dans la table technique CustVendProcessedPayments)
 - **Transfert de crédit ISO20022 (CE)**, où CE correspond à l’extension de pays – Format dérivé du transfert du crédit ISO20022 avec la même structure et certaines différences spécifiques au pays
 - **Pain.002** – Ce format est utilisé avec la mise en correspondance du modèle de paiement avec la destination ISO20022 pour importer le fichier pain.002 dans le journal des transferts de paiements fournisseur
 - **Camt.054** – Ce format est utilisé avec la mise en correspondance du modèle de paiement avec la destination ISO20022 pour importer le fichier camt.054 dans le journal des transferts de paiements fournisseur. La même configuration de format sera utilisée dans la fonctionnalité d’importation de paiements client, mais une mise en correspondance différente sera utilisée dans la configuration de la mise en correspondance du modèle de paiement avec la destination ISO20022.

Pour plus d’informations sur les états électronique, voir, [Vue d’ensemble des états électroniques](../../dev-itpro/analytics/general-electronic-reporting.md).

## <a name="additional-resources"></a>Ressources supplémentaires
- [Créer et exporter des paiements fournisseur à l’aide du format de paiement ISO20022](./tasks/create-export-vendor-payments-iso20022-payment-format.md)
- [Importer la configuration du virement ISO20022](./tasks/import-iso20022-credit-transfer-configuration.md)
- [Importer la configuration du débit direct ISO20022](./tasks/import-iso20022-direct-debit-configuration.md)
- [Paramétrer les comptes bancaires de société pour les virements ISO20022](./tasks/set-up-company-bank-accounts-iso20022-credit-transfers.md)
- [Paramétrer les comptes bancaires de société pour les débits directs ISO20022](./tasks/set-up-company-bank-accounts-iso20022-direct-debits.md)
- [Paramétrer les clients et les comptes bancaires du client pour les débits directs ISO20022](./tasks/set-up-bank-accounts-iso20022-direct-debits.md)
- [Paramétrer le mode de paiement pour les virements ISO20022](./tasks/set-up-method-payment-iso20022-credit-transfer.md)
- [Configurer le mode de paiement pour le débit direct ISO20022](./tasks/setup-method-payment-iso20022-direct-debit.md)
- [Paramétrer les fournisseurs et les comptes bancaires fournisseur pour les virements ISO20022](./tasks/set-up-vendor-iso20022-credit-transfers.md)
