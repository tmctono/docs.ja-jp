---
ms.openlocfilehash: e9d34465970287ed94c0f0373ee4ae94d55aa1ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617179"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a><span data-ttu-id="ddd02-101">MachineKey.Encode メソッドと MachineKey.Decode メソッドが廃止に</span><span class="sxs-lookup"><span data-stu-id="ddd02-101">MachineKey.Encode and MachineKey.Decode methods are now obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="ddd02-102">説明</span><span class="sxs-lookup"><span data-stu-id="ddd02-102">Details</span></span>

<span data-ttu-id="ddd02-103">これらのメソッドは今後使用しません。</span><span class="sxs-lookup"><span data-stu-id="ddd02-103">These methods are now obsolete.</span></span> <span data-ttu-id="ddd02-104">これらのメソッドを呼び出すコードをコンパイルすると、コンパイラ警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="ddd02-104">Compilation of code that calls these methods produces a compiler warning.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ddd02-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ddd02-105">Suggestion</span></span>

<span data-ttu-id="ddd02-106">別の方法として、<xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> および <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])> を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ddd02-106">The recommended alternatives are <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> and <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span></span> <span data-ttu-id="ddd02-107">または、ビルド警告を抑制するか、古いコンパイラを使用して警告を回避できます。</span><span class="sxs-lookup"><span data-stu-id="ddd02-107">Alternatively, the build warnings can be suppressed, or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="ddd02-108">API は、まだサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ddd02-108">The APIs are still supported.</span></span>

| <span data-ttu-id="ddd02-109">名前</span><span class="sxs-lookup"><span data-stu-id="ddd02-109">Name</span></span>    | <span data-ttu-id="ddd02-110">[値]</span><span class="sxs-lookup"><span data-stu-id="ddd02-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ddd02-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="ddd02-111">Scope</span></span>   | <span data-ttu-id="ddd02-112">マイナー</span><span class="sxs-lookup"><span data-stu-id="ddd02-112">Minor</span></span>       |
| <span data-ttu-id="ddd02-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="ddd02-113">Version</span></span> | <span data-ttu-id="ddd02-114">4.5</span><span class="sxs-lookup"><span data-stu-id="ddd02-114">4.5</span></span>         |
| <span data-ttu-id="ddd02-115">種類</span><span class="sxs-lookup"><span data-stu-id="ddd02-115">Type</span></span>    | <span data-ttu-id="ddd02-116">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="ddd02-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="ddd02-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ddd02-117">Affected APIs</span></span>

- <xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
- <xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
