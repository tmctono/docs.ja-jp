---
title: DataSet と DataTable のセキュリティ ガイダンス
ms.date: 07/14/2020
dev_langs:
- csharp
ms.openlocfilehash: f0fa43c467cc7866e69115acb5f807e6487fda7a
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608528"
---
# <a name="dataset-and-datatable-security-guidance"></a><span data-ttu-id="559e9-102">DataSet と DataTable のセキュリティ ガイダンス</span><span class="sxs-lookup"><span data-stu-id="559e9-102">DataSet and DataTable security guidance</span></span>

<span data-ttu-id="559e9-103">この記事は以下に適用されます。</span><span class="sxs-lookup"><span data-stu-id="559e9-103">This article applies to:</span></span>

* <span data-ttu-id="559e9-104">.NET Framework (すべてのバージョン)</span><span class="sxs-lookup"><span data-stu-id="559e9-104">.NET Framework (all versions)</span></span>
* <span data-ttu-id="559e9-105">.NET Core 以降</span><span class="sxs-lookup"><span data-stu-id="559e9-105">.NET Core and later</span></span>
* <span data-ttu-id="559e9-106">.NET 5.0 以降</span><span class="sxs-lookup"><span data-stu-id="559e9-106">.NET 5.0 and later</span></span>

<span data-ttu-id="559e9-107">[DataSet](/dotnet/api/system.data.dataset) 型と [DataTable](/dotnet/api/system.data.datatable) 型は .NET のレガシ コンポーネントであり、マネージド オブジェクトとしてデータ セットを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="559e9-107">The [DataSet](/dotnet/api/system.data.dataset) and [DataTable](/dotnet/api/system.data.datatable) types are legacy .NET components that allow representing data sets as managed objects.</span></span> <span data-ttu-id="559e9-108">これらのコンポーネントは、元の [ADO.NET インフラストラクチャ](/dotnet/framework/data/adonet/dataset-datatable-dataview/)の一部として .NET 1.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="559e9-108">These components were introduced in .NET 1.0 as part of the original [ADO.NET infrastructure](/dotnet/framework/data/adonet/dataset-datatable-dataview/).</span></span> <span data-ttu-id="559e9-109">それらの目標は、リレーショナル データ セットに対するマネージド ビューを提供し、基になるデータのソースが XML、SQL、または他のテクノロジであるかどうかを抽象化することでした。</span><span class="sxs-lookup"><span data-stu-id="559e9-109">Their goal was to provide a managed view over a relational data set, abstracting away whether the underlying source of the data was XML, SQL, or another technology.</span></span>

<span data-ttu-id="559e9-110">最新のデータ ビュー パラダイムを含め、ADO.NET の詳細については、[ADO.NET のドキュメント](/dotnet/framework/data/adonet/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559e9-110">For more information on ADO.NET, including more modern data view paradigms, see [the ADO.NET documentation](/dotnet/framework/data/adonet/).</span></span>

## <a name="default-restrictions-when-deserializing-a-dataset-or-datatable-from-xml"></a><span data-ttu-id="559e9-111">XML から DataSet または DataTable を逆シリアル化するときの既定の制限</span><span class="sxs-lookup"><span data-stu-id="559e9-111">Default restrictions when deserializing a DataSet or DataTable from XML</span></span>

<span data-ttu-id="559e9-112">.NET Framework、.NET Core、.NET のサポートされているすべてのバージョンで、`DataSet` と `DataTable` には、逆シリアル化されるデータに存在できるオブジェクトの型に関して次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-112">On all supported versions of .NET Framework, .NET Core, and .NET, `DataSet` and `DataTable` place the following restrictions on what types of objects may be present in the deserialized data.</span></span> <span data-ttu-id="559e9-113">既定では、このリストは以下に制限されます。</span><span class="sxs-lookup"><span data-stu-id="559e9-113">By default, this list is restricted to:</span></span>

* <span data-ttu-id="559e9-114">プリミティブとプリミティブに相当するもの: `bool`、`char`、`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`float`、`double`、`decimal`、`DateTime`、`DateTimeOffset`、`TimeSpan`、`string`、`Guid`、`SqlBinary`、`SqlBoolean`、`SqlByte`、`SqlBytes`、`SqlChars`、`SqlDateTime`、`SqlDecimal`、`SqlDouble`、`SqlGuid`、`SqlInt16`、`SqlInt32`、`SqlInt64`、`SqlMoney`、`SqlSingle`、`SqlString`。</span><span class="sxs-lookup"><span data-stu-id="559e9-114">Primitives and primitive equivalents: `bool`, `char`, `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, `decimal`, `DateTime`, `DateTimeOffset`, `TimeSpan`, `string`, `Guid`, `SqlBinary`, `SqlBoolean`, `SqlByte`, `SqlBytes`, `SqlChars`, `SqlDateTime`, `SqlDecimal`, `SqlDouble`, `SqlGuid`, `SqlInt16`, `SqlInt32`, `SqlInt64`, `SqlMoney`, `SqlSingle`, and `SqlString`.</span></span>
* <span data-ttu-id="559e9-115">一般に使用される非プリミティブ: `Type`、`Uri`、`BigInteger`。</span><span class="sxs-lookup"><span data-stu-id="559e9-115">Commonly used non-primitives: `Type`, `Uri`, and `BigInteger`.</span></span>
* <span data-ttu-id="559e9-116">一般に使用される _System.Drawing_ 型: `Color`、`Point`、`PointF`、`Rectangle`、`RectangleF`、`Size`、`SizeF`。</span><span class="sxs-lookup"><span data-stu-id="559e9-116">Commonly used _System.Drawing_ types: `Color`, `Point`, `PointF`, `Rectangle`, `RectangleF`, `Size`, and `SizeF`.</span></span>
* <span data-ttu-id="559e9-117">`Enum` 型。</span><span class="sxs-lookup"><span data-stu-id="559e9-117">`Enum` types.</span></span>
* <span data-ttu-id="559e9-118">上記の型の配列およびリスト。</span><span class="sxs-lookup"><span data-stu-id="559e9-118">Arrays and lists of the above types.</span></span>

<span data-ttu-id="559e9-119">受信 XML データに、このリストにない型のオブジェクトが含まれている場合:</span><span class="sxs-lookup"><span data-stu-id="559e9-119">If the incoming XML data contains an object whose type is not in this list:</span></span>

* <span data-ttu-id="559e9-120">例外がスローされる。</span><span class="sxs-lookup"><span data-stu-id="559e9-120">An exception is thrown.</span></span>
* <span data-ttu-id="559e9-121">逆シリアル化操作が失敗する。</span><span class="sxs-lookup"><span data-stu-id="559e9-121">The deserialization operation fails.</span></span>

<span data-ttu-id="559e9-122">既存の `DataSet` または `DataTable` インスタンスに XML を読み込むときは、既存の列の定義も考慮されます。</span><span class="sxs-lookup"><span data-stu-id="559e9-122">When loading XML into an existing `DataSet` or `DataTable` instance, the existing column definitions are also taken into account.</span></span> <span data-ttu-id="559e9-123">テーブルにカスタム型の列定義が既に含まれている場合は、XML の逆シリアル化操作の間だけ、その型が許可リストに一時的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="559e9-123">If the table already contains a column definition of a custom type, that type is temporarily added to the allow list for the duration of the XML deserialization operation.</span></span>

```cs
XmlReader xmlReader = GetXmlReader();

// Assume the XML blob contains data for type MyCustomClass.
// The following call to ReadXml fails because MyCustomClass isn't in the allowed types list.

DataTable table = new DataTable("MyDataTable");
table.ReadXml(xmlReader);

// However, the following call to ReadXml succeeds, since the DataTable instance
// already defines a column of type MyCustomClass.

DataTable table = new DataTable("MyDataTable");
table.Columns.Add("MyColumn", typeof(MyCustomClass));
table.ReadXml(xmlReader); // this call will succeed
```

<span data-ttu-id="559e9-124">オブジェクトの型の制限は、`XmlSerializer` を使用して `DataSet` または `DataTable` のインスタンスを逆シリアル化するときにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="559e9-124">The object type restrictions also apply when using `XmlSerializer` to deserialize an instance of `DataSet` or `DataTable`.</span></span> <span data-ttu-id="559e9-125">ただし、`BinaryFormatter` を使用して `DataSet` または `DataTable` のインスタンスを逆シリアル化するときは、適用されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-125">However, they may not apply when using `BinaryFormatter` to deserialize an instance of `DataSet` or `DataTable`.</span></span>

<span data-ttu-id="559e9-126">XML の逆シリアル化 API を使用せずにデータベースから直接 `DataTable` のインスタンスにデータを設定する場合など、`DataAdapter.Fill` を使用するときは、オブジェクトの型の制限は適用されません。</span><span class="sxs-lookup"><span data-stu-id="559e9-126">The object type restrictions don't apply when using `DataAdapter.Fill`, such as when a `DataTable` instance is populated directly from a database without using the XML deserialization APIs.</span></span>

### <a name="extend-the-list-of-allowed-types"></a><span data-ttu-id="559e9-127">許可される型のリストを拡張する</span><span class="sxs-lookup"><span data-stu-id="559e9-127">Extend the list of allowed types</span></span>

<span data-ttu-id="559e9-128">アプリでは、許可される型のリストを拡張して、上記の組み込み型に加えてカスタム型を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="559e9-128">An app can extend the allowed types list to include custom types in addition to the built-in types listed above.</span></span> <span data-ttu-id="559e9-129">許可される型のリストを拡張する場合、その変更は、アプリ内の "_すべての_" `DataSet` および `DataTable` のインスタンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="559e9-129">If extending the allowed types list, the change affects _all_ `DataSet` and `DataTable` instances within the app.</span></span> <span data-ttu-id="559e9-130">組み込みの許可される型のリストから、型を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="559e9-130">Types cannot be removed from the built-in allowed types list.</span></span>

#### <a name="extend-through-configuration-net-framework-40---48"></a><span data-ttu-id="559e9-131">構成によって拡張する (.NET Framework 4.0 - 4.8)</span><span class="sxs-lookup"><span data-stu-id="559e9-131">Extend through configuration (.NET Framework 4.0 - 4.8)</span></span>

<span data-ttu-id="559e9-132">_App.config_ を使用して、許可される型のリストを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="559e9-132">_App.config_ can be used to extend the allowed types list.</span></span> <span data-ttu-id="559e9-133">許可される型のリストを拡張するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="559e9-133">To extend the allowed types list:</span></span>

* <span data-ttu-id="559e9-134">`<configSections>` 要素を使用して、_System.Data_ 構成セクションへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="559e9-134">Use the `<configSections>` element to add a reference to the _System.Data_ configuration section.</span></span>
* <span data-ttu-id="559e9-135">`<system.data.dataset.serialization>`/`<allowedTypes>` を使用して、追加の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="559e9-135">Use `<system.data.dataset.serialization>`/`<allowedTypes>` to specify additional types.</span></span>

<span data-ttu-id="559e9-136">各 `<add>` 要素では、アセンブリ修飾型名を使用して、型を 1 つだけ指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-136">Each `<add>` element must specify only one type by using its assembly qualified type name.</span></span> <span data-ttu-id="559e9-137">許可される型のリストに型を追加するには、複数の `<add>` 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="559e9-137">To add additional types to the allowed types list, use multiple `<add>` elements.</span></span>

<span data-ttu-id="559e9-138">次の例では、カスタム型 `Fabrikam.CustomType` を追加することによって、許可される型のリストを拡張する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="559e9-138">The following sample shows extending the allowed types list by adding the custom type `Fabrikam.CustomType`.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add type="assembly qualified type name" /> -->
      <add type="Fabrikam.CustomType, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
      <!-- additional <add /> elements as needed -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

<span data-ttu-id="559e9-139">型のアセンブリ修飾名を取得するには、次のコードで示すように、[Type.AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="559e9-139">To retrieve the assembly qualified name of a type, use the [Type.AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) property, as demonstrated in the following code.</span></span>

```cs
string assemblyQualifiedName = typeof(Fabrikam.CustomType).AssemblyQualifiedName;
```

<a name="etc"></a>

#### <a name="extend-through-configuration-net-framework-20---35"></a><span data-ttu-id="559e9-140">構成によって拡張する (.NET Framework 2.0 - 3.5)</span><span class="sxs-lookup"><span data-stu-id="559e9-140">Extend through configuration (.NET Framework 2.0 - 3.5)</span></span>

<span data-ttu-id="559e9-141">アプリの対象が .NET Framework 2.0 または 3.5 の場合でも、上記の _App.config_ のメカニズムを使用して、許可される型のリストを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="559e9-141">If your app targets .NET Framework 2.0 or 3.5, you can still use the above _App.config_ mechanism to extend the allowed types list.</span></span> <span data-ttu-id="559e9-142">ただし、次のコードで示すように、`<configSections>` 要素は少し異なります。</span><span class="sxs-lookup"><span data-stu-id="559e9-142">However, your `<configSections>` element will look slightly different, as shown in the following code:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- The below <sectionGroup> and <section> are specific to .NET Framework 2.0 and 3.5. -->
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add /> elements, as demonstrated in the .NET Framework 4.0 - 4.8 sample code above. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

#### <a name="extend-programmatically-net-framework-net-core-net-50"></a><span data-ttu-id="559e9-143">プログラムによって拡張する (.NET Framework、.NET Core、.NET 5.0 以降)</span><span class="sxs-lookup"><span data-stu-id="559e9-143">Extend programmatically (.NET Framework, .NET Core, .NET 5.0+)</span></span>

<span data-ttu-id="559e9-144">許可される型のリストは、次のコードで示すように、[AppDomain.SetData](/dotnet/api/system.appdomain.setdata) と既知のキー _System.Data.DataSetDefaultAllowedTypes_ を使用することにより、プログラムで拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="559e9-144">The list of allowed types can also be extended programmatically by using [AppDomain.SetData](/dotnet/api/system.appdomain.setdata) with the well-known key _System.Data.DataSetDefaultAllowedTypes_, as shown in the following code.</span></span>

```cs
Type[] extraAllowedTypes = new Type[]
{
    typeof(Fabrikam.CustomType),
    typeof(Contoso.AdditionalCustomType)
};

AppDomain.CurrentDomain.SetData("System.Data.DataSetDefaultAllowedTypes", extraAllowedTypes);
```

<span data-ttu-id="559e9-145">拡張メカニズムを使用している場合、キー _System.Data.DataSetDefaultAllowedTypes_ に関連付ける値は、`Type[]` 型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-145">If using the extension mechanism, the value associated with the key _System.Data.DataSetDefaultAllowedTypes_ must be of type `Type[]`.</span></span>

<span data-ttu-id="559e9-146">.NET Framework では、_App.config_ と `AppDomain.SetData` の両方で、許可される型のリストを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="559e9-146">On .NET Framework, the list of allowed types may be extended both with _App.config_ and `AppDomain.SetData`.</span></span> <span data-ttu-id="559e9-147">この場合、`DataSet` と `DataTable` では、その型がいずれかのリストに存在する場合、データの一部としてオブジェクトを逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="559e9-147">In this case, `DataSet` and `DataTable` will allow an object to be deserialized as part of the data if its type is present in either list.</span></span>

### <a name="run-an-app-in-audit-mode-net-framework"></a><span data-ttu-id="559e9-148">監査モードでアプリを実行する (.NET Framework)</span><span class="sxs-lookup"><span data-stu-id="559e9-148">Run an app in audit mode (.NET Framework)</span></span>

<span data-ttu-id="559e9-149">.NET Framework では、`DataSet` と `DataTable` において監査モード機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="559e9-149">In .NET Framework, `DataSet` and `DataTable` provide an audit mode capability.</span></span> <span data-ttu-id="559e9-150">監査モードが有効になっていると、`DataSet` と `DataTable` では、受信したオブジェクトの型が、許可される型のリストと比較されます。</span><span class="sxs-lookup"><span data-stu-id="559e9-150">When audit mode is enabled, `DataSet` and `DataTable` compare the types of incoming objects against the allowed types list.</span></span> <span data-ttu-id="559e9-151">ただし、許可されていない型のオブジェクトが見つかった場合でも、例外はスローされ**ません**。</span><span class="sxs-lookup"><span data-stu-id="559e9-151">However, if an object whose type is not allowed is seen, an exception is **not** thrown.</span></span> <span data-ttu-id="559e9-152">代わりに、`DataSet` と `DataTable` では、アタッチされている `TraceListener` のインスタンスに、疑わしい型が存在することが通知されます。これにより、`TraceListener` ではこの情報をログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="559e9-152">Instead, `DataSet` and `DataTable` notify any attached `TraceListener` instances that a suspicious type is present, allowing the `TraceListener` to log this information.</span></span> <span data-ttu-id="559e9-153">例外はスローされず、逆シリアル化操作は続行されます。</span><span class="sxs-lookup"><span data-stu-id="559e9-153">No exception is thrown and the deserialization operation continues.</span></span>

> [!WARNING]
> <span data-ttu-id="559e9-154">"監査モード" でのアプリの実行は、テストに使用する一時的な手段のみにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-154">Running an app in "audit mode" should only be a temporary measure used for testing.</span></span> <span data-ttu-id="559e9-155">監査モードが有効になっていると、`DataSet` と `DataTable` では型の制限が適用されず、これによりアプリ内にセキュリティ ホールが生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-155">When audit mode is enabled, `DataSet` and `DataTable` do not enforce type restrictions, which can introduce a security hole inside your app.</span></span> <span data-ttu-id="559e9-156">詳細については、「[すべての型の制限を削除する](#ratr)」および「[信頼されていない入力に関する安全性](#swr)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="559e9-156">For more information, see the sections titled [Removing all type restrictions](#ratr) and [Safety with regard to untrusted input](#swr).</span></span>

<span data-ttu-id="559e9-157">監査モードは、_App.config_ を使用して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="559e9-157">Audit mode can be enabled through _App.config_:</span></span>

* <span data-ttu-id="559e9-158">`<configSections>` 要素に設定する適切な値については、このドキュメントの[構成による拡張](#etc)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="559e9-158">See the [Extending through configuration](#etc) section in this document for information on the proper value to put for the `<configSections>` element.</span></span>
* <span data-ttu-id="559e9-159">次のマークアップで示すように、監査モードを有効にするには `<allowedTypes auditOnly="true">` を使用します。</span><span class="sxs-lookup"><span data-stu-id="559e9-159">Use `<allowedTypes auditOnly="true">` to enable audit mode, as shown in the following markup.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- See the section of this document titled "Extending through configuration" for the appropriate
         <sectionGroup> and <section> elements to put here, depending on whether you're running .NET
         Framework 2.0 - 3.5 or 4.0 - 4.8. -->
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes auditOnly="true"> <!-- setting auditOnly="true" enables audit mode -->
      <!-- Optional <add /> elements as needed. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

<span data-ttu-id="559e9-160">監査モードを有効にした後は、_App.config_ を使用して、適切な `TraceListener` を `DataSet` の組み込みの `TraceSource.` に接続できます。組み込みのトレース ソースの名前は _System.Data.DataSet_ です。</span><span class="sxs-lookup"><span data-stu-id="559e9-160">Once audit mode is enabled, you can use _App.config_ to connect your preferred `TraceListener` to the `DataSet` built-in `TraceSource.` The name of the built-in trace source is _System.Data.DataSet_.</span></span> <span data-ttu-id="559e9-161">次の例では、トレース イベントをコンソール_と_ディスク上のログ ファイルに書き込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="559e9-161">The following sample demonstrates writing trace events to the console _and_ to a log file on disk.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.diagnostics>
    <sources>
      <source name="System.Data.DataSet"
              switchType="System.Diagnostics.SourceSwitch"
              switchValue="Warning">
        <listeners>
          <!-- write to the console -->
          <add name="console"
               type="System.Diagnostics.ConsoleTraceListener" />
          <!-- *and* write to a log file on disk -->
          <add name="filelog"
               type="System.Diagnostics.TextWriterTraceListener"
               initializeData="c:\logs\mylog.txt" />
        </listeners>
      </source>
    </sources>
  </system.diagnostics>
</configuration>
```

<span data-ttu-id="559e9-162">`TraceSource` と `TraceListener` の詳細については、「[方法: TraceSource とフィルターをトレース リスナーと共に使用する](../../../debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559e9-162">For more information on `TraceSource` and `TraceListener`, see the document [How to: Use TraceSource and Filters with Trace Listeners](../../../debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md).</span></span>

> [!NOTE]
> <span data-ttu-id="559e9-163">監査モードでのアプリの実行は、.NET Core または .NET 5.0 以降では使用できません。</span><span class="sxs-lookup"><span data-stu-id="559e9-163">Running an app in audit mode is not available in .NET Core or in .NET 5.0 and later.</span></span>

<a name="ratr"></a>

### <a name="remove-all-type-restrictions"></a><span data-ttu-id="559e9-164">すべての型の制限を削除する</span><span class="sxs-lookup"><span data-stu-id="559e9-164">Remove all type restrictions</span></span>

<span data-ttu-id="559e9-165">アプリで `DataSet` と `DataTable` からすべての型の制限を削除する必要がある場合:</span><span class="sxs-lookup"><span data-stu-id="559e9-165">If an app must remove all type limiting restrictions from `DataSet` and `DataTable`:</span></span>

* <span data-ttu-id="559e9-166">型の制限を抑制するには、いくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="559e9-166">There are several options to suppress type limiting restrictions.</span></span>
* <span data-ttu-id="559e9-167">使用できるオプションは、アプリの対象となるフレームワークによって異なります。</span><span class="sxs-lookup"><span data-stu-id="559e9-167">The options available depend on the framework the app targets.</span></span>

> [!WARNING]
> <span data-ttu-id="559e9-168">型の制限をすべて削除すると、アプリ内にセキュリティ ホールが生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-168">Removing all type restrictions can introduce a security hole inside the app.</span></span> <span data-ttu-id="559e9-169">このメカニズムを使用するときは、アプリで信頼されていない入力を読み取るために `DataSet` または `DataTable` を使用して**いない**ことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="559e9-169">When using this mechanism, ensure the app does **not** use `DataSet` or `DataTable` to read untrusted input.</span></span> <span data-ttu-id="559e9-170">詳細については、[CVE-2020-1147](https://portal.msrc.microsoft.com/en-us/security-guidance/advisory/CVE-2020-1147) および後のセクション「[信頼されていない入力に関する安全性](#swr)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559e9-170">For more information, see [CVE-2020-1147](https://portal.msrc.microsoft.com/en-us/security-guidance/advisory/CVE-2020-1147) and the following section titled [Safety with regard to untrusted input](#swr).</span></span>

#### <a name="through-appcontext-configuration-net-framework-46---48-net-core-21-and-later-net-50-and-later"></a><span data-ttu-id="559e9-171">AppContext の構成を使用 (.NET Framework 4.6 - 4.8、.NET Core 2.1 以降、.NET 5.0 以降)</span><span class="sxs-lookup"><span data-stu-id="559e9-171">Through AppContext configuration (.NET Framework 4.6 - 4.8, .NET Core 2.1 and later, .NET 5.0 and later)</span></span>

<span data-ttu-id="559e9-172">`AppContext` スイッチの `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` を `true` に設定すると、`DataSet` および `DataTable` からすべての型制限が削除されます。</span><span class="sxs-lookup"><span data-stu-id="559e9-172">The `AppContext` switch, `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation`, when set to `true` removes all type limiting restrictions from `DataSet` and `DataTable`.</span></span>

<span data-ttu-id="559e9-173">.NET Framework では、次の構成で示すように、_App.config_ を使用してこのスイッチを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="559e9-173">In .NET Framework, this switch can be enabled via _App.config_, as shown in the following configuration:</span></span>

```xml
<configuration>
   <runtime>
      <!-- Warning: setting the following switch can introduce a security problem. -->
      <AppContextSwitchOverrides value="Switch.System.Data.AllowArbitraryDataSetTypeInstantiation=true" />
   </runtime>
</configuration>
```

<span data-ttu-id="559e9-174">ASP.NET では、`<AppContextSwitchOverrides>` 要素は使用できません。</span><span class="sxs-lookup"><span data-stu-id="559e9-174">In ASP.NET, the `<AppContextSwitchOverrides>` element is not available.</span></span> <span data-ttu-id="559e9-175">代わりに、次の構成で示すように、_Web.config_ を使用してスイッチを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="559e9-175">Instead, the switch can be enabled via _Web.config_, as shown in the following configuration:</span></span>

```xml
<configuration>
    <appSettings>
        <!-- Warning: setting the following switch can introduce a security problem. -->
        <add key="AppContext.SetSwitch:Switch.System.Data.AllowArbitraryDataSetTypeInstantiation" value="true" />
    </appSettings>
</configuration>
```

<span data-ttu-id="559e9-176">詳細については、[\<AppContextSwitchOverrides>](../../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 要素を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559e9-176">For more information, see the [\<AppContextSwitchOverrides>](../../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element.</span></span>

<span data-ttu-id="559e9-177">.NET Core、.NET 5、および ASP.NET Core では、次の JSON で示すように、この設定は _runtimeconfig.json_ によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="559e9-177">In .NET Core, .NET 5, and ASP.NET Core, this setting is controlled by _runtimeconfig.json_, as shown in the following JSON:</span></span>

```json
{
  "runtimeOptions": {
    "configProperties": {
      "Switch.System.Data.AllowArbitraryDataSetTypeInstantiation": true
    }
  }
}
```

<span data-ttu-id="559e9-178">詳細については、「[.NET Core ランタイム構成設定](/dotnet/core/run-time-config/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559e9-178">For more information, see [".NET Core run-time configuration settings"](/dotnet/core/run-time-config/).</span></span>

<span data-ttu-id="559e9-179">`AllowArbitraryDataSetTypeInstantiation` は、構成ファイルを使用する代わりに、次のコードで示すように、[AppContext.SetSwitch](/dotnet/api/system.appcontext.setswitch) を使用してプログラムで設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="559e9-179">`AllowArbitraryDataSetTypeInstantiation` can also be set programmatically via [AppContext.SetSwitch](/dotnet/api/system.appcontext.setswitch) instead of using a configuration file, as shown in the following code:</span></span>

```cs
// Warning: setting the following switch can introduce a security problem.
AppContext.SetSwitch("Switch.System.Data.AllowArbitraryDataSetTypeInstantiation", true);
```

 <span data-ttu-id="559e9-180">前述のプログラムによる方法を選択する場合は、アプリの起動の初期段階で `AppContext.SetSwitch` の呼び出しを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-180">If you choose the preceding programmatic approach, the call to `AppContext.SetSwitch` should occur early in the apps startup.</span></span>

#### <a name="through-the-machine-wide-registry-net-framework-20---48"></a><span data-ttu-id="559e9-181">コンピューター全体のレジストリを使用 (.NET Framework 2.0 - 4.8)</span><span class="sxs-lookup"><span data-stu-id="559e9-181">Through the machine-wide registry (.NET Framework 2.0 - 4.8)</span></span>

<span data-ttu-id="559e9-182">`AppContext` を使用できない場合は、Windows レジストリを使用して、型制限のチェックを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="559e9-182">If `AppContext` is not available, type limiting checks can be disabled with the Windows registry:</span></span>

* <span data-ttu-id="559e9-183">管理者は、レジストリを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-183">An administrator must configure the registry.</span></span>
* <span data-ttu-id="559e9-184">レジストリの使用は、コンピューター全体の変更であり、コンピューター上で実行されている "_すべての_" アプリに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="559e9-184">Using the registry is a machine-wide change and will affect _all_ apps running on the machine.</span></span>

| <span data-ttu-id="559e9-185">種類</span><span class="sxs-lookup"><span data-stu-id="559e9-185">Type</span></span>  |  <span data-ttu-id="559e9-186">[値]</span><span class="sxs-lookup"><span data-stu-id="559e9-186">Value</span></span> |
|---|---|
| <span data-ttu-id="559e9-187">**レジストリ キー**</span><span class="sxs-lookup"><span data-stu-id="559e9-187">**Registry key**</span></span> | `HKLM\SOFTWARE\Microsoft\.NETFramework\AppContext` |
| <span data-ttu-id="559e9-188">**値の名前**</span><span class="sxs-lookup"><span data-stu-id="559e9-188">**Value name**</span></span> | `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` |
| <span data-ttu-id="559e9-189">**値の型**</span><span class="sxs-lookup"><span data-stu-id="559e9-189">**Value type**</span></span> | `REG_SZ` |
| <span data-ttu-id="559e9-190">**値のデータ**</span><span class="sxs-lookup"><span data-stu-id="559e9-190">**Value data**</span></span> | `true` |

<span data-ttu-id="559e9-191">64 ビットのオペレーティング システムでは、64 ビット キー (上記) と 32 ビット キーの両方に、この値を追加することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-191">On a 64-bit operating system, this value my need to be added for both the 64-bit key (shown above) and the 32-bit key.</span></span> <span data-ttu-id="559e9-192">32 ビット キーは `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext` にあります。</span><span class="sxs-lookup"><span data-stu-id="559e9-192">The 32-bit key is located at `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext`.</span></span>

<span data-ttu-id="559e9-193">レジストリを使用して `AppContext` を構成する方法の詳細については、「[ライブラリ コンシューマーの AppContext](/dotnet/api/system.appcontext#appcontext-for-library-consumers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559e9-193">For more information on using the registry to configure `AppContext`, see ["AppContext for library consumers"](/dotnet/api/system.appcontext#appcontext-for-library-consumers).</span></span>

<a name="swr"></a>

## <a name="safety-with-regard-to-untrusted-input"></a><span data-ttu-id="559e9-194">信頼されていない入力に関する安全性</span><span class="sxs-lookup"><span data-stu-id="559e9-194">Safety with regard to untrusted input</span></span>

<span data-ttu-id="559e9-195">`DataSet` と `DataTable` では、XML ペイロードの逆シリアル化中に存在することが許可される型に対して既定の制限が適用されますが、 __`DataSet` と `DataTable` は、信頼されていない入力で設定されるときは一般に安全ではありません__。</span><span class="sxs-lookup"><span data-stu-id="559e9-195">While `DataSet` and `DataTable` do impose default limitations on the types that are allowed to be present while deserializing XML payloads, __`DataSet` and `DataTable` are in general not safe when populated with untrusted input.__</span></span> <span data-ttu-id="559e9-196">次に示すのは、`DataSet` または `DataTable` のインスタンスが信頼されていない入力を読み取る可能性がある方法の一覧ですが、これだけではありません。</span><span class="sxs-lookup"><span data-stu-id="559e9-196">The following is a non-exhaustive list of ways that a `DataSet` or `DataTable` instance might read untrusted input.</span></span>

* <span data-ttu-id="559e9-197">`DataAdapter` でデータベースを参照し、`DataAdapter.Fill` メソッドを使用してデータベース クエリの内容を `DataSet` に設定します。</span><span class="sxs-lookup"><span data-stu-id="559e9-197">A `DataAdapter` references a database, and the `DataAdapter.Fill` method is used to populate a `DataSet` with the contents of a database query.</span></span>
* <span data-ttu-id="559e9-198">`DataSet.ReadXml` または `DataTable.ReadXml` メソッドを使用して、列と行の情報が含まれる XML ファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="559e9-198">The `DataSet.ReadXml` or `DataTable.ReadXml` method is used to read an XML file containing column and row information.</span></span>
* <span data-ttu-id="559e9-199">ASP.NET (SOAP) Web サービスまたは WCF エンドポイントの一部として、`DataSet` または `DataTable` のインスタンスをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="559e9-199">A `DataSet` or `DataTable` instance is serialized as part of a ASP.NET (SOAP) web services or WCF endpoint.</span></span>
* <span data-ttu-id="559e9-200">`XmlSerializer` などのシリアライザーを使用して、XML ストリームから `DataSet` または `DataTable` のインスタンスを逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="559e9-200">A serializer such as `XmlSerializer` is used to deserialize a `DataSet` or `DataTable` instance from an XML stream.</span></span>
* <span data-ttu-id="559e9-201">`JsonConvert` などのシリアライザーを使用して、JSON ストリームから `DataSet` または `DataTable` のインスタンスを逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="559e9-201">A serializer such as `JsonConvert` is used to deserialize a `DataSet` or `DataTable` instance from a JSON stream.</span></span> <span data-ttu-id="559e9-202">`JsonConvert` は、一般的なサードパーティの [Newtonsoft.Json](https://www.newtonsoft.com/json) ライブラリのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="559e9-202">`JsonConvert` is a method in the popular third-party [Newtonsoft.Json](https://www.newtonsoft.com/json) library.</span></span>
* <span data-ttu-id="559e9-203">`BinaryFormatter` などのシリアライザーを使用して、RAW 型バイト ストリームから `DataSet` または `DataTable` のインスタンスを逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="559e9-203">A serializer such as `BinaryFormatter` is used to deserialize a `DataSet` or `DataTable` instance from a raw byte stream.</span></span>

<span data-ttu-id="559e9-204">このドキュメントでは、前述のシナリオの安全性に関する考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="559e9-204">This document discusses safety considerations for the preceding scenarios.</span></span>

## <a name="use-dataadapterfill-to-populate-a-dataset-from-an-untrusted-data-source"></a><span data-ttu-id="559e9-205">`DataAdapter.Fill` を使用して、信頼されていないデータ ソースから `DataSet` を設定する</span><span class="sxs-lookup"><span data-stu-id="559e9-205">Use `DataAdapter.Fill` to populate a `DataSet` from an untrusted data source</span></span>

<span data-ttu-id="559e9-206">次の例で示すように、[`DataAdapter.Fill` メソッド](/dotnet/api/system.data.common.dataadapter.fill)を使用して `DataAdapter` から `DataSet` インスタンスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="559e9-206">A `DataSet` instance can be populated from a `DataAdapter` by using [the `DataAdapter.Fill` method](/dotnet/api/system.data.common.dataadapter.fill), as shown in the following example.</span></span>

```cs
// Assumes that connection is a valid SqlConnection object.  
string queryString =
  "SELECT CustomerID, CompanyName FROM dbo.Customers";  
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");
```

<span data-ttu-id="559e9-207">(上のコード例は、「[DataAdapter からの DataSet の読み込み](../populating-a-dataset-from-a-dataadapter.md)」にある、より大きな例の一部です。)</span><span class="sxs-lookup"><span data-stu-id="559e9-207">(The code sample above is part of a larger sample found at [Populating a DataSet from a DataAdapter](../populating-a-dataset-from-a-dataadapter.md).)</span></span>

> <span data-ttu-id="559e9-208">ほとんどのアプリでは単純化し、データベース レイヤーが信頼されていると想定できます。</span><span class="sxs-lookup"><span data-stu-id="559e9-208">Most apps can simplify and assume that their database layer is trusted.</span></span> <span data-ttu-id="559e9-209">ただし、アプリの[脅威モデリング](https://www.microsoft.com/securityengineering/sdl/threatmodeling)を行う習慣がある場合は、脅威モデルで、アプリケーション (クライアント) とデータベース層 (サーバー) の間に信頼境界があると考えられる場合があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-209">However, if you are in the habit of [threat modeling](https://www.microsoft.com/securityengineering/sdl/threatmodeling) your apps, your threat model may consider there to be a trust boundary between the application (client) and database layer (server).</span></span> <span data-ttu-id="559e9-210">クライアントとサーバーの間で[相互認証](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections)または [AAD 認証](/azure/azure-sql/database/authentication-aad-overview)を使用することは、これに関連するリスクに対処するための 1 つの方法です。</span><span class="sxs-lookup"><span data-stu-id="559e9-210">Using [mutual authentication](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) or [AAD authentication](/azure/azure-sql/database/authentication-aad-overview) between client and server is one way to help address the risks associated with this.</span></span> <span data-ttu-id="559e9-211">このセクションの残りの部分では、信頼されていないサーバーに接続するクライアントで可能性のある結果について説明します。</span><span class="sxs-lookup"><span data-stu-id="559e9-211">The remainder of this section discusses the possible result of a client connecting to an untrusted server.</span></span>

<span data-ttu-id="559e9-212">信頼されていないデータ ソースで `DataAdapter` を参照した場合の結果は、`DataAdapter` 自体の実装によって異なります。</span><span class="sxs-lookup"><span data-stu-id="559e9-212">The consequences of pointing a `DataAdapter` at an untrusted data source depend on the implementation of the `DataAdapter` itself.</span></span>

### <a name="sqldataadapter"></a><span data-ttu-id="559e9-213">SqlDataAdapter</span><span class="sxs-lookup"><span data-stu-id="559e9-213">SqlDataAdapter</span></span>

<span data-ttu-id="559e9-214">組み込み型 [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter) の場合、信頼されていないデータ ソースを参照すると、サービス拒否 (DoS) 攻撃が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-214">For the built-in type [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter), referencing an untrusted data source could result in a denial of service (DoS) attack.</span></span> <span data-ttu-id="559e9-215">DoS 攻撃により、アプリが応答しなくなったりクラッシュしたりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-215">The DoS attack could result in the app becoming unresponsive or crashing.</span></span> <span data-ttu-id="559e9-216">攻撃者がアプリと一緒に DLL を仕掛けることができる場合は、ローカル コード実行も実現できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-216">If an attacker can plant a DLL alongside the app, they may also be able to achieve local code execution.</span></span>

### <a name="other-dataadapter-types"></a><span data-ttu-id="559e9-217">その他の DataAdapter 型</span><span class="sxs-lookup"><span data-stu-id="559e9-217">Other DataAdapter types</span></span>

<span data-ttu-id="559e9-218">サードパーティによる `DataAdapter` の実装では、信頼されていない入力に対して提供するセキュリティ保証について、独自の評価を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-218">Third-party `DataAdapter` implementations must make their own assessments about what security guarantees they provide in the face of untrusted inputs.</span></span> <span data-ttu-id="559e9-219">.NET では、これらの実装に関する安全性についてどのような保証も行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="559e9-219">.NET cannot make any safety guarantees regarding these implementations.</span></span>

<a name="dsrdtr"></a>

## <a name="datasetreadxml-and-datatablereadxml"></a><span data-ttu-id="559e9-220">DataSet.ReadXml と DataTable.ReadXml</span><span class="sxs-lookup"><span data-stu-id="559e9-220">DataSet.ReadXml and DataTable.ReadXml</span></span>

<span data-ttu-id="559e9-221">`DataSet.ReadXml` メソッドと `DataTable.ReadXml` メソッドは、信頼されていない入力で使用するときは安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="559e9-221">The `DataSet.ReadXml` and `DataTable.ReadXml` methods are not safe when used with untrusted input.</span></span> <span data-ttu-id="559e9-222">代わりにこのドキュメントで後述する代替手段のいずれかの使用を検討することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="559e9-222">We strongly recommend that consumers instead consider using one of the alternatives outlined later in this document.</span></span>

<span data-ttu-id="559e9-223">`DataSet.ReadXml` と `DataTable.ReadXml` の実装は、もともと、シリアル化の脆弱性がよく理解された脅威カテゴリになる前に作成されました。</span><span class="sxs-lookup"><span data-stu-id="559e9-223">The implementations of `DataSet.ReadXml` and `DataTable.ReadXml` were originally created before serialization vulnerabilities were a well-understood threat category.</span></span> <span data-ttu-id="559e9-224">このため、そのコードは現在のセキュリティのベスト プラクティスに従っていません。</span><span class="sxs-lookup"><span data-stu-id="559e9-224">As a result, the code does not follow current security best practices.</span></span> <span data-ttu-id="559e9-225">これらの API は、攻撃者が Web アプリに対して DoS 攻撃を実行するためのベクトルとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="559e9-225">These APIs can be used as vectors for attackers to perform DoS attacks against web apps.</span></span> <span data-ttu-id="559e9-226">これらの攻撃によって、Web サービスが応答しなくなったり、予期しないプロセスの終了が発生したりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-226">These attacks might render the web service unresponsive or result in unexpected process termination.</span></span> <span data-ttu-id="559e9-227">フレームワークでは、これらの攻撃カテゴリに対する軽減策が提供されず、.NET ではこの動作は "仕様" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="559e9-227">The framework does not provide mitigations for these attack categories and .NET considers this behavior "by design".</span></span>

<span data-ttu-id="559e9-228">.NET では、`DataSet.ReadXml` および `DataTable.ReadXml` での情報漏えいやリモート コード実行などの一部の問題を軽減するために、セキュリティ更新プログラムがリリースされています。</span><span class="sxs-lookup"><span data-stu-id="559e9-228">.NET has released security updates to mitigate some issues such as information disclosure or remote code execution in `DataSet.ReadXml` and `DataTable.ReadXml`.</span></span> <span data-ttu-id="559e9-229">.NET のセキュリティ更新プログラムでは、これらの脅威カテゴリに対する完全な保護が提供されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-229">The .NET security updates may not provide complete protection against these threat categories.</span></span> <span data-ttu-id="559e9-230">コンシューマーは、個々のシナリオを評価し、これらのリスクに対する潜在的な危険を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-230">Consumers should assess their individual scenarios and consider their potential exposure to these risks.</span></span>

<span data-ttu-id="559e9-231">コンシューマーは、これらの API に対するセキュリティ更新プログラムが、アプリケーションの互換性に影響する場合があることに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-231">Consumers should be aware that security updates to these APIs may impact application compatibility in some situations.</span></span> <span data-ttu-id="559e9-232">さらに、これらの API には .NET でセキュリティ更新プログラムを実質的に公開できない新しい脆弱性が検出される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-232">Furthermore, the possibility exists that a novel vulnerability in these APIs will be discovered for which .NET can't practically publish a security update.</span></span>

<span data-ttu-id="559e9-233">これらの API のコンシューマーには、次のいずれかをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="559e9-233">We recommend that consumers of these APIs either:</span></span>

* <span data-ttu-id="559e9-234">後で説明するいずれかの代替手段を使用することを検討します。</span><span class="sxs-lookup"><span data-stu-id="559e9-234">Consider using one of the alternatives outlined later in this document.</span></span>
* <span data-ttu-id="559e9-235">アプリで個々のリスク評価を実行します。</span><span class="sxs-lookup"><span data-stu-id="559e9-235">Perform individual risk assessments on their apps.</span></span>

<span data-ttu-id="559e9-236">これらの API を利用するかどうかの判断に関する責任は、すべてコンシューマーにあります。</span><span class="sxs-lookup"><span data-stu-id="559e9-236">It is the consumer's sole responsibility to determine whether to utilize these APIs.</span></span> <span data-ttu-id="559e9-237">コンシューマーは、これらの API の使用に伴う可能性のある、規制要件を含む、セキュリティ、技術的、および法的リスクを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-237">Consumers should assess any security, technical, and legal risks, including regulatory requirements, that may accompany using these APIs.</span></span>

## <a name="dataset-and-datatable-via-aspnet-web-services-or-wcf"></a><span data-ttu-id="559e9-238">ASP.NET Web サービスまたは WCF による DataSet と DataTable</span><span class="sxs-lookup"><span data-stu-id="559e9-238">DataSet and DataTable via ASP.NET web services or WCF</span></span>

<span data-ttu-id="559e9-239">次のコードで示すように、ASP.NET (SOAP) Web サービスで `DataSet` または `DataTable` のインスタンスを受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="559e9-239">It is possible to accept a `DataSet` or a `DataTable` instance in an ASP.NET (SOAP) web service, as demonstrated in the following code:</span></span>

```cs
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(DataTable dataTable)
    {
        /* Web method implementation. */
    }
}
```

<span data-ttu-id="559e9-240">これのバリエーションとしては、`DataSet` または `DataTable` をパラメーターとして直接受け入れるのではなく、次のコードで示すように、SOAP でシリアル化されたオブジェクト グラフ全体の一部として受け入れます。</span><span class="sxs-lookup"><span data-stu-id="559e9-240">A variation on this is not to accept `DataSet` or `DataTable` directly as a parameter, but instead to accept it as part of the overall SOAP serialized object graph, as shown in the following code:</span></span>

```cs
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(MyClass data)
    {
        /* Web method implementation. */
    }
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="559e9-241">または、ASP.NET Web サービスの代わりに WCF を使用します。</span><span class="sxs-lookup"><span data-stu-id="559e9-241">Or, using WCF instead of ASP.NET web services:</span></span>

```cs
using System.Data;
using System.ServiceModel;

[ServiceContract(Namespace = "http://contoso.com/")]
public interface IMyContract
{
    [OperationContract]
    string MyMethod(DataTable dataTable);
    [OperationContract]
    string MyOtherMethod(MyClass data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="559e9-242">これらのどのケースでも、脅威モデルとセキュリティの保証は「[DataSet.ReadXml と DataTable.ReadXml section](#dsrdtr)」セクションと同じです。</span><span class="sxs-lookup"><span data-stu-id="559e9-242">In all of these cases, the threat model and security guarantees are the same as the [DataSet.ReadXml and DataTable.ReadXml section](#dsrdtr).</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-xmlserializer"></a><span data-ttu-id="559e9-243">XmlSerializer を使用して DataSet または DataTable を逆シリアル化する</span><span class="sxs-lookup"><span data-stu-id="559e9-243">Deserialize a DataSet or DataTable via XmlSerializer</span></span>

<span data-ttu-id="559e9-244">開発者は、次のコードで示すように、`XmlSerializer` を使用して `DataSet` や `DataTable` のインスタンスを逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="559e9-244">Developers can use `XmlSerializer` to deserialize `DataSet` and `DataTable` instances, as shown in the following code:</span></span>

```cs
using System.Data;
using System.IO;
using System.Xml.Serialization;

public DataSet PerformDeserialization1(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(DataSet));
    return (DataSet)serializer.Deserialize(stream);
}

public MyClass PerformDeserialization2(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(MyClass));
    return (MyClass)serializer.Deserialize(stream);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="559e9-245">これらのケースでも、脅威モデルとセキュリティの保証は「[DataSet.ReadXml と DataTable.ReadXml section](#dsrdtr)」セクションと同じです</span><span class="sxs-lookup"><span data-stu-id="559e9-245">In these cases, the threat model and security guarantees are the same as the [DataSet.ReadXml and DataTable.ReadXml section](#dsrdtr)</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-jsonconvert"></a><span data-ttu-id="559e9-246">JsonConvert を使用して DataSet または DataTable を逆シリアル化する</span><span class="sxs-lookup"><span data-stu-id="559e9-246">Deserialize a DataSet or DataTable via JsonConvert</span></span>

<span data-ttu-id="559e9-247">一般的なサードパーティの Newtonsoft ライブラリ [JSON.NET](https://www.newtonsoft.com/json) を使用すると、次のコードで示すように、`DataSet` および `DataTable` のインスタンスを逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="559e9-247">The popular third-party Newtonsoft library [JSON.NET](https://www.newtonsoft.com/json) can be used to deserialize `DataSet` and `DataTable` instances, as shown in the following code:</span></span>

```cs
using System.Data;
using Newtonsoft.Json;

public DataSet PerformDeserialization1(string json) {
    return JsonConvert.DeserializeObect<DataSet>(data);
}

public MyClass PerformDeserialization2(string json) {
    return JsonConvert.DeserializeObect<MyClass>(data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="559e9-248">この方法で信頼されていない JSON BLOB から `DataSet` または `DataTable` を逆シリアル化することは、安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="559e9-248">Deserializing a `DataSet` or `DataTable` in this manner from an untrusted JSON blob is not safe.</span></span> <span data-ttu-id="559e9-249">このパターンは、サービス拒否攻撃に対して脆弱です。</span><span class="sxs-lookup"><span data-stu-id="559e9-249">This pattern is vulnerable to a denial of service attack.</span></span> <span data-ttu-id="559e9-250">このような攻撃によって、アプリがクラッシュしたり、応答しなくなったりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="559e9-250">Such an attack could crash the app or render it unresponsive.</span></span>

> [!NOTE]
> <span data-ttu-id="559e9-251">Microsoft では、_Newtonsoft.Json_ のようなサードパーティ製ライブラリの実装については、保証もサポートも行いません。</span><span class="sxs-lookup"><span data-stu-id="559e9-251">Microsoft does not warrant or support the implementation of third-party libraries like _Newtonsoft.Json_.</span></span> <span data-ttu-id="559e9-252">この情報は完全を期すために提供されており、このドキュメントの執筆時点の正確な情報です。</span><span class="sxs-lookup"><span data-stu-id="559e9-252">This information is provided for completeness and is accurate as of the time of this writing.</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-binaryformatter"></a><span data-ttu-id="559e9-253">BinaryFormatter を使用して DataSet または DataTable を逆シリアル化する</span><span class="sxs-lookup"><span data-stu-id="559e9-253">Deserialize a DataSet or DataTable via BinaryFormatter</span></span>

<span data-ttu-id="559e9-254">開発者は、`BinaryFormatter`、`NetDataContractSerializer`、`SoapFormatter`、または関連する "***安全でない***" フォーマッタを使用して、信頼されていないペイロードから `DataSet` または `DataTable` のインスタンスを逆シリアル化しないでください。</span><span class="sxs-lookup"><span data-stu-id="559e9-254">Developers must never use `BinaryFormatter`, `NetDataContractSerializer`, `SoapFormatter`, or related ***unsafe*** formatters to deserialize a `DataSet` or `DataTable` instance from an untrusted payload:</span></span>

* <span data-ttu-id="559e9-255">これは、完全なリモート コード実行攻撃の影響を受けやすくなります。</span><span class="sxs-lookup"><span data-stu-id="559e9-255">This is susceptible to a full remote code execution attack.</span></span>
* <span data-ttu-id="559e9-256">このような攻撃を防ぐには、カスタム `SerializationBinder` を使用するだけでは不十分です。</span><span class="sxs-lookup"><span data-stu-id="559e9-256">Using a custom `SerializationBinder` is not sufficient to prevent such an attack.</span></span>

## <a name="safe-replacements"></a><span data-ttu-id="559e9-257">安全な置換</span><span class="sxs-lookup"><span data-stu-id="559e9-257">Safe replacements</span></span>

<span data-ttu-id="559e9-258">次のいずれかのアプリの場合:</span><span class="sxs-lookup"><span data-stu-id="559e9-258">For apps that either:</span></span>

* <span data-ttu-id="559e9-259">.asmx SOAP エンドポイントまたは WCF エンドポイントを通して `DataSet` または `DataTable` を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="559e9-259">Accept `DataSet` or `DataTable` through an .asmx SOAP endpoint or a WCF endpoint.</span></span>
* <span data-ttu-id="559e9-260">信頼されていないデータを `DataSet` または `DataTable` のインスタンスに逆シリアル化する。</span><span class="sxs-lookup"><span data-stu-id="559e9-260">Deserialize untrusted data into an instance of `DataSet` or `DataTable`.</span></span>

<span data-ttu-id="559e9-261">[Entity Framework](/ef) を使用するようにオブジェクト モデルを置き換えることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="559e9-261">Consider replacing the object model to use [Entity Framework](/ef).</span></span> <span data-ttu-id="559e9-262">Entity Framework:</span><span class="sxs-lookup"><span data-stu-id="559e9-262">Entity Framework:</span></span>

* <span data-ttu-id="559e9-263">リレーショナル データを表すことができる、高度な最新のオブジェクト指向フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="559e9-263">Is a rich, modern, object-oriented framework that can represent relational data.</span></span>
* <span data-ttu-id="559e9-264">データベース プロバイダーの[さまざまなエコシステム](/ef/core/providers/)を使用して、Entity Framework オブジェクト モデルによるデータベース クエリを簡単に射影できます。</span><span class="sxs-lookup"><span data-stu-id="559e9-264">Brings [a diverse ecosystem](/ef/core/providers/) of database providers to make it easy to project database queries via your Entity Framework object models.</span></span>
* <span data-ttu-id="559e9-265">信頼されていないソースからデータを逆シリアル化するときに、組み込みの保護が提供されます。</span><span class="sxs-lookup"><span data-stu-id="559e9-265">Offers built-in protections when deserializing data from untrusted sources.</span></span>

<span data-ttu-id="559e9-266">`.aspx` SOAP エンドポイントを使用するアプリの場合、[WCF](/dotnet/framework/wcf/) を使用するようにそれらのエンドポイントを変更することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="559e9-266">For apps that use `.aspx` SOAP endpoints, consider changing those endpoints to use [WCF](/dotnet/framework/wcf/).</span></span> <span data-ttu-id="559e9-267">WCF は、`.asmx` Web サービスに対する、より完全な機能を備えた代替手段です。</span><span class="sxs-lookup"><span data-stu-id="559e9-267">WCF is a more fully featured replacement for `.asmx` web services.</span></span> <span data-ttu-id="559e9-268">既存の呼び出し元との互換性のため、WCF エンドポイントは [SOAP 経由で公開できます](../../../wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="559e9-268">WCF endpoints [can be exposed via SOAP](../../../wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md) for compatibility with existing callers.</span></span>

## <a name="code-analyzers"></a><span data-ttu-id="559e9-269">コード アナライザー</span><span class="sxs-lookup"><span data-stu-id="559e9-269">Code analyzers</span></span>

<span data-ttu-id="559e9-270">自分のソース コードをコンパイルするときに実行されるコード アナライザーのセキュリティ規則は、C# および Visual Basic コードで、このセキュリティの問題に関連する脆弱性を検出するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="559e9-270">Code analyzer security rules, which run when your source code is compiled, can help to find vulnerabilities related to this security issue in C# and Visual Basic code.</span></span> <span data-ttu-id="559e9-271">Microsoft.CodeAnalysis.FxCopAnalyzers は、[nuget.org](https://www.nuget.org/) で配布されるコード アナライザーの NuGet パッケージです。</span><span class="sxs-lookup"><span data-stu-id="559e9-271">Microsoft.CodeAnalysis.FxCopAnalyzers is a NuGet package of code analyzers that's distributed on [nuget.org](https://www.nuget.org/).</span></span>

<span data-ttu-id="559e9-272">コード アナライザーの概要については、「[ソース コード アナライザーの概要](https://docs.microsoft.com/visualstudio/code-quality/roslyn-analyzers-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559e9-272">For an overview of code analyzers, see [Overview of source code analyzers](https://docs.microsoft.com/visualstudio/code-quality/roslyn-analyzers-overview).</span></span>

<span data-ttu-id="559e9-273">次の Microsoft.CodeAnalysis.FxCopAnalyzers 規則を有効にします。</span><span class="sxs-lookup"><span data-stu-id="559e9-273">Enable the following Microsoft.CodeAnalysis.FxCopAnalyzers rules:</span></span>

- <span data-ttu-id="559e9-274">[CA2350](https://docs.microsoft.com/visualstudio/code-quality/ca2350):信頼されていないデータで DataTable.ReadXml() を使用しない</span><span class="sxs-lookup"><span data-stu-id="559e9-274">[CA2350](https://docs.microsoft.com/visualstudio/code-quality/ca2350): Do not use DataTable.ReadXml() with untrusted data</span></span>
- <span data-ttu-id="559e9-275">[CA2351](https://docs.microsoft.com/visualstudio/code-quality/ca2351):信頼されていないデータで DataSet.ReadXml() を使用しない</span><span class="sxs-lookup"><span data-stu-id="559e9-275">[CA2351](https://docs.microsoft.com/visualstudio/code-quality/ca2351): Do not use DataSet.ReadXml() with untrusted data</span></span>
- <span data-ttu-id="559e9-276">[CA2352](https://docs.microsoft.com/visualstudio/code-quality/ca2352):シリアル化可能な型の安全でない DataSet または DataTable は、リモート コード実行攻撃に対して脆弱になる可能性があります</span><span class="sxs-lookup"><span data-stu-id="559e9-276">[CA2352](https://docs.microsoft.com/visualstudio/code-quality/ca2352): Unsafe DataSet or DataTable in serializable type can be vulnerable to remote code execution attacks</span></span>
- <span data-ttu-id="559e9-277">[CA2353](https://docs.microsoft.com/visualstudio/code-quality/ca2353):シリアル化可能な型の安全でない DataSet または DataTable</span><span class="sxs-lookup"><span data-stu-id="559e9-277">[CA2353](https://docs.microsoft.com/visualstudio/code-quality/ca2353): Unsafe DataSet or DataTable in serializable type</span></span>
- <span data-ttu-id="559e9-278">[CA2354](https://docs.microsoft.com/visualstudio/code-quality/ca2354):逆シリアル化されたオブジェクト グラフの安全でない DataSet または DataTable が、リモート コード実行攻撃に対して脆弱になる可能性があります</span><span class="sxs-lookup"><span data-stu-id="559e9-278">[CA2354](https://docs.microsoft.com/visualstudio/code-quality/ca2354): Unsafe DataSet or DataTable in deserialized object graph can be vulnerable to remote code execution attacks</span></span>
- <span data-ttu-id="559e9-279">[CA2355](https://docs.microsoft.com/visualstudio/code-quality/ca2355):逆シリアル化可能なオブジェクト グラフに、安全でない DataSet または DataTable 型が見つかりました</span><span class="sxs-lookup"><span data-stu-id="559e9-279">[CA2355](https://docs.microsoft.com/visualstudio/code-quality/ca2355): Unsafe DataSet or DataTable type found in deserializable object graph</span></span>
- <span data-ttu-id="559e9-280">[CA2356](https://docs.microsoft.com/visualstudio/code-quality/ca2356):Web の逆シリアル化可能なオブジェクト グラフに含まれる安全でない DataSet または DataTable 型</span><span class="sxs-lookup"><span data-stu-id="559e9-280">[CA2356](https://docs.microsoft.com/visualstudio/code-quality/ca2356): Unsafe DataSet or DataTable type in web deserializable object graph</span></span>
- <span data-ttu-id="559e9-281">[CA2361](https://docs.microsoft.com/visualstudio/code-quality/ca2361):DataSet.ReadXml() を含む自動生成クラスが信頼されていないデータで使用されていないことを確認してください</span><span class="sxs-lookup"><span data-stu-id="559e9-281">[CA2361](https://docs.microsoft.com/visualstudio/code-quality/ca2361): Ensure autogenerated class containing DataSet.ReadXml() is not used with untrusted data</span></span>
- <span data-ttu-id="559e9-282">[CA2362](https://docs.microsoft.com/visualstudio/code-quality/ca2362):シリアル化可能な自動生成型の安全でない DataSet または DataTable は、リモート コード実行攻撃に対して脆弱になる可能性があります</span><span class="sxs-lookup"><span data-stu-id="559e9-282">[CA2362](https://docs.microsoft.com/visualstudio/code-quality/ca2362): Unsafe DataSet or DataTable in autogenerated serializable type can be vulnerable to remote code execution attacks</span></span>

<span data-ttu-id="559e9-283">ルールの構成の詳細については、「[コード アナライザーを使用する](https://docs.microsoft.com/visualstudio/code-quality/use-roslyn-analyzers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559e9-283">For more information about configuring rules, see [Use code analyzers](https://docs.microsoft.com/visualstudio/code-quality/use-roslyn-analyzers).</span></span>

<span data-ttu-id="559e9-284">この新しいルールは、次の NuGet パッケージで入手できます。</span><span class="sxs-lookup"><span data-stu-id="559e9-284">The new security rules are available in the following NuGet packages:</span></span>

- <span data-ttu-id="559e9-285">Microsoft.CodeAnalysis.FxCopAnalyzers 3.3.0: Visual Studio 2019 バージョン 16.3 以降向け</span><span class="sxs-lookup"><span data-stu-id="559e9-285">Microsoft.CodeAnalysis.FxCopAnalyzers 3.3.0: for Visual Studio 2019 version 16.3 or later</span></span>
- <span data-ttu-id="559e9-286">Microsoft.CodeAnalysis.FxCopAnalyzers 2.9.11: Visual Studio 2017 バージョン 15.9 向け</span><span class="sxs-lookup"><span data-stu-id="559e9-286">Microsoft.CodeAnalysis.FxCopAnalyzers 2.9.11: for Visual Studio 2017 version 15.9 or later</span></span>
