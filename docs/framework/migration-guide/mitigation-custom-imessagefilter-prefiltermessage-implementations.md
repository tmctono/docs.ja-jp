---
title: '軽減策: カスタムの IMessageFilter.PreFilterMessage 実装'
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
ms.openlocfilehash: 7757e8d1fd0258ab2d972b7321082e4afa37f710
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398647"
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a><span data-ttu-id="e799a-102">軽減策: カスタムの IMessageFilter.PreFilterMessage 実装</span><span class="sxs-lookup"><span data-stu-id="e799a-102">Mitigation: Custom IMessageFilter.PreFilterMessage Implementations</span></span>

<span data-ttu-id="e799a-103">.NET Framework の .NET Framework 4.6.1 以降のバージョンを対象とする Windows フォーム アプリでは、<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> メソッドが呼び出されると、カスタムの <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 実装は <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 実装が次のような場合に、メッセージを安全にフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="e799a-103">In Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1, a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation can safely filter messages when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called if the <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation:</span></span>

- <span data-ttu-id="e799a-104">次の操作のいずれか、または両方を行う場合:</span><span class="sxs-lookup"><span data-stu-id="e799a-104">Does one or both of the following:</span></span>

  - <span data-ttu-id="e799a-105"><xref:System.Windows.Forms.Application.AddMessageFilter%2A> メソッドを呼び出してメッセージ フィルターを追加する。</span><span class="sxs-lookup"><span data-stu-id="e799a-105">Adds a message filter by calling the <xref:System.Windows.Forms.Application.AddMessageFilter%2A> method.</span></span>

  - <span data-ttu-id="e799a-106"><xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> メソッドを呼び出してメッセージ フィルターを削除する。</span><span class="sxs-lookup"><span data-stu-id="e799a-106">Removes a message filter by calling the <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> method.</span></span> <span data-ttu-id="e799a-107">メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="e799a-107">method.</span></span>

- <span data-ttu-id="e799a-108">**なおかつ**、<xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> メソッドを呼び出してメッセージをポンプする場合。</span><span class="sxs-lookup"><span data-stu-id="e799a-108">**And** pumps messages by calling the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method.</span></span>

## <a name="impact"></a><span data-ttu-id="e799a-109">影響</span><span class="sxs-lookup"><span data-stu-id="e799a-109">Impact</span></span>

<span data-ttu-id="e799a-110">この変更によって影響を受けるのは、.NET Framework の .NET Framework 4.6.1 以降のバージョンを対象とする Windows フォーム アプリのみです。</span><span class="sxs-lookup"><span data-stu-id="e799a-110">This change only affects Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>

<span data-ttu-id="e799a-111">.NET Framework の以前のバージョンを対象とする Windows フォーム アプリの場合、このような実装で、<xref:System.IndexOutOfRangeException> メソッドが呼び出されると <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="e799a-111">For Windows Forms apps that target previous versions of the .NET Framework, such implementations in some cases throw an <xref:System.IndexOutOfRangeException> exception when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called</span></span>

## <a name="mitigation"></a><span data-ttu-id="e799a-112">対応策</span><span class="sxs-lookup"><span data-stu-id="e799a-112">Mitigation</span></span>

<span data-ttu-id="e799a-113">この変更が望ましくない場合は、.NET Framework 4.6.1 以降のバージョンを対象とするアプリでこの変更を無効にできます。これは、そのアプリの構成ファイルの [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) セクションに次の構成設定を追加して行います。</span><span class="sxs-lookup"><span data-stu-id="e799a-113">If this change is undesirable, apps that target the .NET Framework 4.6.1 or a later version can opt out of it by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />
</runtime>
```

<span data-ttu-id="e799a-114">また、以前のバージョンの .NET Framework を対象とするものの、.NET Framework 4.6.1 以降のバージョンで実行されているアプリでは、そのアプリの構成ファイルの [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) セクションに構成設定を追加して、この動作を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e799a-114">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 or a later version can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />
</runtime>
```

## <a name="see-also"></a><span data-ttu-id="e799a-115">参照</span><span class="sxs-lookup"><span data-stu-id="e799a-115">See also</span></span>

- [<span data-ttu-id="e799a-116">アプリケーションの互換性</span><span class="sxs-lookup"><span data-stu-id="e799a-116">Application compatibility</span></span>](application-compatibility.md)
