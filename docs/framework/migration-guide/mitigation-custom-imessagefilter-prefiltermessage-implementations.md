---
title: '軽減策: カスタムの IMessageFilter.PreFilterMessage 実装'
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3ac43b574c4382c4aec5070acde0fa77516727d
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2019
ms.locfileid: "66251145"
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a><span data-ttu-id="8050a-102">軽減策: カスタムの IMessageFilter.PreFilterMessage 実装</span><span class="sxs-lookup"><span data-stu-id="8050a-102">Mitigation: Custom IMessageFilter.PreFilterMessage Implementations</span></span>

<span data-ttu-id="8050a-103">.NET Framework の .NET Framework 4.6.1 以降のバージョンを対象とする Windows フォーム アプリでは、<xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> メソッドが呼び出されると、カスタムの <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 実装は <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 実装が次のような場合に、メッセージを安全にフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="8050a-103">In Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1, a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation can safely filter messages when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called if the <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation:</span></span>

- <span data-ttu-id="8050a-104">次の操作のいずれか、または両方を行う場合:</span><span class="sxs-lookup"><span data-stu-id="8050a-104">Does one or both of the following:</span></span>

  - <span data-ttu-id="8050a-105"><xref:System.Windows.Forms.Application.AddMessageFilter%2A> メソッドを呼び出してメッセージ フィルターを追加する。</span><span class="sxs-lookup"><span data-stu-id="8050a-105">Adds a message filter by calling the <xref:System.Windows.Forms.Application.AddMessageFilter%2A> method.</span></span>

  - <span data-ttu-id="8050a-106"><xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> メソッドを呼び出してメッセージ フィルターを削除する。</span><span class="sxs-lookup"><span data-stu-id="8050a-106">Removes a message filter by calling the <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> method.</span></span> <span data-ttu-id="8050a-107">メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="8050a-107">method.</span></span>

- <span data-ttu-id="8050a-108">**なおかつ**、<xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> メソッドを呼び出してメッセージをポンプする場合。</span><span class="sxs-lookup"><span data-stu-id="8050a-108">**And** pumps messages by calling the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method.</span></span>

## <a name="impact"></a><span data-ttu-id="8050a-109">影響</span><span class="sxs-lookup"><span data-stu-id="8050a-109">Impact</span></span>

<span data-ttu-id="8050a-110">この変更によって影響を受けるのは、.NET Framework の .NET Framework 4.6.1 以降のバージョンを対象とする Windows フォーム アプリのみです。</span><span class="sxs-lookup"><span data-stu-id="8050a-110">This change only affects Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>

<span data-ttu-id="8050a-111">.NET Framework の以前のバージョンを対象とする Windows フォーム アプリの場合、このような実装で、<xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> メソッドが呼び出されると <xref:System.IndexOutOfRangeException> 例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="8050a-111">For Windows Forms apps that target previous versions of the .NET Framework, such implementations in some cases throw an <xref:System.IndexOutOfRangeException> exception when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called</span></span>

## <a name="mitigation"></a><span data-ttu-id="8050a-112">軽減策</span><span class="sxs-lookup"><span data-stu-id="8050a-112">Mitigation</span></span>

<span data-ttu-id="8050a-113">この変更が望ましくない場合は、.NET Framework 4.6.1 以降のバージョンを対象とするアプリでこの変更を無効にできます。これは、そのアプリの構成ファイルの [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに次の構成設定を追加して行います。</span><span class="sxs-lookup"><span data-stu-id="8050a-113">If this change is undesirable, apps that target the .NET Framework 4.6.1 or a later version can opt out of it by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />
</runtime>
```

<span data-ttu-id="8050a-114">また、以前のバージョンの .NET Framework を対象とするものの、.NET Framework 4.6.1 以降のバージョンで実行されているアプリでは、そのアプリの構成ファイルの [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに構成設定を追加して、この動作を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8050a-114">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 or a later version can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />
</runtime>
```

## <a name="see-also"></a><span data-ttu-id="8050a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="8050a-115">See also</span></span>

- [<span data-ttu-id="8050a-116">変更の再ターゲット</span><span class="sxs-lookup"><span data-stu-id="8050a-116">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
