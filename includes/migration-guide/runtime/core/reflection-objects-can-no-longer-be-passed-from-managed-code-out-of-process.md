---
ms.openlocfilehash: f011f6ebe0fa85a59f3e69c93bba9eddc4c1689b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496911"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a><span data-ttu-id="7d289-101">リフレクション オブジェクトが、マネージド コードからアウト プロセス DCOM クライアントに渡されなくなった</span><span class="sxs-lookup"><span data-stu-id="7d289-101">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients</span></span>

#### <a name="details"></a><span data-ttu-id="7d289-102">説明</span><span class="sxs-lookup"><span data-stu-id="7d289-102">Details</span></span>

<span data-ttu-id="7d289-103">リフレクション オブジェクトはマネージド コードからアウト プロセス DCOM クライアントに渡されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7d289-103">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients.</span></span> <span data-ttu-id="7d289-104">影響を受ける型は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7d289-104">The following types are affected:</span></span>

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <span data-ttu-id="7d289-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (およびその派生型、<xref:System.Reflection.FieldInfo?displayProperty=fullName>、<xref:System.Reflection.MethodInfo?displayProperty=fullName>、<xref:System.Type?displayProperty=fullName>、<xref:System.Reflection.TypeInfo?displayProperty=fullName> など)</span><span class="sxs-lookup"><span data-stu-id="7d289-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (and its derived types, including <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName>, and <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span></span>
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>

<span data-ttu-id="7d289-106">オブジェクトの <code>IMarshal</code> の呼び出しは <code>E_NOINTERFACE</code> を返します。</span><span class="sxs-lookup"><span data-stu-id="7d289-106">Calls to <code>IMarshal</code> for the object return <code>E_NOINTERFACE</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7d289-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="7d289-107">Suggestion</span></span>

<span data-ttu-id="7d289-108">非リフレクション オブジェクトで動作するように、マーシャリング コードを更新します。</span><span class="sxs-lookup"><span data-stu-id="7d289-108">Update marshaling code to work with non-reflection objects.</span></span>

| <span data-ttu-id="7d289-109">名前</span><span class="sxs-lookup"><span data-stu-id="7d289-109">Name</span></span>    | <span data-ttu-id="7d289-110">値</span><span class="sxs-lookup"><span data-stu-id="7d289-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7d289-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="7d289-111">Scope</span></span>   |<span data-ttu-id="7d289-112">マイナー</span><span class="sxs-lookup"><span data-stu-id="7d289-112">Minor</span></span>|
|<span data-ttu-id="7d289-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="7d289-113">Version</span></span>|<span data-ttu-id="7d289-114">4.6</span><span class="sxs-lookup"><span data-stu-id="7d289-114">4.6</span></span>|
|<span data-ttu-id="7d289-115">種類</span><span class="sxs-lookup"><span data-stu-id="7d289-115">Type</span></span>|<span data-ttu-id="7d289-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="7d289-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="7d289-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="7d289-117">Affected APIs</span></span>

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <xref:System.Reflection.FieldInfo?displayProperty=fullName>
- <xref:System.Reflection.MemberInfo?displayProperty=fullName>
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.MethodInfo?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>
- <xref:System.Reflection.TypeInfo?displayProperty=fullName>
- <xref:System.Type?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Reflection.Assembly`
- `T:System.Reflection.FieldInfo`
- `T:System.Reflection.MemberInfo`
- `T:System.Reflection.MethodBody`
- `T:System.Reflection.MethodInfo`
- `T:System.Reflection.Module`
- `T:System.Reflection.ParameterInfo`
- `T:System.Reflection.TypeInfo`
- `T:System.Type`

-->
