<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="custom-fields-mobile.md" target-language="fr-FR">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-d915bc8" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>custom-fields-mobile.2a9e5e.4343c875da05641c57b7784bf52f1c814dd26d20.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>4343c875da05641c57b7784bf52f1c814dd26d20</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>19859d8566a8c7840066b2c10c6b08b67f1b83f4</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>06/04/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\financials\project-management\custom-fields-mobile.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Implement custom fields for the Microsoft Dynamics 365 Project Timesheet mobile app on iOS and Android</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Mettre en œuvre des champs personnalisés pour l'application mobile Microsoft Dynamics 365 Project Timesheet sur IOS et Android</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic provides common patterns for using extensions to implement custom fields.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cette rubrique fournit des modèles courants pour l'utilisation des extensions pour mettre en œuvre des champs personnalisés.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Implement custom fields for the Microsoft Dynamics 365 Project Timesheet mobile app on iOS and Android</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Mettre en œuvre des champs personnalisés pour l'application mobile Microsoft Dynamics 365 Project Timesheet sur IOS et Android</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>This topic provides common patterns for using extensions to implement custom fields.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Cette rubrique fournit des modèles courants pour l'utilisation des extensions pour mettre en œuvre des champs personnalisés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>The following topics are covered:</source><target logoport:matchpercent="82" state="translated" state-qualifier="fuzzy-match">Les rubriques suivantes sont couvertes :</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>The various data types that the custom field framework supports</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Les différents types de données que la structure de champ personnalisé prend en charge</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>How to show read-only or editable fields on timesheet entries, and save user-provided values back to the database</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Comment afficher des champs en lecture seule ou modifiables sur les entrées de feuille de temps, et sauvegarder les valeurs fournies par l'utilisateur dans la base de données</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>How to show read-only fields on the timesheet header</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Comment afficher des champs en lecture seule sous l'en-tête de feuille de temps</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>How to integrate other custom business logic to enter default values in fields and do additional validation</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Comment intégrer une autre logique métier personnalisée pour entrer des valeurs par défaut dans les champs et effectuer un contrôle supplémentaire</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Audience</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Public</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>This topic is intended for developers who are integrating their custom fields into the Microsoft Dynamics 365 Project Timesheet mobile application that is available for Apple iOS and Google Android.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cette rubrique est prévue pour les développeurs qui intègrent leurs champs personnalisés dans l'application mobile Microsoft Dynamics 365 Project Timesheet disponible pour Apple IOS et Google Android.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>The assumption is that readers are familiar with X++ development and project timesheet functionality.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Le présupposé est que des lecteurs sont au fait du développement X++ et de la fonctionnalité de feuille de temps de projet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Data contract – TSTimesheetCustomField X++ class</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Contrat de données – classe X++ TSTimesheetCustomField</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>The <bpt id="p1">**</bpt>TSTimesheetCustomField<ept id="p1">**</ept> class is the X++ data contract class that represents information about a custom field for timesheet functionality.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">La classe <bpt id="p1">**</bpt>TSTimesheetCustomField<ept id="p1">**</ept> est la classe de contrat de données X++ qui représente des informations sur un champ personnalisé pour la fonctionnalité de feuille de temps.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Lists of the custom field objects are passed on both the TSTimesheetDetails data contract and the TSTimesheetEntry data contract to show custom fields in the mobile app.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Les listes des objets de champ personnalisés sont transmises au contrat de données TSTimesheetDetails et au contrat de données TSTimesheetEntry pour afficher les champs personnalisés dans l'application mobile.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source><bpt id="p1">**</bpt>TSTimesheetDetails<ept id="p1">**</ept> - The timesheet header contract.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>TSTimesheetDetails<ept id="p1">**</ept> - Le contrat d'en-tête de feuille de temps.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source><bpt id="p1">**</bpt>TSTimesheetEntry<ept id="p1">**</ept> - The timesheet transaction contract.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>TSTimesheetEntry<ept id="p1">**</ept> - Le contrat de transaction de feuille de temps.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Groups of these objects that have the same project information and <bpt id="p1">**</bpt>timesheetLineRecId<ept id="p1">**</ept> value constitute a line.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Les groupes de ces objets avec les mêmes informations de projet et la valeur <bpt id="p1">**</bpt>timesheetLineRecId<ept id="p1">**</ept> constituent une ligne.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>fieldBaseType (Types)</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">fieldBaseType (types)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>The <bpt id="p1">**</bpt>FieldBaseType<ept id="p1">**</ept> property on the <bpt id="p2">**</bpt>TsTimesheetCustom<ept id="p2">**</ept> object determines the type of the field that appears in the app.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">La propriété <bpt id="p1">**</bpt>FieldBaseType<ept id="p1">**</ept> sur l'objet <bpt id="p2">**</bpt>TsTimesheetCustom<ept id="p2">**</ept> détermine le type de champ qui apparaît dans l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>The following <bpt id="p1">**</bpt>Types<ept id="p1">**</ept> values that are supported.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Les valeurs <bpt id="p1">**</bpt>Types<ept id="p1">**</ept> suivantes qui sont prises en charge.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Types value</source><target logoport:matchpercent="81" state="translated" state-qualifier="fuzzy-match">Valeur de types</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Type</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Type</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Notes</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Notes</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>0</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">0</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>String (and Enum)</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Chaîne (et énumération)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>The field appears as a text field.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Le champ apparaît comme champ de texte.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>1</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">1</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Integer</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Entier</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>The value is shown as a number without decimal places.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">La valeur est affichée comme nombre sans décimales.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>2</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">2</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Real</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Réel</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>The value is shown as a number that has decimal places.</source><target logoport:matchpercent="84" state="translated" state-qualifier="fuzzy-match">La valeur est affichée comme nombre avec décimales.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>To show the real value as a currency in the app, use the <bpt id="p1">**</bpt>fieldExtenededType<ept id="p1">**</ept> property.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Pour afficher la valeur réelle comme devise dans l'application, utilisez la propriété <bpt id="p1">**</bpt>fieldExtenededType<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>You can use the <bpt id="p1">**</bpt>numberOfDecimals<ept id="p1">**</ept> property to set the number of decimal places that are shown.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Vous pouvez utiliser la propriété <bpt id="p1">**</bpt>numberOfDecimals<ept id="p1">**</ept> pour définir le nombre de décimales à afficher.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>3</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">3</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>Date</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Date</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>Date formats are determined by the user's <bpt id="p1">**</bpt>Date, times, and number format<ept id="p1">**</ept> setting that is specified under <bpt id="p2">**</bpt>Language and country/region preference<ept id="p2">**</ept> in <bpt id="p3">**</bpt>User options<ept id="p3">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Les formats de date sont déterminés par le paramètre <bpt id="p1">**</bpt>Date, périodes et format de numéro<ept id="p1">**</ept> de l'utilisateur qui est spécifié sous <bpt id="p2">**</bpt>Préférences de langue et paramètres locaux<ept id="p2">**</ept> dans <bpt id="p3">**</bpt>Options utilisateur<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>4</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">4</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Boolean</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Booléen</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>15</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">15</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>GUID</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">GUID</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>16</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">16</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>Int64</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Int64</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>If the <bpt id="p1">**</bpt>stringOptions<ept id="p1">**</ept> property isn't provided on the <bpt id="p2">**</bpt>TSTimesheetCustomField<ept id="p2">**</ept> object, a free-text field is provided to the user.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Si la propriété <bpt id="p1">**</bpt>stringOptions<ept id="p1">**</ept> n'est pas fournie dans l'objet <bpt id="p2">**</bpt>TSTimesheetCustomField<ept id="p2">**</ept>, un champ de texte libre est fourni à l'utilisateur.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>The <bpt id="p1">**</bpt>stringLength<ept id="p1">**</ept> property can be used to set the maximum string length that users can enter.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">La propriété <bpt id="p1">**</bpt>stringLength<ept id="p1">**</ept> peut être utilisée pour définir la longueur maximale de chaîne que les utilisateurs peuvent entrer.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>If the <bpt id="p1">**</bpt>stringOptions<ept id="p1">**</ept> property is provided on the <bpt id="p2">**</bpt>TSTimesheetCustomField<ept id="p2">**</ept> object, those list elements are the only values that users can select by using option buttons (radio buttons).</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Si la propriété <bpt id="p1">**</bpt>stringOptions<ept id="p1">**</ept> est indiquée dans l'objet <bpt id="p2">**</bpt>TSTimesheetCustomField<ept id="p2">**</ept>, ces éléments de liste sont les seules valeurs que les utilisateurs peuvent sélectionner à l'aide des boutons d'option (cases d'options).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>In this case, the string field can act as an enum value for the purpose of user entry.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Dans ce cas, le champ de chaîne peut agir de valeur d'énumération destinée à l'entrée utilisateur.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>To save the value to the database as an enum, manually map the string value back to the enum value before you save to the database by using chain of command (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Pour enregistrer la valeur dans la base de données comme énumération, mettez en correspondance manuellement la valeur de chaîne avec la valeur d'énumération avant d'enregistrer dans la base de données à l'aide de la chaîne de la commande (voir la section « Utiliser la chaîne de commande sur la classe TSTimesheetEntryService pour enregistrer une entrée de feuille de temps de l'application dans la base de données » plus loin dans cette rubrique pour obtenir un exemple).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>fieldExtendedType (TSCustomFieldExtendedType)</source><target logoport:matchpercent="0" state="translated">fieldExtendedType (TSCustomFieldExtendedType)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>You can use this property to format real values as currency.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Vous pouvez utiliser cette propriété pour mettre en forme des valeurs réelles comme devises.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>This approach is applicable only when the <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> value is <bpt id="p2">**</bpt>Real<ept id="p2">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cette approche s'applique uniquement lorsque la valeur <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> est <bpt id="p2">**</bpt>Réel<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source><bpt id="p1">**</bpt>TSCustomFieldExtendedType:None<ept id="p1">**</ept> – No formatting is applied.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>TSCustomFieldExtendedType:None<ept id="p1">**</ept> – Aucune mise en forme n'est appliquée.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source><bpt id="p1">**</bpt>TSCustomFieldExtendedType::Currency<ept id="p1">**</ept> – Format the value as currency.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>TSCustomFieldExtendedType::Currency<ept id="p1">**</ept> – Mise en forme de la valeur comme devise.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>When currency formatting is active, the <bpt id="p1">**</bpt>stringValue<ept id="p1">**</ept> field can be used pass the currency code that should be shown in the app.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Lorsque la mise en forme comme devises est active, le champ <bpt id="p1">**</bpt>stringValue<ept id="p1">**</ept> peut être utilisée pour transmettre le code devise qui doit être affiché dans l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>The value is a read-only value.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">La valeur est une valeur en lecture seule.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>The <bpt id="p1">**</bpt>realValue<ept id="p1">**</ept> field contains the money amount that should be saved to the database.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Le champ <bpt id="p1">**</bpt>realValue<ept id="p1">**</ept> contient la somme d'argent qui doit être enregistrée dans la base de données.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>fieldSection (TSCustomFieldSection)</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">fieldSection (TSCustomFieldSection)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>You can use this property specify where the custom field should appear in the app.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Vous pouvez utiliser cette propriété pour spécifier à quel emplacement le champ personnalisé doit apparaître dans l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source><bpt id="p1">**</bpt>TSCustomFieldSection::Header<ept id="p1">**</ept> – The field will appear in the <bpt id="p2">**</bpt>View more details<ept id="p2">**</ept> section in the app.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>TSCustomFieldSection::Header<ept id="p1">**</ept> – Le champ apparaît dans la section <bpt id="p2">**</bpt>Afficher plus de détails<ept id="p2">**</ept> de l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>These fields are always read-only.</source><target logoport:matchpercent="83" state="translated" state-qualifier="fuzzy-match">Ces champs sont toujours en lecture seule.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source><bpt id="p1">**</bpt>TSCustomFieldSection::Line<ept id="p1">**</ept> – The field will appear after all the out-of-box line fields on timesheet entries.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>TSCustomFieldSection::Line<ept id="p1">**</ept> – Le champ apparaît après tous les champs de ligne prédéfinis sur les entrées de feuille de temps.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>These fields can be either editable or read-only.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ces champs peuvent être modifiables ou en lecture seule.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>fieldName (FieldNameShort)</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">fieldName (FieldNameShort)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>This property identifies the field when values that the app provides are saved back to the database.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cette propriété identifie le champ lorsque des valeurs que l'application fournit sont enregistrées dans la base de données.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>tableName (TableNameShort)</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">tableName (TableNameShort)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>This property identifies the field when values that the app provides are saved back to the database.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Cette propriété identifie le champ lorsque des valeurs que l'application fournit sont enregistrées dans la base de données.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>isEditable (NoYes)</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">isEditable (NoYes)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>Set this property to <bpt id="p1">**</bpt>Yes<ept id="p1">**</ept> to specify that the field in the timesheet entry section should be editable by users.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Définissez cette propriété sur <bpt id="p1">**</bpt>Oui<ept id="p1">**</ept> pour spécifier que le champ de la section d'entrée de feuille de temps doit être modifié par les utilisateurs.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>Set the property to <bpt id="p1">**</bpt>No<ept id="p1">**</ept> to make the field read-only.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Définissez la propriété sur <bpt id="p1">**</bpt>Non<ept id="p1">**</ept> pour rendre le champ en lecture seule.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>isMandatory (NoYes)</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">isMandatory (NoYes)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>Set this property to <bpt id="p1">**</bpt>Yes<ept id="p1">**</ept> to specify that the field in the timesheet entry section should be mandatory.</source><target logoport:matchpercent="87" state="translated" state-qualifier="fuzzy-match">Définissez cette propriété sur <bpt id="p1">**</bpt>Oui<ept id="p1">**</ept> pour spécifier que le champ de la section d'entrée de feuille de temps doit être obligatoire.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>label (str)</source><target logoport:matchpercent="0" state="translated">label (str)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>This property specifies the label that is shown next the field in the app.</source><target logoport:matchpercent="0" state="translated">Cette propriété spécifie l'étiquette qui s'affiche en regard du champ de l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>stringOptions (List of Strings)</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">stringOptions (liste des chaînes)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>This property is applicable only when <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> is set to <bpt id="p2">**</bpt>String<ept id="p2">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cette propriété s'applique uniquement lorsque <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> est défini sur <bpt id="p2">**</bpt>Chaîne<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>If <bpt id="p1">**</bpt>stringOptions<ept id="p1">**</ept> is set, the string values that are available for selection via option buttons (radio buttons) are specified by the strings in the list.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Si <bpt id="p1">**</bpt>stringOptions<ept id="p1">**</ept> est défini, les valeurs de chaîne disponibles pour la sélection à l'aide des boutons d'option (cases d'options) sont spécifiées par les chaînes dans la liste.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>If no strings are provided, free-text entry in the string field is allowed (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Si aucune chaîne n'est fournie, l'entrée de texte libre est autorisée dans le champ de chaîne (voir la section « Utiliser la chaîne de commande sur la classe TSTimesheetEntryService pour enregistrer une entrée de feuille de temps de l'application dans la base de données » plus loin dans cette rubrique pour obtenir un exemple).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>stringLength (int)</source><target logoport:matchpercent="0" state="translated">stringLength (int)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>This property specifies the maximum length for a string field.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cette propriété spécifie la longueur maximale d'un champ de chaîne.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>It's applicable only when <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> is set to <bpt id="p2">**</bpt>String<ept id="p2">**</ept>.</source><target logoport:matchpercent="79" state="translated" state-qualifier="fuzzy-match">Elle s'applique uniquement lorsque <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> est défini sur <bpt id="p2">**</bpt>Chaîne<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>numberOfDecimals (int)</source><target logoport:matchpercent="0" state="translated">numberOfDecimals (int)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>This property specifies the number of decimal places that are shown for a real field.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cette propriété spécifie le nombre de décimales à afficher pour un champ réel.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>It's applicable only when <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> is set to <bpt id="p2">**</bpt>Real<ept id="p2">**</ept>.</source><target logoport:matchpercent="89" state="translated" state-qualifier="fuzzy-match">Elle s'applique uniquement lorsque <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> est défini sur <bpt id="p2">**</bpt>Réel<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>orderSequence (int)</source><target logoport:matchpercent="0" state="translated">orderSequence (int)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>This property controls the order in which the custom fields are shown in the app when more than one custom field is specified.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cette propriété détermine l'ordre dans lequel les champs personnalisés sont affichés dans l'application lorsque plusieurs champs personnalisés sont spécifiés.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>Fields that have lower numbers are shown first.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Les champs qui ont des nombres plus petits sont affichés en premier.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>booleanValue (boolean)</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">booleanValue (booléen)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>For fields of the <bpt id="p1">**</bpt>Boolean<ept id="p1">**</ept> type, this property passes the Boolean value of the field between the server and the app.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Pour les champs de type <bpt id="p1">**</bpt>Booléen<ept id="p1">**</ept>, cette propriété transmet la valeur booléenne du champ entre le serveur et l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>guidValue (guid)</source><target logoport:matchpercent="0" state="translated">guidValue (guid)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>For fields of the <bpt id="p1">**</bpt>GUID<ept id="p1">**</ept> type, this property passes the globally unique identifier (GUID) value of the field between the server and the app.</source><target logoport:matchpercent="81" state="translated" state-qualifier="fuzzy-match">Pour les champs de type <bpt id="p1">**</bpt>GUID<ept id="p1">**</ept>, cette propriété transmet la valeur de l'identificateur global unique (GUID) du champ entre le serveur et l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>int64Value (int64)</source><target logoport:matchpercent="0" state="translated">int64Value (int64)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>For fields of the <bpt id="p1">**</bpt>Int64<ept id="p1">**</ept> type, this property passes the int64 value of the field between the server and the app.</source><target logoport:matchpercent="89" state="translated" state-qualifier="fuzzy-match">Pour les champs de type <bpt id="p1">**</bpt>Int64<ept id="p1">**</ept>, cette propriété transmet la valeur int64 du champ entre le serveur et l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>intValue (int)</source><target logoport:matchpercent="0" state="translated">intValue (int)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>For fields of the <bpt id="p1">**</bpt>Int<ept id="p1">**</ept> type, this property passes the int value of the field between the server and the app.</source><target logoport:matchpercent="92" state="translated" state-qualifier="fuzzy-match">Pour les champs de type <bpt id="p1">**</bpt>Int<ept id="p1">**</ept>, cette propriété transmet la valeur int du champ entre le serveur et l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>realValue (real)</source><target logoport:matchpercent="0" state="translated">realValue (real)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>For fields of the <bpt id="p1">**</bpt>Real<ept id="p1">**</ept> type, this property passes the real value of the field between the server and the app .</source><target logoport:matchpercent="89" state="translated" state-qualifier="fuzzy-match">Pour les champs de type <bpt id="p1">**</bpt>Réel<ept id="p1">**</ept>, cette propriété transmet la valeur réelle du champ entre le serveur et l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>stringValue (str)</source><target logoport:matchpercent="0" state="translated">stringValue (str)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>For fields of the <bpt id="p1">**</bpt>String<ept id="p1">**</ept> type, this property passes the string value of the field between the server and the app.</source><target logoport:matchpercent="89" state="translated" state-qualifier="fuzzy-match">Pour les champs de type <bpt id="p1">**</bpt>Chaîne<ept id="p1">**</ept>, cette propriété transmet la valeur de chaîne du champ entre le serveur et l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>It's also used for fields of the <bpt id="p1">**</bpt>Real<ept id="p1">**</ept> type that are formatted as currency.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Elle est également utilisée pour les champs de type <bpt id="p1">**</bpt>Réel<ept id="p1">**</ept> qui sont mis en forme comme devises.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>For those fields, the property is used to pass the currency code to the app.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Pour ces champs, la propriété est utilisée pour transmettre un code devise à l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>dateValue (date)</source><target logoport:matchpercent="0" state="translated">dateValue (date)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>For fields of the <bpt id="p1">**</bpt>Date<ept id="p1">**</ept> type, this property passes the date value of the field between the server and the app.</source><target logoport:matchpercent="89" state="translated" state-qualifier="fuzzy-match">Pour les champs de type <bpt id="p1">**</bpt>Date<ept id="p1">**</ept>, cette propriété transmet la valeur de date du champ entre le serveur et l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>Show and save a custom field in the timesheet entry section</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Afficher et enregistrer un champ personnalisé dans la section des entrées de feuille de temps</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>Below is a screenshot from the mobile app of a timesheet entry creation.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Voici une capture d'écran de l'application mobile d'une création d'entrée de feuille de temps.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>It shows the out-of-box fields and a custom field in the "Time entry" section called "Test string" with an enum value of "Second option" already set.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Elle affiche les champs prédéfinis et un champ personnalisé dans la chaîne « Entrée de temps » appelée « Chaîne de test » avec une valeur d'énumération « Seconde option » déjà définie.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>Test string custom field in the app</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Champ personnalisé de chaîne de test dans l'application</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>Below is a screenshot from the mobile app of the user selecting one of the enum options available for the "Test string" custom field.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Voici une capture d'écran de l'application mobile de l'utilisateur sélectionnant l'une des options d'énumération disponibles pour le champ personnalisé « Chaîne de test ».</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>The two options are "First option" and "Second option" shown as radio buttons.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Les deux options sont « Première option » et « Seconde option » affichées sous forme de cases d'options.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>The second option is currently selected.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">La seconde option est sélectionnée actuellement.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>Option buttons (radio buttons) for the Test string custom field</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Boutons d'option (cases d'options) du champ personnalisé Chaîne de test</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Extend the TSTimesheetLine table so that it has a custom field</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Étendre la table TSTimesheetLine afin qu'elle dispose d'un champ personnalisé</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>In typical scenarios, it's likely that the data for a custom field in the timesheet entry section will be saved to the TSTimesheetLine table.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Dans les scénarios typiques, il est probable que les données d'un champ personnalisé dans la section des entrées de feuille de temps soient enregistrées dans la table TSTimesheetLine.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>However, other tables can be used if the data can be retrieved based on a TSTimesheetTrans record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Toutefois, d'autres tables peuvent être utilisées si les données peuvent être extraites selon un enregistrement TSTimesheetTrans qui est fourni, ou s'il n'y a pas de contexte spécifique d'enregistrement (par exemple, si le champ est défini en lecture seule dans les paramètres de projet).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>Note that custom fields don't have to have any backing database records.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Notez que les champs personnalisés ne doivent pas avoir d'enregistrements de base de données de sauvegarde.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>They can be dynamically generated based on X++ logic.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ils peuvent être générés dynamiquement selon la logique X++.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>This approach can be useful in read-only scenarios (see the “Use chain of command on the TSTimesheetDetails class, buildCustomFieldListForHeader method to fill in timesheet details” section for an example of dynamically generated custom field values.)</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cette approche peut être utile dans les scénarios en lecture seule (voir la section « Utiliser la chaîne de commande sur la classe TSTimesheetDetails, la méthode buildCustomFieldListForHeader pour renseigner les détails de la feuille de temps » pour obtenir un exemple de valeurs de champ personnalisé générées dynamiquement.)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>Below is a screenshot from Visual Studio of the Application Object Tree.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Voici une capture d'écran Visual Studio de l'arbre d'objets d'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>It shows an extension of the TSTimesheetLine table with the TestLineString field added as a custom field.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Elle présente une extension de la table TSTimesheetLine avec le champ TestLineString ajouté comme champ personnalisé.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source>Line string</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Chaîne de ligne</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the timesheet entry section</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Section Utiliser la chaîne de commande sur la méthode buildCustomFieldList de la classe TSTimesheetSettings pour afficher un champ dans l'entrée de feuille de temps</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>This code controls the display settings for the field in the app.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ce code contrôle les paramètres d'affichage du champ dans l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Par exemple, il contrôle le type de champ, l'étiquette, si le champ est obligatoire, et dans quelle section le champ apparaît.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>The following example shows a string field on time entries.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">L'exemple suivant montre un champ de chaîne sur les entrées de temps.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source>This field has two options, <bpt id="p1">**</bpt>First option<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Second option<ept id="p2">**</ept>, that are available via option buttons (radio buttons).</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ce champ propose deux options, <bpt id="p1">**</bpt>Première option<ept id="p1">**</ept> et <bpt id="p2">**</bpt>Deuxième option<ept id="p2">**</ept>, disponibles via les boutons d'option (cases d'options).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source>The field in the app is associated with the <bpt id="p1">**</bpt>TestLineString<ept id="p1">**</ept> field that is added to the TSTimesheetLine table.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Le champ dans l'application est associé au champ <bpt id="p1">**</bpt>TestLineString<ept id="p1">**</ept> ajouté à la table TSTimesheetLine.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source>Note the use of the <bpt id="p1">**</bpt>TSTimesheetCustomField::newFromMetatdata()<ept id="p1">**</ept> method to simplify the initialization of the custom field properties: <bpt id="p2">**</bpt>fieldBaseType<ept id="p2">**</ept>, <bpt id="p3">**</bpt>tableName<ept id="p3">**</ept>, <bpt id="p4">**</bpt>fieldname<ept id="p4">**</ept>, <bpt id="p5">**</bpt>label<ept id="p5">**</ept>, <bpt id="p6">**</bpt>isEditable<ept id="p6">**</ept>, <bpt id="p7">**</bpt>isMandatory<ept id="p7">**</ept>, <bpt id="p8">**</bpt>stringLength<ept id="p8">**</ept>, and <bpt id="p9">**</bpt>numberOfDecimals<ept id="p9">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Notez l'utilisation de la méthode <bpt id="p1">**</bpt>TSTimesheetCustomField::newFromMetatdata()<ept id="p1">**</ept> pour simplifier l'initialisation des propriétés de champ personnalisées : <bpt id="p2">**</bpt>fieldBaseType<ept id="p2">**</ept>, <bpt id="p3">**</bpt>tableName<ept id="p3">**</ept>, <bpt id="p4">**</bpt>fieldname<ept id="p4">**</ept>, <bpt id="p5">**</bpt>label<ept id="p5">**</ept>, <bpt id="p6">**</bpt>isEditable<ept id="p6">**</ept>, <bpt id="p7">**</bpt>isMandatory<ept id="p7">**</ept>, <bpt id="p8">**</bpt>stringLength<ept id="p8">**</ept>, et <bpt id="p9">**</bpt>numberOfDecimals<ept id="p9">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>You can also set these parameters manually, as you prefer.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Vous pouvez également définir ces paramètres manuellement, comme vous le souhaitez.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>Use chain of command on the buildCustomFieldListForEntry method of the TSTimesheetEntry class to enter values in a timesheet entry</source><target logoport:matchpercent="75" state="translated" state-qualifier="fuzzy-match">Utiliser la chaîne de commande sur la méthode buildCustomFieldListForEntry de la classe TSTimesheetEntry pour entrer des valeurs dans une entrée de feuille de temps</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>The <bpt id="p1">**</bpt>buildCustomFieldListForEntry<ept id="p1">**</ept> method is used to enter values on the saved timesheet lines in the mobile app.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">La méthode <bpt id="p1">**</bpt>buildCustomFieldListForEntry<ept id="p1">**</ept> est utilisée pour entrer des valeurs dans les lignes de feuille de temps enregistrées dans l'application mobile.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>It takes a TSTimesheetTrans record as a parameter.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Elle utilise un enregistrement TSTimesheetTrans comme paramètre.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>Fields from that record can be used to fill in the custom field value in the app.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Les champs de cet enregistrement peuvent être utilisés pour renseigner la valeur du champ personnalisé dans l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Utiliser la chaîne de commande sur la classe TSTimesheetEntryService pour enregistrer une entrée de feuille de temps depuis l'application dans la base de données</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>To save a custom field back to the database in typical usage, you must extend multiple methods:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Pour enregistrer un champ personnalisé dans la base de données dans un usage classique, vous devez étendre plusieurs méthodes :</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>The <bpt id="p1">**</bpt>timesheetLineNeedsUpdating<ept id="p1">**</ept> method is used to determine whether the line record has been changed by the user in the app and must be saved to the database.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">La méthode <bpt id="p1">**</bpt>timesheetLineNeedsUpdating<ept id="p1">**</ept> est utilisée pour déterminer si l'enregistrement de ligne a été modifié par l'utilisateur de l'application et doit être enregistré dans la base de données.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source>If performance isn't a concern, this method can be simplified so that it always returns <bpt id="p1">**</bpt>true<ept id="p1">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Si les performances ne sont pas un problème, cette méthode peut être simplifiée de sorte qu'elle renvoie toujours <bpt id="p1">**</bpt>true<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>The <bpt id="p1">**</bpt>populateTimesheetLineFromEntryDuringCreate<ept id="p1">**</ept> and <bpt id="p2">**</bpt>populateTimesheetLineFromEntryDuringUpdate<ept id="p2">**</ept> methods can be extended so that they enter values in the TSTimesheetLine database record from the TSTimesheetEntry data contract record that is provided.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Les méthodes <bpt id="p1">**</bpt>populateTimesheetLineFromEntryDuringCreate<ept id="p1">**</ept> et <bpt id="p2">**</bpt>populateTimesheetLineFromEntryDuringUpdate<ept id="p2">**</ept> peuvent être étendues afin qu'elles entrent des valeurs dans l'enregistrement de base de données TSTimesheetLine de l'enregistrement de contrat de données TSTimesheetEntry qui est fourni.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>In the example that follows, notice how the mapping between the database field and the entry field is manually done via X++ code.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Dans l'exemple suivant, notez comment la mise en correspondance entre le champ de base de données et le champ d'entrée manuelle est effectuée via un code X++.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>The <bpt id="p1">**</bpt>populateTimesheetWeekFromEntry<ept id="p1">**</ept> method can also be extended if the custom field that is mapped to the <bpt id="p2">**</bpt>TSTimesheetEntry<ept id="p2">**</ept> object must write back to the TSTimesheetLineweek database table.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">La méthode <bpt id="p1">**</bpt>populateTimesheetWeekFromEntry<ept id="p1">**</ept> peut également être étendue si le champ personnalisé qui est mis en correspondance avec l'objet <bpt id="p2">**</bpt>TSTimesheetEntry<ept id="p2">**</ept> doit écrire dans la table de base de données TSTimesheetLineweek.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>The following example saves the <bpt id="p1">**</bpt>firstOption<ept id="p1">**</ept> or <bpt id="p2">**</bpt>secondOption<ept id="p2">**</ept> value that the user selects to the database as a raw string value.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">L'exemple suivant enregistre la valeur <bpt id="p1">**</bpt>firstOption<ept id="p1">**</ept> ou <bpt id="p2">**</bpt>secondOption<ept id="p2">**</ept> que l'utilisateur sélectionne dans la base de données comme valeur de la chaîne brute.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>If the database field is a field of the <bpt id="p1">**</bpt>Enum<ept id="p1">**</ept> type, those values can be manually mapped to an enum value and then saved to an enum field on the database table.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Si le champ de base de données est un champ de type <bpt id="p1">**</bpt>Énumération<ept id="p1">**</ept>, ces valeurs peuvent être manuellement mises en correspondance avec une valeur d'énumération puis enregistrées dans un champ d'énumération de la table de base de données.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source>Show a custom field in the timesheet header section</source><target logoport:matchpercent="75" state="translated" state-qualifier="fuzzy-match">Afficher un champ personnalisé dans la section d'en-tête de feuille de temps</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source>Below is a screenshot from the mobile app of a user viewing a timesheet.</source><target logoport:matchpercent="82" state="translated" state-qualifier="fuzzy-match">Voici une capture d'écran de l'application mobile d'un utilisateur affichant une feuille de temps.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="244">
          <source>The "More information" button has been selected in the upper-right corner to show the "View more details" option.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Le bouton « Informations supplémentaires » a été sélectionné dans l'angle supérieur droit pour afficher l'option « Afficher plus de détails ».</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="245">
          <source>View more details command</source><target logoport:matchpercent="77" state="translated" state-qualifier="fuzzy-match">Commande Afficher plus de détails</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="246">
          <source>Below is a screenshot from the mobile app showing the “More” section of a timesheet.</source><target logoport:matchpercent="75" state="translated" state-qualifier="fuzzy-match">Voici une capture d'écran de l'application mobile affichant la section « Plus » d'une feuille de temps.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="247">
          <source>A custom field called “Utilization rate of this timesheet (computed custom field)” has been added to the timesheet header section.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Un champ personnalisé appelé « Taux d'utilisation de cette feuille de temps (champ personnalisé calculé) » a été ajouté dans la section d'en-tête de feuille de temps.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="248">
          <source>A read-only value of "0.667" is set on the custom field.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Une valeur en lecture seule de « 0,667 » est définie dans le champ personnalisé.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="249">
          <source>More section</source><target logoport:matchpercent="79" state="translated" state-qualifier="fuzzy-match">Section Plus</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="250">
          <source>Extend the TSTimesheetTable table so that it has a custom field</source><target logoport:matchpercent="90" state="translated" state-qualifier="fuzzy-match">Étendre la table TSTimesheetTable afin qu'elle dispose d'un champ personnalisé</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="251">
          <source>In typical scenarios, it's likely that the data for a custom field in the header section will be pulled from the TSTimesheetHeader table.</source><target logoport:matchpercent="82" state="translated" state-qualifier="fuzzy-match">Dans les scénarios typiques, il est probable que les données d'un champ personnalisé dans la section d'en-tête soient extraites de la table TSTimesheetHeader.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="252">
          <source>However, other tables can be used if the data can be retrieved based on a TSTimesheetTable record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</source><target logoport:matchpercent="97" state="translated" state-qualifier="fuzzy-match">Toutefois, d'autres tables peuvent être utilisées si les données peuvent être extraites selon un enregistrement TSTimesheetTable qui est fourni, ou s'il n'y a pas de contexte spécifique d'enregistrement (par exemple, si le champ est défini en lecture seule dans les paramètres de projet).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="253">
          <source>Note that custom fields don't have to have any backing database records.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Notez que les champs personnalisés ne doivent pas avoir d'enregistrements de base de données de sauvegarde.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="254">
          <source>They can be dynamically generated based on X++ logic.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Ils peuvent être générés dynamiquement selon la logique X++.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="255">
          <source>The example that follows shows this approach.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">L'exemple suivant montre cette approche.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="256">
          <source>Fields in the header section are always read-only in the app.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Les champs de la section d'en-tête sont toujours en lecture seule dans l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="257">
          <source>Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the header section</source><target logoport:matchpercent="89" state="translated" state-qualifier="fuzzy-match">Section Utiliser la chaîne de commande sur la méthode buildCustomFieldList de la classe TSTimesheetSettings pour afficher un champ dans l'en-tête</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="258">
          <source>This code controls the display settings for the field in the app.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Ce code contrôle les paramètres d'affichage du champ dans l'application.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="259">
          <source>For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Par exemple, il contrôle le type de champ, l'étiquette, si le champ est obligatoire, et dans quelle section le champ apparaît.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="260">
          <source>The following example shows a computed value in the header section in the app.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">L'exemple suivant montre une valeur calculée dans la section d'en-tête de l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="261">
          <source>Use chain of command on the buildCustomFieldListForHeader method of the TSTimesheetDetails class to fill in timesheet details</source><target logoport:matchpercent="75" state="translated" state-qualifier="fuzzy-match">Utiliser la chaîne de commande sur la méthode buildCustomFieldListForHeader de la classe TSTimesheetDetails pour renseigner des informations dans une feuille de temps</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="262">
          <source>The <bpt id="p1">**</bpt>buildCustomFieldListForHeader<ept id="p1">**</ept> method is used to fill in the timesheet header details in the mobile app.</source><target logoport:matchpercent="71" state="translated" state-qualifier="fuzzy-match">La méthode <bpt id="p1">**</bpt>buildCustomFieldListForHeader<ept id="p1">**</ept> est utilisée pour renseigner des détails de l'en-tête de la feuille de temps dans l'application mobile.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="263">
          <source>It takes a TSTimesheetTable record as a parameter.</source><target logoport:matchpercent="87" state="translated" state-qualifier="fuzzy-match">Elle utilise un enregistrement TSTimesheetTable comme paramètre.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="264">
          <source>Fields from that record can be used to fill in the custom field value in the app.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Les champs de cet enregistrement peuvent être utilisés pour renseigner la valeur du champ personnalisé dans l'application.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="265">
          <source>The following example doesn't read any values from the database.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">L'exemple suivant ne lit aucune valeur de la base de données.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="266">
          <source>Instead, it uses X++ logic to generate a computed value that is then shown in the app.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Au lieu de cela, il utilise la logique X++ pour générer une valeur calculée qui est ensuite affichée dans l'application.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="267">
          <source>Other configurability/extensibility opportunities</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Autres possibilités de configuration/extensibilité</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="268">
          <source>Adding additional validation for the app</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ajout d'un contrôle supplémentaire pour l'application</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="269">
          <source>Existing logic for timesheet functionality at the database level will still work as expected.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">La logique existante pour la fonctionnalité de feuille de temps au niveau de la base de données fonctionne toujours comme prévu.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="270">
          <source>To interrupt the completion of save or submit operations and show a specific error message, you can add <bpt id="p1">**</bpt>throw error("message to user")<ept id="p1">**</ept> to the code via a chain of command extension.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Pour interrompre l'exécution de l'enregistrement ou envoyer des opérations et afficher un message d'erreur spécifique, vous pouvez ajouter <bpt id="p1">**</bpt>throw error("message to user")<ept id="p1">**</ept> au code via une chaîne d'extension de commande.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="271">
          <source>Here are three examples of useful extensible methods:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Voici trois exemples de méthodes extensibles utiles :</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="272">
          <source>If <bpt id="p1">**</bpt>validateWrite<ept id="p1">**</ept> on the TSTimesheetLine table returns <bpt id="p2">**</bpt>false<ept id="p2">**</ept> during a save operation for a timesheet line, an error message is shown in the mobile app.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Si <bpt id="p1">**</bpt>validateWrite<ept id="p1">**</ept> dans la table TSTimesheetLine renvoie <bpt id="p2">**</bpt>false<ept id="p2">**</ept> au cours d'une opération d'enregistrement pour une ligne de feuille de temps, un message d'erreur s'affiche dans l'application mobile.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="273">
          <source>If <bpt id="p1">**</bpt>validateSubmit<ept id="p1">**</ept> on the TSTimesheetTable table returns <bpt id="p2">**</bpt>false<ept id="p2">**</ept> during timesheet submission in the app, an error message is shown to the user.</source><target logoport:matchpercent="72" state="translated" state-qualifier="fuzzy-match">Si <bpt id="p1">**</bpt>validateSubmit<ept id="p1">**</ept> dans la table TSTimesheetTable renvoie <bpt id="p2">**</bpt>false<ept id="p2">**</ept> au cours de l'envoi d'une feuille de temps dans l'application, un message d'erreur s'affiche pour l'utilisateur.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="274">
          <source>Logic that fills in fields (for example, <bpt id="p1">**</bpt>Line Property<ept id="p1">**</ept>) during the <bpt id="p2">**</bpt>insert<ept id="p2">**</ept> method on the TSTimesheetLine table will still run.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">La logique qui renseigne les champs (par exemple, <bpt id="p1">**</bpt>Propriété de ligne<ept id="p1">**</ept>) lors de la méthode <bpt id="p2">**</bpt>insert<ept id="p2">**</ept> dans la table TSTimesheetLine s'exécute toujours.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="275">
          <source>Hiding and marking out-of-box fields as read-only via configuration</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Masquage et marquage des champs prédéfinis comme en lecture seule via la configuration</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="276">
          <source>From the project parameters, you can make out-of-box fields read-only or hidden in the mobile app.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Dans les paramètres de projet, vous pouvez rendre les champs prédéfinis en lecture seule ou les masquer dans l'application mobile.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="277">
          <source>Set the options in the <bpt id="p1">**</bpt>Mobile timesheets<ept id="p1">**</ept> section on the <bpt id="p2">**</bpt>Timesheet<ept id="p2">**</ept> tab of the <bpt id="p3">**</bpt>Project management and accounting parameters<ept id="p3">**</ept> page.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Définissez les options de la section <bpt id="p1">**</bpt>Feuilles de temps mobiles<ept id="p1">**</ept> sur l'onglet <bpt id="p2">**</bpt>Feuille de temps<ept id="p2">**</ept> de la page <bpt id="p3">**</bpt>Paramètres de gestion et comptabilité des projets<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="278">
          <source>Project parameters</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Paramètres de projet</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="279">
          <source>Changing the activities that are available for selection via extensions</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Modification des activités disponibles pour la sélection via les extensions</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="280">
          <source>The activities that are available for selection for a project are filled in via the <bpt id="p1">**</bpt>getActivitiesForProject()<ept id="p1">**</ept> and <bpt id="p2">**</bpt>getActivityQuery()<ept id="p2">**</ept> methods in the <bpt id="p3">**</bpt>TsTimesheetProjectService<ept id="p3">**</ept> class.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Les activités disponibles pour la sélection d'un projet sont renseignées via les méthodes <bpt id="p1">**</bpt>getActivitiesForProject()<ept id="p1">**</ept> et <bpt id="p2">**</bpt>getActivityQuery()<ept id="p2">**</ept> dans la classe <bpt id="p3">**</bpt>TsTimesheetProjectService<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="281">
          <source>You can use chain of command to change this behavior to match your business scenario for the activities that are available for selection for a specific project.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Vous pouvez utiliser une chaîne de commande pour modifier ce comportement en fonction de votre scénario métier pour les activités disponibles pour la sélection pour un projet spécifique.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="282">
          <source>Entering a default project category on timesheet entries</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Entrée d'une catégorie de projet par défaut dans les entrées de feuille de temps</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="283">
          <source>Entry of a default project category on timesheet entries occurs at three levels.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">L'entrée d'une catégorie de projet par défaut dans les entrées de feuille de temps se produit à trois niveaux.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="284">
          <source>You can use chain of command to extend the behavior at any or all of these levels to achieve the desired behavior.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Vous pouvez utiliser la chaîne de commande pour étendre le comportement à tout ou partie de ces niveaux pour obtenir le comportement souhaité.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="285">
          <source>The following hierarchy is used:</source><target logoport:matchpercent="82" state="translated" state-qualifier="fuzzy-match">La hiérarchie utilisée est la suivante :</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="286">
          <source>The app tries to put the default category from the project resource.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">L'application essaie de mettre la catégorie par défaut de la ressource de projet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="287">
          <source>This default category is set in the <bpt id="p1">**</bpt>getCurrentUserResource<ept id="p1">**</ept> and <bpt id="p2">**</bpt>getDelegatedResourcesForCurrentUser<ept id="p2">**</ept> methods in the <bpt id="p3">**</bpt>TSTimesheetSettingsService<ept id="p3">**</ept> class.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cette catégorie par défaut est définie dans les méthodes <bpt id="p1">**</bpt>getCurrentUserResource<ept id="p1">**</ept> et <bpt id="p2">**</bpt>getDelegatedResourcesForCurrentUser<ept id="p2">**</ept> dans la classe <bpt id="p3">**</bpt>TSTimesheetSettingsService<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="288">
          <source>If the default category isn't provided at the project resource level, the app tries to pull it from the project activity.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Si la catégorie par défaut n'est pas fournie au niveau de ressources de projet, l'application essaie de l'extraire de l'activité de projet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="289">
          <source>This default category is set in the <bpt id="p1">**</bpt>getActivitiesForProject<ept id="p1">**</ept> method in the <bpt id="p2">**</bpt>TSTimesheetProjectService<ept id="p2">**</ept> class.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cette catégorie par défaut est définie dans la méthode <bpt id="p1">**</bpt>getActivitiesForProject<ept id="p1">**</ept> de la classe <bpt id="p2">**</bpt>TSTimesheetProjectService<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="290">
          <source>If the default category isn't provided at the project activity level, the default category it taken from the project parameters.</source><target logoport:matchpercent="82" state="translated" state-qualifier="fuzzy-match">Si la catégorie par défaut n'est pas fournie au niveau de l'activité de projet, la catégorie de projet est extraite des paramètres du projet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="291">
          <source>This default category is set in the <bpt id="p1">**</bpt>getProjectDetailsbyRule<ept id="p1">**</ept> method in the <bpt id="p2">**</bpt>TSTimesheetProjectService<ept id="p2">**</ept> class.</source><target logoport:matchpercent="91" state="translated" state-qualifier="fuzzy-match">Cette catégorie par défaut est définie dans la méthode <bpt id="p1">**</bpt>getProjectDetailsbyRule<ept id="p1">**</ept> de la classe <bpt id="p2">**</bpt>TSTimesheetProjectService<ept id="p2">**</ept>.</target>
        </trans-unit>
      </group>
    </body>
  </file>
</xliff>