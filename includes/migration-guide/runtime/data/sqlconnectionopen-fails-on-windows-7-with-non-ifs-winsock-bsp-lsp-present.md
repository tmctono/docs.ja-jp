---
ms.openlocfilehash: 9ab1686f60bcdbfef5f18576be17aee8c931f9aa
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497930"
---
### <a name="sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a><span data-ttu-id="c9af4-101">IFS 以外の Winsock BSP または LSP が存在する Windows 7 で SqlConnection.Open が失敗する</span><span class="sxs-lookup"><span data-stu-id="c9af4-101">SqlConnection.Open fails on Windows 7 with non-IFS Winsock BSP or LSP present</span></span>

#### <a name="details"></a><span data-ttu-id="c9af4-102">説明</span><span class="sxs-lookup"><span data-stu-id="c9af4-102">Details</span></span>

<span data-ttu-id="c9af4-103"><xref:System.Data.SqlClient.SqlConnection.Open> および <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)> は、コンピューター上に IFS 以外の Winsock BSP または LSP が存在する Windows 7 コンピューターで実行している場合、.NET Framework 4.5 では失敗します。IFS 以外の BSP または LSP がインストールされているかどうかを確認するには、<code>netsh WinSock Show Catalog</code> コマンドを使用して、返される <code>Winsock Catalog Provider Entry</code> 項目をすべて調べてください。</span><span class="sxs-lookup"><span data-stu-id="c9af4-103"><xref:System.Data.SqlClient.SqlConnection.Open> and <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)> fail in the .NET Framework 4.5 if running on a Windows 7 machine with a non-IFS Winsock BSP or LSP are present on the computer.To determine whether a non-IFS BSP or LSP is installed, use the <code>netsh WinSock Show Catalog</code> command, and examine every <code>Winsock Catalog Provider Entry</code> item that is returned.</span></span> <span data-ttu-id="c9af4-104">Service Flags 値の <code>0x20000</code> ビットがセットされている場合、プロバイダーは IFS ハンドルを使用していて、正しく機能します。</span><span class="sxs-lookup"><span data-stu-id="c9af4-104">If the Service Flags value has the <code>0x20000</code> bit set, the provider uses IFS handles and will work correctly.</span></span> <span data-ttu-id="c9af4-105"><code>0x20000</code> ビットがクリアされている (セットされていない) 場合は、IFS 以外の BSP または LSP です。</span><span class="sxs-lookup"><span data-stu-id="c9af4-105">If the <code>0x20000</code> bit is clear (not set), it is a non-IFS BSP or LSP.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c9af4-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="c9af4-106">Suggestion</span></span>

<span data-ttu-id="c9af4-107">このバグは .NET framework 4.5.2 で修正されたため、.NET Framework をアップグレードすることによって回避できます。</span><span class="sxs-lookup"><span data-stu-id="c9af4-107">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="c9af4-108">または、インストールされている IFS 以外の Winsock LSP を削除することによって回避できます。</span><span class="sxs-lookup"><span data-stu-id="c9af4-108">Alternatively, it can be avoided by removing any installed non-IFS Winsock LSPs.</span></span>

| <span data-ttu-id="c9af4-109">名前</span><span class="sxs-lookup"><span data-stu-id="c9af4-109">Name</span></span>    | <span data-ttu-id="c9af4-110">[値]</span><span class="sxs-lookup"><span data-stu-id="c9af4-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c9af4-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="c9af4-111">Scope</span></span>   |<span data-ttu-id="c9af4-112">マイナー</span><span class="sxs-lookup"><span data-stu-id="c9af4-112">Minor</span></span>|
|<span data-ttu-id="c9af4-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="c9af4-113">Version</span></span>|<span data-ttu-id="c9af4-114">4.5</span><span class="sxs-lookup"><span data-stu-id="c9af4-114">4.5</span></span>|
|<span data-ttu-id="c9af4-115">種類</span><span class="sxs-lookup"><span data-stu-id="c9af4-115">Type</span></span>|<span data-ttu-id="c9af4-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="c9af4-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c9af4-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c9af4-117">Affected APIs</span></span>

- <xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Data.SqlClient.SqlConnection.Open`
- `M:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)`

-->
