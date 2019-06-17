<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="configure-account-structures.md" target-language="fr-FR">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-d915bc8" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>configure-account-structures.6e0715.5fbd4b34d09b4ba8e1d34234c8e32268bba18778.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>5fbd4b34d09b4ba8e1d34234c8e32268bba18778</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>aec1dcd44274e9b8d0770836598fde5533b7b569</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>06/03/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\financials\general-ledger\configure-account-structures.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Configure account structures</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurer les structures de compte</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic provides information about account structures and financial dimensions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette rubrique fournit des informations sur les structures de compte et les dimensions financières.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Configure account structures</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurer les structures de compte</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>Account structures use the main account and financial dimensions to create a set of rules that determine the order and values used when entering the account number.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les structures de compte utilisent le compte principal et les dimensions financières pour créer un ensemble de règles qui déterminent l'ordre et les valeurs utilisées lors de la saisie du numéro de compte.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>You can set up as many account structures as you need for your business.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez paramétrer autant de structures de compte que nécessaire pour votre entreprise.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>The account structures are assigned to a company’s ledger setup, so they can be shared.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les structures de compte sont affectées au paramétrage de la comptabilité d'une société, elles peuvent donc être partagées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>When creating an account structure, the maximum number of segments is 11.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lors de la création d'une structure de compte, le nombre maximal de segments est 11.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>If you need more segments than this, thoroughly evaluate your setup and requirements, as it will impact the user experience.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si vous avez besoin de plus de segments, évaluez soigneusement vos paramètres et vos besoins, car l'expérience de l'utilisateur en sera affectée.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Consider if a segment could be derived in a reporting scenario using a hierarchy instead of during data entry, or by using a user-defined field.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Déterminez si un segment peut être dérivé dans un scénario de génération d'états en utilisant une hiérarchie, et non lors de la saisie de données, ou en utilisant un champ défini par l'utilisateur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>For example, if you want to report on location, but you can figure location by department or cost center, you would not need location as a financial dimension.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par exemple, si vous souhaitez générer un état sur l'emplacement, mais vous pouvez déterminer l'emplacement par département ou centre de coût, il n'est pas nécessaire d'utiliser l'emplacement comme dimension financière.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>If after evaluation you do determine more than 11 segments are needed, you can add additional segments using advanced rules.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si, après l'évaluation, vous déterminez que plus de 11 segments sont nécessaires, vous pouvez ajouter des segments supplémentaires à l'aide de règles avancées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>Account structures require the main account.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les structures de compte requièrent le compte principal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>The main account does not need to be the first segment in the structure, but it does identify what account structure is being used during the account number entry.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il n'est pas nécessaire que le compte principal soit le premier segment de la structure, mais il identifie la structure de compte utilisée lors de la saisie du numéro de compte.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Because of this, a main account value can only exist in one structure assigned to the ledger so that they do not overlap.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour cette raison, une valeur de compte principal peut uniquement exister dans une structure affectée à la comptabilité afin d'éviter tout chevauchement.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>After the account structure is identified, the allowed values list is filtered to guide the user through picking only valid dimension values, decreasing the possibility of an incorrect journal entry.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une fois que la structure de compte est identifiée, la liste des valeurs autorisées est filtrée pour guider l'utilisateur dans la sélection des valeurs de dimension valides, ce qui réduit la possibilité d'une entrée de journal incorrecte.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>If you plan to budget against a financial dimension, it will need to be part of an account structure.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si vous prévoyez de budgétiser une dimension financière, elle doit faire partie d'une structure de compte.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Budgeting does not currently utilize advanced rules.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La budgétisation n'utilise pas actuellement des règles avancées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exemple</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>To illustrate a best practice for setting up an account structure, let's assume that a company wants to track their balance sheet accounts (100000..399999) at the account and business unit financial dimension level.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour illustrer une pratique recommandée de paramétrage d'une structure de compte, supposons qu'une société souhaite suivre ses comptes de bilan (100000..399999) au niveau de la dimension financière du compte et de l'unité commerciale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>For revenue and expense accounts (400000..999999), they track financial dimensions Business Unit, Department, and Cost center.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les comptes de produit et de dépenses (400000..999999), elle suit les dimensions financières Unité commerciale, Département et Centre de coût.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>If they make a sale, they also like to track Customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si elle effectue une vente, elle peut également suivre la dimension financière Client.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Using this scenario, it would be recommended to have two account structures assigned to the company’s ledger - one for Balance sheet accounts, and one for Profit and Loss accounts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Avec ce scénario, il est recommandé que deux structures de compte soient affectées à la comptabilité de la société (une pour les comptes de bilan et une pour les comptes de résultat).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>To optimize the user experience and validation, Customer should be an advanced rule that is only used when a sales account is used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour optimiser l'expérience de l'utilisateur et la validation, le client doit être une règle avancée qui est uniquement utilisée lorsqu'un compte de vente est utilisé.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source><bpt id="p1">**</bpt>Balance sheet account structure<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Structure du compte de bilan<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Main account</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Compte principal</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>Business unit</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Unité commerciale</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>100000..399999</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">100000..399999</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>*;” “</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">*;” “</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source><bpt id="p1">**</bpt>Profit and loss account structure<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Structure du compte de résultat<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>Main account</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Compte principal</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Business unit</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Unité commerciale</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Department</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Département</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>Cost center</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Centre de coût</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>400000..999999</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">400000..999999</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>*;” “</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">*;” “</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>*;” “</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">*;” “</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>*;” “</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">*;” “</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>*;” “</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">*;” “</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source><bpt id="p1">**</bpt>Advanced rule for adding a Customer<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Règle avancée pour ajouter un client<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Criteria: Where Main account is between 400000 and 499999, then add customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Critères : si le compte principal est compris entre 400000 et 499999, ajoutez le client.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>It cannot be left blank.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il doit être renseigné.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Customer</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Client</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>In this simplified example, all values and blank are allowed so * and “ “ are used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans cet exemple simplifié, toutes les valeurs et les vides sont autorisés, * et " " sont donc utilisés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>Segments and allowed values</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Segments et valeurs autorisées</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>The <bpt id="p1">**</bpt>Segments<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Allowed values details<ept id="p2">**</ept> section provides a grid like experience for entering the rules that will be followed on validation during posting.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La section <bpt id="p1">**</bpt>Segments<ept id="p1">**</ept> et <bpt id="p2">**</bpt>Détails des valeurs autorisées<ept id="p2">**</ept> fournit une expérience sous forme de grille pour saisir les règles à suivre lors de la validation.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>You can type directly in the cells in the grid, import it from Excel, or use the <bpt id="p1">**</bpt>Allowed value details<ept id="p1">**</ept> section to guide you through it.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez taper directement dans les cellules de la grille, l'importer depuis Excel ou utiliser la section <bpt id="p1">**</bpt>Détails des valeurs autorisées<ept id="p1">**</ept> pour vous guider.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>The <bpt id="p1">**</bpt>Allowed value details<ept id="p1">**</ept> section guides you through creating criteria using <bpt id="p2">**</bpt>Operators<ept id="p2">**</ept> such as begins with, is between, includes, and many others.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">La section <bpt id="p1">**</bpt>Détails des valeurs autorisées<ept id="p1">**</ept> vous aide à créer des critères à l'aide d'<bpt id="p2">**</bpt>Opérateurs<ept id="p2">**</ept> tels que commence par, compris entre, comprend, etc.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Allow values<ept id="p1">](./media/account.png)](./media/account.png)</ept></source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Autoriser des valeurs<ept id="p1">](./media/account.png)](./media/account.png)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Allowed values will default onto a journal or accounting distribution entry page when there are no other possible values to select according to the account structure setup.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Les valeurs autorisées seront par défaut celles d'un journal ou d'une page d'entrée de répartition comptable s'il n'y a pas de autres valeurs possibles à sélectionner en fonction du paramétrage de la structure de compte.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Here's an example of the <bpt id="p1">**</bpt>Profit and loss account structure<ept id="p1">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Voici un exemple de <bpt id="p1">**</bpt>Structure de compte de résultat<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>Main account</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Compte principal</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>Business unit</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Unité commerciale</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>Department</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Département</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>Cost center</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Centre de coût</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>400000..999999</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">400000..999999</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>002</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">002</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>022</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">022</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>014</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">014</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>When entering a journal and selecting an account in the profit and loss range, selecting business unit '002' will cause values 022 and 014 to be the default on the account control.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Lorsque vous saisissez dans un journal et que vous sélectionnez un compte dans la plage du compte de résultat, sélectionner l'unité commerciale « 002 » génère les valeurs 022 et 014 comme valeurs par défaut du contrôle de compte.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>This behavior will also occur with the accounting distribution page.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ce comportement se produira également avec la page de répartition comptable.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>More than 7 criteria needed</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Plus de 7 critères requis</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>If you have more than 7 criteria that are needed, you can continue adding them on the next line.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Si plus de 7 critères sont requis, vous pouvez continuer à les ajouter sur la ligne suivante.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>You will notice when working in the <bpt id="p1">**</bpt>Allowed value details<ept id="p1">**</ept> section that the <bpt id="p2">**</bpt>+Add new<ept id="p2">**</ept> criteria is nt longer active after the seventh criteria is entered.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous remarquerez lors de l'utilisation de la section <bpt id="p1">**</bpt>Détails des valeurs autorisées<ept id="p1">**</ept> que le critère <bpt id="p2">**</bpt>+Ajouter nouveau<ept id="p2">**</ept> n'est plus actif après la saisie du septième critère.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>This is due to many factors such as:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cela est dû à de nombreux facteurs tels que :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>Column width</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Largeur de colonne</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>How the data is stored</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mode de stockage des données</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>Performance of the <bpt id="p1">**</bpt>Allowed value details<ept id="p1">**</ept> control</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Performances du contrôle <bpt id="p1">**</bpt>Détails des valeurs autorisées<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>Usability</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Facilité d'utilisation</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>To continue to add additional criteria, click <bpt id="p1">**</bpt>Duplicate in the Segment<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Allowed values section<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour continuer à ajouter des critères supplémentaires, cliquez sur la section <bpt id="p1">**</bpt>Doublon dans le segment<ept id="p1">**</ept> et <bpt id="p2">**</bpt>Valeurs autorisées<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>This will copy the criteria to a new line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les critères sont copiés sur une nouvelle ligne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>You can then type over or modify the <bpt id="p1">**</bpt>Allowed value details<ept id="p1">**</ept> section.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Vous pouvez ensuite effectuer votre saisie ou modifier la section <bpt id="p1">**</bpt>Détails des valeurs autorisées<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>Best practices</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Utilisation optimale</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>When setting up your account structures there are some best practices you can follow.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Lors du paramétrage de vos structures de compte, certaines pratiques recommandées peuvent être suivies.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>However, this is only guidance so a holistic discussion about your business, growth plan, and maintenance plan should be considered as part of that discussion.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Toutefois, il s'agit seulement de recommandations, une discussion holistique sur votre entreprise, votre plan de croissance et votre plan de maintenance doit être envisagée dans le cadre de cette discussion.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>Make main account first or as close to the front of the account structure as possible, so users get the best guided experience they can during account entry.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Placez le compte principal en premier ou le plus proche possible de la structure de compte, afin que les utilisateurs puissent bénéficier de la meilleure expérience guidée possible lors de l'écriture de compte.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>Reuse account structures as much as possible to reduce maintenance across your legal entities.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Réutilisez les structures de compte autant que possible pour réduire la maintenance dans vos entités juridiques.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>For variations across legal entities, consider using advanced rules so that account structures can be reused.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les écarts entre plusieurs entités juridiques, pensez à utiliser des règles avancées afin que les structures de compte peuvent être réutilisées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>When defining allowed values, use ranges and wildcards as much as possible.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lors de la définition des valeurs autorisées, utilisez les plages et les caractères génériques autant que possible.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>This not only allows you to grow and change without maintenance, but the system also performs more ideally with this configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cela vous permet non seulement de vous développer et d'effectuer des modifications sans maintenance, mais le système fonctionne de manière optimale avec cette configuration.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Do not just put an asterisk for every segment in the account structure and then solely rely on the advanced rules.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il ne suffit d'ajouter un astérisque pour chaque segment de la structure de compte et de se baser uniquement sur les règles avancées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>This can be difficult to manage and often leads to user error during maintenance that can make the system unable to post.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cela peut s'avérer difficile à gérer et entraîne généralement des erreurs pendant la maintenance, ce qui rend la validation impossible.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>Account structure activation</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Activation de la structure de compte</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>When you are satifisfied with your new setup or a change to an account structure, you must activate it.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsque vous êtes satisfait de vos nouveaux paramétrages ou des modifications de la structure de compte, vous devez les activer.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>If an account structure is assigned to a ledger, this activation can be a long running process, as all unposted transactions in the system must be synced to the new structure.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si une structure de compte est affectée à une comptabilité, cette activation peut prendre du temps, car toutes les transactions non validées dans le système doivent être synchronisées avec la nouvelle structure.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>Posted transactions are not impacted with account structure changes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les transactions validées ne sont pas affectées par les modifications de la structure de compte.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>For more information, see <bpt id="p1">[</bpt>Plan your chart of accounts<ept id="p1">](plan-chart-of-accounts.md)</ept>, <bpt id="p2">[</bpt>Financial dimensions<ept id="p2">](financial-dimensions.md)</ept> and <bpt id="p3">[</bpt>Enter account and dimension combinations (segmented entry control)<ept id="p3">](enter-account-dimension-combinations-segmented-entry-control.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour plus d'informations, voir, <bpt id="p1">[</bpt>Planifier votre plan de comptes<ept id="p1">](plan-chart-of-accounts.md)</ept>, <bpt id="p2">[</bpt>Dimensions financières<ept id="p2">](financial-dimensions.md)</ept> et <bpt id="p3">[</bpt>Entrer des combinaisons de compte et de dimensions (contrôle d'accès segmenté)<ept id="p3">](enter-account-dimension-combinations-segmented-entry-control.md)</ept>.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>