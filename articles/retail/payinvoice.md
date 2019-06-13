<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="payinvoice.md" target-language="fr-FR">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>payinvoice.758282.b7132dc9b3c78fa04fcfc38ea72b5678ad08deb2.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>b7132dc9b3c78fa04fcfc38ea72b5678ad08deb2</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/15/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\payinvoice.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Set up pay invoice scenarios</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Paramétrer des scénarios de règlement de facture</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes how to configure Dynamics 365 for Retail to support various scenarios relating to invoice payments.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette rubrique décrit la procédure de configuration de Dynamics 365 for Retail pour prendre en charge différents scénarios relatifs aux règlements de facture.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Set up pay invoice scenarios</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Paramétrer des scénarios de règlement de facture</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>The Pay invoice functionality in Dynamics 365 for Retail has been expanded to support:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La fonctionnalité Payer la facture de Dynamics 365 for Retail a été développée pour prendre en charge ce qui suit :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>Payoff of multiple sales order invoices in a single POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le règlement de plusieurs factures de commande client dans une transaction de point de vente unique.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>Payment of various customer invoice types including free text invoices, project-based invoices, and credit notes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le paiement de différents types de facture client, y compris des factures financières, des factures basées sur des projets et des avoirs.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>To enable these scenarios, the functionality profile for stores must be configured as outlined in below.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour activer ces scénarios, le profil de fonctionnalité pour les magasins doit être configuré, comme indiqué ci-dessous.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Go to <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> POS setup <ph id="ph3">\&gt;</ph> POS profiles <ph id="ph4">\&gt;</ph> Functionality profiles<ept id="p1">**</ept> and select a profile that's linked to the stores that you want to make the changes for.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Accédez à <bpt id="p1">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Paramétrage du canal <ph id="ph2">\&gt;</ph> Paramétrage Point de vente <ph id="ph3">\&gt;</ph> Profils Point de vente <ph id="ph4">\&gt;</ph> Profils de fonctionnalité<ept id="p1">**</ept> et sélectionnez un profil associé au magasin auquel vous souhaitez apporter des modifications.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>On the <bpt id="p1">**</bpt>Functions<ept id="p1">**</ept> tab, configure the following parameters as needed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans l'onglet <bpt id="p1">**</bpt>Fonctions<ept id="p1">**</ept>, configurez les paramètres suivants selon les besoins.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source><bpt id="p1">**</bpt>Sales order invoice<ept id="p1">**</ept> – Select <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept> to allow users to pay one or more sales order-based invoices in a single POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Facture de commande client<ept id="p1">**</ept> : Sélectionnez <bpt id="p2">**</bpt>Oui<ept id="p2">**</ept> pour autoriser les utilisateurs à régler une ou plusieurs factures basées sur une commande client dans une transaction de point de vente unique.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source><bpt id="p1">**</bpt>Free text invoice<ept id="p1">**</ept> – Select <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept> to allow users to pay one or more free text-based invoices in a single POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Facture financière<ept id="p1">**</ept> : Sélectionnez <bpt id="p2">**</bpt>Oui<ept id="p2">**</ept> pour autoriser les utilisateurs à régler une ou plusieurs factures financières dans une transaction de point de vente unique.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source><bpt id="p1">**</bpt>Project invoice<ept id="p1">**</ept> – Select <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept> to allow users to pay one or more project-based invoices in a single POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Facture de projet<ept id="p1">**</ept> : Sélectionnez <bpt id="p2">**</bpt>Oui<ept id="p2">**</ept> pour autoriser les utilisateurs à régler une ou plusieurs factures de projet dans une transaction de point de vente unique.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source><bpt id="p1">**</bpt>Sales order credit note<ept id="p1">**</ept> – Select <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept> to allow users to settle multiple sales order-based credit notes against open invoices or process a refund to the customer for an open credit note.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Commande client - Avoir<ept id="p1">**</ept> : Sélectionnez <bpt id="p2">**</bpt>Oui<ept id="p2">**</ept> pour autoriser les utilisateurs à régler plusieurs avoirs basés sur des commandes dans le cadre des factures en cours ou pour rembourser un avoir en cours à un client.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Payment or settlement of partial amounts is not yet supported.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le paiement ou le règlement des montants partiels n'est pas encore pris en charge.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>