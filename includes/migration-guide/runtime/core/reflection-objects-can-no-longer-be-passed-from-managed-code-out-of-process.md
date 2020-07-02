---
ms.openlocfilehash: a54b17b2002bd0f85b8b47c5e37e040470d6c494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621332"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a><span data-ttu-id="33692-101">リフレクション オブジェクトが、マネージド コードからアウト プロセス DCOM クライアントに渡されなくなった</span><span class="sxs-lookup"><span data-stu-id="33692-101">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients</span></span>

#### <a name="details"></a><span data-ttu-id="33692-102">説明</span><span class="sxs-lookup"><span data-stu-id="33692-102">Details</span></span>

<span data-ttu-id="33692-103">リフレクション オブジェクトはマネージド コードからアウト プロセス DCOM クライアントに渡されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="33692-103">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients.</span></span> <span data-ttu-id="33692-104">影響を受ける型は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="33692-104">The following types are affected:</span></span><ul><li><xref:System.Reflection.Assembly?displayProperty=fullName></li><li><span data-ttu-id="33692-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (およびその派生型、<xref:System.Reflection.FieldInfo?displayProperty=fullName>、<xref:System.Reflection.MethodInfo?displayProperty=fullName>、<xref:System.Type?displayProperty=fullName>、<xref:System.Reflection.TypeInfo?displayProperty=fullName> など)</span><span class="sxs-lookup"><span data-stu-id="33692-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (and its derived types, including <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName>, and <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span></span></li><li><xref:System.Reflection.MethodBody?displayProperty=fullName></li><li><xref:System.Reflection.Module?displayProperty=fullName></li><li><span data-ttu-id="33692-106">[https://login.microsoftonline.com/consumers/](<xref:System.Reflection.ParameterInfo?displayProperty=fullName>)</span><span class="sxs-lookup"><span data-stu-id="33692-106"><xref:System.Reflection.ParameterInfo?displayProperty=fullName>.</span></span></li></ul><span data-ttu-id="33692-107">オブジェクトの <code>IMarshal</code> の呼び出しは <code>E_NOINTERFACE</code> を返します。</span><span class="sxs-lookup"><span data-stu-id="33692-107">Calls to <code>IMarshal</code> for the object return <code>E_NOINTERFACE</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="33692-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="33692-108">Suggestion</span></span>

<span data-ttu-id="33692-109">非リフレクション オブジェクトで動作するように、マーシャリング コードを更新します。</span><span class="sxs-lookup"><span data-stu-id="33692-109">Update marshaling code to work with non-reflection objects</span></span>

| <span data-ttu-id="33692-110">名前</span><span class="sxs-lookup"><span data-stu-id="33692-110">Name</span></span>    | <span data-ttu-id="33692-111">値</span><span class="sxs-lookup"><span data-stu-id="33692-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="33692-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="33692-112">Scope</span></span>   |<span data-ttu-id="33692-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="33692-113">Minor</span></span>|
|<span data-ttu-id="33692-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="33692-114">Version</span></span>|<span data-ttu-id="33692-115">4.6</span><span class="sxs-lookup"><span data-stu-id="33692-115">4.6</span></span>|
|<span data-ttu-id="33692-116">種類</span><span class="sxs-lookup"><span data-stu-id="33692-116">Type</span></span>|<span data-ttu-id="33692-117">ランタイム</span><span class="sxs-lookup"><span data-stu-id="33692-117">Runtime</span></span>|
