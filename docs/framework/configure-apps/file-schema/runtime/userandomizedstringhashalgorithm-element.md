---
title: <UseRandomizedStringHashAlgorithm> 要素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
ms.openlocfilehash: 148d55c8b8a63737867c4bfdf3ab118dfdefd6f9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174096"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="67ced-102">\<UseRandomizedStringHashAlgorithm> 要素</span><span class="sxs-lookup"><span data-stu-id="67ced-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>

<span data-ttu-id="67ced-103">共通言語ランタイムがアプリケーション ドメインごとに文字列のハッシュ コードを計算するかどうかを判定します。</span><span class="sxs-lookup"><span data-stu-id="67ced-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**  
  
## <a name="syntax"></a><span data-ttu-id="67ced-104">構文</span><span class="sxs-lookup"><span data-stu-id="67ced-104">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67ced-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="67ced-105">Attributes and Elements</span></span>  

 <span data-ttu-id="67ced-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="67ced-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67ced-107">属性</span><span class="sxs-lookup"><span data-stu-id="67ced-107">Attributes</span></span>  
  
|<span data-ttu-id="67ced-108">属性</span><span class="sxs-lookup"><span data-stu-id="67ced-108">Attribute</span></span>|<span data-ttu-id="67ced-109">説明</span><span class="sxs-lookup"><span data-stu-id="67ced-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="67ced-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="67ced-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="67ced-111">アプリケーション ドメインごとに文字列のハッシュ コードを計算するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="67ced-111">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="67ced-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="67ced-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="67ced-113">値</span><span class="sxs-lookup"><span data-stu-id="67ced-113">Value</span></span>|<span data-ttu-id="67ced-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="67ced-114">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="67ced-115">共通言語ランタイムは、アプリケーション ドメインごとに文字列のハッシュ コードを計算しません。1 つのアルゴリズムを使用して文字列のハッシュ コードを計算します。</span><span class="sxs-lookup"><span data-stu-id="67ced-115">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="67ced-116">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="67ced-116">This is the default.</span></span>|  
|`1`|<span data-ttu-id="67ced-117">共通言語ランタイムは、アプリケーション ドメインごとに文字列のハッシュ コードを計算します。</span><span class="sxs-lookup"><span data-stu-id="67ced-117">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="67ced-118">異なるアプリケーション ドメインや異なるプロセスで同一の文字列のハッシュ コードは異なります。</span><span class="sxs-lookup"><span data-stu-id="67ced-118">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67ced-119">子要素</span><span class="sxs-lookup"><span data-stu-id="67ced-119">Child Elements</span></span>  

 <span data-ttu-id="67ced-120">なし。</span><span class="sxs-lookup"><span data-stu-id="67ced-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67ced-121">親要素</span><span class="sxs-lookup"><span data-stu-id="67ced-121">Parent Elements</span></span>  
  
|<span data-ttu-id="67ced-122">要素</span><span class="sxs-lookup"><span data-stu-id="67ced-122">Element</span></span>|<span data-ttu-id="67ced-123">説明</span><span class="sxs-lookup"><span data-stu-id="67ced-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="67ced-124">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="67ced-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="67ced-125">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="67ced-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67ced-126">解説</span><span class="sxs-lookup"><span data-stu-id="67ced-126">Remarks</span></span>  

 <span data-ttu-id="67ced-127">既定では、<xref:System.StringComparer> のクラスと <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> のメソッドは、アプリケーション ドメイン間で一貫したハッシュ コードを生成する単一のハッシュ アルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="67ced-127">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="67ced-128">これは、`enabled` 要素の `<UseRandomizedStringHashAlgorithm>` 属性を `0` に設定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="67ced-128">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="67ced-129">これは、.NET Framework 4 で使用されるハッシュアルゴリズムです。</span><span class="sxs-lookup"><span data-stu-id="67ced-129">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="67ced-130"><xref:System.StringComparer> クラスと <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> メソッドは、別のハッシュ アルゴリズムを使用してアプリケーション ドメインごとのハッシュ コードを計算することもできます。</span><span class="sxs-lookup"><span data-stu-id="67ced-130">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="67ced-131">その結果、同じ文字列のハッシュ コードが、アプリケーション ドメイン間で異なります。</span><span class="sxs-lookup"><span data-stu-id="67ced-131">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="67ced-132">これはオプトイン機能であり、この機能を利用するには、`enabled` 要素の `<UseRandomizedStringHashAlgorithm>` 属性を `1` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67ced-132">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="67ced-133">ハッシュ テーブルの文字列検索は、通常 O(1) 操作です。</span><span class="sxs-lookup"><span data-stu-id="67ced-133">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="67ced-134">ただし、多数の競合が発生した場合、参照は O (n<sup>2</sup>) 操作になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67ced-134">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="67ced-135">特にハッシュ コードを計算するキーがユーザーによる入力データに基づいている場合、`<UseRandomizedStringHashAlgorithm>` 構成要素を使用して、アプリケーション ドメインごとにランダムなハッシュ アルゴリズムを生成でき、潜在的な競合の数を制限できます。</span><span class="sxs-lookup"><span data-stu-id="67ced-135">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67ced-136">例</span><span class="sxs-lookup"><span data-stu-id="67ced-136">Example</span></span>  

 <span data-ttu-id="67ced-137">次の例では、値が「This is a string.」であるプライベート文字列定数 `DisplayString` を含む `s` クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="67ced-137">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="67ced-138">また、メソッドを実行しているアプリケーション ドメインの名前と共に文字列値とハッシュ コードを表示する `ShowStringHashCode` メソッドも含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ced-138">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="67ced-139">構成ファイルを指定せずにこの例を実行すると、次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="67ced-139">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="67ced-140">文字列のハッシュ コードが 2 つアプリケーション ドメインで同じであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="67ced-140">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="67ced-141">ただし、例のディレクトリに次の構成ファイルを追加して例を実行すると、同じ文字列のハッシュ コードがアプリケーション ドメインによって異なります。</span><span class="sxs-lookup"><span data-stu-id="67ced-141">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="67ced-142">構成ファイルが存在する場合、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="67ced-142">When the configuration file is present, the example displays the following output:</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="67ced-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="67ced-143">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
