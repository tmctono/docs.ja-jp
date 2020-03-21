---
title: 相互運用可能なオブジェクト参照
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: 0927f217a1666f8f27ca9c3e68f80a96b9c0f2b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184702"
---
# <a name="interoperable-object-references"></a><span data-ttu-id="566a1-102">相互運用可能なオブジェクト参照</span><span class="sxs-lookup"><span data-stu-id="566a1-102">Interoperable object references</span></span>
<span data-ttu-id="566a1-103">既定では、<xref:System.Runtime.Serialization.DataContractSerializer>オブジェクトを値でシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="566a1-103">By default, <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="566a1-104">このプロパティを<xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>使用すると、オブジェクトをシリアル化するときにオブジェクト参照を保持するようにデータ コントラクト シリアライザーに指示できます。</span><span class="sxs-lookup"><span data-stu-id="566a1-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the data contract serializer to preserve object references when serializing objects.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="566a1-105">生成される XML</span><span class="sxs-lookup"><span data-stu-id="566a1-105">Generated XML</span></span>  
 <span data-ttu-id="566a1-106">例として、次のオブジェクトを考えます。</span><span class="sxs-lookup"><span data-stu-id="566a1-106">As an example, consider the following object:</span></span>  
  
```csharp  
[DataContract]  
public class X  
{  
    SomeClass someInstance = new SomeClass();  
    [DataMember]  
    public SomeClass A = someInstance;  
    [DataMember]  
    public SomeClass B = someInstance;  
}  
  
public class SomeClass
{  
}  
```  
  
 <span data-ttu-id="566a1-107"><xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> を `false` (既定値) に設定すると、次の XML が生成されます。</span><span class="sxs-lookup"><span data-stu-id="566a1-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="566a1-108"><xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> を `true` に設定すると、次の XML が生成されます。</span><span class="sxs-lookup"><span data-stu-id="566a1-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <span data-ttu-id="566a1-109">ただし、<xref:System.Runtime.Serialization.XsdDataContractExporter>プロパティ`id`が`ref``true`に設定されている場合でも、スキーマの属性と`preserveObjectReferences`属性は記述しません。</span><span class="sxs-lookup"><span data-stu-id="566a1-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> doesn't describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="566a1-110">IsReference の使用</span><span class="sxs-lookup"><span data-stu-id="566a1-110">Using IsReference</span></span>  
 <span data-ttu-id="566a1-111">スキーマに従って有効なオブジェクト参照情報を生成するには、<xref:System.Runtime.Serialization.DataContractAttribute>属性を型に適用し、<xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>フラグを に`true`設定します。</span><span class="sxs-lookup"><span data-stu-id="566a1-111">To generate object reference information that's valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="566a1-112">次の例では、前`X`の例のクラスを追加`IsReference`して変更します。</span><span class="sxs-lookup"><span data-stu-id="566a1-112">The following example modifies class `X` in the previous example by adding `IsReference`:</span></span>  
  
```csharp
[DataContract(IsReference=true)]
public class X
{  
     SomeClass someInstance = new SomeClass();
     [DataMember]
     public SomeClass A = someInstance;
     [DataMember]
     public SomeClass B = someInstance;
}
  
public class SomeClass
{
}  
````

 <span data-ttu-id="566a1-113">次のような XML が生成されます。</span><span class="sxs-lookup"><span data-stu-id="566a1-113">The generated XML is as follows:</span></span>  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 <span data-ttu-id="566a1-114">`IsReference` を使用すると、メッセージのラウンド トリップに対応できます。</span><span class="sxs-lookup"><span data-stu-id="566a1-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="566a1-115">この機能を使用しない場合、型がスキーマから生成される場合、その型の XML 出力は、当初想定されていたスキーマと必ずしも互換性があるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="566a1-115">Without it, when a type is generated from schema, the XML output for that type isn't necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="566a1-116">つまり、`id` 属性と `ref` 属性がシリアル化されたとしても、元のスキーマによってこれらの属性 (またはすべての属性) が拒否される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="566a1-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="566a1-117">データ`IsReference`メンバーに適用すると、ラウンド トリップ時にメンバーが*参照可能*であると認識され続けます。</span><span class="sxs-lookup"><span data-stu-id="566a1-117">With `IsReference` applied to a data member, the member continues to be recognized as *referenceable* when round-tripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="566a1-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="566a1-118">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
