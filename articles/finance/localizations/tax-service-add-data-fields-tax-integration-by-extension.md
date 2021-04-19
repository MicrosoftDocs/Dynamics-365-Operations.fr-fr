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
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a>Ajouter des champs de données dans l’intégration fiscale à l’aide d’une extension

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Cette rubrique explique comment utiliser les extensions X++ pour ajouter des champs de données à l’intégration fiscale. Ces champs peuvent être étendus au modèle de données fiscales du service de taxe et être utilisés pour déterminer les codes taxe. Pour plus d’informations, consultez [Ajouter des champs de données dans les configurations de taxe](tax-service-add-data-fields-tax-configurations.md).

## <a name="data-model"></a>Modèle de données

Les données du modèle de données sont portées par des objets et implémentées par des classes.

Voici une liste des principaux objets :

* AxClass/TaxIntegration **Document** Object
* AxClass/TaxIntegration **Line** Object
* AxClass/TaxIntegration **TaxLine** Object

L’illustration suivante montre les relations entre ces objets.

[![Relation d’objet du modèle de données](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)

Un objet **Document** peut contenir plusieurs objets **Ligne**. Chaque objet contient des métadonnées pour le service de taxe.

- `TaxIntegrationDocumentObject` comporte les métadonnées `originAddress`, qui contiennent des informations sur l’adresse source, et les métadonnées `includingTax`, qui indiquent si le montant de la ligne comprend la taxe de vente.
- `TaxIntegrationLineObject` comporte les métadonnées `itemId`, `quantity` et `categoryId`.

> [!NOTE]
> `TaxIntegrationLineObject` implémente également les objets **Frais**.

## <a name="integration-flow"></a>Flux d’intégration

Les données du flux sont manipulées par des activités.

### <a name="key-activities"></a>Principales activités

* AxClass/TaxIntegration **Calculation** ActivityOnDocument
* AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument
* AxClass/TaxIntegration **DataPersistence** ActivityOnDocument
* AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument
* AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument

Les activités sont exécutées dans l’ordre suivant :

1. Récupération des paramètres
2. Récupération des données
3. Service de calcul
4. Change de la devise
5. Persistance des données

Par exemple, étendez **Récupération des données** avant **Service de calcul**.

#### <a name="data-retrieval-activities"></a>Activités de récupération de données

Les activités de **Récupération de données** récupèrent les données de la base de données. Il existe des adaptateurs pour différentes transactions permettant de récupérer des données à partir de différentes tables de transaction :

- AxClass/TaxIntegration **PurchTable** DataRetrieval
- AxClass/TaxIntegration **PurchParmTable** DataRetrieval
- AxClass/TaxIntegration **PurchREQTable** DataRetrieval
- AxClass/TaxIntegration **PurchRFQTable** DataRetrieval
- AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval
- AxClass/TaxIntegration **SalesTable** DataRetrieval
- AxClass/TaxIntegration **SalesParm** DataRetrieval

Dans ces activités de **Récupération de données**, les données sont copiées de la base de données vers `TaxIntegrationDocumentObject` et `TaxIntegrationLineObject`. Étant donné que toutes ces activités étendent la même classe de modèle abstrait, elles ont des méthodes communes.

#### <a name="calculation-service-activities"></a>Activités du service de calcul

L’activité **Service de calcul** est le lien entre le service de taxe et l’intégration fiscale. Cette activité est responsable des fonctions suivantes :

1. Construire la requête.
2. Valider la requête auprès du service de taxe.
3. Obtenir la réponse de la part du service de taxe.
4. Analyser la réponse.

Un champ de données que vous ajoutez à la requête sera validé avec d’autres métadonnées. 

## <a name="extension-implementation"></a>Implémentation de l’extension

Cette section fournit des étapes détaillées qui expliquent comment implémenter l’extension. Elle prend comme exemples les dimensions financières **Centre de coûts** et **Projet**.

### <a name="step-1-add-the-data-variable-in-the-object-class"></a>Étape 1. Ajouter la variable de données dans la classe d’objets

La classe d’objets contient la variable de données et les méthodes getter/setter pour les données. Ajoutez le champ de données à `TaxIntegrationDocumentObject` ou à `TaxIntegrationLineObject`, en fonction du niveau du champ. L’exemple suivant utilise le niveau de ligne et le nom de fichier est `TaxIntegrationLineObject_Extension.xpp`.

> [!NOTE]
> Si le champ de données que vous ajoutez se trouve au niveau document, remplacez le nom du fichier par `TaxIntegrationDocumentObject_Extension.xpp`.

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

**Centre de coûts** et **Projet** sont ajoutés en tant que variables privées. Créez des méthodes getter et setter pour ces champs de données afin de manipuler les données.

### <a name="step-2-retrieve-data-from-the-database"></a>Étape 2. Récupérer les données de la base de données

Spécifiez la transaction et étendez les classes d’adaptateur appropriées pour récupérer les données. Par exemple, si vous utilisez une transaction **Commande fournisseur**, vous devez étendre `TaxIntegrationPurchTableDataRetrieval` et `TaxIntegrationVendInvoiceInfoTableDataRetrieval`. 

> [!NOTE]
> `TaxIntegrationPurchParmTableDataRetrieval` est hérité de `TaxIntegrationPurchTableDataRetrieval`. Il ne doit pas être modifié à moins que la logique des tables `purchTable` et `purchParmTable` ne soit différente.

Si le champ de données doit être ajouté pour toutes les transactions, étendez toutes les classes `DataRetrieval`.

Comme toutes les activités **Récupération de données** étendent la même classe de modèle, les structures de classe, les variables et les méthodes sont similaires.

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

L’exemple suivant montre la structure de base lorsque la table `PurchTable` est utilisée.

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

Lorsque la méthode `CopyToDocument` est appelée, le tampon `this.purchTable` existe déjà. Le but de cette méthode est de copier toutes les données requises à partir de la table `this.purchTable` vers l’objet `document` en utilisant la méthode setter qui a été créée dans la classe `DocumentObject`.

De même, un tampon `this.purchLine` existe déjà dans la méthode `CopyToLine`. Le but de cette méthode est de copier toutes les données requises à partir de la table `this.purchLine` vers l’objet `_line` en utilisant la méthode setter qui a été créée dans la classe `LineObject`.

L’approche la plus simple consiste à étendre les méthodes `CopyToDocument` et `CopyToLine`. Cependant, nous vous recommandons d’essayer d’abord les méthodes `copyToDocumentFromHeaderTable` et `copyToLineFromLineTable`. Si elles ne fonctionnent pas comme vous le souhaitez, implémentez votre propre méthode et appelez-la dans `CopyToDocument` et `CopyToLine`. Il existe trois situations courantes dans lesquelles vous pouvez utiliser cette approche :

- Le champ obligatoire se trouve dans `PurchTable` ou `PurchLine`. Dans cette situation, vous pouvez étendre `copyToDocumentFromHeaderTable` et `copyToLineFromLineTable`. Voici l’exemple de code.

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

- Les données requises ne figurent pas dans la table par défaut de la transaction. Cependant, il existe des relations de jointure avec la table par défaut et le champ est requis sur la plupart des lignes. Dans cette situation, remplacez `getDocumentQueryObject` ou `getLineObject` pour interroger la table par relation de jointure. Dans l’exemple suivant, le champ **Livrer maintenant** est intégré à la commande client au niveau de la ligne.

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

    Dans cet exemple, un tampon `mcrSalesLineDropShipment` est déclaré et la requête est définie dans `getLineQueryObject`. La requête utilise la relation `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`. Pendant que vous réalisez l’extension dans cette situation, vous pouvez remplacer `getLineQueryObject` par votre propre objet de requête construit. Notez toutefois les points suivants :

    * Parce que la valeur de retour de la méthode `getLineQueryObject` est `SysDaQueryObject`, vous devez construire cet objet à l’aide de l’approche SysDa.
    * Impossible de supprimer la table existante.

- Les données requises sont liées à la table de transaction par une relation de jointure complexe, ou la relation n’est pas un à un (1 : 1) mais un à plusieurs (1 : N). Dans cette situation, les choses deviennent un peu compliquées. Cette situation s’applique à l’exemple des dimensions financières. 

    Dans ce cas, vous pouvez implémenter votre propre méthode pour récupérer les données. Voici l’exemple de code dans le fichier `TaxIntegrationPurchTableDataRetrieval_Extension.xpp`.

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

### <a name="step-3-add-data-to-the-request"></a>Étape 3. Ajouter des données à la requête

Étendez la méthode `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` ou `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` pour ajouter des données à la requête. Voici l’exemple de code dans le fichier `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp`.

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

Dans ce code, `_destination` est l’objet wrapper utilisé pour générer la requête de validation, et `_source` est l’objet `TaxIntegrationLineObject`. 

> [!NOTE]
> * Définissez la clé utilisée dans le formulaire de requête comme `private const str`.
> * Définissez le champ dans la méthode `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` en utilisant la méthode `SetField`. Le type de données du deuxième paramètre doit être `string`. Si le type de données n’est pas `string`, convertissez-le en `string`.

## <a name="appendix"></a>Annexe

Cette annexe présente l’exemple de code complet pour l’intégration des dimensions financières (**Centre de coûts** et **Projet**) au niveau de la ligne.

### <a name="taxintegrationlineobject_extensionxpp"></a>TaxIntegrationLineObject_Extension.xpp

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

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a>TaxIntegrationPurchTableDataRetrieval_Extension.xpp

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

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a>TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp

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
