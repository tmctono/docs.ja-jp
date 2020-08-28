---
ms.openlocfilehash: cf51d5f6b3eee7189fd9613b3d780a829d197a04
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558006"
---
### <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a><span data-ttu-id="586c2-101">System.Security.Cryptography.Oid は機能的に初期化専用</span><span class="sxs-lookup"><span data-stu-id="586c2-101">System.Security.Cryptography.Oid is functionally init-only</span></span>

<span data-ttu-id="586c2-102">ASN.1 オブジェクト識別子の値とその "わかりやすい" 名前を表すために使用される <xref:System.Security.Cryptography.Oid?displayProperty=fullName> クラスは、以前は完全に変更可能でした。</span><span class="sxs-lookup"><span data-stu-id="586c2-102">The <xref:System.Security.Cryptography.Oid?displayProperty=fullName> class, which is used to represent ASN.1 Object Identifier values and their "friendly" names, was previously fully mutable.</span></span> <span data-ttu-id="586c2-103">この変更可能性は意外にも見落とされがちでした。</span><span class="sxs-lookup"><span data-stu-id="586c2-103">This mutability was often overlooked or came as a surprise.</span></span> <span data-ttu-id="586c2-104">割り当てられた後に値を変更しようとすると、プロパティの setter で <xref:System.PlatformNotSupportedException> がスローされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="586c2-104">The property setters now throw a <xref:System.PlatformNotSupportedException> when you attempt to change the value after it's already been assigned.</span></span>

#### <a name="change-description"></a><span data-ttu-id="586c2-105">変更の説明</span><span class="sxs-lookup"><span data-stu-id="586c2-105">Change description</span></span>

<span data-ttu-id="586c2-106">以前のバージョンでは、<xref:System.Security.Cryptography.Oid> のプロパティの setter を使用して、<xref:System.Security.Cryptography.Oid.FriendlyName> および <xref:System.Security.Cryptography.Oid.Value> プロパティの値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="586c2-106">In previous versions, the property setters on <xref:System.Security.Cryptography.Oid> can be used to change the value of the <xref:System.Security.Cryptography.Oid.FriendlyName> and <xref:System.Security.Cryptography.Oid.Value> properties.</span></span>

<span data-ttu-id="586c2-107">.NET 5.0 以降のバージョンでは、プロパティの setter は値の初期化にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="586c2-107">In .NET 5.0 and later versions, the property setters can only be used to initialize the value.</span></span> <span data-ttu-id="586c2-108">プロパティにコンストラクターから、あるいはプロパティの setter の前の呼び出しからの値が設定されると、プロパティの setter で常に <xref:System.PlatformNotSupportedException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="586c2-108">Once the property has a value, either from a constructor or a previous call to the property setter, the property setter always throws a <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="586c2-109">変更理由</span><span class="sxs-lookup"><span data-stu-id="586c2-109">Reason for change</span></span>

<span data-ttu-id="586c2-110">この変更により、パブリック API で戻り値の一部として <xref:System.Security.Cryptography.Oid> オブジェクトを再利用し、オブジェクト割り当てプロファイルを減らせるようになります。</span><span class="sxs-lookup"><span data-stu-id="586c2-110">This change enables the reuse of <xref:System.Security.Cryptography.Oid> objects as part of return values in public APIs to reduce object allocation profiles.</span></span> <span data-ttu-id="586c2-111"><xref:System.Security.Cryptography.Oid> 値が入力として使用されるときに、一時的な "防御用" コピーを作成する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="586c2-111">It avoids the need to create temporary "defensive" copies when <xref:System.Security.Cryptography.Oid> values are used as inputs.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="586c2-112">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="586c2-112">Version introduced</span></span>

<span data-ttu-id="586c2-113">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="586c2-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="586c2-114">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="586c2-114">Recommended action</span></span>

<span data-ttu-id="586c2-115">オブジェクトの初期化以外に、<xref:System.Security.Cryptography.Oid> プロパティの setter を使用しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="586c2-115">Avoid using the <xref:System.Security.Cryptography.Oid> property setters other than for object initialization.</span></span> <span data-ttu-id="586c2-116">新しい値を表す場合は、既存のオブジェクトの値を変更するのではなく、新しいインスタンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="586c2-116">To represent a new value, use a new instance instead of changing the value on an existing object.</span></span>

#### <a name="category"></a><span data-ttu-id="586c2-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="586c2-117">Category</span></span>

<span data-ttu-id="586c2-118">暗号</span><span class="sxs-lookup"><span data-stu-id="586c2-118">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="586c2-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="586c2-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

-->
