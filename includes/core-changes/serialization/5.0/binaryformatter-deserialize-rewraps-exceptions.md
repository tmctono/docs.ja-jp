---
ms.openlocfilehash: 4aef35502fc93cbf0399e3c8d0932338829d6c07
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517355"
---
### <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a><span data-ttu-id="cb2f1-101">BinaryFormatter.Deserialize によって SerializationException の例外の一部が再ラップされる</span><span class="sxs-lookup"><span data-stu-id="cb2f1-101">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>

<span data-ttu-id="cb2f1-102"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> メソッドによって、<xref:System.Runtime.Serialization.SerializationException> 内の一部の例外オブジェクトが、例外を呼び出し元に伝達する前に再ラップされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="cb2f1-102">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method now rewraps some exception objects inside a <xref:System.Runtime.Serialization.SerializationException> before propagating the exception back to the caller.</span></span>

#### <a name="change-description"></a><span data-ttu-id="cb2f1-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="cb2f1-103">Change description</span></span>

<span data-ttu-id="cb2f1-104">以前の <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> メソッドでは、<xref:System.ArgumentNullException> などの一部の任意の例外が、スタックの上の呼び出し元に伝達されることが可能でした。</span><span class="sxs-lookup"><span data-stu-id="cb2f1-104">Previously, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method allowed some arbitrary exceptions, such as <xref:System.ArgumentNullException>, to propagate up the stack to its callers.</span></span>

<span data-ttu-id="cb2f1-105">.NET 5.0 以降の <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> メソッドでは、無効な逆シリアル化操作によって発生した例外がより積極的にキャッチされ、<xref:System.Runtime.Serialization.SerializationException> にラップされます。</span><span class="sxs-lookup"><span data-stu-id="cb2f1-105">In .NET 5.0 and later, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method more aggressively catches exceptions that occur due to invalid deserialization operations and wraps them in a <xref:System.Runtime.Serialization.SerializationException>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cb2f1-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="cb2f1-106">Version introduced</span></span>

<span data-ttu-id="cb2f1-107">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="cb2f1-107">5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cb2f1-108">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="cb2f1-108">Recommended action</span></span>

<span data-ttu-id="cb2f1-109">ほとんどの場合、お客様が何らかのアクションを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cb2f1-109">In most cases, you don't need to take any action.</span></span> <span data-ttu-id="cb2f1-110">ただし、呼び出しサイトが、スローされる特定の例外に依存している場合は、次の例に示すように、外側の <xref:System.Runtime.Serialization.SerializationException> から例外のラップを解除できます。</span><span class="sxs-lookup"><span data-stu-id="cb2f1-110">However, if your call site depends on a particular exception being thrown, you can unwrap the exception from the outer <xref:System.Runtime.Serialization.SerializationException>, as shown in the following example.</span></span>

```csharp
Stream inputStream = GetInputStream();
var formatter = new BinaryFormatter();

try
{
    object deserialized = formatter.Deserialize(inputStream);
}
catch (MyException myEx)
{
    // Handle 'myEx' here in case it was thrown directly.
}
catch (SerializationException serEx)
{
    if (serEx.InnerException is MyException myEx)
    {
        // Handle 'myEx' here in case it was wrapped in SerializationException.
    }
    else
    {
        throw;
    }
}
```

#### <a name="category"></a><span data-ttu-id="cb2f1-111">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="cb2f1-111">Category</span></span>

<span data-ttu-id="cb2f1-112">シリアル化</span><span class="sxs-lookup"><span data-stu-id="cb2f1-112">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cb2f1-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="cb2f1-113">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

-->
