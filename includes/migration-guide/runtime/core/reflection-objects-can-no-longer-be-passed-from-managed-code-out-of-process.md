---
ms.openlocfilehash: d00f86c492a7d32344b1067a48c8e53aa2a43426
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761333"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a><span data-ttu-id="31a9b-101">リフレクション オブジェクトが、マネージド コードからアウト プロセス DCOM クライアントに渡されなくなった</span><span class="sxs-lookup"><span data-stu-id="31a9b-101">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients</span></span>

|   |   |
|---|---|
|<span data-ttu-id="31a9b-102">説明</span><span class="sxs-lookup"><span data-stu-id="31a9b-102">Details</span></span>|<span data-ttu-id="31a9b-103">リフレクション オブジェクトはマネージド コードからアウト プロセス DCOM クライアントに渡されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="31a9b-103">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients.</span></span> <span data-ttu-id="31a9b-104">影響を受ける型は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="31a9b-104">The following types are affected:</span></span><ul><li><xref:System.Reflection.Assembly?displayProperty=name></li><li><span data-ttu-id="31a9b-105"><xref:System.Reflection.MemberInfo?displayProperty=name> (およびその派生型、<xref:System.Reflection.FieldInfo?displayProperty=name>、<xref:System.Reflection.MethodInfo?displayProperty=name>、<xref:System.Type?displayProperty=name>、<xref:System.Reflection.TypeInfo?displayProperty=name> など)</span><span class="sxs-lookup"><span data-stu-id="31a9b-105"><xref:System.Reflection.MemberInfo?displayProperty=name> (and its derived types, including <xref:System.Reflection.FieldInfo?displayProperty=name>, <xref:System.Reflection.MethodInfo?displayProperty=name>, <xref:System.Type?displayProperty=name>, and <xref:System.Reflection.TypeInfo?displayProperty=name>)</span></span></li><li><xref:System.Reflection.MethodBody?displayProperty=name></li><li><xref:System.Reflection.Module?displayProperty=name></li><li><span data-ttu-id="31a9b-106"><xref:System.Reflection.ParameterInfo?displayProperty=name>。</span><span class="sxs-lookup"><span data-stu-id="31a9b-106"><xref:System.Reflection.ParameterInfo?displayProperty=name>.</span></span></li></ul><span data-ttu-id="31a9b-107">オブジェクトの <code>IMarshal</code> の呼び出しは <code>E_NOINTERFACE</code> を返します。</span><span class="sxs-lookup"><span data-stu-id="31a9b-107">Calls to <code>IMarshal</code> for the object return <code>E_NOINTERFACE</code>.</span></span>|
|<span data-ttu-id="31a9b-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="31a9b-108">Suggestion</span></span>|<span data-ttu-id="31a9b-109">非リフレクション オブジェクトで動作するように、マーシャリング コードを更新します。</span><span class="sxs-lookup"><span data-stu-id="31a9b-109">Update marshaling code to work with non-reflection objects</span></span>|
|<span data-ttu-id="31a9b-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="31a9b-110">Scope</span></span>|<span data-ttu-id="31a9b-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="31a9b-111">Minor</span></span>|
|<span data-ttu-id="31a9b-112">Version</span><span class="sxs-lookup"><span data-stu-id="31a9b-112">Version</span></span>|<span data-ttu-id="31a9b-113">4.6</span><span class="sxs-lookup"><span data-stu-id="31a9b-113">4.6</span></span>|
|<span data-ttu-id="31a9b-114">型</span><span class="sxs-lookup"><span data-stu-id="31a9b-114">Type</span></span>|<span data-ttu-id="31a9b-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="31a9b-115">Runtime</span></span>|

