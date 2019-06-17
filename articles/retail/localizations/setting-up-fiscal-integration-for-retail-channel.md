<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="setting-up-fiscal-integration-for-retail-channel.md" target-language="fr-FR">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>setting-up-fiscal-integration-for-retail-channel.bcaf21.fda94e77480b9d9455fc0e214e43772ab2921f2d.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>fda94e77480b9d9455fc0e214e43772ab2921f2d</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>ffc37f7c2a63bada3055f37856a30424040bc9a3</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/16/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\localizations\setting-up-fiscal-integration-for-retail-channel.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Set up the fiscal integration for Retail channels</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Paramétrer l'intégration fiscale pour les canaux de vente au détail</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic provides guidelines for setting up the fiscal integration functionality for Retail channels.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette rubrique donne des instructions pour paramétrer la fonctionnalité d'intégration fiscale pour les canaux de vente au détail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Set up the fiscal integration for Retail channels</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Paramétrer l'intégration fiscale pour les canaux de vente au détail</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>Introduction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Introduction</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>This topic provides guidelines for setting up the fiscal integration functionality for Retail channels.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette rubrique donne des instructions pour paramétrer la fonctionnalité d'intégration fiscale pour les canaux de vente au détail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>For more information about the fiscal integration, see <bpt id="p1">[</bpt>Overview of fiscal integration for Retail channels<ept id="p1">](fiscal-integration-for-retail-channel.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour plus d'informations sur l'intégration fiscale, voir <bpt id="p1">[</bpt>Vue d'ensemble de l'intégration fiscale pour les canaux de vente au détail<ept id="p1">](fiscal-integration-for-retail-channel.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>The process of setting up the fiscal integration includes the following tasks:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le processus de paramétrage de l'intégration fiscale inclut les tâches générales suivantes :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Configure fiscal connectors that represent fiscal devices or services that are used for fiscal registration purposes, such as fiscal printers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">configuration des connecteurs fiscaux qui représentent les périphériques ou les services fiscaux utilisés à des fins d'enregistrement fiscal, comme les imprimantes fiscales par exemple ;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Configure document providers that generate fiscal documents that will be registered in fiscal devices or services by fiscal connectors.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">configuration des fournisseurs de documents fiscaux qui seront enregistrés dans les périphériques ou services fiscaux par les connecteurs fiscaux ;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Configure the fiscal registration process that defines a sequence of fiscal registration steps and the fiscal connectors and fiscal document providers that are used for each step.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">configuration du processus d'enregistrement fiscal qui définit une séquence des étapes d'enregistrement fiscal ainsi que les connecteurs fiscaux et les fournisseurs de documents fiscaux utilisés pour chaque étape ;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Assign the fiscal registration process to point of sale (POS) functionality profiles.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">affectation du processus d'enregistrement fiscal aux profils de fonctionnalité du PDV ;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>Assign connector technical profiles to hardware profiles.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">affectation des profils techniques de connecteur aux profils matériels.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Set up a fiscal registration process</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurer un processus d'enregistrement fiscal</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Before you use the fiscal integration functionality, you should configure the following settings.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Avant d'utiliser la fonctionnalité d'intégration fiscale, vous devez configurer les paramètres suivants :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Update retail parameters.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mettez à jour les paramètres de vente au détail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>On the <bpt id="p1">**</bpt>Retail shared parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>General<ept id="p2">**</ept> tab, set the <bpt id="p3">**</bpt>Enable fiscal integration<ept id="p3">**</ept> option to <bpt id="p4">**</bpt>Yes<ept id="p4">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Paramètres partagés de la vente au détail<ept id="p1">**</ept>, sous l'onglet <bpt id="p2">**</bpt>Général<ept id="p2">**</ept>, définissez l'option <bpt id="p3">**</bpt>Activer l'intégration fiscale<ept id="p3">**</ept> sur <bpt id="p4">**</bpt>Oui<ept id="p4">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>On the <bpt id="p1">**</bpt>Number sequences<ept id="p1">**</ept> tab, define the number sequences for the following references:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sous l'onglet <bpt id="p1">**</bpt>Souches de numéros<ept id="p1">**</ept>, définissez les souches de numéros pour les références suivantes :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Fiscal technical profile number</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Numéro du profil technique fiscal</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Fiscal connector group number</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Numéro du groupe de connecteurs fiscaux</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>Registration process number</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Numéro du processus d'enregistrement</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>On the <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> page, define the number sequence for the fiscal functional profile number.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Paramètres de vente au détail<ept id="p1">**</ept>, définissez la souche de numéros pour le numéro de profil fonctionnel fiscal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Number sequences are optional.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les souches de numéros sont facultatives.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Numbers for all fiscal integration entities can be generated either from number sequences or manually.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les numéros pour toutes les entités d'intégration fiscale peuvent être générés depuis les souches de numéros ou manuellement.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Upload configurations of fiscal connectors and fiscal document providers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Téléchargez les configurations des connecteurs fiscaux et des fournisseurs de documents fiscaux.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>A fiscal document provider is responsible for generating fiscal documents that represent retail transactions and events that are registered on the POS in a format that is also used for the interaction with a fiscal device or service.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un fournisseur de documents fiscaux est responsable de la génération des documents fiscaux qui représentent les transactions de vente au détail et les événements enregistrés sur le PDV dans un format également compatible avec un périphérique ou un service fiscal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>For example, a fiscal document provider might generate a representation of a fiscal receipt in an XML format.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par exemple, un fournisseur de documents fiscaux peut générer une représentation de reçu fiscal au format XML.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>A fiscal connector is responsible for the communication with a fiscal device or service.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un connecteur fiscal est responsable de la communication avec un périphérique ou un service fiscal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>For example, a fiscal connector might send a fiscal receipt that a fiscal document provider created in an XML format to a fiscal printer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par exemple, un connecteur fiscal peut envoyer un reçu fiscal qu'un fournisseur de documents fiscaux a créé au format XML vers une imprimante fiscale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>For more details about fiscal integration components, see <bpt id="p1">[</bpt>Fiscal registration process and fiscal integration samples for fiscal devices<ept id="p1">](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour en savoir plus sur les composants de l'intégration fiscale, voir <bpt id="p1">[</bpt>Processus d'enregistrement fiscal et exemples d'intégration fiscale pour les périphériques fiscaux<ept id="p1">](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>On the <bpt id="p1">**</bpt>Fiscal connectors<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Fiscal connectors<ept id="p2">**</ept>), upload an XML configuration for each device or service that you plan to use for fiscal integration purposes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Connecteurs fiscaux<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Paramétrage du canal <ph id="ph2">\&gt;</ph> Intégration fiscale <ph id="ph3">\&gt;</ph> Connecteurs fiscaux<ept id="p2">**</ept>), téléchargez une configuration XML pour chaque périphérique ou service que vous prévoyez d'utiliser à des fins d'intégration fiscale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>By selecting <bpt id="p1">**</bpt>View<ept id="p1">**</ept>, you can view all functional and technical profiles that are related to the current fiscal connector.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En sélectionnant <bpt id="p1">**</bpt>Affichage<ept id="p1">**</ept>, vous pouvez afficher tous les profils fonctionnels et techniques liés au connecteur fiscal actuel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>On the <bpt id="p1">**</bpt>Fiscal document providers<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Fiscal document providers<ept id="p2">**</ept>), upload an XML configuration for each device or service that you plan to use.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Fournisseurs de documents fiscaux<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Paramétrage du canal <ph id="ph2">\&gt;</ph> Intégration fiscale <ph id="ph3">\&gt;</ph> Fournisseurs de documents fiscaux<ept id="p2">**</ept>), téléchargez une configuration XML pour chaque périphérique ou service que vous prévoyez d'utiliser à des fins d'intégration fiscale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>By selecting <bpt id="p1">**</bpt>View<ept id="p1">**</ept>, you can view all functional profiles that are related to the current fiscal document provider.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En sélectionnant <bpt id="p1">**</bpt>Affichage<ept id="p1">**</ept>, vous pouvez afficher tous les profils fonctionnels et techniques liés au fournisseur de documents fiscaux actuel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>For examples of configurations of fiscal connectors and fiscal document providers, see <bpt id="p1">[</bpt>Fiscal integration samples in the Retail SDK<ept id="p1">](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-retail-sdk)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour des exemples de configuration des connecteurs fiscaux et fournisseurs de documents fiscaux, voir <bpt id="p1">[</bpt>Exemples fiscaux d'intégration dans le SDK de Retail<ept id="p1">](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-retail-sdk)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>Data mapping is considered part of a fiscal document provider.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La mise en correspondance des données est considérée comme faisant partie du fournisseur de documents fiscaux.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>To set up different data mappings for the same connector (for example, state-specific regulations), you should create different fiscal document providers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour paramétrer différentes mises en correspondance de données pour le même connecteur (par exemple, les réglementations spécifiques à chaque état), vous devez créer différents fournisseurs de documents fiscaux.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>Create connector functional profiles and connector technical profiles.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Créez des profils fonctionnels de connecteur et des profils techniques de connecteur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>On the <bpt id="p1">**</bpt>Connector functional profiles<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Connector functional profiles<ept id="p2">**</ept>), create a connector functional profile for each combination of a fiscal connector and a fiscal document provider that is related to this fiscal connector.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Profils fonctionnels du connecteur<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Paramétrage du canal <ph id="ph2">\&gt;</ph> Intégration fiscale <ph id="ph3">\&gt;</ph> Profils fonctionnels du connecteur<ept id="p2">**</ept>), créez un profil fonctionnel du connecteur pour chaque combinaison de connecteur fiscal et de fournisseur de documents fiscaux associée à ce connecteur fiscal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Select a connector name.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sélectionnez un nom de connecteur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Select a document provider.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sélectionnez un fournisseur de document.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>You can change the data mapping parameters in a connector functional profile.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez changer les paramètres de mise en correspondance des données dans un profil fonctionnel de connecteur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>To restore the default parameters that are defined in the fiscal document provider configuration, select <bpt id="p1">**</bpt>Update<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour rétablir les paramètres par défaut définis dans la configuration du fournisseur de documents fiscaux, sélectionnez <bpt id="p1">**</bpt>Mettre à jour<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source><bpt id="p1">**</bpt>Examples<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Exemples<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>Format</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Formats</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>Example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exemple</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source><bpt id="p1">**</bpt>VAT rates settings<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Paramètres de taux de TVA<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>value : VATrate</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">valeur : VATrate</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>1 : 2000, 2 : 1800</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">1 : 2 000, 2 : 1 800</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source><bpt id="p1">**</bpt>VAT codes mapping<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Mise en correspondance des codes de TVA<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>VATcode : value</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">VATcode : valeur</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>vat20 : 1, vat18 : 2</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">vat20 : 1, vat18 : 2</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source><bpt id="p1">**</bpt>Tender types mapping<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Mise en correspondance des types de modes de paiement<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>TenderType : value</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">TenderType : Valeur</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>Cash : 1, Card : 2</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Disponibilités : 1, Carte : 2</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>Connector functional profiles are company-specific.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les profils fonctionnels du connecteur sont spécifiques à la société.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>If you plan to use the same combination of a fiscal connector and a fiscal document provider in different companies, you should create a connector functional profile for each company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si vous prévoyez d'utiliser la même combinaison d'un connecteur fiscal et d'un fournisseur de documents fiscaux dans différentes sociétés, vous devez créer un profil fonctionnel de connecteur pour chaque entreprise.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>On the <bpt id="p1">**</bpt>Connector technical profiles<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Connector technical profiles<ept id="p2">**</ept>), create a connector technical profile for each fiscal connector.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Profils techniques du connecteur<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Paramétrage du canal <ph id="ph2">\&gt;</ph> Intégration fiscale <ph id="ph3">\&gt;</ph> Profils techniques du connecteur<ept id="p2">**</ept>), créez un profil technique du connecteur pour chaque connecteur fiscal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Select a connector name.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sélectionnez un nom de connecteur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Select a connector type.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sélectionnez un type de connecteur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>For devices that are connected to a Hardware station, select <bpt id="p1">**</bpt>Local<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les périphériques associés à une station matérielle, sélectionnez <bpt id="p1">**</bpt>Local<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>Only local connectors are currently supported.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Seuls les connecteurs locaux sont actuellement pris en charge.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>Parameters on the <bpt id="p1">**</bpt>Device<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Settings<ept id="p2">**</ept> tabs in a connector technical profile can be changed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les paramètres des onglets <bpt id="p1">**</bpt>Périphérique<ept id="p1">**</ept> et <bpt id="p2">**</bpt>Paramètres<ept id="p2">**</ept> dans un profil technique du connecteur peuvent être modifiés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>To restore the default parameters that are defined in the fiscal connector configuration, select <bpt id="p1">**</bpt>Update<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour rétablir les paramètres par défaut définis dans la configuration du connecteur fiscal, sélectionnez <bpt id="p1">**</bpt>Mettre à jour<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>While a new version of an XML configuration is loaded, you receive a message that states that the current fiscal connector or fiscal document provider is already being used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Même si une nouvelle version d'une configuration XML est téléchargée, vous recevez un message stipulant que le connecteur fiscal actuel ou le fournisseur de documents fiscaux est déjà utilisé.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>This procedure doesn't override manual changes that were previously made in connector functional profiles and connector technical profiles.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette procédure ne remplace pas les modifications manuelles qui ont déjà été apportées aux profils fonctionnels du connecteur et des profils techniques du connecteur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>To apply the default set of parameters from a new configuration, on the <bpt id="p1">**</bpt>Connector functional profiles<ept id="p1">**</ept> page or the <bpt id="p2">**</bpt>Connector technical profiles<ept id="p2">**</ept> page, select <bpt id="p3">**</bpt>Update<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour appliquer l'ensemble des paramètres par défaut depuis une nouvelle configuration, sur la page <bpt id="p1">**</bpt>Profils fonctionnels du connecteur<ept id="p1">**</ept> ou sur la page <bpt id="p2">**</bpt>Profils techniques du connecteur<ept id="p2">**</ept>, sélectionnez <bpt id="p3">**</bpt>Mettre à jour<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>Create fiscal connector groups.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Créez des groupes de connecteurs fiscaux.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>A fiscal connector group combines functional profiles of fiscal connectors that perform identical functions and are used at the same step of a fiscal registration process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un groupe de connecteurs fiscaux associe des profils fonctionnels des connecteurs fiscaux exécutant des fonctions identiques et utilisés à la même étape d'un processus d'enregistrement fiscal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>For example, if several fiscal printer models can be used in a retail store, fiscal connectors for those fiscal printers can be combined in a fiscal connector group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par exemple, si plusieurs modèles fiscaux d'impression peuvent être utilisés dans un magasin de vente au détail, les connecteurs fiscaux pour ces imprimantes fiscales peuvent être associés en un groupe de connecteurs fiscaux.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>On the <bpt id="p1">**</bpt>Fiscal connector group<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Fiscal connector groups<ept id="p2">**</ept>), create a new fiscal connector group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Groupe de connecteurs fiscaux<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Paramétrage du canal <ph id="ph2">\&gt;</ph> Intégration fiscale <ph id="ph3">\&gt;</ph> Groupes de connecteurs fiscaux<ept id="p2">**</ept>), créez un nouveau groupe de connecteurs fiscaux.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>Add functional profiles to the connector group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ajoutez des profils fonctionnels dans le groupe de connecteurs.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>On the <bpt id="p1">**</bpt>Functional profiles<ept id="p1">**</ept> tab, select <bpt id="p2">**</bpt>Add<ept id="p2">**</ept>, and select a profile number.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur l'onglet <bpt id="p1">**</bpt>Profils fonctionnels<ept id="p1">**</ept>, sélectionnez <bpt id="p2">**</bpt>Ajouter<ept id="p2">**</ept>, puis sélectionnez un numéro de profil.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Each fiscal connector in a connector group can only have one functional profile.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Chaque connecteur fiscal au sein d'un groupe de connecteurs ne peut avoir qu'un profil fonctionnel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>To suspend use of the functional profile, set the <bpt id="p1">**</bpt>Disable<ept id="p1">**</ept> option to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour interrompre l'utilisation du profil fonctionnel, définissez <bpt id="p1">**</bpt>Désactiver<ept id="p1">**</ept> sur <bpt id="p2">**</bpt>Oui<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>This change affects only the current connector group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette modification affecte uniquement le groupe de connecteurs actuel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>You can continue to use the same functional profile in other connector groups.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez continuer à utiliser le même profil fonctionnel dans d'autres groupes de connecteurs.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>Create a fiscal registration process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Créez un processus d'enregistrement fiscal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>A fiscal registration process is defined by the sequence of registration steps and the connector group that is used for each step.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un processus d'enregistrement fiscal est défini par la séquence des étapes d'enregistrement et du groupe de connecteurs utilisé dans chaque étape.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>On the <bpt id="p1">**</bpt>Fiscal registration process<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Fiscal registration processes<ept id="p2">**</ept>), create a new record for each unique process of fiscal registration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Processus d'enregistrement fiscal<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Paramétrage du canal <ph id="ph2">\&gt;</ph> Intégration fiscale <ph id="ph3">\&gt;</ph> Processus d'intégration fiscale<ept id="p2">**</ept>), créez un enregistrement pour chaque processus unique d'enregistrement fiscal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Add registration steps to the process:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ajoutez les étapes d'enregistrement au processus :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Select <bpt id="p1">**</bpt>Add<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sélectionnez <bpt id="p1">**</bpt>Ajouter<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>Select a fiscal connector type.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sélectionnez un type de connecteur fiscal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>In the <bpt id="p1">**</bpt>Group number<ept id="p1">**</ept> field, select an appropriate fiscal connector group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans le champ <bpt id="p1">**</bpt>Numéro du groupe<ept id="p1">**</ept>, sélectionnez un groupe de connecteurs fiscaux approprié.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>Assign entities of the fiscal registration process to POS profiles.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Affectez les entités du processus d'enregistrement fiscal aux profils du PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>On the <bpt id="p1">**</bpt>POS functionality profiles<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> POS setup <ph id="ph3">\&gt;</ph> POS profiles <ph id="ph4">\&gt;</ph> Functionality profiles<ept id="p2">**</ept>), assign the fiscal registration process to a POS functionality profile.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Profils de fonctionnalité du PDV<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Paramétrage du canal <ph id="ph2">\&gt;</ph> Paramétrage du PDV <ph id="ph3">\&gt;</ph> Profils du PDV <ph id="ph4">\&gt;</ph> Profils de fonctionnalité<ept id="p2">**</ept>), affectez le processus d'enregistrement fiscal à un profil de fonctionnalité du PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>Select <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept>, and then, on the <bpt id="p2">**</bpt>Fiscal registration process<ept id="p2">**</ept> tab, in the <bpt id="p3">**</bpt>Process number<ept id="p3">**</ept> field, select a process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sélectionnez <bpt id="p1">**</bpt>Modifier<ept id="p1">**</ept>, puis, dans l'onglet <bpt id="p2">**</bpt>Processus d'enregistrement fiscal<ept id="p2">**</ept>, dans le champ <bpt id="p3">**</bpt>Numéro du processus<ept id="p3">**</ept>, sélectionnez un processus.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>On the <bpt id="p1">**</bpt>POS hardware profile<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> POS setup <ph id="ph3">\&gt;</ph> POS profiles <ph id="ph4">\&gt;</ph> Hardware profiles<ept id="p2">**</ept>), assign connector technical profiles to a hardware profile.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Profil matériel de PDV<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Paramétrage du canal <ph id="ph2">\&gt;</ph> Paramétrage du PDV <ph id="ph3">\&gt;</ph> Profils du PDV <ph id="ph4">\&gt;</ph> Profils du matériel<ept id="p2">**</ept>), affectez des profils techniques de connecteur à un profil matériel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>Select <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept>, add a line on the <bpt id="p2">**</bpt>Fiscal peripherals<ept id="p2">**</ept> tab, and then, in the <bpt id="p3">**</bpt>Profile number<ept id="p3">**</ept> field, select a connector technical profile.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sélectionnez <bpt id="p1">**</bpt>Modifier<ept id="p1">**</ept>, ajoutez une ligne à l'onglet <bpt id="p2">**</bpt>Périphériques fiscaux<ept id="p2">**</ept>, puis dans le champ <bpt id="p3">**</bpt>Numéro de profil<ept id="p3">**</ept>, sélectionnez un profil technique de connecteur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>You can add several technical profiles to the same hardware profile.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez ajouter plusieurs profils techniques à un profil matériel identique.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>However, a hardware profile or POS functionality profile should have only one intersection with any fiscal connector group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Toutefois, un profil matériel ou un profil de fonctionnalité de PDV doit avoir une seule intersection avec n'importe quel groupe de connecteurs fiscaux.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>The fiscal registration flow is defined by the fiscal registration process and also by some parameters of fiscal integration components: the Commerce runtime extension for the fiscal document provider and the Hardware station extension for the fiscal connector.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le flux d'enregistrement fiscal est défini par le processus d'enregistrement fiscal ainsi que par certains paramètres de composants d'intégration fiscale : l'extension Commerce runtime (CRT) pour le fournisseur de documents fiscaux et l'extension de la station matérielle pour le connecteur fiscal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>The subscription of events and transactions to fiscal registration is predefined in the fiscal document provider.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'abonnement des événements et des transactions à l'enregistrement fiscal est prédéfini dans le fournisseur de documents fiscaux.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>The fiscal document provider is also responsible for identifying the fiscal connector that is used for fiscal registration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le fournisseur de documents fiscaux est également responsable de l'identification du connecteur fiscal utilisé pour l'enregistrement fiscal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>It matches the connector functional profiles that are included in the fiscal connector group that is specified for the current step of the fiscal registration process with the connector technical profile that is assigned to the hardware profile of the Hardware station that the POS is paired to.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il correspond aux profils fonctionnels du connecteur inclus dans le groupe de connecteurs fiscaux spécifié pour l'étape actuelle du processus d'enregistrement fiscal avec le profil technique du connecteur attribué au profil matériel de la station matérielle à laquelle le PDV est relié.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>The fiscal document provider uses the data mapping settings from the fiscal document provider configuration to transform transaction/event data such as taxes and payments while a fiscal document is generated.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le fournisseur de documents fiscaux utilise les paramètres de mise en correspondance des données depuis la configuration du fournisseur de documents fiscaux pour transformer les données d'événement/de transaction, tels que les impôts et les paiements, tandis qu'un document fiscal est généré.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>When the fiscal document provider generates a fiscal document, the fiscal connector can either send it to the fiscal device as is, or parse it and transform it into a sequence of commands of the device application programming interface (API), depending on how the communication is handled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsque le fournisseur de documents fiscaux génère un document fiscal, le connecteur fiscal peut soit l'envoyer au périphérique fiscal en l'état, soit l'analyser et le transformer en une séquence de commandes de l'API du périphérique, selon la manière dont la communication est gérée.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>On the <bpt id="p1">**</bpt>Fiscal registration process<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Fiscal registration processes<ept id="p2">**</ept>), select <bpt id="p3">**</bpt>Validate<ept id="p3">**</ept> to validate the fiscal registration process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Processus d'enregistrement fiscal<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Paramétrage du canal <ph id="ph2">\&gt;</ph> Intégration fiscale <ph id="ph3">\&gt;</ph> Processus d'intégration fiscale<ept id="p2">**</ept>), sélectionnez <bpt id="p3">**</bpt>Valider<ept id="p3">**</ept> pour valider le processus d'enregistrement fiscal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>We recommend that you run this type of validation in the following cases:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nous vous recommandons d'exécuter ce type de validation dans les cas suivants :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>After you've completed all the settings for a new registration process, including when you assign registration processes to POS functionality profiles and hardware profiles.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Après avoir exécuté tous les paramètres pour un nouveau processus d'enregistrement, y compris l'affectation des processus d'enregistrement aux profils de fonctionnalité du PDV et aux profils matériels.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>After you make changes to an existing fiscal registration process, and those changes might cause a different fiscal connector to be selected at runtime (for example, if you change the connector group for a fiscal registration process step, enable a connector functional profile in a connector group, or add a new connector functional profile to a connector group).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Après avoir apporté des changements à un processus d'enregistrement fiscal, et une fois que ces changements sont susceptibles d'entraîner la sélection d'un autre connecteur fiscal lors de l'exécution (par exemple, si vous changez le groupe de connecteurs pour une étape de processus d'enregistrement fiscal, activez un profil fonctionnel de connecteur dans un groupe de connecteurs, ou ajoutez un nouveau profil fonctionnel de connecteur à un groupe de connecteurs).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>After you make changes in the assignment of connector technical profiles to hardware profiles.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez ensuite apporter des modifications à l'affectation des profils techniques du connecteur aux profils matériels.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>On the <bpt id="p1">**</bpt>Distribution schedule<ept id="p1">**</ept> page, run the <bpt id="p2">**</bpt>1070<ept id="p2">**</ept> and <bpt id="p3">**</bpt>1090<ept id="p3">**</ept> jobs to transfer data to the channel database.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Programme de distribution<ept id="p1">**</ept>, exécutez les tâches <bpt id="p2">**</bpt>1070<ept id="p2">**</ept> et <bpt id="p3">**</bpt>1090<ept id="p3">**</ept> pour transférer des données vers la base de données des canaux.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>Set up fiscal texts for discounts</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurer les textes fiscaux pour les remises</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>In some cases, a special text must be printed on a fiscal receipt if a discount is applied.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans certains cas, un texte spécifique doit être imprimé sur un reçu fiscal si une remise est appliquée.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>You can set up fiscal texts for discounts on the <bpt id="p1">**</bpt>Fiscal connector group<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Fiscal connector groups<ept id="p2">**</ept>).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez définir les textes fiscaux pour les remises sur la page <bpt id="p1">**</bpt>Groupe de connecteurs fiscaux<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Paramétrage du canal <ph id="ph2">\&gt;</ph> Intégration fiscale <ph id="ph3">\&gt;</ph> Groupes de connecteurs fiscaux<ept id="p2">**</ept>).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>For manual discounts that are applied at the POS, you should set a fiscal text for the info code or info code group that is specified as the <bpt id="p1">**</bpt>Product discount<ept id="p1">**</ept> info code in the POS functionality profile.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les remises manuelles appliquées au PDV, vous devez configurer un texte fiscal pour le code d'informations ou le groupe de codes d'informations spécifié comme code d'informations <bpt id="p1">**</bpt>Remise de produit<ept id="p1">**</ept> dans le profil de fonctionnalité du PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>On the <bpt id="p1">**</bpt>Fiscal connector group<ept id="p1">**</ept> page, select <bpt id="p2">**</bpt>Text for fiscal receipt<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Groupe de connecteurs fiscaux<ept id="p1">**</ept>, sélectionnez <bpt id="p2">**</bpt>Texte du reçu fiscal<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>On the <bpt id="p1">**</bpt>Info codes<ept id="p1">**</ept> tab, select <bpt id="p2">**</bpt>Add<ept id="p2">**</ept>, and select an info code or info code group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans l'onglet <bpt id="p1">**</bpt>Codes info<ept id="p1">**</ept>, sélectionnez <bpt id="p2">**</bpt>Ajouter<ept id="p2">**</ept>, puis sélectionnez un code info ou un groupe de codes info.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>In the <bpt id="p1">**</bpt>Info code number<ept id="p1">**</ept>, select a value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans <bpt id="p1">**</bpt>Numéro de code info<ept id="p1">**</ept>, sélectionnez une valeur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>In the <bpt id="p1">**</bpt>Subcode number<ept id="p1">**</ept> field, select a value if a subcode is required for the selected info code.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans le champ <bpt id="p1">**</bpt>Numéro de sous-code<ept id="p1">**</ept>, sélectionnez une valeur si un sous-code est requis pour le code info sélectionné.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>In the <bpt id="p1">**</bpt>Text for fiscal receipt<ept id="p1">**</ept> field, specify a fiscal text that should be printed on a fiscal receipt.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans le champ <bpt id="p1">**</bpt>Texte du reçu fiscal<ept id="p1">**</ept>, spécifiez un texte fiscal qui doit être imprimé sur un reçu fiscal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Set the <bpt id="p1">**</bpt>Print user input on fiscal receipt<ept id="p1">**</ept> option to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept> to override the text on a fiscal receipt with information that a user manually enters at the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Définissez l'option <bpt id="p1">**</bpt>Imprimer l'entrée utilisateur sur le reçu fiscal<ept id="p1">**</ept> sur <bpt id="p2">**</bpt>Oui<ept id="p2">**</ept> pour remplacer le texte d'un reçu fiscal avec les informations qu'un utilisateur renseigne manuellement dans le système du PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>This option applies only to info codes that have an input type of <bpt id="p1">**</bpt>Text<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette option s'applique uniquement aux codes info dont la saisie est de type <bpt id="p1">**</bpt>Texte<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>You can specify a fiscal text for several info codes to support scenarios where info code groups, linked info codes, and triggered info codes are used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez préciser un texte fiscal afin que plusieurs codes info soient compatibles avec les scénarios où les groupes de codes info, codes info associés et codes info déclenchés sont utilisés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>In these scenarios, the fiscal receipt will contain the fiscal texts from all info codes that are linked to the transaction line where the discount was applied.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans ces scénarios, le reçu fiscal contient les textes fiscaux depuis tous les codes info associés à la ligne de transaction lorsque la remise est appliquée.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>For channel-specific discounts, you should define a fiscal text for the discount ID.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les remises spécifiques au canal, vous devez définir un texte fiscal pour l'ID de remise.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>On the <bpt id="p1">**</bpt>Fiscal connector group<ept id="p1">**</ept> page, select <bpt id="p2">**</bpt>Text for fiscal receipt<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Groupe de connecteurs fiscaux<ept id="p1">**</ept>, sélectionnez <bpt id="p2">**</bpt>Texte du reçu fiscal<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>On the <bpt id="p1">**</bpt>Discounts<ept id="p1">**</ept> tab, select <bpt id="p2">**</bpt>Add<ept id="p2">**</ept>, and select a discount ID.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans l'onglet <bpt id="p1">**</bpt>Remises<ept id="p1">**</ept>, sélectionnez <bpt id="p2">**</bpt>Ajouter<ept id="p2">**</ept>, puis sélectionnez un ID de remise.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>In the <bpt id="p1">**</bpt>Text for fiscal receipt<ept id="p1">**</ept> field, specify a fiscal text that should be printed on a fiscal receipt.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans le champ <bpt id="p1">**</bpt>Texte du reçu fiscal<ept id="p1">**</ept>, spécifiez un texte fiscal qui doit être imprimé sur un reçu fiscal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source>If several discounts are applied to the same transaction line, the fiscal receipt will contain fiscal texts from all discounts that are linked to those transaction line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si plusieurs remises sont appliquées à la même ligne de transaction, le reçu fiscal contient les textes fiscaux de toutes les remises associées à cette ligne de transaction.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>Set error handling settings</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Définir les paramètres de traitement des erreurs</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>The error handling options that are available in the fiscal integration are set in the fiscal registration process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les options de traitement des erreurs disponibles dans l'intégration fiscale sont définies dans le processus d'enregistrement fiscal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>For more information about error handling in the fiscal integration, see <bpt id="p1">[</bpt>Error handling<ept id="p1">](fiscal-integration-for-retail-channel.md#error-handling)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour plus d'informations sur le traitement des erreurs de l'intégration fiscale, voir <bpt id="p1">[</bpt>Gestion des erreurs<ept id="p1">](fiscal-integration-for-retail-channel.md#error-handling)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>On the <bpt id="p1">**</bpt>Fiscal registration process<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Fiscal registration processes<ept id="p2">**</ept>), you can set the following parameters for each step of the fiscal registration process:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Processus d'enregistrement fiscal<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Paramétrage du canal <ph id="ph2">\&gt;</ph> Intégration fiscale <ph id="ph3">\&gt;</ph> Processus d'intégration fiscale<ept id="p2">**</ept>), vous pouvez définir les paramètres suivants pour chaque étape du processus d'enregistrement fiscal :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source><bpt id="p1">**</bpt>Allow skip<ept id="p1">**</ept> – This parameter enables the <bpt id="p2">**</bpt>Skip<ept id="p2">**</ept> option in the error handling dialog box.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Autoriser Ignorer<ept id="p1">**</ept> – Ce paramètre active l'option <bpt id="p2">**</bpt>Ignorer<ept id="p2">**</ept> dans la boîte de dialogue de traitement des erreurs.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source><bpt id="p1">**</bpt>Allow mark as registered<ept id="p1">**</ept> – This parameter enables the <bpt id="p2">**</bpt>Mark as registered<ept id="p2">**</ept> option in the error handling dialog box.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Autoriser Marquer comme enregistrée<ept id="p1">**</ept> – Ce paramètre active l'option <bpt id="p2">**</bpt>Marquer comme enregistrée<ept id="p2">**</ept> dans la boîte de dialogue de traitement des erreurs.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source><bpt id="p1">**</bpt>Continue on error<ept id="p1">**</ept> – If this parameter is enabled, the fiscal registration process can continue on the POS register if the fiscal registration of a transaction or event fails.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Continuer lors d'erreurs<ept id="p1">**</ept> : si ce paramètre est activé, le processus d'enregistrement fiscal peut se poursuivre sur l'appareil de PDV si l'enregistrement fiscal d'une transaction ou d'un événement échoue.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>Otherwise, to run the fiscal registration of the next transaction or event, the operator must retry the failed fiscal registration, skip it, or mark the transaction or event as registered.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans le cas contraire, pour exécuter l'enregistrement fiscal de la transaction ou de l'événement suivant, l'opérateur doit renouveler la tentative d'enregistrement fiscal échoué, l'ignorer, ou marquer la transaction ou l'événement comme enregistré.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>For more information, see <bpt id="p1">[</bpt>Optional fiscal registration<ept id="p1">](fiscal-integration-for-retail-channel.md#optional-fiscal-registration)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour plus d'informations, voir <bpt id="p1">[</bpt>Enregistrement fiscal facultatif<ept id="p1">](fiscal-integration-for-retail-channel.md#optional-fiscal-registration)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>If the <bpt id="p1">**</bpt>Continue on error<ept id="p1">**</ept> parameter is enabled, the <bpt id="p2">**</bpt>Allow skip<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Allow mark as registered<ept id="p3">**</ept> parameters are automatically disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si le paramètre <bpt id="p1">**</bpt>Continuer lors d'erreurs<ept id="p1">**</ept> est activé, les paramètres <bpt id="p2">**</bpt>Autoriser Ignorer<ept id="p2">**</ept> et <bpt id="p3">**</bpt>Autoriser Marquer comme enregistré<ept id="p3">**</ept> sont automatiquement désactivés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>The <bpt id="p1">**</bpt>Skip<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Mark as registered<ept id="p2">**</ept> options in the error handling dialog box require the <bpt id="p3">**</bpt>Allow skip registration or mark as registered<ept id="p3">**</ept> permission.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les options <bpt id="p1">**</bpt>Ignorer<ept id="p1">**</ept> et <bpt id="p2">**</bpt>Marquer comme enregistré<ept id="p2">**</ept> dans la boîte de dialogue de traitement des erreurs nécessite l'autorisation <bpt id="p3">**</bpt>Autoriser Ignorer l'enregistrement ou Marquer comme enregistré<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>Therefore, on the <bpt id="p1">**</bpt>Permission groups<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Employees <ph id="ph2">\&gt;</ph> Permission groups<ept id="p2">**</ept>), enable the <bpt id="p3">**</bpt>Allow skip registration or mark as registered<ept id="p3">**</ept> permission.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par conséquent, sur la page <bpt id="p1">**</bpt>Groupes d'autorisations<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Employés <ph id="ph2">\&gt;</ph> Groupes d'autorisations<ept id="p2">**</ept>), activez l'autorisation <bpt id="p3">**</bpt>Autoriser Ignorer l'enregistrement ou Marquer comme enregistrée<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>The <bpt id="p1">**</bpt>Skip<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Mark as registered<ept id="p2">**</ept> options let operators enter additional information when fiscal registration fails.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les options <bpt id="p1">**</bpt>Ignorer<ept id="p1">**</ept> et <bpt id="p2">**</bpt>Marquer comme enregistrée<ept id="p2">**</ept> permettent aux opérateurs de renseigner des informations supplémentaires lorsque l'enregistrement fiscal échoue.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>To make this functionality available, you should specify the <bpt id="p1">**</bpt>Skip<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Mark as registered<ept id="p2">**</ept> info codes on a fiscal connector group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour rendre cette fonctionnalité disponible, vous devez spécifier les codes info <bpt id="p1">**</bpt>Ignorer<ept id="p1">**</ept> et <bpt id="p2">**</bpt>Marquer comme enregistrée<ept id="p2">**</ept> sur un groupe de connecteurs fiscaux.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>The information that operators enter is then saved as an info code transaction that is linked to the fiscal transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les informations que les opérateurs saisissent sont ensuite enregistrées comme transaction de code info liée à la transaction fiscale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source>For more details about info codes, see <bpt id="p1">[</bpt>Info codes and info code groups<ept id="p1">](../info-codes-retail.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour plus d'informations sur les codes info, voir <bpt id="p1">[</bpt>Codes info et groupes de codes info<ept id="p1">](../info-codes-retail.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>The <bpt id="p1">**</bpt>Product<ept id="p1">**</ept> trigger function isn't supported for the info codes that are used for <bpt id="p2">**</bpt>Skip<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Mark as registered<ept id="p3">**</ept> in fiscal connector groups.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La fonction de déclenchement <bpt id="p1">**</bpt>Produit<ept id="p1">**</ept> n'est pas prise en charge pour les codes info utilisés pour <bpt id="p2">**</bpt>Ignorer<ept id="p2">**</ept> et <bpt id="p3">**</bpt>Marquer comme enregistrée<ept id="p3">**</ept> dans les groupes de connecteurs fiscaux.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>On the <bpt id="p1">**</bpt>Fiscal connector group<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Info codes<ept id="p2">**</ept> tab, select info codes or info code groups in the <bpt id="p3">**</bpt>Skip<ept id="p3">**</ept> and <bpt id="p4">**</bpt>Mark as registered<ept id="p4">**</ept> fields.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Groupe de connecteurs fiscaux<ept id="p1">**</ept>, sous l'onglet <bpt id="p2">**</bpt>Codes info<ept id="p2">**</ept>, sélectionnez les codes info ou les groupes de codes info dans les champs <bpt id="p3">**</bpt>Ignorer<ept id="p3">**</ept> et <bpt id="p4">**</bpt>Marquer comme enregistrée<ept id="p4">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>One fiscal document and one non-fiscal document can be generated on any step of a fiscal registration process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un document fiscal et un document non fiscal peuvent être générés à chaque étape d'un processus fiscal d'enregistrement.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>A fiscal document provider extension identifies every type of transaction or event as related to fiscal or non-fiscal documents.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une extension de fournisseur de documents fiscaux identifie chaque type de transaction ou d'événement comme associé à des documents fiscaux ou non fiscaux.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>The error handling feature applies only to fiscal documents.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La fonctionnalité de gestion des erreurs s'applique uniquement aux documents fiscaux.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source><bpt id="p1">**</bpt>Fiscal document<ept id="p1">**</ept> – A mandatory document that should be registered successfully (for example, a fiscal receipt).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Document fiscal<ept id="p1">**</ept> – Désigne un document obligatoire qui doit être enregistré avec succès (par exemple, un reçu fiscal).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source><bpt id="p1">**</bpt>Non-fiscal document<ept id="p1">**</ept> – A supplementary document for the transaction or event (for example, a gift card slip).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Document non fiscal<ept id="p1">**</ept> – Désigne un document supplémentaire pour la transaction ou l'événement (par exemple, un bordereau de carte cadeau).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="244">
          <source>If the operator must be able to continue to process the current operation (for example, creation or finalization of a transaction) after a health check error occurs, you should enable the <bpt id="p1">**</bpt>Allow skip health check error<ept id="p1">**</ept> permission on the <bpt id="p2">**</bpt>Permission groups<ept id="p2">**</ept> page (<bpt id="p3">**</bpt>Retail <ph id="ph1">\&gt;</ph> Employees <ph id="ph2">\&gt;</ph> Permission groups<ept id="p3">**</ept>).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si l'opérateur doit pouvoir continuer le traitement de l'opération en cours (par exemple, la création ou la finalisation d'une transaction) après la survenue d'une erreur de contrôle d'intégrité, vous devez activer l'autorisation <bpt id="p1">**</bpt>Autoriser d'ignorer l'erreur du contrôle d'intégrité<ept id="p1">**</ept> dans la page <bpt id="p2">**</bpt>Groupes d'autorisations<ept id="p2">**</ept> (<bpt id="p3">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Employés <ph id="ph2">\&gt;</ph> Groupes d'autorisations<ept id="p3">**</ept>).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="245">
          <source>For more information about the health check procedure, see <bpt id="p1">[</bpt>Fiscal registration health check<ept id="p1">](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour plus d'informations sur la procédure de contrôle d'intégrité, voir <bpt id="p1">[</bpt>Contrôle d'intégrité d'enregistrement fiscal<ept id="p1">](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="246">
          <source>Set up fiscal X/Z reports from the POS</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurer les états X/Z fiscaux depuis le PDV</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="247">
          <source>To enable fiscal X/Z reports to be run from the POS, you should add new buttons to a POS layout.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour activer les états X/Z fiscaux à exécuter depuis le PDV, vous devez ajouter de nouveaux boutons à la mise en page d'un écran de PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="248">
          <source>On the <bpt id="p1">**</bpt>Button grids<ept id="p1">**</ept> page, follow the instructions in <bpt id="p2">[</bpt>Add a custom operation button to the POS layout in Retail headquarters<ept id="p2">](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters)</ept> to install the designer and update a POS layout.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Groupes de boutons<ept id="p1">**</ept>, suivez les instructions d'installation dans <bpt id="p2">[</bpt>Ajouter un bouton d'opération personnalisé à la mise en page d'un écran de PDV dans Retail Siège<ept id="p2">](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters)</ept> pour installer le concepteur et mettre à jour la mise en page d'un écran de PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="249">
          <source>Select the layout to update.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Permet de sélectionner la mise en page à mettre à jour.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="250">
          <source>Add a new button, and set the <bpt id="p1">**</bpt>Print fiscal X<ept id="p1">**</ept> button property.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ajoutez un nouveau bouton, puis définissez la propriété de bouton <bpt id="p1">**</bpt>Imprimer X fiscal<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="251">
          <source>Add a new button, and set the <bpt id="p1">**</bpt>Print fiscal Z<ept id="p1">**</ept> button property.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ajoutez un nouveau bouton, puis définissez la propriété de bouton <bpt id="p1">**</bpt>Imprimer Z fiscal<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="252">
          <source>On the <bpt id="p1">**</bpt>Distribution schedule<ept id="p1">**</ept> page, run the <bpt id="p2">**</bpt>1090<ept id="p2">**</ept> job to transfer changes to the channel database.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Planification de la distribution<ept id="p1">**</ept>, exécutez la tâche <bpt id="p2">**</bpt>1090<ept id="p2">**</ept> pour transférer les changements vers la base de données des canaux.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="253">
          <source>Enable manual execution of postponed fiscal registration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Activer l'exécution manuelle d'un enregistrement fiscal reporté</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="254">
          <source>To enable manual execution of a postponed fiscal registration, you should add a new button to a POS layout.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour activer l'exécution manuelle d'un enregistrement fiscal reporté, vous devez ajouter un nouveau bouton à la disposition de l'appareil de PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="255">
          <source>On the <bpt id="p1">**</bpt>Button grids<ept id="p1">**</ept> page, follow the instructions in <bpt id="p2">[</bpt>Add a custom operation button to the POS layout in Retail headquarters<ept id="p2">](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters)</ept> to install the designer and update a POS layout.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Groupes de boutons<ept id="p1">**</ept>, suivez les instructions d'installation dans <bpt id="p2">[</bpt>Ajouter un bouton d'opération personnalisé à la mise en page d'un écran de PDV dans Retail Siège<ept id="p2">](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters)</ept> pour installer le concepteur et mettre à jour la mise en page d'un écran de PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="256">
          <source>Select the layout to update.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Permet de sélectionner la mise en page à mettre à jour.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="257">
          <source>Add a new button, and set the <bpt id="p1">**</bpt>Complete fiscal registration process<ept id="p1">**</ept> button property.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ajoutez un nouveau bouton, puis définissez la propriété du bouton <bpt id="p1">**</bpt>Terminer le processus d'enregistrement fiscal<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="258">
          <source>On the <bpt id="p1">**</bpt>Distribution schedule<ept id="p1">**</ept> page, run the <bpt id="p2">**</bpt>1090<ept id="p2">**</ept> job to transfer your changes to the channel database.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans la page <bpt id="p1">**</bpt>Programme de distribution<ept id="p1">**</ept>, exécutez la tâche <bpt id="p2">**</bpt>1090<ept id="p2">**</ept> pour transférer vos modifications vers la base de données des canaux.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>