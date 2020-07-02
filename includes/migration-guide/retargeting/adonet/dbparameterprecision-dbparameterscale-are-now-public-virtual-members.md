---
ms.openlocfilehash: 063e10b0310880af255793215a80a5529a5db0ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616107"
---
### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a><span data-ttu-id="61a02-101">DbParameter.Precision と DbParameter.Scale は、パブリック仮想メンバーになった</span><span class="sxs-lookup"><span data-stu-id="61a02-101">DbParameter.Precision and DbParameter.Scale are now public virtual members</span></span>

#### <a name="details"></a><span data-ttu-id="61a02-102">説明</span><span class="sxs-lookup"><span data-stu-id="61a02-102">Details</span></span>

<span data-ttu-id="61a02-103"><xref:System.Data.Common.DbParameter.Precision> および <xref:System.Data.Common.DbParameter.Scale> はパブリック仮想プロパティとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="61a02-103"><xref:System.Data.Common.DbParameter.Precision> and <xref:System.Data.Common.DbParameter.Scale> are implemented as public virtual properties.</span></span> <span data-ttu-id="61a02-104">これらは、対応する明示的なインターフェイス実装、<xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> と <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale> を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="61a02-104">They replace the corresponding explicit interface implementations, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> and <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="61a02-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="61a02-105">Suggestion</span></span>

<span data-ttu-id="61a02-106">ADO.NET データベース プロバイダーを再構築するとき、これらの違いにより、「override」キーワードが Precision および Scale プロパティに適用される必要があります。</span><span class="sxs-lookup"><span data-stu-id="61a02-106">When re-building an ADO.NET database provider, these differences will require the 'override' keyword to be applied to the Precision and Scale properties.</span></span> <span data-ttu-id="61a02-107">これは、コンポーネントを再構築するときにのみ必要です。既存のバイナリは引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="61a02-107">This is only needed when re-building the components; existing binaries will continue to work.</span></span>

| <span data-ttu-id="61a02-108">名前</span><span class="sxs-lookup"><span data-stu-id="61a02-108">Name</span></span>    | <span data-ttu-id="61a02-109">[値]</span><span class="sxs-lookup"><span data-stu-id="61a02-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="61a02-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="61a02-110">Scope</span></span>   | <span data-ttu-id="61a02-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="61a02-111">Minor</span></span>       |
| <span data-ttu-id="61a02-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="61a02-112">Version</span></span> | <span data-ttu-id="61a02-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="61a02-113">4.5.1</span></span>       |
| <span data-ttu-id="61a02-114">種類</span><span class="sxs-lookup"><span data-stu-id="61a02-114">Type</span></span>    | <span data-ttu-id="61a02-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="61a02-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="61a02-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="61a02-116">Affected APIs</span></span>

- <xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType>
- <xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType>
