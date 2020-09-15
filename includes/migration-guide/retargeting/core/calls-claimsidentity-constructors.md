---
ms.openlocfilehash: b88f7d4a17f885b687d99ab9410a56039e176080
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614637"
---
### <a name="calls-to-claimsidentity-constructors"></a><span data-ttu-id="4c1e8-101">ClaimsIdentity コンストラクターを呼び出す</span><span class="sxs-lookup"><span data-stu-id="4c1e8-101">Calls to ClaimsIdentity constructors</span></span>

#### <a name="details"></a><span data-ttu-id="4c1e8-102">説明</span><span class="sxs-lookup"><span data-stu-id="4c1e8-102">Details</span></span>

<span data-ttu-id="4c1e8-103">.NET Framework 4.6.2 以降、<xref:System.Security.Claims.ClaimsIdentity> コンストラクターと <xref:System.Security.Principal.IIdentity?displayProperty=fullName> パラメーターの組み合わせで <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> プロパティが設定されるしくみに変更があります。</span><span class="sxs-lookup"><span data-stu-id="4c1e8-103">Starting with the .NET Framework 4.6.2, there is a change in how <xref:System.Security.Claims.ClaimsIdentity> constructors with an <xref:System.Security.Principal.IIdentity?displayProperty=fullName> parameter set the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property.</span></span> <span data-ttu-id="4c1e8-104"><xref:System.Security.Principal.IIdentity?displayProperty=fullName> 引数が <xref:System.Security.Claims.ClaimsIdentity> オブジェクトで、その <xref:System.Security.Claims.ClaimsIdentity> オブジェクトの <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> プロパティが `null` ではない場合、<xref:System.Security.Claims.ClaimsIdentity.Clone> メソッドを使用して <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> プロパティがアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="4c1e8-104">If the <xref:System.Security.Principal.IIdentity?displayProperty=fullName> argument is a <xref:System.Security.Claims.ClaimsIdentity> object, and the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of that <xref:System.Security.Claims.ClaimsIdentity> object is not `null`, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property is attached by using the <xref:System.Security.Claims.ClaimsIdentity.Clone> method.</span></span> <span data-ttu-id="4c1e8-105">Framework 4.6.1 以前のバージョンでは、<xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> プロパティは既存の参照として付けられます。この変更によって、.NET Framework 4.6.2 以降、新しい <xref:System.Security.Claims.ClaimsIdentity> オブジェクトの <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> プロパティはコンストラクターの <xref:System.Security.Principal.IIdentity?displayProperty=fullName> 引数の <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> プロパティとは等しくなくなります。</span><span class="sxs-lookup"><span data-stu-id="4c1e8-105">In the Framework 4.6.1 and earlier versions, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property is attached as an existing reference.Because of this change, starting with the .NET Framework 4.6.2, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of the new <xref:System.Security.Claims.ClaimsIdentity> object is not equal to the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of the constructor's <xref:System.Security.Principal.IIdentity?displayProperty=fullName> argument.</span></span> <span data-ttu-id="4c1e8-106">.NET Framework 4.6.1 以前のバージョンでは、等しくなります。</span><span class="sxs-lookup"><span data-stu-id="4c1e8-106">In the .NET Framework 4.6.1 and earlier versions, it is equal.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4c1e8-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="4c1e8-107">Suggestion</span></span>

<span data-ttu-id="4c1e8-108">この動作が望ましくない場合、アプリケーション構成ファイルで `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` スイッチを `true` に設定して以前の動作を復元することができます。</span><span class="sxs-lookup"><span data-stu-id="4c1e8-108">If this behavior is undesirable, you can restore the previous behavior by setting the `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` switch in your application configuration file to `true`.</span></span> <span data-ttu-id="4c1e8-109">この場合、web.config ファイルの `<runtime>` セクションに次を追加します。</span><span class="sxs-lookup"><span data-stu-id="4c1e8-109">This requires that you add the following to the `<runtime>` section of your web.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="4c1e8-110">名前</span><span class="sxs-lookup"><span data-stu-id="4c1e8-110">Name</span></span>    | <span data-ttu-id="4c1e8-111">値</span><span class="sxs-lookup"><span data-stu-id="4c1e8-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4c1e8-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="4c1e8-112">Scope</span></span>   | <span data-ttu-id="4c1e8-113">エッジ</span><span class="sxs-lookup"><span data-stu-id="4c1e8-113">Edge</span></span>        |
| <span data-ttu-id="4c1e8-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="4c1e8-114">Version</span></span> | <span data-ttu-id="4c1e8-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="4c1e8-115">4.6.2</span></span>       |
| <span data-ttu-id="4c1e8-116">種類</span><span class="sxs-lookup"><span data-stu-id="4c1e8-116">Type</span></span>    | <span data-ttu-id="4c1e8-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="4c1e8-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="4c1e8-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="4c1e8-118">Affected APIs</span></span>

- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity)>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim})>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim},System.String,System.String,System.String)>
