---
ms.openlocfilehash: 4075eadf7cfb39c913b7657d43335bae5497deff
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216931"
---
### <a name="custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively"></a><span data-ttu-id="173ef-101">カスタム EncoderFallbackBuffer インスタンスが再帰的にフォールバックしない</span><span class="sxs-lookup"><span data-stu-id="173ef-101">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>

<span data-ttu-id="173ef-102">カスタム <xref:System.Text.EncoderFallbackBuffer> インスタンスが再帰的にフォールバックしません。</span><span class="sxs-lookup"><span data-stu-id="173ef-102">Custom <xref:System.Text.EncoderFallbackBuffer> instances cannot fall back recursively.</span></span> <span data-ttu-id="173ef-103"><xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> を実装した場合、文字のシーケンスが変換先のエンコードに変換されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="173ef-103">The implementation of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> must result in a character sequence that is convertible to the destination encoding.</span></span> <span data-ttu-id="173ef-104">それ以外の場合は、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="173ef-104">Otherwise, an exception occurs.</span></span>

#### <a name="details"></a><span data-ttu-id="173ef-105">説明</span><span class="sxs-lookup"><span data-stu-id="173ef-105">Details</span></span>

<span data-ttu-id="173ef-106">文字をバイトに変換する操作中に、ランタイムによって不適切な形式または変換不能な UTF-16 のシーケンスが検出され、それらの文字は <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="173ef-106">During a character-to-byte transcoding operation, the runtime detects ill-formed or nonconvertible UTF-16 sequences and provides those characters to the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="173ef-107">元の変換不能なデータの代わりに置き換える文字は、`Fallback` メソッドによって決定されますが、これらの文字は、<xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> をループで呼び出すことによってドレインされます。</span><span class="sxs-lookup"><span data-stu-id="173ef-107">The `Fallback` method determines which characters should be substituted for the original nonconvertible data, and these characters are drained by calling <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> in a loop.</span></span>

<span data-ttu-id="173ef-108">それからランタイムはこれらの置換文字を、ターゲットのエンコードに変換しようとします。</span><span class="sxs-lookup"><span data-stu-id="173ef-108">The runtime then attempts to transcode these substitution characters to the target encoding.</span></span> <span data-ttu-id="173ef-109">この操作が成功する場合、ランタイムによって、元の入力文字列の中断した箇所からコード変換が継続されます。</span><span class="sxs-lookup"><span data-stu-id="173ef-109">If this operation succeeds, the runtime continues transcoding from where it left off in the original input string.</span></span>

<span data-ttu-id="173ef-110">.NET Core Preview 7 以前では、<xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> をカスタム実装することにより、変換先のエンコードに変換できなかった文字シーケンスが返されました。</span><span class="sxs-lookup"><span data-stu-id="173ef-110">In .NET Core Preview 7 and earlier versions, custom implementations of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> can return character sequences that are not convertible to the destination encoding.</span></span> <span data-ttu-id="173ef-111">置換文字がターゲットのエンコードにコード変換できない場合、<xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> メソッドによって新しい置換のシーケンスが返されることを期待し、ランタイムによって置換文字列が使用されて <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> メソッドが再度呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="173ef-111">If the substituted characters cannot be transcoded to the target encoding, the runtime invokes the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> method once again with the substitution characters, expecting the <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> method to return a new substitution sequence.</span></span> <span data-ttu-id="173ef-112">この処理は、結果的に、ランタイムによって正しい形式の、変換可能な代替が確認されるまで、または最大再帰数に到達するまで、継続します。</span><span class="sxs-lookup"><span data-stu-id="173ef-112">This process continues until the runtime eventually sees a well-formed, convertible substitution, or until a maximum recursion count is reached.</span></span>

<span data-ttu-id="173ef-113">.NET Core 3.0 以降では、<xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> をカスタム実装した場合、変換先のエンコードに変換できる文字シーケンスが返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="173ef-113">Starting with .NET Core 3.0, custom implementations of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> must return character sequences that are convertible to the destination encoding.</span></span> <span data-ttu-id="173ef-114">置換文字がターゲットのエンコードにコード変換できない場合、<xref:System.ArgumentException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="173ef-114">If the substituted characters cannot be transcoded to the target encoding, an <xref:System.ArgumentException> is thrown.</span></span> <span data-ttu-id="173ef-115">ランタイムは、それ以上 <xref:System.Text.EncoderFallbackBuffer> インスタンスに対し、再帰呼び出しを実行しなくなります。</span><span class="sxs-lookup"><span data-stu-id="173ef-115">The runtime will no longer make recursive calls into the <xref:System.Text.EncoderFallbackBuffer> instance.</span></span>

<span data-ttu-id="173ef-116">この動作は、次の 3 つの条件がすべて満たされている場合にのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="173ef-116">This behavior only applies when all three of the following conditions are met:</span></span>

- <span data-ttu-id="173ef-117">ランタイムによって、不正な形式の UTF-16 シーケンスまたはターゲットのエンコードに変換できない UTF-16 シーケンスが検出される。</span><span class="sxs-lookup"><span data-stu-id="173ef-117">The runtime detects an ill-formed UTF-16 sequence or a UTF-16 sequence that cannot be converted to the target encoding.</span></span>
- <span data-ttu-id="173ef-118">カスタム <xref:System.Text.EncoderFallback> が指定された。</span><span class="sxs-lookup"><span data-stu-id="173ef-118">A custom <xref:System.Text.EncoderFallback> has been specified.</span></span>
- <span data-ttu-id="173ef-119">カスタム <xref:System.Text.EncoderFallback> によって、新しい不正な形式の、または変換不能な URT-16 シーケンスへの置換を試行される。</span><span class="sxs-lookup"><span data-stu-id="173ef-119">The custom <xref:System.Text.EncoderFallback> attempts to substitute a new ill-formed or nonconvertible UTF-16 sequence.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="173ef-120">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="173ef-120">Version introduced</span></span>

<span data-ttu-id="173ef-121">3.0</span><span class="sxs-lookup"><span data-stu-id="173ef-121">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="173ef-122">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="173ef-122">Recommended action</span></span>

<span data-ttu-id="173ef-123">ほとんどの開発者は、何も措置を講じる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="173ef-123">Most developers needn't take any action.</span></span>

<span data-ttu-id="173ef-124">アプリケーションでカスタム <xref:System.Text.EncoderFallback> および <xref:System.Text.EncoderFallbackBuffer> クラスを使用している場合、<xref:System.Text.EncoderFallbackBuffer.Fallback%2A> メソッドがランタイムによって最初に呼び出されたときに、<xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> を実装することで、ターゲットのエンコードに直接変換できる正しい形式の UTF-16 で、データがフォールバック バッファーに入力されるようにします。</span><span class="sxs-lookup"><span data-stu-id="173ef-124">If an application uses a custom <xref:System.Text.EncoderFallback> and <xref:System.Text.EncoderFallbackBuffer> class, ensure the implementation of <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> populates the fallback buffer with well-formed UTF-16 data that is directly convertible to the target encoding when the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A> method is first invoked by the runtime.</span></span>

#### <a name="category"></a><span data-ttu-id="173ef-125">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="173ef-125">Category</span></span>

<span data-ttu-id="173ef-126">CoreFx</span><span class="sxs-lookup"><span data-stu-id="173ef-126">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="173ef-127">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="173ef-127">Affected APIs</span></span>

- <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>
- <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.EncoderFallbackBuffer.Fallback`
- `M:System.Text.EncoderFallbackBuffer.GetNextChar`

-->
