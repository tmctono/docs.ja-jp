---
ms.openlocfilehash: 77e04333ed2b9a5ca8b900c1355fb5b12957772d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234707"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a><span data-ttu-id="73639-101">MachineKey.Encode メソッドと MachineKey.Decode メソッドが廃止に</span><span class="sxs-lookup"><span data-stu-id="73639-101">MachineKey.Encode and MachineKey.Decode methods are now obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="73639-102">説明</span><span class="sxs-lookup"><span data-stu-id="73639-102">Details</span></span>|<span data-ttu-id="73639-103">これらのメソッドは今後使用しません。</span><span class="sxs-lookup"><span data-stu-id="73639-103">These methods are now obsolete.</span></span> <span data-ttu-id="73639-104">これらのメソッドを呼び出すコードをコンパイルすると、コンパイラ警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="73639-104">Compilation of code that calls these methods produces a compiler warning.</span></span>|
|<span data-ttu-id="73639-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="73639-105">Suggestion</span></span>|<span data-ttu-id="73639-106">別の方法として、<xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> および <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])> を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="73639-106">The recommended alternatives are <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> and <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span></span> <span data-ttu-id="73639-107">または、ビルド警告を抑制するか、古いコンパイラを使用して警告を回避できます。</span><span class="sxs-lookup"><span data-stu-id="73639-107">Alternatively, the build warnings can be suppressed, or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="73639-108">API は、まだサポートされています。</span><span class="sxs-lookup"><span data-stu-id="73639-108">The APIs are still supported.</span></span>|
|<span data-ttu-id="73639-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="73639-109">Scope</span></span>|<span data-ttu-id="73639-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="73639-110">Minor</span></span>|
|<span data-ttu-id="73639-111">Version</span><span class="sxs-lookup"><span data-stu-id="73639-111">Version</span></span>|<span data-ttu-id="73639-112">4.5</span><span class="sxs-lookup"><span data-stu-id="73639-112">4.5</span></span>|
|<span data-ttu-id="73639-113">型</span><span class="sxs-lookup"><span data-stu-id="73639-113">Type</span></span>|<span data-ttu-id="73639-114">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="73639-114">Retargeting</span></span>|
|<span data-ttu-id="73639-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="73639-115">Affected APIs</span></span>|<ul><li><xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li><li><xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li></ul>|
