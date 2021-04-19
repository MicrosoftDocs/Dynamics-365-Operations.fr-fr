---
title: Ajouter des champs de données dans l’intégration fiscale à l’aide d’extensions
description: Cette rubrique explique comment utiliser les extensions X++ pour ajouter des champs de données à l’intégration fiscale.
author: qire
ms.date: 03/26/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: fdf112bbdd5245d19ab1d07cfcf94c58bf8208c5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830338"
---
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a><span data-ttu-id="b230b-103">Ajouter des champs de données dans l’intégration fiscale à l’aide d’une extension</span><span class="sxs-lookup"><span data-stu-id="b230b-103">Add data fields in the tax integration by using extension</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="b230b-104">Cette rubrique explique comment utiliser les extensions X++ pour ajouter des champs de données à l’intégration fiscale.</span><span class="sxs-lookup"><span data-stu-id="b230b-104">This topic explains how to use X++ extensions to add data fields in the tax integration.</span></span> <span data-ttu-id="b230b-105">Ces champs peuvent être étendus au modèle de données fiscales du service de taxe et être utilisés pour déterminer les codes taxe.</span><span class="sxs-lookup"><span data-stu-id="b230b-105">These fields can be extended to the tax data model of the tax service and used to determine tax codes.</span></span> <span data-ttu-id="b230b-106">Pour plus d’informations, consultez [Ajouter des champs de données dans les configurations de taxe](tax-service-add-data-fields-tax-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="b230b-106">For more information, see [Add data fields in tax configurations](tax-service-add-data-fields-tax-configurations.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="b230b-107">Modèle de données</span><span class="sxs-lookup"><span data-stu-id="b230b-107">Data model</span></span>

<span data-ttu-id="b230b-108">Les données du modèle de données sont portées par des objets et implémentées par des classes.</span><span class="sxs-lookup"><span data-stu-id="b230b-108">The data in the data model is carried by objects and implemented by classes.</span></span>

<span data-ttu-id="b230b-109">Voici une liste des principaux objets :</span><span class="sxs-lookup"><span data-stu-id="b230b-109">Here is a list of the major objects:</span></span>

* <span data-ttu-id="b230b-110">AxClass/TaxIntegration **Document** Object</span><span class="sxs-lookup"><span data-stu-id="b230b-110">AxClass/TaxIntegration **Document** Object</span></span>
* <span data-ttu-id="b230b-111">AxClass/TaxIntegration **Line** Object</span><span class="sxs-lookup"><span data-stu-id="b230b-111">AxClass/TaxIntegration **Line** Object</span></span>
* <span data-ttu-id="b230b-112">AxClass/TaxIntegration **TaxLine** Object</span><span class="sxs-lookup"><span data-stu-id="b230b-112">AxClass/TaxIntegration **TaxLine** Object</span></span>

<span data-ttu-id="b230b-113">L’illustration suivante montre les relations entre ces objets.</span><span class="sxs-lookup"><span data-stu-id="b230b-113">The following illustration shows how these objects are related.</span></span>

<span data-ttu-id="b230b-114">[![Relation d’objet du modèle de données](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)</span><span class="sxs-lookup"><span data-stu-id="b230b-114">[![Data model object relationship](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)</span></span>

<span data-ttu-id="b230b-115">Un objet **Document** peut contenir plusieurs objets **Ligne**.</span><span class="sxs-lookup"><span data-stu-id="b230b-115">A **Document** object can contain many **Line** objects.</span></span> <span data-ttu-id="b230b-116">Chaque objet contient des métadonnées pour le service de taxe.</span><span class="sxs-lookup"><span data-stu-id="b230b-116">Each object contains metadata for the tax service.</span></span>

- <span data-ttu-id="b230b-117">`TaxIntegrationDocumentObject` comporte les métadonnées `originAddress`, qui contiennent des informations sur l’adresse source, et les métadonnées `includingTax`, qui indiquent si le montant de la ligne comprend la taxe de vente.</span><span class="sxs-lookup"><span data-stu-id="b230b-117">`TaxIntegrationDocumentObject` has `originAddress` metadata, which contains information about the source address, and `includingTax` metadata, which indicates whether the line amount includes sales tax.</span></span>
- <span data-ttu-id="b230b-118">`TaxIntegrationLineObject` comporte les métadonnées `itemId`, `quantity` et `categoryId`.</span><span class="sxs-lookup"><span data-stu-id="b230b-118">`TaxIntegrationLineObject` has `itemId`, `quantity`, and `categoryId` metadata.</span></span>

> [!NOTE]
> <span data-ttu-id="b230b-119">`TaxIntegrationLineObject` implémente également les objets **Frais**.</span><span class="sxs-lookup"><span data-stu-id="b230b-119">`TaxIntegrationLineObject` also implements **Charge** objects.</span></span>

## <a name="integration-flow"></a><span data-ttu-id="b230b-120">Flux d’intégration</span><span class="sxs-lookup"><span data-stu-id="b230b-120">Integration flow</span></span>

<span data-ttu-id="b230b-121">Les données du flux sont manipulées par des activités.</span><span class="sxs-lookup"><span data-stu-id="b230b-121">The data in the flow is manipulated by activities.</span></span>

### <a name="key-activities"></a><span data-ttu-id="b230b-122">Principales activités</span><span class="sxs-lookup"><span data-stu-id="b230b-122">Key activities</span></span>

* <span data-ttu-id="b230b-123">AxClass/TaxIntegration **Calculation** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="b230b-123">AxClass/TaxIntegration **Calculation** ActivityOnDocument</span></span>
* <span data-ttu-id="b230b-124">AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="b230b-124">AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument</span></span>
* <span data-ttu-id="b230b-125">AxClass/TaxIntegration **DataPersistence** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="b230b-125">AxClass/TaxIntegration **DataPersistence** ActivityOnDocument</span></span>
* <span data-ttu-id="b230b-126">AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="b230b-126">AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument</span></span>
* <span data-ttu-id="b230b-127">AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="b230b-127">AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument</span></span>

<span data-ttu-id="b230b-128">Les activités sont exécutées dans l’ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="b230b-128">Activities are run in the following order:</span></span>

1. <span data-ttu-id="b230b-129">Récupération des paramètres</span><span class="sxs-lookup"><span data-stu-id="b230b-129">Setting Retrieval</span></span>
2. <span data-ttu-id="b230b-130">Récupération des données</span><span class="sxs-lookup"><span data-stu-id="b230b-130">Data Retrieval</span></span>
3. <span data-ttu-id="b230b-131">Service de calcul</span><span class="sxs-lookup"><span data-stu-id="b230b-131">Calculation Service</span></span>
4. <span data-ttu-id="b230b-132">Change de la devise</span><span class="sxs-lookup"><span data-stu-id="b230b-132">Currency Exchange</span></span>
5. <span data-ttu-id="b230b-133">Persistance des données</span><span class="sxs-lookup"><span data-stu-id="b230b-133">Data Persistence</span></span>

<span data-ttu-id="b230b-134">Par exemple, étendez **Récupération des données** avant **Service de calcul**.</span><span class="sxs-lookup"><span data-stu-id="b230b-134">For example, extend **Data Retrieval** before **Calculation Service**.</span></span>

#### <a name="data-retrieval-activities"></a><span data-ttu-id="b230b-135">Activités de récupération de données</span><span class="sxs-lookup"><span data-stu-id="b230b-135">Data Retrieval activities</span></span>

<span data-ttu-id="b230b-136">Les activités de **Récupération de données** récupèrent les données de la base de données.</span><span class="sxs-lookup"><span data-stu-id="b230b-136">**Data Retrieval** activities retrieve data from the database.</span></span> <span data-ttu-id="b230b-137">Il existe des adaptateurs pour différentes transactions permettant de récupérer des données à partir de différentes tables de transaction :</span><span class="sxs-lookup"><span data-stu-id="b230b-137">Adapters for different transactions are available to retrieve data from different transaction tables:</span></span>

- <span data-ttu-id="b230b-138">AxClass/TaxIntegration **PurchTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="b230b-138">AxClass/TaxIntegration **PurchTable** DataRetrieval</span></span>
- <span data-ttu-id="b230b-139">AxClass/TaxIntegration **PurchParmTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="b230b-139">AxClass/TaxIntegration **PurchParmTable** DataRetrieval</span></span>
- <span data-ttu-id="b230b-140">AxClass/TaxIntegration **PurchREQTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="b230b-140">AxClass/TaxIntegration **PurchREQTable** DataRetrieval</span></span>
- <span data-ttu-id="b230b-141">AxClass/TaxIntegration **PurchRFQTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="b230b-141">AxClass/TaxIntegration **PurchRFQTable** DataRetrieval</span></span>
- <span data-ttu-id="b230b-142">AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="b230b-142">AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval</span></span>
- <span data-ttu-id="b230b-143">AxClass/TaxIntegration **SalesTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="b230b-143">AxClass/TaxIntegration **SalesTable** DataRetrieval</span></span>
- <span data-ttu-id="b230b-144">AxClass/TaxIntegration **SalesParm** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="b230b-144">AxClass/TaxIntegration **SalesParm** DataRetrieval</span></span>

<span data-ttu-id="b230b-145">Dans ces activités de **Récupération de données**, les données sont copiées de la base de données vers `TaxIntegrationDocumentObject` et `TaxIntegrationLineObject`.</span><span class="sxs-lookup"><span data-stu-id="b230b-145">In these **Data Retrieval** activities, data is copied from the database to `TaxIntegrationDocumentObject` and `TaxIntegrationLineObject`.</span></span> <span data-ttu-id="b230b-146">Étant donné que toutes ces activités étendent la même classe de modèle abstrait, elles ont des méthodes communes.</span><span class="sxs-lookup"><span data-stu-id="b230b-146">Because all these activities extend the same abstract template class, they have common methods.</span></span>

#### <a name="calculation-service-activities"></a><span data-ttu-id="b230b-147">Activités du service de calcul</span><span class="sxs-lookup"><span data-stu-id="b230b-147">Calculation Service activities</span></span>

<span data-ttu-id="b230b-148">L’activité **Service de calcul** est le lien entre le service de taxe et l’intégration fiscale.</span><span class="sxs-lookup"><span data-stu-id="b230b-148">The **Calculation Service** activity is the link between the tax service and the tax integration.</span></span> <span data-ttu-id="b230b-149">Cette activité est responsable des fonctions suivantes :</span><span class="sxs-lookup"><span data-stu-id="b230b-149">This activity is responsible for the following functions:</span></span>

1. <span data-ttu-id="b230b-150">Construire la requête.</span><span class="sxs-lookup"><span data-stu-id="b230b-150">Construct the request.</span></span>
2. <span data-ttu-id="b230b-151">Valider la requête auprès du service de taxe.</span><span class="sxs-lookup"><span data-stu-id="b230b-151">Post the request to the tax service.</span></span>
3. <span data-ttu-id="b230b-152">Obtenir la réponse de la part du service de taxe.</span><span class="sxs-lookup"><span data-stu-id="b230b-152">Get the response from the tax service.</span></span>
4. <span data-ttu-id="b230b-153">Analyser la réponse.</span><span class="sxs-lookup"><span data-stu-id="b230b-153">Parse the response.</span></span>

<span data-ttu-id="b230b-154">Un champ de données que vous ajoutez à la requête sera validé avec d’autres métadonnées.</span><span class="sxs-lookup"><span data-stu-id="b230b-154">A data field that you add to the request will be posted together with other metadata.</span></span> 

## <a name="extension-implementation"></a><span data-ttu-id="b230b-155">Implémentation de l’extension</span><span class="sxs-lookup"><span data-stu-id="b230b-155">Extension implementation</span></span>

<span data-ttu-id="b230b-156">Cette section fournit des étapes détaillées qui expliquent comment implémenter l’extension.</span><span class="sxs-lookup"><span data-stu-id="b230b-156">This section provides detailed steps that explain how to implement the extension.</span></span> <span data-ttu-id="b230b-157">Elle prend comme exemples les dimensions financières **Centre de coûts** et **Projet**.</span><span class="sxs-lookup"><span data-stu-id="b230b-157">It uses the **Cost center** and **Project** financial dimensions as examples.</span></span>

### <a name="step-1-add-the-data-variable-in-the-object-class"></a><span data-ttu-id="b230b-158">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="b230b-158">Step 1.</span></span> <span data-ttu-id="b230b-159">Ajouter la variable de données dans la classe d’objets</span><span class="sxs-lookup"><span data-stu-id="b230b-159">Add the data variable in the object class</span></span>

<span data-ttu-id="b230b-160">La classe d’objets contient la variable de données et les méthodes getter/setter pour les données.</span><span class="sxs-lookup"><span data-stu-id="b230b-160">The object class contains the data variable and getter/setter methods for the data.</span></span> <span data-ttu-id="b230b-161">Ajoutez le champ de données à `TaxIntegrationDocumentObject` ou à `TaxIntegrationLineObject`, en fonction du niveau du champ.</span><span class="sxs-lookup"><span data-stu-id="b230b-161">Add the data field to either `TaxIntegrationDocumentObject` or `TaxIntegrationLineObject`, depending on the level of the field.</span></span> <span data-ttu-id="b230b-162">L’exemple suivant utilise le niveau de ligne et le nom de fichier est `TaxIntegrationLineObject_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="b230b-162">The following example uses the line level, and the file name is `TaxIntegrationLineObject_Extension.xpp`.</span></span>

> [!NOTE]
> <span data-ttu-id="b230b-163">Si le champ de données que vous ajoutez se trouve au niveau document, remplacez le nom du fichier par `TaxIntegrationDocumentObject_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="b230b-163">If the data field that you're adding is at the document level, change the file name to `TaxIntegrationDocumentObject_Extension.xpp`.</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

<span data-ttu-id="b230b-164">**Centre de coûts** et **Projet** sont ajoutés en tant que variables privées.</span><span class="sxs-lookup"><span data-stu-id="b230b-164">**Cost center** and **Project** are added as private variables.</span></span> <span data-ttu-id="b230b-165">Créez des méthodes getter et setter pour ces champs de données afin de manipuler les données.</span><span class="sxs-lookup"><span data-stu-id="b230b-165">Create getter and setter methods for these data fields to manipulate the data.</span></span>

### <a name="step-2-retrieve-data-from-the-database"></a><span data-ttu-id="b230b-166">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="b230b-166">Step 2.</span></span> <span data-ttu-id="b230b-167">Récupérer les données de la base de données</span><span class="sxs-lookup"><span data-stu-id="b230b-167">Retrieve data from the database</span></span>

<span data-ttu-id="b230b-168">Spécifiez la transaction et étendez les classes d’adaptateur appropriées pour récupérer les données.</span><span class="sxs-lookup"><span data-stu-id="b230b-168">Specify the transaction, and extend the appropriate adapter classes to retrieve the data.</span></span> <span data-ttu-id="b230b-169">Par exemple, si vous utilisez une transaction **Commande fournisseur**, vous devez étendre `TaxIntegrationPurchTableDataRetrieval` et `TaxIntegrationVendInvoiceInfoTableDataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="b230b-169">For example, if you use a **Purchase order** transaction, you must extend `TaxIntegrationPurchTableDataRetrieval` and `TaxIntegrationVendInvoiceInfoTableDataRetrieval`.</span></span> 

> [!NOTE]
> <span data-ttu-id="b230b-170">`TaxIntegrationPurchParmTableDataRetrieval` est hérité de `TaxIntegrationPurchTableDataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="b230b-170">`TaxIntegrationPurchParmTableDataRetrieval` is inherited from `TaxIntegrationPurchTableDataRetrieval`.</span></span> <span data-ttu-id="b230b-171">Il ne doit pas être modifié à moins que la logique des tables `purchTable` et `purchParmTable` ne soit différente.</span><span class="sxs-lookup"><span data-stu-id="b230b-171">It should not be changed unless the logic of the `purchTable` and `purchParmTable` tables differs.</span></span>

<span data-ttu-id="b230b-172">Si le champ de données doit être ajouté pour toutes les transactions, étendez toutes les classes `DataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="b230b-172">If the data field should be added for all transactions, extend all `DataRetrieval` classes.</span></span>

<span data-ttu-id="b230b-173">Comme toutes les activités **Récupération de données** étendent la même classe de modèle, les structures de classe, les variables et les méthodes sont similaires.</span><span class="sxs-lookup"><span data-stu-id="b230b-173">Because all **Data Retrieval** activities extend the same template class, the class structures, variables, and methods are similar.</span></span>

```X++
protected TaxIntegrationDocumentObject document;

/// <summary>
/// Copies to the document.
/// </summary>
protected abstract void copyToDocument()
{
    // It is recommended to implement as:
    //
    // this.copyToDocumentByDefault();
    // this.copyToDocumentFromHeaderTable();
    // this.copyAddressToDocument();
}
 
/// <summary>
/// Copies to the current line of the document.
/// </summary>
/// <param name = "_line">The current line of the document.</param>
protected abstract void copyToLine(TaxIntegrationLineObject _line)
{
    // It is recommended to implement as:
    //
    // this.copyToLineByDefault(_line);
    // this.copyToLineFromLineTable(_line);
    // this.copyQuantityAndTransactionAmountToLine(_line);
    // this.copyAddressToLine(_line);
    // this.copyToLineFromHeaderTable(_line);
}
```

<span data-ttu-id="b230b-174">L’exemple suivant montre la structure de base lorsque la table `PurchTable` est utilisée.</span><span class="sxs-lookup"><span data-stu-id="b230b-174">The following example shows the basic structure when the `PurchTable` table is used.</span></span>

```X++
public class TaxIntegrationPurchTableDataRetrieval extends TaxIntegrationAbstractDataRetrievalTemplate
{
    protected PurchTable purchTable;
    protected PurchLine purchLine;

    // Query builder methods
    [Replaceable]
    protected SysDaQueryObject getDocumentQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineQueryObject()
    [Replaceable]
    protected SysDaQueryObject getDocumentChargeQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineChargeQueryObject()

    // Data retrieval methods
    protected void copyToDocument()
    protected void copyToDocumentFromHeaderTable()
    protected void copyToLine(TaxIntegrationLineObject _line)
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    ...
}
```

<span data-ttu-id="b230b-175">Lorsque la méthode `CopyToDocument` est appelée, le tampon `this.purchTable` existe déjà.</span><span class="sxs-lookup"><span data-stu-id="b230b-175">When the `CopyToDocument` method is called, the `this.purchTable` buffer already exists.</span></span> <span data-ttu-id="b230b-176">Le but de cette méthode est de copier toutes les données requises à partir de la table `this.purchTable` vers l’objet `document` en utilisant la méthode setter qui a été créée dans la classe `DocumentObject`.</span><span class="sxs-lookup"><span data-stu-id="b230b-176">The purpose of this method is to copy all the required data from `this.purchTable` to the `document` object by using the setter method that was created in the `DocumentObject` class.</span></span>

<span data-ttu-id="b230b-177">De même, un tampon `this.purchLine` existe déjà dans la méthode `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="b230b-177">Likewise, a `this.purchLine` buffer already exists in the `CopyToLine` method.</span></span> <span data-ttu-id="b230b-178">Le but de cette méthode est de copier toutes les données requises à partir de la table `this.purchLine` vers l’objet `_line` en utilisant la méthode setter qui a été créée dans la classe `LineObject`.</span><span class="sxs-lookup"><span data-stu-id="b230b-178">The purpose of this method is to copy all the required data from `this.purchLine` to the `_line` object by using the setter method that was created in the `LineObject` class.</span></span>

<span data-ttu-id="b230b-179">L’approche la plus simple consiste à étendre les méthodes `CopyToDocument` et `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="b230b-179">The most straightforward approach is to extend the `CopyToDocument` and `CopyToLine` methods.</span></span> <span data-ttu-id="b230b-180">Cependant, nous vous recommandons d’essayer d’abord les méthodes `copyToDocumentFromHeaderTable` et `copyToLineFromLineTable`.</span><span class="sxs-lookup"><span data-stu-id="b230b-180">However, we recommend that you try the `copyToDocumentFromHeaderTable` and `copyToLineFromLineTable` methods first.</span></span> <span data-ttu-id="b230b-181">Si elles ne fonctionnent pas comme vous le souhaitez, implémentez votre propre méthode et appelez-la dans `CopyToDocument` et `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="b230b-181">If they don't work as you require, implement your own method, and call it in `CopyToDocument` and `CopyToLine`.</span></span> <span data-ttu-id="b230b-182">Il existe trois situations courantes dans lesquelles vous pouvez utiliser cette approche :</span><span class="sxs-lookup"><span data-stu-id="b230b-182">There are three common situations where you might use this approach:</span></span>

- <span data-ttu-id="b230b-183">Le champ obligatoire se trouve dans `PurchTable` ou `PurchLine`.</span><span class="sxs-lookup"><span data-stu-id="b230b-183">The required field is in `PurchTable` or `PurchLine`.</span></span> <span data-ttu-id="b230b-184">Dans cette situation, vous pouvez étendre `copyToDocumentFromHeaderTable` et `copyToLineFromLineTable`.</span><span class="sxs-lookup"><span data-stu-id="b230b-184">In this situation, you can extend `copyToDocumentFromHeaderTable` and `copyToLineFromLineTable`.</span></span> <span data-ttu-id="b230b-185">Voici l’exemple de code.</span><span class="sxs-lookup"><span data-stu-id="b230b-185">Here is the sample code.</span></span>

    ```X++
    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        next copyToLineFromLineTable(_line);
        // if we already added XXX in TaxIntegrationLineObject
        _line.setXXX(this.purchLine.XXX);
    }
    ```

- <span data-ttu-id="b230b-186">Les données requises ne figurent pas dans la table par défaut de la transaction.</span><span class="sxs-lookup"><span data-stu-id="b230b-186">The required data isn't in the default table of the transaction.</span></span> <span data-ttu-id="b230b-187">Cependant, il existe des relations de jointure avec la table par défaut et le champ est requis sur la plupart des lignes.</span><span class="sxs-lookup"><span data-stu-id="b230b-187">However, there are some join relationships with the default table, and the field is required on most lines.</span></span> <span data-ttu-id="b230b-188">Dans cette situation, remplacez `getDocumentQueryObject` ou `getLineObject` pour interroger la table par relation de jointure.</span><span class="sxs-lookup"><span data-stu-id="b230b-188">In this situation, replace `getDocumentQueryObject` or `getLineObject` to query the table by join relationship.</span></span> <span data-ttu-id="b230b-189">Dans l’exemple suivant, le champ **Livrer maintenant** est intégré à la commande client au niveau de la ligne.</span><span class="sxs-lookup"><span data-stu-id="b230b-189">In the following example, the **Deliver Now** field is integrated with the sales order at the line level.</span></span>

    ```X++
    public class TaxIntegrationSalesTableDataRetrieval
    {
        protected MCRSalesLineDropShipment mcrSalesLineDropShipment;

        /// <summary>
        /// Gets the query for the lines of the document.
        /// </summary>
        /// <returns>The query for the lines of the document</returns>
        [Replaceable]
        protected SysDaQueryObject getLineQueryObject()
        {
            return SysDaQueryObjectBuilder::from(this.salesLine)
                .where(this.salesLine, fieldStr(SalesLine, SalesId)).isEqualToLiteral(this.salesTable.SalesId)
                .outerJoin(this.mcrSalesLineDropShipment)
                .where(this.mcrSalesLineDropShipment, fieldStr(MCRSalesLineDropShipment, SalesLine)).isEqualTo(this.salesLine, fieldStr(SalesLine, RecId))
                .toSysDaQueryObject();
        }
    }
    ```

    <span data-ttu-id="b230b-190">Dans cet exemple, un tampon `mcrSalesLineDropShipment` est déclaré et la requête est définie dans `getLineQueryObject`.</span><span class="sxs-lookup"><span data-stu-id="b230b-190">In this example, a `mcrSalesLineDropShipment` buffer is declared, and the query is defined in `getLineQueryObject`.</span></span> <span data-ttu-id="b230b-191">La requête utilise la relation `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`.</span><span class="sxs-lookup"><span data-stu-id="b230b-191">The query uses the relationship `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`.</span></span> <span data-ttu-id="b230b-192">Pendant que vous réalisez l’extension dans cette situation, vous pouvez remplacer `getLineQueryObject` par votre propre objet de requête construit.</span><span class="sxs-lookup"><span data-stu-id="b230b-192">While you're extending in this situation, you can replace `getLineQueryObject` with your own constructed query object.</span></span> <span data-ttu-id="b230b-193">Notez toutefois les points suivants :</span><span class="sxs-lookup"><span data-stu-id="b230b-193">However, note the following points:</span></span>

    * <span data-ttu-id="b230b-194">Parce que la valeur de retour de la méthode `getLineQueryObject` est `SysDaQueryObject`, vous devez construire cet objet à l’aide de l’approche SysDa.</span><span class="sxs-lookup"><span data-stu-id="b230b-194">Because the return value of the `getLineQueryObject` method is `SysDaQueryObject`, you must construct this object by using the SysDa approach.</span></span>
    * <span data-ttu-id="b230b-195">Impossible de supprimer la table existante.</span><span class="sxs-lookup"><span data-stu-id="b230b-195">Can't remove existed table.</span></span>

- <span data-ttu-id="b230b-196">Les données requises sont liées à la table de transaction par une relation de jointure complexe, ou la relation n’est pas un à un (1 : 1) mais un à plusieurs (1 : N).</span><span class="sxs-lookup"><span data-stu-id="b230b-196">The required data is related to the transaction table by a complicated join relationship, or the relation isn't one to one (1:1) but one to many (1:N).</span></span> <span data-ttu-id="b230b-197">Dans cette situation, les choses deviennent un peu compliquées.</span><span class="sxs-lookup"><span data-stu-id="b230b-197">In this situation, things become a little complicated.</span></span> <span data-ttu-id="b230b-198">Cette situation s’applique à l’exemple des dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="b230b-198">This situation applies to the example of financial dimensions.</span></span> 

    <span data-ttu-id="b230b-199">Dans ce cas, vous pouvez implémenter votre propre méthode pour récupérer les données.</span><span class="sxs-lookup"><span data-stu-id="b230b-199">In this situation, you can implement your own method to retrieve the data.</span></span> <span data-ttu-id="b230b-200">Voici l’exemple de code dans le fichier `TaxIntegrationPurchTableDataRetrieval_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="b230b-200">Here is the sample code in the `TaxIntegrationPurchTableDataRetrieval_Extension.xpp` file.</span></span>

    ```X++
    [ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
    final class TaxIntegrationPurchTableDataRetrieval_Extension
    {
        private const str CostCenterKey = 'CostCenter';
        private const str ProjectKey = 'Project';

        /// <summary>
        /// Copies to the current line of the document from.
        /// </summary>
        /// <param name = "_line">The current line of the document.</param>
        protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
        {
            Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
            if (dimensionAttributeMap.exists(CostCenterKey))
            {
                _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
            }
            if (dimensionAttributeMap.exists(ProjectKey))
            {
                _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
            }
            next copyToLineFromLineTable(_line);
        }
        private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
        {
            DimensionAttribute dimensionAttribute;
            DimensionAttributeValue dimensionAttributeValue;
            DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
            Map ret = new Map(Types::String, Types::String);

            select Name, RecId from dimensionAttribute
                join dimensionAttributeValue
                    where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
                join DimensionAttributeValueSetItem
                    where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                        && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;

            while(dimensionAttribute.RecId)
            {
                ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
                next dimensionAttribute;
            }
            return ret;
        }
    }
    ```

### <a name="step-3-add-data-to-the-request"></a><span data-ttu-id="b230b-201">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="b230b-201">Step 3.</span></span> <span data-ttu-id="b230b-202">Ajouter des données à la requête</span><span class="sxs-lookup"><span data-stu-id="b230b-202">Add data to the request</span></span>

<span data-ttu-id="b230b-203">Étendez la méthode `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` ou `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` pour ajouter des données à la requête.</span><span class="sxs-lookup"><span data-stu-id="b230b-203">Extend the `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` or `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` method to add data to the request.</span></span> <span data-ttu-id="b230b-204">Voici l’exemple de code dans le fichier `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="b230b-204">Here is the sample code in the `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp` file.</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```

<span data-ttu-id="b230b-205">Dans ce code, `_destination` est l’objet wrapper utilisé pour générer la requête de validation, et `_source` est l’objet `TaxIntegrationLineObject`.</span><span class="sxs-lookup"><span data-stu-id="b230b-205">In this code, `_destination` is the wrapper object that is used to generate the post request, and `_source` is the `TaxIntegrationLineObject` object.</span></span> 

> [!NOTE]
> * <span data-ttu-id="b230b-206">Définissez la clé utilisée dans le formulaire de requête comme `private const str`.</span><span class="sxs-lookup"><span data-stu-id="b230b-206">Define the key that is used in the request form as `private const str`.</span></span>
> * <span data-ttu-id="b230b-207">Définissez le champ dans la méthode `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` en utilisant la méthode `SetField`.</span><span class="sxs-lookup"><span data-stu-id="b230b-207">Set the field in the `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` method by using the `SetField` method.</span></span> <span data-ttu-id="b230b-208">Le type de données du deuxième paramètre doit être `string`.</span><span class="sxs-lookup"><span data-stu-id="b230b-208">The data type of the second parameter should be `string`.</span></span> <span data-ttu-id="b230b-209">Si le type de données n’est pas `string`, convertissez-le en `string`.</span><span class="sxs-lookup"><span data-stu-id="b230b-209">If the data type isn't `string`, convert it to `string`.</span></span>

## <a name="appendix"></a><span data-ttu-id="b230b-210">Annexe</span><span class="sxs-lookup"><span data-stu-id="b230b-210">Appendix</span></span>

<span data-ttu-id="b230b-211">Cette annexe présente l’exemple de code complet pour l’intégration des dimensions financières (**Centre de coûts** et **Projet**) au niveau de la ligne.</span><span class="sxs-lookup"><span data-stu-id="b230b-211">This appendix shows the complete sample code for the integration of financial dimensions (**Cost center** and **Project**) at the line level.</span></span>

### <a name="taxintegrationlineobject_extensionxpp"></a><span data-ttu-id="b230b-212">TaxIntegrationLineObject_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="b230b-212">TaxIntegrationLineObject_Extension.xpp</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a><span data-ttu-id="b230b-213">TaxIntegrationPurchTableDataRetrieval_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="b230b-213">TaxIntegrationPurchTableDataRetrieval_Extension.xpp</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
final class TaxIntegrationPurchTableDataRetrieval_Extension
{
    private const str CostCenterKey = 'CostCenter';
    private const str ProjectKey = 'Project';

    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
        if (dimensionAttributeMap.exists(CostCenterKey))
        {
            _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
        }
        if (dimensionAttributeMap.exists(ProjectKey))
        {
            _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
        }
        next copyToLineFromLineTable(_line);
    }
    private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
    {
        DimensionAttribute dimensionAttribute;
        DimensionAttributeValue dimensionAttributeValue;
        DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
        Map ret = new Map(Types::String, Types::String);
        select Name, RecId from dimensionAttribute
            join dimensionAttributeValue
                where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
            join DimensionAttributeValueSetItem
                where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                    && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;
        while(dimensionAttribute.RecId)
        {
            ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
            next dimensionAttribute;
        }
        return ret;
    }
}
```

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a><span data-ttu-id="b230b-214">TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="b230b-214">TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```
