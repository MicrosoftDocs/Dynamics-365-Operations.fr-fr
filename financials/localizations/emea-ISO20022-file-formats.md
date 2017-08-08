---
title: Importation de fichiers ISO20022
description: "Cette rubrique explique comment importer des fichiers de paiement au format camt.054 et pain.002 de la norme ISO 20022 dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: neserovleo
manager: AnnBe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Italy, Latvia, Lithuania, Norway, Poland, Spain, Sweden, Switzerland, United Kingdom
ms.author: v-lenest
ms.search.validFrom: 2017-06-01T00:00:00.000Z
ms.dyn365.ops.version: Enterprise edition, July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 48e280bf0a6c5db237bd389fe448c9d698d3ae12
ms.openlocfilehash: acf6ed5f503d77f372d802a51a71cec062c2b24b
ms.contentlocale: fr-fr
ms.lasthandoff: 07/25/2017

---

# <a name="import-iso20022-files"></a>Importer des fichiers ISO20022

## <a name="overview"></a>Vue d'ensemble
Vous pouvez importer les fichiers de paiement qui ont les formats suivants :

 - **Avis de crédit camt.054 ISO20022** : Importez des paiements entrants à partir d'un fichier dans ce format dans le journal des paiements client.
 - **Statut du retour pain.002 ISO20022** et **Avis de débit camt.054 ISO20022** : Importez des fichiers de retour dans ces formats dans le journal de transfert de paiement d'achats.

## <a name="prerequisites-for-importing-the-camt054-credit-advice-file"></a>Conditions préalables pour importer le fichier d'avis de crédit camt.054
Vous devez effectuer les tâches préalables suivantes pour importer les messages de notification bancaire au format camt.054.001.002 dans le journal des paiements client.

1. Importez la configuration de la gestion des états électroniques **camt.054 ISO20022** de Microsoft Dynamics Lifecycle Services (LCS). Puis, sur la page **Mode de paiement du client**, dans le champ **Importer la configuration du format**, sélectionnez cette configuration. Pour plus d'informations, voir [Formats de fichier des modes de paiement](emea-select-file-formats-for-the-method-of-payments.md).
2. Sur la page **Tous les clients**, entrez un nom et un numéro d'organisation pour chaque client.
3. Sur la page **Compte bancaire client**, paramétrez un enregistrement de compte bancaire client en entrant les informations suivantes : IBAN ou numéro de compte bancaire, et code SWIFT ou numéro d'acheminement.
4. Sur la page **Comptes bancaires**, paramétrez des comptes bancaires d'entité légale en entrant les informations suivantes : IBAN ou numéro de compte bancaire, et code SWIFT ou numéro d'acheminement, devise et adresse.

    > [!NOTE]
    > Si vous envisagez d'utiliser le rapprochement bancaire avancé, sous l'organisateur **Rapprochement**, définissez l'option **Rapprochement bancaire avancé** sur **Oui**. Si vous envisagez de rapprocher les paiements importés non validés, définissez l'option **Utiliser les relevés bancaires comme confirmation des paiements électroniques** sur **Oui**.

5. Facultatif : Sur la page **Mappage de code de transaction**, paramétrez la mise en correspondance entre les codes de transaction bancaire du fichier et les types de transaction bancaire.
6. Si le fichier contient des frais de transaction que vous souhaitez valider avec le paiement entrant, créez des frais de paiement sur la page **Frais de paiement client**. Puis, sur la page **Modes de paiement**, associez les frais de paiement au compte bancaire dans le paramétrage de frais de paiement.
7. Si les paiements ESR seront importés et contiendront des références ISR (applicables pour les entités juridiques en Suisse), effectuez la configuration suivante :

    - Dans le champ **Paiements client, longueur du compte**, entrez la longueur du code client utilisé dans les références ISR ou pour l'identification automatique du client.
    - Assurez-vous que le numéro client et le numéro de facture (souches de numéros) contiennent uniquement des chiffres. Ils ne doivent pas comporter d'autres caractères. Le numéro de facture ne doit pas comporter de zéros non significatifs.
    - Entrez l'ESR, le BESR et le numéro d'acheminement du compte bancaire de l'entité juridique. Pour plus d'informations, voir [fonctionnalité ESR héritée](emea-che-esr-customer-payments-import.md), car des paramètres similaires sont requis.
    
## <a name="import-the-camt054-credit-advice-file-into-the-customer-payment-journal"></a>Importer le fichier de l'avis de crédit camt.054 dans le journal des paiements client
1. Sur la page **Lignes du journal des paiements client**, cliquez sur **Fonctions** > **Importer les paiements**.
2. Sélectionnez le mode de paiement incluant les paramètres requis pour le format camt.054 ISO20022.
3. Indiquez les paramètres requis et le chemin d'accès du fichier, puis cliquez sur **OK**.

Le fichier est importé.

## <a name="prerequisites-for-importing-files-in-the-pain002-status-return-and-camt054-debit-advice-formats-into-the-ap-payment-transfer-journal"></a>Conditions préalables pour l'importation de fichiers dans le statut du retour pain.002 et l'avis de débit camt.054 dans le journal de transfert de paiement d'achats
Vous devez effectuer les tâches préalables suivantes avant d'importer les messages de la banque aux formats ISO20022 suivants sur la page **Transfert de paiement fournisseur** : messages du statut du retour pain.002.001.003 et avis de débit camt.054.001.002.

1. Importez les configurations ER **camt.054 ISO20022** et **pain.002 ISO20022** de LCS.
2. Sur la page **Mode de paiement fournisseur**, dans les champs **Configuration du format de retour** et **Configuration secondaire du format de retour**, sélectionnez les configurations ER que vous avez importées. Vous devrez activer le format de retour électronique générique pour le mode de paiement sélectionné.
3. Sur la page **Mise en correspondance du statut du format de retour**, paramétrez la mise en correspondance des codes de statut entre les statuts pain.002 et les statuts de journal des paiements fournisseur.

    Voici un exemple de configuration de statut.

    Statut de retour | Statut de paiement
    --------------|---------------
    RJCT          | Rejeté
    ACCP          | Acceptée
    ACSP          | Reçu(e)

4. Sur la page **Codes d'erreur du format de retour**, configurez les codes d'erreur et les descriptions pain.002 conformément aux codes de motif du statut ISO20022 externes.

    Voici un exemple d'une partie de la configuration d'un code d'erreur.

    Code | Nom
    -----|-----
    AC01 | IncorrectAccountNumber
    AC02 | InvalidDebtorAccountNumber
    AC03 | InvalidCreditorAccountNumber
    AC04 | ClosedAccountNumber
    AC05 | ClosedDebtorAccountNumber
    AC06 | BlockedAccount

5. Si le fichier camt.054 contient des frais de transaction que vous souhaitez valider avec le paiement entrant, créez des frais de paiement sur la page **Frais de paiement fournisseur**. Puis, sur la page **Modes de paiement**, associez les frais de paiement au compte bancaire dans le paramétrage de frais de paiement.

## <a name="import-the-pain002-status-return-or-camt054-debit-advice-files-into-the-vendor-payment-journal"></a>Importez les fichiers de retour de statut pain.002 ou d'avis de débit camt.054 dans le journal des paiements fournisseur
1. Ouvrez la page **Transferts de paiement** dans le menu Comptabilité fournisseur.
2. Dans la page **Transferts de paiement**, cliquez sur **Fichier retourné - fournisseur**.
3. Sélectionnez le mode de paiement incluant les paramètres requis pour les fichiers ISO20022, puis cliquez sur **OK**.
4. Sélectionnez le format de fichier que vous envisagez d'importer, puis cliquez sur **OK**.
5. Indiquez les paramètres requis et le chemin d'accès du fichier, puis cliquez sur **OK**.

Si vous importez le fichier pain.002, le statut des lignes de paiement fournisseur est mis à jour, selon les informations du fichier importé.

Si vous importez le fichier camt.054, vous devez spécifier les paramètres supplémentaires suivants :

- **ID frais** : Entrez l'ID frais qui détermine les nouvelles lignes de frais de paiement, qui sont créées sur la ligne de journal des paiements fournisseur si un montant de frais est présent dans le fichier camt.054.
- **Nouveau nom de journal** et **Description nouveau journal** : Entrez le nom et la description du journal vers lequel les transactions traitées seront transférées. Après le transfert, de nouveaux n° document doivent être affectés dans le nouveau journal.
- **Importer des transactions de débits directs** : Définissez cette option sur **Oui** si les débits directs sortants doivent être importés dans le journal des paiements fournisseur.
- **Nom de journal** : Attribuez un nouveau nom de journal pour les transactions de débit direct importées.
- **Régler les transactions** : Définissez cette option sur **Oui** si les paiements fournisseur importés doivent être réglés avec des factures qui se trouvent dans le système.

Vous pouvez consultez les informations importées sur l'écran **Transferts de paiement**. 

