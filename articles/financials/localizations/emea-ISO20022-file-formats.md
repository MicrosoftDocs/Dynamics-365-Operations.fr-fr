<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="emea-ISO20022-file-formats.md" target-language="fr-FR">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>emea-ISO20022-file-formats.35e138.d91e937c62d4d498e67d753e39676514835f4161.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>d91e937c62d4d498e67d753e39676514835f4161</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/15/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\financials\localizations\emea-ISO20022-file-formats.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>ISO20022 files import</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importation de fichiers ISO20022</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic explains how to import payment files of the ISO 20022 camt.054 and pain.002 formats into Microsoft Dynamics 365 for Finance and Operations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette rubrique explique comment importer des fichiers de paiement au format camt.054 et pain.002 de la norme ISO 20022 dans Microsoft Dynamics 365 for Finance and Operations.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Import ISO20022 files</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importer des fichiers ISO20022</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>You can import payment files that have the following formats:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez importer les fichiers de paiement qui ont les formats suivants :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source><bpt id="p1">**</bpt>ISO20022 camt.054 credit advice<ept id="p1">**</ept> – Import incoming payments from a file in this format into the Customer payment journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Avis de crédit camt.054 ISO20022<ept id="p1">**</ept> : Importez des paiements entrants à partir d'un fichier dans ce format dans le journal des paiements client.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source><bpt id="p1">**</bpt>ISO20022 pain.002 status return<ept id="p1">**</ept> and <bpt id="p2">**</bpt>ISO20022 camt.054 debit advice<ept id="p2">**</ept> – Import return files in these formats into the AP Payment transfer journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Statut du retour pain.002 ISO20022<ept id="p1">**</ept> et <bpt id="p2">**</bpt>Avis de débit camt.054 ISO20022<ept id="p2">**</ept> : Importez des fichiers de retour dans ces formats dans le journal de transfert de paiement d'achats.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Prerequisites for importing the camt.054 credit advice file</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Conditions préalables pour importer le fichier d'avis de crédit camt.054</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>You must complete the following prerequisites to import bank notification messages in the camt.054.001.002 format into the Customer payment journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous devez effectuer les tâches préalables suivantes pour importer les messages de notification bancaire au format camt.054.001.002 dans le journal des paiements client.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Import the <bpt id="p1">**</bpt>ISO20022 camt.054<ept id="p1">**</ept> Electronic reporting (ER) configuration from Microsoft Dynamics Lifecycle Services (LCS).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importez la configuration de la gestion des états électroniques <bpt id="p1">**</bpt>camt.054 ISO20022<ept id="p1">**</ept> de Microsoft Dynamics Lifecycle Services (LCS).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Then, on the <bpt id="p1">**</bpt>Customer method of payment<ept id="p1">**</ept> page, in the <bpt id="p2">**</bpt>Import format configuration<ept id="p2">**</ept> field, select that configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Puis, sur la page <bpt id="p1">**</bpt>Mode de paiement du client<ept id="p1">**</ept>, dans le champ <bpt id="p2">**</bpt>Importer la configuration du format<ept id="p2">**</ept>, sélectionnez cette configuration.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>For more information, see <bpt id="p1">[</bpt>File formats for methods of payment<ept id="p1">](emea-select-file-formats-for-the-method-of-payments.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour plus d'informations, voir <bpt id="p1">[</bpt>Formats de fichier des modes de paiement<ept id="p1">](emea-select-file-formats-for-the-method-of-payments.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>On the <bpt id="p1">**</bpt>All customers<ept id="p1">**</ept> page, enter a name and organization number for each customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Tous les clients<ept id="p1">**</ept>, entrez un nom et un numéro d'organisation pour chaque client.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>On the <bpt id="p1">**</bpt>Customer bank account<ept id="p1">**</ept> page, set up a customer bank account record by entering the following information: IBAN or bank account number, and SWIFT code or routing number.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Compte bancaire client<ept id="p1">**</ept>, paramétrez un enregistrement de compte bancaire client en entrant les informations suivantes : IBAN ou numéro de compte bancaire, et code SWIFT ou numéro d'acheminement.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>On the <bpt id="p1">**</bpt>Bank accounts<ept id="p1">**</ept> page, set up legal entity bank accounts by entering the following information: IBAN or bank account number, SWIFT code or routing number, currency, and address.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Comptes bancaires<ept id="p1">**</ept>, paramétrez des comptes bancaires d'entité légale en entrant les informations suivantes : IBAN ou numéro de compte bancaire, et code SWIFT ou numéro d'acheminement, devise et adresse.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>If you plan to use Advanced bank reconciliation, on the <bpt id="p1">**</bpt>Reconciliation<ept id="p1">**</ept> FastTab, set the <bpt id="p2">**</bpt>Advanced bank reconciliation<ept id="p2">**</ept> option to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si vous envisagez d'utiliser le rapprochement bancaire avancé, sous l'organisateur <bpt id="p1">**</bpt>Rapprochement<ept id="p1">**</ept>, définissez l'option <bpt id="p2">**</bpt>Rapprochement bancaire avancé<ept id="p2">**</ept> sur <bpt id="p3">**</bpt>Oui<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>If you plan to reconcile unposted imported payments, set the <bpt id="p1">**</bpt>Use bank statements as confirmation of electronic payments<ept id="p1">**</ept> option to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si vous envisagez de rapprocher les paiements importés non validés, définissez l'option <bpt id="p1">**</bpt>Utiliser les relevés bancaires comme confirmation des paiements électroniques<ept id="p1">**</ept> sur <bpt id="p2">**</bpt>Oui<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Optional: On the <bpt id="p1">**</bpt>Transaction code mapping<ept id="p1">**</ept> page, set up the mapping between bank transaction codes in the file and bank transaction types.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Facultatif : Sur la page <bpt id="p1">**</bpt>Mappage de code de transaction<ept id="p1">**</ept>, paramétrez la mise en correspondance entre les codes de transaction bancaire du fichier et les types de transaction bancaire.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>If the file contains transaction charges that you want to post together with the incoming payment, create a payment fee on the <bpt id="p1">**</bpt>Customer payment fee<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si le fichier contient des frais de transaction que vous souhaitez valider avec le paiement entrant, créez des frais de paiement sur la page <bpt id="p1">**</bpt>Frais de paiement client<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Then, on the <bpt id="p1">**</bpt>Methods of payment<ept id="p1">**</ept> page, associate the payment fee with the bank account in the payment fee setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Puis, sur la page <bpt id="p1">**</bpt>Modes de paiement<ept id="p1">**</ept>, associez les frais de paiement au compte bancaire dans le paramétrage de frais de paiement.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>If ESR payments will be imported and will contain ISR references (applicable for legal entities in Switzerland), complete the following setup:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si les paiements ESR seront importés et contiendront des références ISR (applicables pour les entités juridiques en Suisse), effectuez la configuration suivante :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>In the <bpt id="p1">**</bpt>Customer payments, account lengths<ept id="p1">**</ept> field, enter the length of the customer code that is used in ISR references or for automatic identification of the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans le champ <bpt id="p1">**</bpt>Paiements client, longueur du compte<ept id="p1">**</ept>, entrez la longueur du code client utilisé dans les références ISR ou pour l'identification automatique du client.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Make sure that the customer number and invoice number (number sequences) contain only digits.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Assurez-vous que le numéro client et le numéro de facture (souches de numéros) contiennent uniquement des chiffres.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>They must contain no other characters.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ils ne doivent pas comporter d'autres caractères.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>The invoice number must not have leading zeros.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le numéro de facture ne doit pas comporter de zéros non significatifs.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Enter the ESR, BESR, and routing number for the legal entity bank account.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Entrez l'ESR, le BESR et le numéro d'acheminement du compte bancaire de l'entité juridique.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>For more information, see <bpt id="p1">[</bpt>legacy ESR feature<ept id="p1">](emea-che-esr-customer-payments-import.md)</ept>, because similar settings are required.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour plus d'informations, voir <bpt id="p1">[</bpt>fonctionnalité ESR héritée<ept id="p1">](emea-che-esr-customer-payments-import.md)</ept>, car des paramètres similaires sont requis.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>Import the camt.054 credit advice file into the Customer payment journal</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importer le fichier de l'avis de crédit camt.054 dans le journal des paiements client</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>On the <bpt id="p1">**</bpt>Customer payment journal lines<ept id="p1">**</ept> page, click <bpt id="p2">**</bpt>Functions<ept id="p2">**</ept><ph id="ph1"> &gt; </ph><bpt id="p3">**</bpt>Import payments<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Lignes du journal des paiements client<ept id="p1">**</ept>, cliquez sur <bpt id="p2">**</bpt>Fonctions<ept id="p2">**</ept><ph id="ph1"> &gt; </ph><bpt id="p3">**</bpt>Importer les paiements<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Select the method of payment that has the required settings for the ISO20022 camt.054 format.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sélectionnez le mode de paiement incluant les paramètres requis pour le format camt.054 ISO20022.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>Specify the required parameters and the path of the file, and then click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Indiquez les paramètres requis et le chemin d'accès du fichier, puis cliquez sur <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>The file is imported.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le fichier est importé.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Prerequisites for importing files in the pain.002 status return and camt.054 debit advice formats into the AP Payment transfer journal</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Conditions préalables pour l'importation de fichiers dans le statut du retour pain.002 et l'avis de débit camt.054 dans le journal de transfert de paiement d'achats</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>You must complete the following prerequisites to import bank messages in the following ISO20022 formats to the <bpt id="p1">**</bpt>Vendor payment transfer<ept id="p1">**</ept> page: pain.002.001.003 status return messages and camt.054.001.002 debit advice.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous devez effectuer les tâches préalables suivantes avant d'importer les messages de la banque aux formats ISO20022 suivants sur la page <bpt id="p1">**</bpt>Transfert de paiement fournisseur<ept id="p1">**</ept> : messages du statut du retour pain.002.001.003 et avis de débit camt.054.001.002.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>Import the <bpt id="p1">**</bpt>ISO20022 camt.054<ept id="p1">**</ept> and <bpt id="p2">**</bpt>ISO20022 pain.002<ept id="p2">**</ept> ER configurations from LCS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importez les configurations ER <bpt id="p1">**</bpt>camt.054 ISO20022<ept id="p1">**</ept> et <bpt id="p2">**</bpt>pain.002 ISO20022<ept id="p2">**</ept> de LCS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>On the <bpt id="p1">**</bpt>Vendor method of payment<ept id="p1">**</ept> page, in the <bpt id="p2">**</bpt>Return format configuration<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Return format secondary configuration<ept id="p3">**</ept> fields, select the ER configurations that you imported.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Mode de paiement fournisseur<ept id="p1">**</ept>, dans les champs <bpt id="p2">**</bpt>Configuration du format de retour<ept id="p2">**</ept> et <bpt id="p3">**</bpt>Configuration secondaire du format de retour<ept id="p3">**</ept>, sélectionnez les configurations ER que vous avez importées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>You will have to activate the generic electronic return format for the selected method of payment.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous devrez activer le format de retour électronique générique pour le mode de paiement sélectionné.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>On the <bpt id="p1">**</bpt>Return format status mapping<ept id="p1">**</ept> page, set up the mapping of status codes between pain.002 statuses and Vendor payment journal statuses.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Mise en correspondance du statut du format de retour<ept id="p1">**</ept>, paramétrez la mise en correspondance des codes de statut entre les statuts pain.002 et les statuts de journal des paiements fournisseur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>Here is an example of a status setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Voici un exemple de configuration de statut.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Return status</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Statut de retour</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Payment status</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Statut de paiement</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>RJCT</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">RJCT</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Rejected</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rejeté</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>ACCP</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">ACCP</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>Accepted</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Acceptée</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>ACSP</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">ACSP</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>Received</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Reçu(e)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>On the <bpt id="p1">**</bpt>Return format error codes<ept id="p1">**</ept> page, set up pain.002 error codes and descriptions in accordance with external ISO20022 status reason codes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Codes d'erreur du format de retour<ept id="p1">**</ept>, configurez les codes d'erreur et les descriptions pain.002 conformément aux codes de motif du statut ISO20022 externes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>Here is an example of part of an error code setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Voici un exemple d'une partie de la configuration d'un code d'erreur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Code</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Code</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Name</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nom</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>AC01</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC01</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>IncorrectAccountNumber</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">IncorrectAccountNumber</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>AC02</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC02</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>InvalidDebtorAccountNumber</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">InvalidDebtorAccountNumber</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>AC03</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC03</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>InvalidCreditorAccountNumber</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">InvalidCreditorAccountNumber</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>AC04</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC04</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>ClosedAccountNumber</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">ClosedAccountNumber</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>AC05</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC05</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>ClosedDebtorAccountNumber</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">ClosedDebtorAccountNumber</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>AC06</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC06</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>BlockedAccount</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">BlockedAccount</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>If the camt.054 file contains transaction charges that you want to post together with the incoming payment, create a payment fee on the <bpt id="p1">**</bpt>Vendor payment fee<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si le fichier camt.054 contient des frais de transaction que vous souhaitez valider avec le paiement entrant, créez des frais de paiement sur la page <bpt id="p1">**</bpt>Frais de paiement fournisseur<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>Then, on the <bpt id="p1">**</bpt>Methods of payment<ept id="p1">**</ept> page, associate the payment fee with the bank account in the payment fee setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Puis, sur la page <bpt id="p1">**</bpt>Modes de paiement<ept id="p1">**</ept>, associez les frais de paiement au compte bancaire dans le paramétrage de frais de paiement.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>Import the pain.002 status return or camt.054 debit advice files into the Vendor payment journal</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importez les fichiers de retour de statut pain.002 ou d'avis de débit camt.054 dans le journal des paiements fournisseur</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Open the <bpt id="p1">**</bpt>Payment transfers<ept id="p1">**</ept> page in Accounts Payable menu.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ouvrez la page <bpt id="p1">**</bpt>Transferts de paiement<ept id="p1">**</ept> dans le menu Comptabilité fournisseur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>On the <bpt id="p1">**</bpt>Payment transfers<ept id="p1">**</ept> page, click <bpt id="p2">**</bpt>Return file - vendor<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans la page <bpt id="p1">**</bpt>Transferts de paiement<ept id="p1">**</ept>, cliquez sur <bpt id="p2">**</bpt>Fichier retourné - fournisseur<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>Select the method of payment that has the required settings for ISO20022 files, and then click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sélectionnez le mode de paiement incluant les paramètres requis pour les fichiers ISO20022, puis cliquez sur <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>Select the file format that you plan to import, and then click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sélectionnez le format de fichier que vous envisagez d'importer, puis cliquez sur <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>Specify the required parameters and the path of the file, and then click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Indiquez les paramètres requis et le chemin d'accès du fichier, puis cliquez sur <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>If you're importing the pain.002 file, the status of vendor payment lines is updated, based the information in the imported file.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si vous importez le fichier pain.002, le statut des lignes de paiement fournisseur est mis à jour, selon les informations du fichier importé.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>If you're importing the camt.054 file, you should specify the following additional parameters:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si vous importez le fichier camt.054, vous devez spécifier les paramètres supplémentaires suivants :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source><bpt id="p1">**</bpt>Fee ID<ept id="p1">**</ept> – Enter the Fee ID which will define new payment fee lines, which will be created on the Vendor payment journal line if a charge amount is present in the camt.054 file.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>ID frais<ept id="p1">**</ept> : Entrez l'ID frais qui détermine les nouvelles lignes de frais de paiement, qui sont créées sur la ligne de journal des paiements fournisseur si un montant de frais est présent dans le fichier camt.054.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source><bpt id="p1">**</bpt>New journal name<ept id="p1">**</ept> and <bpt id="p2">**</bpt>New journal description<ept id="p2">**</ept> – Enter the name and description of the journal that processed transactions will be transferred to.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Nouveau nom de journal<ept id="p1">**</ept> et <bpt id="p2">**</bpt>Description nouveau journal<ept id="p2">**</ept> : Entrez le nom et la description du journal vers lequel les transactions traitées seront transférées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>After the transfer, new voucher numbers should be assigned in the new journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Après le transfert, de nouveaux n° document doivent être affectés dans le nouveau journal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source><bpt id="p1">**</bpt>Import direct debit transactions<ept id="p1">**</ept> – Set this option to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept> if outgoing direct debits must be imported into the Vendor payment journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Importer des transactions de débits directs<ept id="p1">**</ept> : Définissez cette option sur <bpt id="p2">**</bpt>Oui<ept id="p2">**</ept> si les débits directs sortants doivent être importés dans le journal des paiements fournisseur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source><bpt id="p1">**</bpt>Journal name<ept id="p1">**</ept> – Define a new journal name for the imported direct debit transactions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Nom de journal<ept id="p1">**</ept> : Attribuez un nouveau nom de journal pour les transactions de débit direct importées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source><bpt id="p1">**</bpt>Settle transactions<ept id="p1">**</ept> – Set this option to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept> if imported vendor payments must be settled with invoices that are found in the system.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Régler les transactions<ept id="p1">**</ept> : Définissez cette option sur <bpt id="p2">**</bpt>Oui<ept id="p2">**</ept> si les paiements fournisseur importés doivent être réglés avec des factures qui se trouvent dans le système.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>You can view the imported information on the <bpt id="p1">**</bpt>Payment transfers<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez consultez les informations importées sur l'écran <bpt id="p1">**</bpt>Transferts de paiement<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Additional details</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Détails supplémentaires</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>When you import a format configuration from LCS, you import the whole configuration tree which means that the Model and Model mapping configurations are included.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsque vous importez une configuration de format à partir de LCS, vous importez toute l'arborescence de configuration, ce qui signifie que les configurations Modèle et Mise en correspondance des modèles sont incluses.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>In the Payment model starting from version 8, the mappings are located in separate ER configurations in the solution tree (Payment model mapping 1611, Payment model mapping to destination ISO20022, etc).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans le modèle de paiement commençant à partir de la version 8, les mises en correspondance sont situées dans des configurations ER distinctes dans l'arborescence de la solution (mise en correspondance du modèle de paiement 1611, mise en correspondance du modèle de paiement avec la destination ISO20022, etc.)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>There are many different payment formats under one model (Payment model), thus separate mapping handling is a key for easy solution maintenance.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il existe plusieurs formats de paiement dans un modèle (modèle de paiement), une gestion séparée des mises en correspondance est donc primordiale pour faciliter la maintenance de la solution.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>For example, consider this scenario: you use ISO20022 payments to generate credit transfer files and then you import the return messages from the bank.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par exemple, prenez le scénario suivant : vous utilisez les paiements ISO20022 pour générer des fichiers de transfert de crédit, puis vous importez les messages retournés par la banque.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>In this scenario, you should use the following configurations:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans ce scénario, vous devez utiliser les configurations suivantes :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source><bpt id="p1">**</bpt>Payment model<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Modèle de paiement<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source><bpt id="p1">**</bpt>Payment model mapping 1611<ept id="p1">**</ept> – this mapping will be used to generate the export file</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Mise en correspondance du modèle de paiement 1611<ept id="p1">**</ept> – Cette mise en correspondance sera utilisée pour générer le fichier d'exportation</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source><bpt id="p1">**</bpt>Payment model mapping to destination ISO20022<ept id="p1">**</ept> – this configuration includes all mappings which will be used to import the data (“to destination” mapping direction)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Mise en correspondance du modèle de paiement avec la destination ISO20022<ept id="p1">**</ept> – Cette configuration inclut toutes les mises en correspondance qui seront utilisées pour importer les données (direction de mise en correspondance « vers la destination »)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source><bpt id="p1">**</bpt>ISO20022 Credit transfer<ept id="p1">**</ept> – this configuration includes a format component that is responsible for export file generation (pain.001) based on the Payment model mapping 1611, as well as a format to model mapping component which will be used together with Payment model mapping to destination ISO20022 to register exported payments in the system for further import purposes (import in CustVendProcessedPayments technical table)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Transfert de crédit ISO20022<ept id="p1">**</ept> – Cette configuration inclut un composant de format qui doit générer le fichier d'exportation (pain.001) en fonction de la mise en correspondance du modèle de paiement 1611, ainsi qu'un composant de mise en correspondance du format avec le modèle qui sera utilisé avec la mise en correspondance du modèle de paiement avec la destination ISO20022 pour enregistrer les paiements exportés dans le système à des fins d'importation (importation dans la table technique CustVendProcessedPayments)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source><bpt id="p1">**</bpt>ISO20022 Credit transfer (CE)<ept id="p1">**</ept>, where CE correspond to country extension – derived format to the ISO20022 Credit transfer with the same structure and with certain country-specific differences</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Transfert de crédit ISO20022 (CE)<ept id="p1">**</ept>, où CE correspond à l'extension de pays – Format dérivé du transfert du crédit ISO20022 avec la même structure et certaines différences spécifiques au pays</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source><bpt id="p1">**</bpt>Pain.002<ept id="p1">**</ept> – this format will be used together with the Payment model mapping to destination ISO20022 in order to import the pain.002 file into vendor payments transfers journal</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Pain.002<ept id="p1">**</ept> – Ce format est utilisé avec la mise en correspondance du modèle de paiement avec la destination ISO20022 pour importer le fichier pain.002 dans le journal des transferts de paiements fournisseur</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source><bpt id="p1">**</bpt>Camt.054<ept id="p1">**</ept> – this format will be used together with the Payment model mapping to destination ISO20022 to import the camt.054 file into vendor payments transfers journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Camt.054<ept id="p1">**</ept> – Ce format est utilisé avec la mise en correspondance du modèle de paiement avec la destination ISO20022 pour importer le fichier camt.054 dans le journal des transferts de paiements fournisseur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>The same format configuration will be used in customer payments import functionality, but the different mapping will be used in the Payment model mapping to destination ISO20022 configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La même configuration de format sera utilisée dans la fonctionnalité d'importation de paiements client, mais une mise en correspondance différente sera utilisée dans la configuration de la mise en correspondance du modèle de paiement avec la destination ISO20022.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>For more information about Electronic reporting, refer to <bpt id="p1">[</bpt>Electronic reporting overview<ept id="p1">](../../dev-itpro/analytics/general-electronic-reporting.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour plus d'informations sur les états électronique, voir, <bpt id="p1">[</bpt>Vue d'ensemble des états électroniques<ept id="p1">](../../dev-itpro/analytics/general-electronic-reporting.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>Additional resources</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ressources supplémentaires</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source><bpt id="p1">[</bpt>Create and export vendor payments using ISO20022 payment format<ept id="p1">](./tasks/create-export-vendor-payments-iso20022-payment-format.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Créer et exporter des paiements fournisseur à l'aide du format de paiement ISO20022<ept id="p1">](./tasks/create-export-vendor-payments-iso20022-payment-format.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source><bpt id="p1">[</bpt>Import ISO20022 credit transfer configuration<ept id="p1">](./tasks/import-iso20022-credit-transfer-configuration.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Importer la configuration du virement ISO20022<ept id="p1">](./tasks/import-iso20022-credit-transfer-configuration.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source><bpt id="p1">[</bpt>Import ISO20022 direct debit configuration<ept id="p1">](./tasks/import-iso20022-direct-debit-configuration.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Importer la configuration du débit direct ISO20022<ept id="p1">](./tasks/import-iso20022-direct-debit-configuration.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source><bpt id="p1">[</bpt>Set up company bank accounts for ISO20022 credit transfers<ept id="p1">](./tasks/set-up-company-bank-accounts-iso20022-credit-transfers.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Paramétrer les comptes bancaires de société pour les virements ISO20022<ept id="p1">](./tasks/set-up-company-bank-accounts-iso20022-credit-transfers.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source><bpt id="p1">[</bpt>Set up company bank accounts for ISO20022 direct debits<ept id="p1">](./tasks/set-up-company-bank-accounts-iso20022-direct-debits.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Paramétrer les comptes bancaires de société pour les débits directs ISO20022<ept id="p1">](./tasks/set-up-company-bank-accounts-iso20022-direct-debits.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source><bpt id="p1">[</bpt>Set up customers and customer bank accounts for ISO20022 direct debits<ept id="p1">](./tasks/set-up-bank-accounts-iso20022-direct-debits.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Paramétrer les clients et les comptes bancaires du client pour les débits directs ISO20022<ept id="p1">](./tasks/set-up-bank-accounts-iso20022-direct-debits.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source><bpt id="p1">[</bpt>Set up method of payment for ISO20022 credit transfer<ept id="p1">](./tasks/set-up-method-payment-iso20022-credit-transfer.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Paramétrer le mode de paiement pour les virements ISO20022<ept id="p1">](./tasks/set-up-method-payment-iso20022-credit-transfer.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source><bpt id="p1">[</bpt>Set up method of payment for ISO20022 direct debit<ept id="p1">](./tasks/setup-method-payment-iso20022-direct-debit.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Paramétrer le mode de paiement pour le débit direct ISO20022<ept id="p1">](./tasks/setup-method-payment-iso20022-direct-debit.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source><bpt id="p1">[</bpt>Set up vendors and vendor bank accounts for ISO20022 credit transfers<ept id="p1">](./tasks/set-up-vendor-iso20022-credit-transfers.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Paramétrer les fournisseurs et les comptes bancaires fournisseur pour les virements ISO20022<ept id="p1">](./tasks/set-up-vendor-iso20022-credit-transfers.md)</ept></target></trans-unit>
      </group>
    </body>
  </file>
</xliff>