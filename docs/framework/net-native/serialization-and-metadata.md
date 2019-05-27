---
title: シリアル化とメタデータ
ms.date: 03/30/2017
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1ee70c2701492acd331e5faed849ff0b2e8b559
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052386"
---
# <a name="serialization-and-metadata"></a><span data-ttu-id="0576f-102">シリアル化とメタデータ</span><span class="sxs-lookup"><span data-stu-id="0576f-102">Serialization and Metadata</span></span>
<span data-ttu-id="0576f-103">アプリでオブジェクトをシリアル化および逆シリアル化する場合、ランタイム ディレクティブ (.rd.xml) ファイルにエントリを追加して、必要なメタデータが実行時に確実に存在するようにする必要があることがあります。</span><span class="sxs-lookup"><span data-stu-id="0576f-103">If your app serializes and deserializes objects, you may need to add entries to your runtime directives (.rd.xml) file to ensure that the necessary metadata is present at run time.</span></span> <span data-ttu-id="0576f-104">シリアライザーには次の 2 つのカテゴリがあり、それぞれランタイム ディレクティブ ファイルで異なる処理が必要です。</span><span class="sxs-lookup"><span data-stu-id="0576f-104">There are two categories of serializers, and each requires different handling in your runtime directives file:</span></span>  
  
- <span data-ttu-id="0576f-105">リフレクション ベースのサードパーティ シリアライザー。</span><span class="sxs-lookup"><span data-stu-id="0576f-105">Reflection-based third-party serializers.</span></span> <span data-ttu-id="0576f-106">この場合、ランタイム ディレクティブ ファイルの変更が必要です。詳細については次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="0576f-106">These require modifications to your runtime directives file, and are discussed in the next section.</span></span>  
  
- <span data-ttu-id="0576f-107">.NET Framework クラス ライブラリにある非リフレクション ベースのシリアライザー。</span><span class="sxs-lookup"><span data-stu-id="0576f-107">Non-reflection based serializers found in the .NET Framework class library.</span></span> <span data-ttu-id="0576f-108">この場合、ランタイム ディレクティブ ファイルの変更が必要なことがあります。詳細については、「[Microsoft のシリアライザー](#Microsoft)」セクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="0576f-108">These may require modifications to your runtime directives file, and are discussed in the [Microsoft serializers](#Microsoft) section.</span></span>  
  
<a name="ThirdParty"></a>   
## <a name="third-party-serializers"></a><span data-ttu-id="0576f-109">サードパーティ シリアライザー</span><span class="sxs-lookup"><span data-stu-id="0576f-109">Third-party serializers</span></span>  
 <span data-ttu-id="0576f-110">Newtonsoft.JSON などのサードパーティ シリアライザーは通常リフレクション ベースです。</span><span class="sxs-lookup"><span data-stu-id="0576f-110">Third-part serializers, including Newtonsoft.JSON, typically are reflection-based.</span></span> <span data-ttu-id="0576f-111">シリアル化データのバイナリ ラージ オブジェクト (BLOB) の場合、対象の型のフィールドを名前で検索することで、データ内のフィールドが具象型に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0576f-111">Given a binary large object (BLOB) of serialized data, the fields in the data are assigned to a concrete type by looking up the fields of the target type by name.</span></span> <span data-ttu-id="0576f-112">少なくとも、これらのライブラリを使用すると、`List<Type>` コレクションでシリアル化または逆シリアル化しようとする <xref:System.Type> オブジェクトごとに [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) 例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="0576f-112">At a minimum, using these libraries causes [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exceptions for each <xref:System.Type> object that you try to serialize or deserialize in a `List<Type>` collection.</span></span>  
  
 <span data-ttu-id="0576f-113">これらのシリアライザーでメタデータの欠落により引き起こされる問題に対処する最も簡単な方法は、1 つの名前空間 (`App.Models` など) でシリアル化に使用される型を収集し、`Serialize` メタデータ ディレクティブを適用することです。</span><span class="sxs-lookup"><span data-stu-id="0576f-113">The easiest way to address issues caused by missing metadata for these serializers is to collect types that will be used in serialization under a single namespace (such as `App.Models`) and apply a `Serialize` metadata directive to it:</span></span>  
  
```xml  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 <span data-ttu-id="0576f-114">この例で使用されている構文の詳細については、「[\<Namespace> 要素](../../../docs/framework/net-native/namespace-element-net-native.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0576f-114">For information about the syntax used in the example, see [\<Namespace> Element](../../../docs/framework/net-native/namespace-element-net-native.md).</span></span>  
  
<a name="Microsoft"></a>   
## <a name="microsoft-serializers"></a><span data-ttu-id="0576f-115">Microsoft のシリアライザー</span><span class="sxs-lookup"><span data-stu-id="0576f-115">Microsoft serializers</span></span>  
 <span data-ttu-id="0576f-116"><xref:System.Runtime.Serialization.DataContractSerializer>、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>、および <xref:System.Xml.Serialization.XmlSerializer> クラスではリフレクションを利用しませんが、シリアル化または逆シリアル化されるオブジェクトに基づいてコードが生成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="0576f-116">Although the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes do not rely on reflection, they do require code to be generated based on the object to be serialized or deserialized.</span></span> <span data-ttu-id="0576f-117">各シリアライザーのオーバーロードされたコンストラクターには、シリアル化または逆シリアル化される型を指定する <xref:System.Type> パラメーターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0576f-117">The overloaded constructors for each serializer include a <xref:System.Type> parameter that specifies the type to be serialized or deserialized.</span></span> <span data-ttu-id="0576f-118">次の 2 つのセクションで説明するように、コードでのその型の指定方法によってユーザーが実行する必要のあるアクションが定義されます。</span><span class="sxs-lookup"><span data-stu-id="0576f-118">How you specify that type in your code defines the action you must take, as discussed in the next two sections.</span></span>  
  
### <a name="typeof-used-in-the-constructor"></a><span data-ttu-id="0576f-119">コンストラクターで使用される typeof</span><span class="sxs-lookup"><span data-stu-id="0576f-119">typeof used in the constructor</span></span>  
 <span data-ttu-id="0576f-120">これらのシリアル化クラスのコンストラクターを呼び出し、メソッド呼び出しに C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) キーワードを含めた場合、**それ以外に行う必要がある作業はありません**。</span><span class="sxs-lookup"><span data-stu-id="0576f-120">If you call a constructor of these serialization classes and include the C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) keyword in the method call, **you do not have to do any additional work**.</span></span> <span data-ttu-id="0576f-121">たとえば、シリアル化クラス コンストラクターに対する次の各呼び出しでは、`typeof` キーワードがコンストラクターに渡される式の一部として使用されます。</span><span class="sxs-lookup"><span data-stu-id="0576f-121">For example, in each of the following calls to a serialization class constructor, the `typeof` keyword is used as part of the expression passed to the constructor.</span></span>  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 <span data-ttu-id="0576f-122">.NET ネイティブ コンパイラでは、このコードは自動的に処理します。</span><span class="sxs-lookup"><span data-stu-id="0576f-122">The .NET Native compiler will automatically handle this code.</span></span>  
  
### <a name="typeof-used-outside-the-constructor"></a><span data-ttu-id="0576f-123">コンストラクターの外部で使用される typeof</span><span class="sxs-lookup"><span data-stu-id="0576f-123">typeof used outside the constructor</span></span>  
 <span data-ttu-id="0576f-124">これらのシリアル化クラスのコンス トラクターの呼び出しを使用したかどうか、 C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) 、コンス トラクターに提供する式の外部キーワード<xref:System.Type>パラメーターは、次のコードのように、.NET ネイティブ コンパイラことはできません型を解決するには。</span><span class="sxs-lookup"><span data-stu-id="0576f-124">If you call a constructor of these serialization classes and use the C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) keyword outside the expression supplied to the constructor’s <xref:System.Type> parameter, as in the following code, the .NET Native compiler cannot resolve the type:</span></span>  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 <span data-ttu-id="0576f-125">この場合は、次のようなエントリを追加して、ランタイム ディレクティブ ファイルで型を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0576f-125">In this case, you must specify the type in the runtime directives file by adding an entry like this:</span></span>  
  
```xml  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 <span data-ttu-id="0576f-126">同様に、コンス トラクターを呼び出すことがある場合<xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType>その他の配列を指定<xref:System.Type>オブジェクトをシリアル化、ように、.NET ネイティブ コンパイラでは、次のコードでは、これらの型を解決することはできません。</span><span class="sxs-lookup"><span data-stu-id="0576f-126">Similarly, if you call a constructor such as <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType> and provide an array of additional <xref:System.Type> objects to serialize, as in the following code, the .NET Native compiler cannot resolve these types.</span></span>  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
 <span data-ttu-id="0576f-127">型ごとに次のようなエントリをランタイム ディレクティブ ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0576f-127">You must add entries such as the following for each type to the runtime directives file:</span></span>  
  
```xml  
<Type Name="t" Browse="Required Public" />  
```  
  
 <span data-ttu-id="0576f-128">この例で使用されている構文の詳細については、「[\<Type> 要素](../../../docs/framework/net-native/type-element-net-native.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0576f-128">For information about the syntax used in the example, see [\<Type> Element](../../../docs/framework/net-native/type-element-net-native.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0576f-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="0576f-129">See also</span></span>

- [<span data-ttu-id="0576f-130">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="0576f-130">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="0576f-131">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="0576f-131">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="0576f-132">\<型 > 要素</span><span class="sxs-lookup"><span data-stu-id="0576f-132">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)
- [<span data-ttu-id="0576f-133">\<Namespace > 要素</span><span class="sxs-lookup"><span data-stu-id="0576f-133">\<Namespace> Element</span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)
