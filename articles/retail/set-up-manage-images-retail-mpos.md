<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="set-up-manage-images-retail-mpos.md" target-language="fr-FR">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>set-up-manage-images-retail-mpos.3cc4ad.c256569135a00ea98a5c059b9dd12a07a000ee6a.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>c256569135a00ea98a5c059b9dd12a07a000ee6a</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>e2fb0846fcc6298050a0ec82c302e5eb5254e0b5</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/27/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\set-up-manage-images-retail-mpos.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Set up and manage images for Retail Modern POS (MPOS)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Paramétrer et gérer des images pour Retail Modern POS (MPOS)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This article explains the steps that are involved in setting up and managing images for the various entities that appear in Retail Modern POS (MPOS).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cet article décrit les étapes impliquées dans le paramétrage et la gestion des images pour les différentes entités qui apparaissent dans Retail Modern POS (MPOS).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Set up and manage images for Retail Modern POS (MPOS)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Paramétrer et gérer des images pour Retail Modern POS (MPOS)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>This article explains the steps that are involved in setting up and managing images for the various entities that appear in Retail Modern POS (MPOS).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cet article décrit les étapes impliquées dans le paramétrage et la gestion des images pour les différentes entités qui apparaissent dans Retail Modern POS (MPOS).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>Setting up the media base URL and defining media templates to configure the format for image URLs</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Paramétrage de l'URL de base de média et définition des modèles de média pour configurer le format des URL d'image</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>The images that appear in Retail Modern POS (MPOS) must be hosted externally, outside Microsoft Dynamics 365 for Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les images qui apparaissent dans Retail Modern POS (MPOS) doivent être hébergés en externe, en dehors de Microsoft Dynamics 365 for Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Typically, they are hosted in a content management system, content delivery network (CDN), or media server.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Généralement, elles sont hébergées dans un système de gestion de contenu, un réseau de diffusion de contenu (CDN), ou un serveur multimédia.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>MPOS then fetches and displays the images for the appropriate entities, such as products and catalogs, by accessing the target URL.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">MPOS ensuite extrait et affiche les images pour les entités appropriées, telles que des produits et des catalogues, en accédant à l'URL cible.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>To fetch these externally hosted images, MPOS requires the correct URL format for the images.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour extraire les images hébergées en externe, MPOS nécessite le format URL approprié pour les images.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>You can configure the required URL format for the images by setting up the <bpt id="p1">**</bpt>Media base URL<ept id="p1">**</ept> value in the channel profile and using the <bpt id="p2">**</bpt>Define media template<ept id="p2">**</ept> functionality for each entity.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez configurer le format d'URL requis pour les images en paramétrant la valeur de l'<bpt id="p1">**</bpt>URL de base de support<ept id="p1">**</ept> dans le profil de canal et en utilisant la fonctionnalité <bpt id="p2">**</bpt>Définir modèle de média<ept id="p2">**</ept> pour chaque entité.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>You can also overwrite the standard URL format for a subset of entities by using the <bpt id="p1">**</bpt>Edit in Excel<ept id="p1">**</ept> functionality.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez également remplacer le format standard URL pour un sous-ensemble d'entités à l'aide de la fonction <bpt id="p1">**</bpt>Modifier dans Excel<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>In the current version of Dynamics 365 for Retail, you can no longer set up the URL format by using the <bpt id="p1">**</bpt>Image<ept id="p1">**</ept> attribute XML for MPOS in the <bpt id="p2">**</bpt>Default<ept id="p2">**</ept> attribute group for entities.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans la version actuelle de Dynamics 365 for Retail, vous ne pouvez plus paramétrer le format d'URL à l'aide de l'attribut XML <bpt id="p1">**</bpt>Image<ept id="p1">**</ept> pour MPOS dans le groupe d'attributs <bpt id="p2">**</bpt>Par défaut<ept id="p2">**</ept> pour les entités.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>If you're familiar with Microsoft Dynamics AX 2012 R3 and are now using the current version of Dynamics 365 for Retail, make sure that you always use the new <bpt id="p1">**</bpt>Define media template<ept id="p1">**</ept> functionality to set up images.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si vous êtes familiarisé avec Microsoft Dynamics AX 2012 R3 et que vous utilisez maintenant la version actuelle de Dynamics 365 for Retail, vérifiez que vous utilisez toujours la nouvelle fonctionnalité <bpt id="p1">**</bpt>Définir modèle de média<ept id="p1">**</ept> pour paramétrer des images.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Don't use or modify the <bpt id="p1">**</bpt>Image<ept id="p1">**</ept> attribute in the <bpt id="p2">**</bpt>Default<ept id="p2">**</ept> attribute group for any entities, including products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">N'utilisez pas ou ne modifiez pas l'attribut <bpt id="p1">**</bpt>Image<ept id="p1">**</ept> dans le groupe d'attributs <bpt id="p2">**</bpt>par défaut<ept id="p2">**</ept> pour les entités, notamment les produits.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Changes that you make directly in the <bpt id="p1">**</bpt>Default<ept id="p1">**</ept> attribute group for images won't be reflected.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les modifications effectuées directement dans le groupe d'attributs <bpt id="p1">**</bpt>par défaut<ept id="p1">**</ept> pour les images ne seront pas répercutées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>This option will be disabled in a future release.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette option sera désactivée dans la prochaine version.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>In the following procedures, images are set up for the Catalog entity as an example.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans les procédures suivantes, des images sont paramétrés pour l'entité de catalogue à titre d'exemple.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>These procedures will help guarantee that the correct image destination path is set implicitly for all catalog images that use a common path.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ces procédures aideront à garantir que le chemin d'accès de destination de l'image correct est défini implicitement pour toutes les images du catalogue qui utilisent un chemin d'accès commun.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>For example, if you've set up a media server or CDN externally, and want the images to appear in MPOS for a given store, the <bpt id="p1">**</bpt>Define media template<ept id="p1">**</ept> functionality helps you the set the path where MPOS can look up and retrieve the images.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par exemple, si vous avez paramétré un serveur multimédia ou un CDN en externe, et que vous souhaitez voir les images apparaître dans MPOS pour un magasin donné, la fonctionnalité <bpt id="p1">**</bpt>Définir modèle de média<ept id="p1">**</ept> vous permet de définir le chemin d'accès dans lequel MPOS peut rechercher et récupérer les images.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>For this demo data example, the media server is deployed on the Retail Server.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour cet exemple de données de démonstration, le serveur multimédia est déployé sur le serveur Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>However, you can have it anywhere outside Dynamics 365 for Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Toutefois, il peut être n'importe où à l'extérieur de Dynamics 365 for Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Set up the media base URL for a channel</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Paramétrer l'URL de base de support pour un canal</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Open the Dynamics 365 for Retail HQ portal.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Ouvrez le portail Dynamics 365 for Retail HQ.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Click <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Channel setup<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Channel profiles<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Cliquez sur <bpt id="p1">**</bpt>Vente au détail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Paramétrage du canal<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Profils du canal<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Navigation<ept id="p1">](./media/channel-profile1.png)](./media/channel-profile1.png)</ept></source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Navigation<ept id="p1">](./media/channel-profile1.png)](./media/channel-profile1.png)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>In the channel profile that your store uses for MPOS, update the <bpt id="p1">**</bpt>Media base URL<ept id="p1">**</ept> field with the base URL of your media server or CDN.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Dans le profil de canal que votre magasin utilise pour MPOS, mettez à jour le champ <bpt id="p1">**</bpt>URL de base de support<ept id="p1">**</ept> avec l'URL de base de votre serveur multimédia ou CDN.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>The base URL is the first part of the URL that is shared by all image folders of different entities.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">L'URL de base est la première partie de l'URL qui est partagée par tous les fichiers d'image de différentes entités.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Channel profiles page<ept id="p1">](./media/channel-profile2.png)](./media/channel-profile2.png)</ept></source><target logoport:matchpercent="79" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Page Profils du canal<ept id="p1">](./media/channel-profile2.png)](./media/channel-profile2.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Define the media template for an entity</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Définissez le modèle de média d'une entité</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>Click <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Catalog management<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Catalog images<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Cliquez sur <bpt id="p1">**</bpt>Vente au détail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Gestion des catalogues<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Images de catalogue<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>On the <bpt id="p1">**</bpt>Catalog images<ept id="p1">**</ept> page, on the Action Pane, click <bpt id="p2">**</bpt>Define media template<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans la page <bpt id="p1">**</bpt>Images de catalogue<ept id="p1">**</ept>, dans le Volet Actions, cliquez sur <bpt id="p2">**</bpt>Définir modèle de média<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>In the <bpt id="p1">**</bpt>Define media template<ept id="p1">**</ept> dialog box, in the <bpt id="p2">**</bpt>Entity<ept id="p2">**</ept> field, <bpt id="p3">**</bpt>Catalog<ept id="p3">**</ept> should be selected by default.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans la boîte de dialogue <bpt id="p1">**</bpt>Définir modèle de média<ept id="p1">**</ept>, dans le champ <bpt id="p2">**</bpt>Entité<ept id="p2">**</ept>, <bpt id="p3">**</bpt>Catalogue<ept id="p3">**</ept> doit être sélectionné par défaut.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>On the <bpt id="p1">**</bpt>Media path<ept id="p1">**</ept> FastTab, enter the remaining path of the image location.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans l'organisateur <bpt id="p1">**</bpt>Chemin d'accès de média<ept id="p1">**</ept>, entrez le chemin restant de l'emplacement d'image.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>The media path supports <bpt id="p1">**</bpt>LanguageID<ept id="p1">**</ept> as a variable.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le chemin d'accès de média prend en charge <bpt id="p1">**</bpt>LanguageID<ept id="p1">**</ept> comme variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>For example, for the demo data, you can create a <bpt id="p1">**</bpt>Catalogs<ept id="p1">**</ept> folder for all catalog images under the media base URL for your media server (<ph id="ph1">`https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer`</ph>).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par exemple, pour les données de démonstration, vous pouvez créer un dossier <bpt id="p1">**</bpt>Catalogues<ept id="p1">**</ept> pour toutes les image de catalogue sous l'URL de base de support pour votre serveur multimédia (<ph id="ph1">`https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer`</ph>).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>You can then have a folder for each language, such as en-US or fr-FR, and copy the appropriate images under each folder.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez ensuite avoir un dossier pour chaque langue (par ex., en-US ou fr-FR) et copier les images appropriées sous chaque dossier.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>If you don't have different images for the various languages, you can omit the <bpt id="p1">**</bpt>LanguageID<ept id="p1">**</ept> variable from your folder structure and point directly to the Catalogs folder that contains the catalog images.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si vous n'avez pas différentes images pour les différentes langues, vous pouvez omettre la variable <bpt id="p1">**</bpt>LanguageID<ept id="p1">**</ept> de votre arborescence et pointer directement sur le dossier Catalogues qui contient les images du catalogue.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>The current version of Dynamics 365 for Retail supports the <bpt id="p1">**</bpt>{LanguageId}<ept id="p1">**</ept> token for Catalog, Product, and Category entities.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La version actuelle de Dynamics 365 for Retailprend en charge le jeton <bpt id="p1">**</bpt>{LanguageId}<ept id="p1">**</ept> pour les entités Catalogue, Produit et Catégorie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>(The <bpt id="p1">**</bpt>{LanguageID}<ept id="p1">**</ept> token isn't supported for Customer and Worker entities, according to the existing standard that has been effective since Microsoft Dynamics AX 6.x.)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">(Le jeton <bpt id="p1">**</bpt>{LanguageID}<ept id="p1">**</ept> n'est pas pris en charge pour les entités Client et Collaborateur, selon la norme existante effective depuis Microsoft Dynamics AX 6.x).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>For images, the file name format is hard-coded to the catalog name and can't be changed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les images, le format du nom de fichier est codé de manière irréversible dans le nom du catalogue et ne peut pas être modifié.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>Therefore, rename your images so that they have appropriate catalog names, to help guarantee that MPOS handles them correctly.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Renommez, par conséquent, les images afin qu'elles aient des noms de catalogue appropriés, pour aider à garantir que MPOS les gère correctement.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>In the <bpt id="p1">**</bpt>File Extension<ept id="p1">**</ept> field, select the expected file name extension, depending on the type of images that you have.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans le champ <bpt id="p1">**</bpt>Extension de fichier<ept id="p1">**</ept>, sélectionnez l'extension de nom de fichier prévue, selon le type d'image que vous avez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>For example, for the demo data, the catalog images are set to the .jpg extension.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par exemple, pour les données de démonstration, les images de catalogue sont définies sur l'extension .jpg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>(The image files are also renamed so that they have catalog names.)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">(Les fichiers image sont également renommés afin qu'ils aient des noms de catalogue.)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>Click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cliquez sur <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>To validate that the media template for images has been saved correctly, on the <bpt id="p1">**</bpt>Catalog images<ept id="p1">**</ept> page, click <bpt id="p2">**</bpt>Define media template<ept id="p2">**</ept> again.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour contrôler que le modèle de média pour les images a été correctement enregistré, dans la page <bpt id="p1">**</bpt>Images de catalogue<ept id="p1">**</ept>, cliquez sur <bpt id="p2">**</bpt>Définir modèle de média<ept id="p2">**</ept> de nouveau.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>To validate the template without closing the <bpt id="p1">**</bpt>Define media template<ept id="p1">**</ept> dialog box, you can use the <bpt id="p2">**</bpt>Generate Image URLs for Excel<ept id="p2">**</ept> FastTab.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour valider le modèle sans fermer la boîte de dialogue <bpt id="p1">**</bpt>Définir modèle de média<ept id="p1">**</ept>, vous pouvez utiliser l'organisateur <bpt id="p2">**</bpt>Générer des URL d'image pour Excel<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>Check the appearance of the image URL, and verify that the URL complies with the template standard that was mentioned earlier.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Activez l'apparence de l'URL d'image, et vérifiez que l'URL est conforme au standard du modèle qui a été précédemment cité.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>The <bpt id="p1">**</bpt>Define media template<ept id="p1">**</ept> dialog box has now set the image path implicitly for all catalog images that use this common URL path.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La boîte de dialogue <bpt id="p1">**</bpt>Définir modèle de média<ept id="p1">**</ept> a maintenant défini le chemin d'accès à l'image implicitement pour toutes les images du catalogue qui utilisent ce chemin d'accès commun à l'URL.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>This URL path applies to all catalog images unless they are overwritten.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ce chemin d'accès à l'URL s'applique à toutes les images du catalogue sauf si elles sont remplacées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>The first part of the image path is taken from the media base URL that you defined in the channel profile.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La première partie du chemin d'image est extraite de l'URL de base de support que vous avez définie dans le profil de canal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>The remaining part of the path is taken from the path that you defined in the media template.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La partie restante du chemin d'accès est extraite du chemin d'accès que vous avez défini dans le modèle de média.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>The two parts are concatenated to provide the full URL of the image location.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les deux parties sont concaténées pour fournir l'URL complète de l'emplacement d'image.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>For example, a catalog in the demo data is named Fabrikam Base Catalog.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par exemple, un catalogue dans les données de démonstration s'appelle Fabrikam Base Catalog.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>Therefore, the image name must be Fabrikam Base Catalog.jpg so that it uses the catalog name and the .jpg file name extension that is configured in the template.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par conséquent, le nom de l'image doit être Fabrikam Base Catalog.jpg pour qu'il utilise le nom du catalogue et l'extension du nom de fichier .jpg configurée dans le modèle.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>In this case, after concatenation, the URL will be <ph id="ph1">`https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer/Catalogs/en-US/Fabrikam Base Catalog.jpg`</ph>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans ce cas, après concaténation, l'URL est <ph id="ph1">`https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer/Catalogs/en-US/Fabrikam Base Catalog.jpg`</ph>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>Run the synchronization jobs to push the new template to the channel database, so that MPOS can use the template to access the images.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exécutez les tâches de synchronisation pour pousser le nouveau modèle dans la base de données de canal, de sorte que MPOS puisse utiliser le modèle pour accéder aux images.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>To update the media template for catalog images on the channel side, be sure to run <bpt id="p1">**</bpt>Catalog Job 1150<ept id="p1">**</ept> from <bpt id="p2">**</bpt>Retail IT<ept id="p2">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p3">**</bpt>Distribution schedule<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Pour mettre à jour le modèle de média pour les images du catalogue côté canal, veillez à l'exécution de la <bpt id="p1">**</bpt>Tâche de catalogue 1150<ept id="p1">**</ept> dans <bpt id="p2">**</bpt>IT de vente au détail<ept id="p2">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p3">**</bpt>Programme de distribution<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Define media template dialog box<ept id="p1">](./media/catalog1.png)](./media/catalog1.png)</ept></source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Définir la boîte de dialogue Modèle de support<ept id="p1">](./media/catalog1.png)](./media/catalog1.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Previewing an image from the entity level</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Afficher l'aperçu d'une image à partir du niveau d'entité</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>From the page for the entity item in HQ, you can preview the image that uses the image URL that is derived from the media template.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Dans la page de l'article d'entité dans HQ, vous pouvez prévisualiser l'image qui utilise l'URL d'image dérivée du modèle de média.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>For this example, go to the appropriate catalog, and then, on the Action Pane, click <bpt id="p1">**</bpt>Media<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Images<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour cet exemple, accédez au catalogue approprié, puis, dans le Volet Actions, cliquez sur <bpt id="p1">**</bpt>Supports<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Images<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>Use the drop-down list to select different stores that might have different channel profiles.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Utilisez la liste déroulante pour sélectionner différents magasins qui peuvent avoir divers profils de canal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>To edit or remove the implicit media template, you must return to the <bpt id="p1">**</bpt>Define media template<ept id="p1">**</ept> dialog box for the <bpt id="p2">**</bpt>Catalog images<ept id="p2">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour modifier ou supprimer le modèle de média implicite, vous devez revenir à la boîte de dialogue <bpt id="p1">**</bpt>Définir modèle de média<ept id="p1">**</ept> de la page <bpt id="p2">**</bpt>Images du catalogue<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>You can use the <bpt id="p1">**</bpt>Add<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Remove<ept id="p2">**</ept> buttons to manually change the path that is based on the implicit template and used for a specific image.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez utiliser les boutons <bpt id="p1">**</bpt>Ajouter<ept id="p1">**</ept> et <bpt id="p2">**</bpt>Supprimer<ept id="p2">**</ept> pour modifier manuellement le chemin d'accès basé sur le modèle implicite et utilisé pour une image spécifique.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>For more information, see the <bpt id="p1">[</bpt>Overwriting the media template for entity items<ept id="p1">](#overwriting-the-media-template-for-entity-items)</ept> section later in this article.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour plus d'informations, voir la section <bpt id="p1">[</bpt>Remplacement du modèle de média pour les articles d'entité<ept id="p1">](#overwriting-the-media-template-for-entity-items)</ept> ultérieurement dans cet article.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>After you've finished previewing an image and making any changes that you require, start the MPOS instance for the appropriate store, and see whether the catalog images are shown.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Après avoir terminé de prévisualiser une image et d'apporter les modifications nécessaires, démarrez l'instance de MPOS pour le magasin approprié, et vérifiez si les images du catalogue sont affichées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Images dialog box<ept id="p1">](./media/catalog4.png)](./media/catalog4.png)</ept></source><target logoport:matchpercent="68" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Boîte de dialogue Images<ept id="p1">](./media/catalog4.png)](./media/catalog4.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>You can use the same procedure for all the five entities that are supported: Worker, Customer, Catalog, Category, and Products.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Vous pouvez utiliser la même procédure pour les cinq entités qui sont prises en charge : Collaborateur, Client, Catalogue, Catégorie et Produits.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>"Catalog Products" (products that are set at the catalog level) and "Channel Products" (products that are set at the channel level) use the media template that is set for the Products entity.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">« Produits du catalogue » (produits définis au niveau du catalogue) et « Produits du canal » (produits définis au niveau du canal) utilisent le modèle de média défini pour l'entité Produits.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>For the Products media template, you can select the number of product images to show per product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour le modèle de média Produits, vous pouvez sélectionner le nombre d'images de produit à afficher par produit.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>You can also set the default image for a given product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez également définir l'image par défaut pour un produit donné.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>In this way, you can prevent blank images in MPOS and help to control which image is used as the default image for a product item.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">De cette manière, vous pouvez empêcher les images vides dans MPOS et aider à contrôler quelle image est utilisée comme image par défaut pour un article.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>In the following example, each product has five images, and the first image is set as the default image.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans l'exemple suivant, chaque produit a cinq images, et la première image est définie comme image par défaut.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>Variant products are treated the same way as master products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les variantes de produits sont traitées la même manière que les produits principaux.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>The file name of the image file should be based on the product number.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le nom du fichier image doit être basé sur le numéro de produit.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>Some characters are also escaped while the file name is generated.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Certains caractères sont également échappés lorsque le nom de fichier est généré.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>Therefore, it's a good to verify the file name by using the <bpt id="p1">**</bpt>Generate Image URLs for Excel<ept id="p1">**</ept> section.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Par conséquent, il est bon de vérifier le nom de fichier à l'aide de la section <bpt id="p1">**</bpt>Générer des URL d'image pour Excel<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Define media template dialog box<ept id="p1">](./media/prods.png)](./media/prods.png)</ept></source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Définir la boîte de dialogue Modèle de support<ept id="p1">](./media/prods.png)](./media/prods.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Synchronization jobs to send a media template to the channel side</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Tâches de synchronisation pour envoyer un modèle de média du côté du canal</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>For all the five supported entities (Worker, Customer, Catalog, Category, and Products), whenever you update the <bpt id="p1">**</bpt>Define media template<ept id="p1">**</ept> dialog to set up an image, make sure that you run the Catalog job (1150) from <bpt id="p2">**</bpt>Retail IT<ept id="p2">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p3">**</bpt>Distribution schedule<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les cinq entités prises en charge (Collaborateur, Client, Catalogue, Catégorie et Produits), chaque fois que vous mettez à jour la boîte de dialogue <bpt id="p1">**</bpt>Définir modèle de média<ept id="p1">**</ept>  pour paramétrer une image, assurez-vous que vous exécutez la tâche de catalogue (1150) à partir de <bpt id="p2">**</bpt>IT de vente au détail<ept id="p2">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p3">**</bpt>Programme de distribution<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>This job will enable the updated media template to be synced to the channel and used by MPOS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette tâche permettra au modèle de média mis à jour d'être synchronisé sur le canal et utilisé par MPOS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>Run the Catalog job (1150) after you make any of the following changes:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exécutez la Tâche de catalogue (1150) après avoir effectué les modifications suivantes :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>You update the Catalog image media template from <bpt id="p1">**</bpt>Catalog images<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Define media template<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous mettez à jour le modèle de média pour les images du catalogue à partir de <bpt id="p1">**</bpt>Images du catalogue<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Définir modèle de média<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>You update the Employee image media template from <bpt id="p1">**</bpt>Employee images<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Define media template<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous mettez à jour le modèle de média pour les images des employés à partir de <bpt id="p1">**</bpt>Images des employés<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Définir modèle de média<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>You update the Customer image media template from <bpt id="p1">**</bpt>Customer image<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Define media template<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous mettez à jour le modèle de média pour les images des clients à partir de <bpt id="p1">**</bpt>Images des clients<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Définir modèle de média<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>You update the Product image media template from <bpt id="p1">**</bpt>Product images<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Define media template<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous mettez à jour le modèle de média pour les images de produits à partir de <bpt id="p1">**</bpt>Images des produits<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Définir modèle de média<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>You update the Category image media template from <bpt id="p1">**</bpt>Category images<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Define media template<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous mettez à jour le modèle de média pour les images des catégories à partir de <bpt id="p1">**</bpt>Images des catégories<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Définir modèle de média<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>You must also publish the channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous devez également publier le canal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Overwriting the media template for entity items</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Remplacement du modèle de média pour les articles d'entité</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>As you learned in the previous section, the media template for a given entity supports only one common path.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Comme vous l'avez appris dans la section précédente, le modèle de média d'une entité donnée prend en charge un seul chemin d'accès commun.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>This path is based on the media base URL that is configured and the media path that is defined.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ce chemin d'accès est basé sur l'URL de base de support configurée et sur le chemin d'accès au support défini.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>However, in many cases, a retailer wants to be able to use images from different sources for a subset of items in an entity.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Toutefois, dans de nombreux cas, un détaillant souhaite pouvoir utiliser les images de différentes sources pour un sous-ensemble d'articles dans une entité.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>For example, a store uses the self-hosted media server for one set of catalog images but uses CDN URLs for another set.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par exemple, un magasin utilise le serveur multimédia auto-hébergé pour un ensemble d'images de catalogue mais utilise les URL CDN pour un autre ensemble.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>To overwrite image URLs that are based on a media template for entity images at the entity level, you can use the Edit in Excel and Manual edit functionality from the <bpt id="p1">**</bpt>Preview<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour remplacer les URL des images basées sur un modèle de média pour les images d'une entité au niveau de l'entité, vous pouvez utiliser la fonction Modifier dans Excel et la fonctionnalité de modification manuelle de la page <bpt id="p1">**</bpt>Aperçu<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>Overwrite by using Edit in Excel</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Remplacer à l'aide de Modifier dans Excel</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>Click <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Catalog management<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Catalog images<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cliquez sur <bpt id="p1">**</bpt>Vente au détail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Gestion des catalogues<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Images de catalogue<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>On the <bpt id="p1">**</bpt>Catalog images<ept id="p1">**</ept> page, click <bpt id="p2">**</bpt>Define media template<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans la page <bpt id="p1">**</bpt>Images de catalogue<ept id="p1">**</ept>, cliquez sur <bpt id="p2">**</bpt>Définir modèle de média<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>In the <bpt id="p1">**</bpt>Define media template<ept id="p1">**</ept> dialog box, in the <bpt id="p2">**</bpt>Entity<ept id="p2">**</ept> field, <bpt id="p3">**</bpt>Catalog<ept id="p3">**</ept> should be selected.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans la boîte de dialogue <bpt id="p1">**</bpt>Définir modèle de média<ept id="p1">**</ept>, dans le champ <bpt id="p2">**</bpt>Entité<ept id="p2">**</ept>, <bpt id="p3">**</bpt>Catalogue<ept id="p3">**</ept> doit être sélectionné.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>On the <bpt id="p1">**</bpt>Media path<ept id="p1">**</ept> FastTab, notice the image location.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans l'organisateur <bpt id="p1">**</bpt>Chemin d'accès de média<ept id="p1">**</ept>, notez l'emplacement de l'image.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>On the <bpt id="p1">**</bpt>Generate Image URLs for Excel<ept id="p1">**</ept> FastTab, click <bpt id="p2">**</bpt>Generate<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans l'organisateur <bpt id="p1">**</bpt>Générer des URL d'image pour Excel<ept id="p1">**</ept>, cliquez sur <bpt id="p2">**</bpt>Générer<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>Whenever the media template is changed, you must click <bpt id="p1">**</bpt>Generate<ept id="p1">**</ept> before you can use the Edit in Excel functionality.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Dès que le modèle de média est modifié, vous devez cliquer sur <bpt id="p1">**</bpt>Générer<ept id="p1">**</ept> pour pouvoir utiliser la fonctionnalité Modifier dans Excel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Generate Image URLs for Excel FastTab<ept id="p1">](./media/excel1.jpg)](./media/excel1.jpg)</ept></source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Générer des URL d'image pour l'organisateur Excel<ept id="p1">](./media/excel1.jpg)](./media/excel1.jpg)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>You now see a preview of the image URLs that were generated based on the last saved media template.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Vous voyez désormais s'afficher un aperçu des URL d'image qui ont été générées selon le dernier modèle de média enregistré.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Generate Image URLs for Excel FastTab after Generate is selected<ept id="p1">](./media/excel2.png)](./media/excel2.png)</ept></source><target logoport:matchpercent="71" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Générer des URL d'image pour Excel dans l'organisateur après avoir cliqué sur Générer<ept id="p1">](./media/excel2.png)](./media/excel2.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>The URLs that are generated for Excel use the path and conventions of the media template that is defined.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Les URL générées pour Excel utilisent le chemin d'accès et les conventions du modèle de support défini.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>These conventions include the conventions for file names.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ces conventions incluent des conventions pour les noms de fichier.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>The expectation is that you've set up the physical images outside Dynamics 365 for Retail, and the images can be retrieved from the URLs that are derived from the media template that you defined earlier.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous devez normalement avoir paramétré les images physiques en dehors de Dynamics 365 for Retail, et les images peuvent être récupérés à partir des URL qui sont dérivées du modèle de média défini précédemment.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>You can overwrite these derived URLs by using the Edit in Excel functionality.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez remplacer ces URL dérivés à l'aide de la fonctionnalité Modifier dans Excel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>Click <bpt id="p1">**</bpt>Edit in Excel<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cliquez sur <bpt id="p1">**</bpt>Modifier dans Excel<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>After the Microsoft Excel worksheet is opened, click <bpt id="p1">**</bpt>Enable edit<ept id="p1">**</ept> when you're prompted.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une fois la feuille de calcul Microsoft Excel ouverte, cliquez sur <bpt id="p1">**</bpt>Activer la modification<ept id="p1">**</ept> lorsque vous y êtes invité.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>When you're prompted, click <bpt id="p1">**</bpt>Trust this add-in<ept id="p1">**</ept> in the right pane, and wait for the add-in to complete the installation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsque vous y êtes invité, cliquez sur <bpt id="p1">**</bpt>Faire confiance à ce complément<ept id="p1">**</ept> dans le volet droit et attendez que le complément ait terminé l'installation.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Trust this add-in<ept id="p1">](./media/excel4.jpg)](./media/excel4.jpg)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Faire confiance à ce complément<ept id="p1">](./media/excel4.jpg)](./media/excel4.jpg)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>If you're prompted to sign in, enter the credentials that you used to sign in to HQ.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si vous êtes invité à vous connecter, entrez les informations d'identification que vous avez utilisées pour vous connecter dans HQ.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Sign-in prompt<ept id="p1">](./media/excel5.png)](./media/excel5.png)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Invite de connexion<ept id="p1">](./media/excel5.png)](./media/excel5.png)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>After you sign in, you should be able to see the list of image URLs for the various catalog entries.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Après vous être connecté, vous devez pouvoir afficher la liste des URL d'image pour les différentes rubriques de catalogue.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>You edit, add, and remove the image URLs for various entity items.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous modifiez, ajoutez et supprimez des URL d'image pour divers articles d'entité.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>For all entities except Products, you can overwrite the image URLs.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour toutes les entités à l'exception des Produits, vous pouvez remplacer les URL d'image.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>Modify the existing image URL, so that it uses the new destination URL of the image, and update the file name with the new file name for the image file.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Modifiez l'URL d'image existante, afin qu'il utilise la nouvelle URL de destination de l'image, et mettez à jour le nom de fichier avec le nouveau nom de fichier d'image.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source>The file name must be unique to help guarantee that the record is unique.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le nom du fichier doit être unique pour garantir que l'enregistrement est unique.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Overwrite the image URLs in Excel<ept id="p1">](./media/excel6.jpg)](./media/excel6.jpg)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Remplacer les URL d'image dans Excel<ept id="p1">](./media/excel6.jpg)](./media/excel6.jpg)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>When you overwrite image URLs for Products entities by using the Edit in Excel functionality or the entity item page, MPOS always shows all the media template image URLs together with the overwritten image URLs.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsque vous remplacez des URL d'image pour les entités de Produits à l'aide de la fonctionnalité Modifier dans Excel ou de la page d'article d'entité, MPOS affiche toujours toutes les URL d'image du modèle du support accompagnées des URL d'image remplacées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>After you've finished making your changes, click <bpt id="p1">**</bpt>Publish in Excel<ept id="p1">**</ept> to create a new explicit association entry.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Après avoir terminé d'apporter les modifications, cliquez sur <bpt id="p1">**</bpt>Publier dans Excel<ept id="p1">**</ept> pour créer une nouvelle entrée d'association explicite.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>Return to HQ, and click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Retourner à HQ, puis cliquez sur <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source>Run the appropriate synchronization jobs for the entity, and check the preview on the entity page or in MPOS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exécutez les tâches appropriées de synchronisation pour l'entité, puis activez l'aperçu dans la page d'entité ou dans MPOS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source>Creating new records</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Création d'enregistrements</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source>You can create new records in Excel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez créer des enregistrements dans Excel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>However, make sure that you provide the correct information.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Toutefois, veillez à fournir les informations appropriées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>For example, to create a new entry for a catalog, make sure that the catalog ID and catalog name are correct, and also provide a unique file name.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par exemple, pour créer une entrée pour un catalogue, veillez à ce que l'ID du catalogue et le nom du catalogue soient corrects, et fournissez également un nom de fichier unique.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>The unique file name is very important, because the uniqueness of records in Excel is validated during publishing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le nom de fichier unique est très important, car l'unicité des enregistrements dans Excel est validée lors de la validation.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>First copy the details from the catalog that you want to create a new record for, and copy the record.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">D'abord, copiez les détails du catalogue pour lequel vous souhaitez créer un enregistrement, puis copiez l'enregistrement.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>You just have to update the file name and URL, because the rest of the information will be same.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous devez seulement mettre à jour le nom du fichier et l'URL, car le reste des informations sera identique.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>To create new records for Product entity items, you use the same basic procedure.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour créer des enregistrements pour des articles d'entité de Produit, vous utilisez la même procédure de base.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>From the Excel worksheet, copy an existing record for the product that you to create a new record for, and then replace the image URL and filename.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">À partir de la feuille de calcul Excel, copiez un enregistrement existant pour le produit pour lequel vous créez un enregistrement, puis remplacez l'URL et le nom du fichier d'image.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>Make sure that the file name is unique.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vérifiez que le nom de fichier est unique.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source>Deleting an existing record</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Suppression d'un enregistrement existant.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>Only the overwritten image URL records can be deleted.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Seuls les enregistrements d'URL d'image remplacés peuvent être supprimés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>After an image is deleted and synchronization is completed, the image will no longer appear on the <bpt id="p1">**</bpt>Preview<ept id="p1">**</ept> page or in MPOS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une fois qu'une image est supprimée et que la synchronisation est terminée, l'image n'apparaît plus dans la page <bpt id="p1">**</bpt>Aperçu<ept id="p1">**</ept> ou dans MPOS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>Image URL records that are derived from the media template can't be deleted, because these records are always derived from the media template every time.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les enregistrements d'URL d'image qui sont dérivés du modèle de média ne peuvent pas être supprimés, car ces enregistrements sont toujours dérivés du modèle de média à chaque fois.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>Overwrite from the entity-level Preview page</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Remplacer à partir de la page d'aperçu au niveau de l'entité</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>For all entities except Products, you can overwrite the image URL for a given entity item at the entity item level from the <bpt id="p1">**</bpt>Preview<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour toutes les entités à l'exception des Produits, vous pouvez remplacer l'URL d'image pour un article d'entité donnée au niveau de l'article d'entité à partir de la page <bpt id="p1">**</bpt>Aperçu<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source>For Products, you can use the "Catalog Products" entity page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les Produits, vous pouvez utiliser la page d'entité « Produits du catalogue ».</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source>This example shows how to overwrite a catalog image.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cet exemple décrit la manière de remplacer une image de catalogue.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="244">
          <source>Click <bpt id="p1">**</bpt>Catalogs<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Media<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Images<ept id="p3">**</ept>, and select the catalog image to update.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cliquez sur <bpt id="p1">**</bpt>Catalogues<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Supports<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Images<ept id="p3">**</ept>, puis sélectionnez l'image de catalogue à mettre à jour.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="245">
          <source>Click <bpt id="p1">**</bpt>Add<ept id="p1">**</ept>, and enter the image URL to overwrite the media template URL.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cliquez sur <bpt id="p1">**</bpt>Ajouter<ept id="p1">**</ept>, puis entrez l'URL d'image pour remplacer l'URL du modèle de média.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="246">
          <source>If you want this image to be shown in MPOS for the catalog, you can set it as the default image.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si vous souhaitez que cette image s'affiche dans MPOS pour le catalogue, vous pouvez la définir comme image par défaut.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="247">
          <source>Click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cliquez sur <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="248">
          <source>The image URL is updated for this catalog image, and a preview is shown.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">L'URL d'image est mise à jour avec cette image de catalogue, puis un aperçu s'affiche.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="249">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>URL updated in the New image dialog box<ept id="p1">](./media/preview3.png)](./media/preview3.png)</ept></source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">[</bpt><ph id="ph1">![</ph>URL mise à jour dans la boîte de dialogue Nouvelle image<ept id="p1">](./media/preview3.png)](./media/preview3.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="250">
          <source>You can also see the image preview for all overwritten image URLs on the <bpt id="p1">**</bpt>Catalog images<ept id="p1">**</ept> gallery page.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Vous pouvez également afficher l'aperçu d'image pour toutes les URL d'image remplacées dans la page de galerie <bpt id="p1">**</bpt>Images de catalogue<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="251">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Catalog images gallery page<ept id="p1">](./media/preview-4.png)](./media/preview-4.png)</ept></source><target logoport:matchpercent="97" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Page de galerie Images de catalogue<ept id="p1">](./media/preview-4.png)](./media/preview-4.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="252">
          <source>Currently, the gallery doesn't show image previews for media template image URLs.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Actuellement, la galerie n'affiche pas les aperçus d'image pour les URL d'image de modèle de média.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="253">
          <source>For Catalog, Worker, Customer, and Category entities, if the user explicitly provides a URL through this page, we recommend that you indicate which image is the default image, because Retail Server clients show only one image per Catalog, Customer, Worker, and Category.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les entités Catalogue, Collaborateur, Client, et Catégorie, si l'utilisateur fournit explicitement une URL via cette page, il est recommandé d'indiquer quelle est l'image par défaut, car les clients du serveur Retail n'indiquent qu'une seule image par Catalogue, Client, Collaborateur et Catégorie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="254">
          <source>If the user doesn't specify a default image, the system determines the default image and send it to the Retail service caller (MPOS or Ecommerce).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si l'utilisateur ne spécifie pas une image par défaut, le système détermine l'image par défaut et l'envoie à l'appelant du service Retail (MPOS ou commerce électronique).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="255">
          <source>Overwrite the image URL for catalog product images from the Preview page</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Remplacer l'URL d'image pour les images de produits du catalogue à partir de la page Aperçu</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="256">
          <source>To overwrite image URLs for catalog product images, you must use the <bpt id="p1">**</bpt>Preview<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour remplacer les URL d'image pour les images de produits du catalogue, vous devez utiliser la page <bpt id="p1">**</bpt>Aperçu<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="257">
          <source>You can't use the Edit in Excel functionality.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous ne pouvez pas utiliser la fonctionnalité Modifier dans Excel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="258">
          <source>To overwrite product images at a catalog level, select a catalog, and then select the product to overwrite the image for.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour remplacer les images des produits au niveau d'un catalogue, sélectionnez un catalogue, puis sélectionnez le produit pour lequel l'image doit être remplacée.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="259">
          <source>Click <bpt id="p1">**</bpt>Attributes<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cliquez sur <bpt id="p1">**</bpt>Attributs<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="260">
          <source>On the next page, select <bpt id="p1">**</bpt>Image<ept id="p1">**</ept>, and then click <bpt id="p2">**</bpt>Edit<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans la page suivante, sélectionnez <bpt id="p1">**</bpt>Image<ept id="p1">**</ept>, puis cliquez sur <bpt id="p2">**</bpt>Modifier<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="261">
          <source>The <bpt id="p1">**</bpt>Preview<ept id="p1">**</ept> page opens as a slider dialog box.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La page <bpt id="p1">**</bpt>Aperçu<ept id="p1">**</ept> s'ouvre sous forme de boîte de dialogue curseur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="262">
          <source>Click <bpt id="p1">**</bpt>Add<ept id="p1">**</ept>, and overwrite the image URL with a new URL.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cliquez sur <bpt id="p1">**</bpt>Ajouter<ept id="p1">**</ept>, puis remplacez l'URL d'image avec un nouvel URL.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="263">
          <source>Click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cliquez sur <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="264">
          <source>You now see the preview of the new image and can set it as the default image.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Vous voyez désormais l'aperçu de la nouvelle image et pouvez la définir comme image par défaut.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="265">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Image preview in the New image dialog box<ept id="p1">](./media/cat3.png)](./media/cat3.png)</ept></source><target logoport:matchpercent="75" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Aperçu de l'image dans la boîte de dialogue Nouvelle image<ept id="p1">](./media/cat3.png)](./media/cat3.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="266">
          <source>After category image association, you must publish the channel and run the Channel job to help guarantee that the changes are published to the channel database.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Après l'association d'une image de catégorie, vous devez publier le canal et exécuter la Tâche du canal pour garantir que les modifications sont publiées dans la base de données du canal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="267">
          <source>Setting up images to appear in Offline mode for MPOS</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Paramétrage des images à afficher dans le mode hors connexion pour MPOS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="268">
          <source>MPOS can run in Online mode (when MPOS connected to Retail Server) or Offline mode (when there is no Retail Server or network connectivity, and transactions are stored in a local offline database).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">MPOS peut s'exécuter en mode en ligne (lorsque MPOS est connecté au serveur Retail) ou en mode hors connexion (lorsqu'il n'existe aucun serveur Retail ni connexions réseau, et si les transactions sont stockées dans une base de données hors connexion locale).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="269">
          <source>When MPOS runs in Offline mode, it can't get images from the external image server to display from Retail Server, because Retail Server connectivity has been lost.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsque MPOS fonctionne en mode hors ligne, il ne peut pas afficher les images du serveur d'images externe à partir du serveur Retail, car la connexion avec le serveur Retail est perdue.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="270">
          <source>However, you can still set up images so that they are shown when MPOS runs in Offline mode.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Toutefois, vous pouvez toujours paramétrer des images afin qu'elles soient affichées lorsque MPOS fonctionne en mode hors ligne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="271">
          <source>Set up product images to appear in Offline mode for MPOS</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Paramétrer des images de produits à afficher dans le mode hors connexion pour MPOS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="272">
          <source>The product images that must be used in Offline mode can be set up by uploading the required physical image into the base product image.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les images de produits qui doivent être utilisées en mode hors connexion peuvent être paramétrées en téléchargeant l'image physique requise dans l'image du produit de base.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="273">
          <source>Click <bpt id="p1">**</bpt>Product information management<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Products<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Products<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cliquez sur <bpt id="p1">**</bpt>Gestion des informations sur les produits<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Produits<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Produits<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="274">
          <source>Select the product to set the offline image for.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sélectionnez le produit pour lequel définir l'image hors connexion.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="275">
          <source>Click <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept>, and then click the arrow in the right corner to show the right pane.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cliquez sur <bpt id="p1">**</bpt>Modifier<ept id="p1">**</ept>, puis cliquez sur la flèche située dans le coin droit pour afficher le volet droit.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="276">
          <source>On the <bpt id="p1">**</bpt>Product image<ept id="p1">**</ept> FastTab, click <bpt id="p2">**</bpt>Change image<ept id="p2">**</ept>, and upload the physical image to use for the selected product in Offline mode.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans l'organisateur <bpt id="p1">**</bpt>Image du produit<ept id="p1">**</ept>, cliquez sur <bpt id="p2">**</bpt>Modifier l'image<ept id="p2">**</ept>, puis téléchargez l'image physique à utiliser pour le produit sélectionné en mode hors ligne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="277">
          <source>Save and close the page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sauvegardez et fermez la page.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="278">
          <source>While MPOS is in Online mode, run the Catalog job in HQ, to make sure that the data is sent at least one time to the offline database.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Alors que MPOS est en mode en ligne, exécutez la tâche de catalogue dans HQ, assurez-vous que les données sont envoyées au moins une fois à la base de données hors ligne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="279">
          <source>Put MPOS into Offline mode.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mettez MPOS en mode hors ligne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="280">
          <source>You should see the image that you uploaded for the specific product in HQ.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Vous devez voir l'image que vous avez téléchargée pour le produit spécifique dans HQ.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="281">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Product image in Offline mode<ept id="p1">](./media/offline1.png)](./media/offline1.png)</ept></source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Image du produit en mode hors connexion<ept id="p1">](./media/offline1.png)](./media/offline1.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="282">
          <source>Set up catalog, category, employee, and customer images to appear in Offline mode for MPOS</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Paramétrer des images de catalogue, de catégorie, d'employé et de client à afficher en mode hors connexion pour MPOS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="283">
          <source>The catalog, category, employee, and customer images that must be used in Offline mode can be set up by adding the required image's destination link to the gallery and setting the image as the default image for the selected entity.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les images de catalogue, de catégorie, d'employé, et de client qui doivent être utilisées en mode hors connexion peuvent être paramétrées en ajoutant le lien de destination de l'image nécessaire à la galerie et en paramétrant l'image comme image par défaut pour l'entité sélectionnée.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="284">
          <source>Go to the catalog, and then, on the Action Pane, click <bpt id="p1">**</bpt>Media<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Images<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Accédez au catalogues, puis dans le volet Actions, cliquez sur <bpt id="p1">**</bpt>Supports<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Images<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="285">
          <source>Follow the steps in the <bpt id="p1">[</bpt>Overwrite from the entity-level Preview page<ept id="p1">](#overwrite-from-the-entity-level-preview-page)</ept> section to add the external image URL.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Suivez les étapes de la section <bpt id="p1">[</bpt>Remplacer à partir de la page d'aperçu au niveau de l'entité<ept id="p1">](#overwrite-from-the-entity-level-preview-page)</ept> pour ajouter l'URL d'image externe.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="286">
          <source>Mark this image as the default image for the catalog by selecting the check box against the Image listed in the grid.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Marquez cette image comme image par défaut pour le catalogue en activant la case à cocher en regard de l'image répertoriée dans la grille.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="287">
          <source>Run the Catalog job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exécutez la tâche de catalogue.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="288">
          <source>This image will now be used as the Offline image for that catalog in MPOS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette image est désormais utilisée comme image hors connexion pour ce catalogue dans MPOS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="289">
          <source>Follow a similar process for other entities, such as Category, Employee, and Customer.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Suivez un processus similaire pour d'autres entités, telles que Catégorie, Employé, et Client.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="290">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Offline image<ept id="p1">](./media/offline2.png)](./media/offline2.png)</ept></source><target logoport:matchpercent="70" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Image en mode hors connexion<ept id="p1">](./media/offline2.png)](./media/offline2.png)</ept></target>
        </trans-unit>
      </group>
    </body>
  </file>
</xliff>