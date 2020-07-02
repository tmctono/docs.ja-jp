---
ms.openlocfilehash: 3f330d5e601d599231ef0336b785e677fe1d114e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616079"
---
### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a><span data-ttu-id="eec43-101">DataObject.GetData は、データを UTF-8 として取得するようになりました</span><span class="sxs-lookup"><span data-stu-id="eec43-101">DataObject.GetData now retrieves data as UTF-8</span></span>

#### <a name="details"></a><span data-ttu-id="eec43-102">説明</span><span class="sxs-lookup"><span data-stu-id="eec43-102">Details</span></span>

<span data-ttu-id="eec43-103">.NET Framework 4 を対象とするアプリまたは .NET Framework 4.5.1 以前のバージョンで実行されるアプリでは、`DataObject.GetData` は HTML 形式のデータを ASCII 文字列として取得します。</span><span class="sxs-lookup"><span data-stu-id="eec43-103">For apps that target the .NET Framework 4 or that run on the .NET Framework 4.5.1 or earlier versions, `DataObject.GetData` retrieves HTML-formatted data as an ASCII string.</span></span> <span data-ttu-id="eec43-104">結果として、非 ASCII 文字 (ASCII コードが 0x7F よりも大きい文字) は 2 つのランダムな文字で表されます。</span><span class="sxs-lookup"><span data-stu-id="eec43-104">As a result, non-ASCII characters (characters whose ASCII codes are greater than 0x7F) are represented by two random characters.</span></span><p/><span data-ttu-id="eec43-105">.NET Framework 4.5 以降を対象とするアプリ、および.NET Framework 4.5.2 で実行するアプリでは、`DataObject.GetData` は HTML 形式のデータを UTF-8 として取得し、これは、0x7F よりも大きい文字を正しく表します。</span><span class="sxs-lookup"><span data-stu-id="eec43-105">For apps that target the .NET Framework 4.5 or later and run on the .NET Framework 4.5.2, `DataObject.GetData` retrieves HTML-formatted data as UTF-8, which represents characters greater than 0x7F correctly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="eec43-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="eec43-106">Suggestion</span></span>

<span data-ttu-id="eec43-107">HTML 形式の文字列を使用するエンコーディングの問題に対する回避策 (例: クリップボードから取得した HTML 文字列を <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> に渡して明示的にエンコードすること) を実装し、アプリをバージョン 4 から 4.5 へ再ターゲットしている場合は、その回避策を削除する必要があります。何らかの理由で古い動作を必要とする場合は、アプリのターゲットを .NET Framework 4.0 にしてその動作を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="eec43-107">If you implemented a workaround for the encoding problem with HTML-formatted strings (for example, by explicitly encoding the HTML string retrieved from the Clipboard by passing it to <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>) and you're retargeting your app from version 4 to 4.5, that workaround should be removed.If the old behavior is needed for some reason, the app can target the .NET Framework 4.0 to get that behavior.</span></span>

| <span data-ttu-id="eec43-108">名前</span><span class="sxs-lookup"><span data-stu-id="eec43-108">Name</span></span>    | <span data-ttu-id="eec43-109">[値]</span><span class="sxs-lookup"><span data-stu-id="eec43-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="eec43-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="eec43-110">Scope</span></span>   | <span data-ttu-id="eec43-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="eec43-111">Edge</span></span>        |
| <span data-ttu-id="eec43-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="eec43-112">Version</span></span> | <span data-ttu-id="eec43-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="eec43-113">4.5.2</span></span>       |
| <span data-ttu-id="eec43-114">種類</span><span class="sxs-lookup"><span data-stu-id="eec43-114">Type</span></span>    | <span data-ttu-id="eec43-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="eec43-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="eec43-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="eec43-116">Affected APIs</span></span>

- <xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType>
