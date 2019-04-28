---
title: 相互運用可能なオブジェクト参照
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: ada9084f6ac3c97dc641571c0cb8379a2fac68a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918971"
---
# <a name="interoperable-object-references"></a><span data-ttu-id="84ebd-102">相互運用可能なオブジェクト参照</span><span class="sxs-lookup"><span data-stu-id="84ebd-102">Interoperable object references</span></span>
<span data-ttu-id="84ebd-103">既定では、<xref:System.Runtime.Serialization.DataContractSerializer>値でオブジェクトをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="84ebd-103">By default, <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="84ebd-104">使用することができます、<xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>オブジェクトをシリアル化するときに、オブジェクト参照を保持するために、データ コントラクト シリアライザーに指示するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="84ebd-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the data contract serializer to preserve object references when serializing objects.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="84ebd-105">生成される XML</span><span class="sxs-lookup"><span data-stu-id="84ebd-105">Generated XML</span></span>  
 <span data-ttu-id="84ebd-106">例として、次のオブジェクトを考えます。</span><span class="sxs-lookup"><span data-stu-id="84ebd-106">As an example, consider the following object:</span></span>  
  
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
  
 <span data-ttu-id="84ebd-107"><xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> を `false` (既定値) に設定すると、次の XML が生成されます。</span><span class="sxs-lookup"><span data-stu-id="84ebd-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="84ebd-108"><xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> を `true` に設定すると、次の XML が生成されます。</span><span class="sxs-lookup"><span data-stu-id="84ebd-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <span data-ttu-id="84ebd-109">ただし、<xref:System.Runtime.Serialization.XsdDataContractExporter>については説明しません、`id`と`ref`そのスキーマ内の属性場合でも、`preserveObjectReferences`プロパティに設定されて`true`します。</span><span class="sxs-lookup"><span data-stu-id="84ebd-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> doesn't describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="84ebd-110">IsReference の使用</span><span class="sxs-lookup"><span data-stu-id="84ebd-110">Using IsReference</span></span>  
 <span data-ttu-id="84ebd-111">スキーマの記述に従って有効なオブジェクト参照情報を生成するには、適用、<xref:System.Runtime.Serialization.DataContractAttribute>属性を型、および設定、<xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>フラグを`true`します。</span><span class="sxs-lookup"><span data-stu-id="84ebd-111">To generate object reference information that's valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="84ebd-112">次の例は、クラスを変更します`X`追加することで、前の例で`IsReference`:。</span><span class="sxs-lookup"><span data-stu-id="84ebd-112">The following example modifies class `X` in the previous example by adding `IsReference`:</span></span>  
  
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

 <span data-ttu-id="84ebd-113">次のような XML が生成されます。</span><span class="sxs-lookup"><span data-stu-id="84ebd-113">The generated XML is as follows:</span></span>  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A> 
    <B ref="1"></B>  
</X>
```  
  
 <span data-ttu-id="84ebd-114">`IsReference` を使用すると、メッセージのラウンド トリップに対応できます。</span><span class="sxs-lookup"><span data-stu-id="84ebd-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="84ebd-115">これがない型がスキーマから生成されたときに、XML 出力の種類がもともと想定してスキーマを必ずしも互換性がないこと。</span><span class="sxs-lookup"><span data-stu-id="84ebd-115">Without it, when a type is generated from schema, the XML output for that type isn't necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="84ebd-116">つまり、`id` 属性と `ref` 属性がシリアル化されたとしても、元のスキーマによってこれらの属性 (またはすべての属性) が拒否される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="84ebd-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="84ebd-117">`IsReference`として認識されるように、メンバーは引き続きデータ メンバーに適用され、 *referenceable*ときにラウンドト リップできます。</span><span class="sxs-lookup"><span data-stu-id="84ebd-117">With `IsReference` applied to a data member, the member continues to be recognized as *referenceable* when round-tripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84ebd-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="84ebd-118">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
